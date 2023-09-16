# Github Dark Mode Bug

This repository demonstrates the bug [github/markup/#1681](https://github.com/github/markup/issues/1681).

The expected behaviour would be to see only **WHITE** circles in dark mode and **BLACK** circles in light mode.

**Things to check:**
- ERROR 1: Open [this page](https://github.com/osiegmar/github-dark-mode-bug)
- ERROR 2: Navigate to another page (e.g. [Issues](https://github.com/osiegmar/github-dark-mode-bug/issues)) **AND** hit the browser back button there
- Errors highly depends on your [GitHub theme preferences](https://github.com/settings/appearance) and OS-settings (if synced with OS)

## Via markdown (deprecated)

Dark mode can be used via markdown as shown on [GitHub blog](https://github.blog/changelog/2021-11-24-specify-theme-context-for-images-in-markdown/)
but is now deprecated (see next section).

![Circle black](./circle_black.png#gh-light-mode-only)
![Circle white](./circle_white.png#gh-dark-mode-only)

## Via HTML picture element

Current recommended way is documented in [GitHub Docs](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#specifying-the-theme-an-image-is-shown-to).

<picture>
    <source media="(prefers-color-scheme: light)" srcset="circle_black.png">
    <source media="(prefers-color-scheme: dark)" srcset="circle_white.png">
    <img src="circle_red.png" alt="">
</picture>

## Via styled SVG as HTML image element

<img src="circle.svg" width="100" height="100" alt=""/>
