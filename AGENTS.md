# Repository Guidelines

## Project Structure & Module Organization

This repository is a single-page static site. `index.html` contains the page structure, inline SVG navigation icons, and content. Styling lives in `styles/index.css`, including the desktop breakpoint at `1000px`. Images used by the banner, profile, and video cards are stored in `styles/assets/`. Keep new assets in that directory and reference them with relative paths such as `./styles/assets/image-name.png`.

There is currently no JavaScript, build output, dependency manifest, or dedicated test directory. Avoid adding generated files to version control.

## Build, Test, and Development Commands

No build step or package installation is required. From the repository root, run:

```powershell
python -m http.server 8000
```

Then open `http://localhost:8000/` to preview the site. A local server is preferred over opening `index.html` directly because it more closely matches GitHub Pages behavior. Use `git status --short` and `git diff --check` before committing to catch unintended files and whitespace errors.

## Coding Style & Naming Conventions

Use two-space indentation in HTML and CSS. Keep HTML semantic, provide meaningful `alt` text for content images, and preserve lowercase kebab-case class names such as `.profile-image` or `.video-title`. Organize CSS from broad element rules to reusable classes, followed by responsive media queries. Match the existing formatting unless a formatter is deliberately introduced for the whole project. Prefer relative URLs so the site continues to work under GitHub Pages project paths.

## Testing Guidelines

Testing is currently manual. Check the page at widths below and above the `1000px` breakpoint. Verify image loading, navigation links, typography, alignment, and overflow. Test with browser developer tools and confirm that the console and network panel show no unexpected errors. For accessibility-related changes, also check keyboard navigation, focus visibility, heading order, and image alternatives.

## Commit & Pull Request Guidelines

Recent commits use short messages prefixed with `ARC:`, for example `ARC: profile image align fixed`. Continue that convention with a concise, present-tense summary: `ARC: improve mobile video spacing`.

Pull requests should describe the user-visible change, list manual checks performed, and link any relevant issue. Include before-and-after screenshots for visual or responsive changes, ideally at both mobile and desktop widths. Keep each pull request focused and avoid mixing unrelated cleanup with feature work.
