# Multilingual Hugo Blog with PaperMod

This repository contains a starter Hugo site configured with the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme via Hugo Modules. It is set up for Turkish (`tr`) and English (`en`) content, includes RSS/sitemap/SEO-friendly defaults, and is ready for automatic deployment to GitHub Pages.

## Prerequisites

- [Hugo Extended v0.152.2](https://github.com/gohugoio/hugo/releases/tag/v0.152.2)
- [Go](https://go.dev/doc/install) (required for Hugo Modules)
- GitHub repository with Pages enabled (deployment uses `gh-pages` branch)

## Getting Started

1. **Install dependencies**
   ```bash
   hugo mod tidy
   ```

2. **Run the development server**
   ```bash
   hugo server -D
   ```
   Visit <http://localhost:1313> to preview the site.

3. **Build the site**
   ```bash
   hugo
   ```
   The generated files will appear in the `public/` directory.

## Adding New Posts

Posts are stored per language:

- Turkish posts: `content/tr/posts/`
- English posts: `content/en/posts/`

To add a new post:

1. Create a new directory inside the appropriate language folder, e.g. `content/tr/posts/yeni-yazi/`.
2. Inside that directory, create an `index.md` file with front matter similar to the examples in `content/tr/posts/merhaba/` or `content/en/posts/hello/`.
3. Update `title`, `date`, `description`, `slug`, and any other metadata needed by your post.
4. Add your Markdown content below the front matter divider (`---`).

## Static Assets

Place static files such as images or downloads in the `static/` directory. They will be available under the same path on the generated site (e.g. `static/images/logo.png` becomes `/images/logo.png`).

## Deployment

This repository includes a GitHub Actions workflow (`.github/workflows/hugo.yml`) that builds the site with Hugo Extended v0.152.2 and deploys it to the `gh-pages` branch. To enable automatic deployments:

1. Push this repository to GitHub.
2. In your repository settings, enable **GitHub Pages** to deploy from the `gh-pages` branch.
3. Ensure the workflow has permission to deploy (default permissions usually work). On the first run, the action will create and manage the `gh-pages` branch for you.

## Updating the Theme

PaperMod is managed via Hugo Modules. To update to the latest version:

```bash
hugo mod get -u github.com/adityatelange/hugo-PaperMod
```

Commit the updated `go.sum`/`go.mod` files after running the command.
