---
title: My Insane Blog Pipeline
date: 2025-10-19
description: A journal of how I created this website
tags:
  - blog
  - CICD
  - github
  - hugo
draft: false
cover:
---

I’ve reached a point where my brain is essentially a browser with too many tabs open. To fix this, I decided to start blogging for two reasons: I needed a "second brain" to offload everything I’m learning, and I stumbled upon a [NetworkChuck video](https://www.youtube.com/watch?v=dnE7c0ELEH8) that made building a blog pipeline look like the perfect sandbox for some DevOps experimentation.

Instead of just "making a website" I decided to treat this like a real engineering project. I’ve been procrastinating on my portfolio for years, so I figured I’d finally build it properly using CI/CD, GitHub Actions, and modern static site practices.

## The Requirements

Before I touched any code or spent a single cent (spoiler: I didn't spend any), I laid out three non-negotiables:

1. **Zero Hosting Costs:** Use GitHub Pages because free is a very good price.
    
2. **Modular Architecture:** The theme lives in its own repo and the blog content in another. This keeps them decoupled and lets me open-source the theme later without exposing my draft notes.
    
3. **The "Hands-Off" Pipeline:** I want to write Markdown, `git push`, and walk away. No manual formatting, no manual uploads. Just automation.
    

---

## The Architecture

Like I mentioned earlier, I wanted to decouple both the theme and the blog repo from each other. Theres two approaches to this, one is to use Git submodules which is like manually embedding another git repo into another git repo but this is fragile can very easily break. The better approach is to use Hugo modules which is the modern way to do it. Hugo modules use Go's dependency system under the hood and it is very CI/CD friendly

### Theme Repository: `wreck-it-ralph-hugo-theme`

This contains all the "how it looks" logic.

```
.
├── layouts/         # HTML templates
├── assets/          # CSS/JS
├── theme.toml       # metadata
├── exampleSite/
├── archetypes/
└── go.mod           # The "engine" that makes it a module
```

### Blog Repository: `joeblogo`

This is the "engine room" where the actual writing happens.

```
.
├── config.toml             # configurations
├── .github                 # the CI/CD automation
│   └── workflows
├── content                 # markdown files
│   ├── _private/
│   ├── about.md
│   ├── posts/
│   └── projects/
├── data                    # other static data
│   ├── engagements.json
│   ├── experience.json
│   ├── skills.yml
│   └── socials.yml
├── go.mod
├── go.sum
└── static
    └── images
```

---

## Step 1: Making the Theme "Professional"

The first step was converting my theme into a Hugo module. This is essentially turning your theme into a package that Hugo can fetch automatically.

Inside the theme repo, I ran:

```bash
go mod init github.com/YOURUSER/wreck-it-ralph-hugo-theme
git add .
git commit -m "module init"
git push
```

```bash
git tag v1.0.0
git push origin v1.0.0
```

**Why the tags?** In the past, I’ve had "hacks" in my themes break my site when I least expected it. By using semantic version tags (v1.0.0), I can "pin" my blog to a specific version. If I break the theme tomorrow, the blog stays safe until I’m ready to update.

---

## Step 2: The Blog Setup & Dependency Pinning

Now, in the blog repo, I tell Hugo to look for that theme module. I initialized the module and edited my `config.toml`:

```TOML
baseURL = 'https://joebyjo.github.io/joeblogo/'
languageCode = 'en-us'
title = 'whois JoeByjo'
pagination.pagerSize = 7

[module]
  [[module.imports]]
    path = "github.com/joebyjo/wreck-it-ralph-hugo-theme"

[params]
  logo = "JoeByjo"
  contentTypeName = "posts"
  showMenuItems = 2
  fullWidthTheme = false
  centerTheme = false

[markup]
  [markup.tableOfContents]
    startLevel = 2
    endLevel = 4

[menu]
  [[menu.main]]
    name = "Projects"
    url = "/projects/"
    weight = 2

  [[menu.main]]
    name = "Posts"
    url = "/posts/"
    weight = 3
    
  [[menu.main]]
    name = "About"
    url = "/about/"
    weight = 1
```

and to now lock the version so the CI/CD pipeline knows exactly which version of the theme to build:

```
hugo mod get github.com/YOURUSER/wreck-it-ralph-hugo-theme@v1.0.0
```

This creates `go.mod` and `go.sum`. These files are the "source of truth" for your dependencies. commit those.


**How to update theme later**

When theme releases:

```
v1.0.1
```

you manually upgrade:

```bash
hugo mod get -u github.com/YOURUSER/wreck-it-ralph-hugo-theme@v1.0.1
```

commit → deploy.

Safe. Controlled. Professional.

---

## Step 3: Where the Magic Happens (CI/CD)

I created a GitHub Action workflow at `.github/workflows/deploy.yml`. This is the part that handles the heavy lifting. Every time I push a new `.md` file, GitHub spins up a little Ubuntu server, installs Go and Hugo, fetches my theme, and builds the site.

{{< code title="deploy.yml" language="yml" >}}
name: Deploy Hugo site

on:
  push:
    branches: [main]

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  build:
    runs-on: ubuntu-latest

	steps:

    - name: Checkout
      uses: actions/checkout@v4

    - name: Setup Go
      uses: actions/setup-go@v5
      with:
        go-version: '1.25.3'

    - name: Setup Hugo
      uses: peaceiris/actions-hugo@v3
      with:
        hugo-version: 'latest'
        extended: true

    - name: Download modules
      run: hugo mod get

    - name: Build hugo
      run: hugo --minify --baseURL "https://joebyjo.github.io/joeblogo/"

    - name: Upload artifact
      uses: actions/upload-pages-artifact@v3
      with:
        path: ./public

  deploy:
	environment:
      name: github-pages
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy
        uses: actions/deploy-pages@v4
{{< /code >}}

_Note: Since I'm serving from the root, I don't need to force the baseURL or use `relativeURLs = true`. It just works._

---
## Step 4: enable Github Pages

in the blog repo settings:

```
Pages → Source → GitHub Actions
`````

DONE.



---

## Conclusion

This project was the perfect excuse to stop procrastinating and actually learn how GitHub Actions work under the hood. I now have a blog that is:

- Fully automated.
    
- Version-controlled.
    
- Hosted for $0.
    

**Future Work:**

- Adding a "Theme Release Bot" to automatically notify my blog repo when a new theme tag is pushed.
    
- Exploring **Lighthouse** performance testing inside the CI pipeline.
    
- Actually writing the content I promised my second brain.
    

If you want to see the code or follow along with my future tutorials, stay tuned or subscribe to my [RSS feed](https://www.google.com/search?q=%23). Hint, hint: I might just drop the **Ultimate Professional Pipeline** setup next.