A Github Pages template for academic websites. This was forked (then detached) by [Stuart Geiger](https://github.com/staeiou) from the [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/), which is © 2016 Michael Rose and released under the MIT License. See LICENSE.md.

I think I've got things running smoothly and fixed some major bugs, but feel free to file issues or make pull requests if you want to improve the generic template / theme.

# Instructions

1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this repository](https://github.com/academicpages/academicpages.github.io) by clicking the "fork" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section
1. (Optional) Use the Jupyter notebooks or python scripts in the `markdown_generator` folder to generate markdown files for publications and talks from a TSV file.

See more info at https://academicpages.github.io/

## Local preview on Windows with Ubuntu WSL

From PowerShell in this repository, start the preview with:

```powershell
powershell -ExecutionPolicy Bypass -File .\scripts\preview.ps1
```

Open <http://localhost:4000>. Saving a page rebuilds the site and reloads the
browser. Press **Ctrl+C** in the terminal to stop the server. After changing
either `_config.yml` or `_config.dev.yml`, stop and restart it.

To check that the site builds without starting a server:

```powershell
powershell -ExecutionPolicy Bypass -File .\scripts\preview.ps1 -Build
```

The script uses the `Ubuntu-24.04` WSL distribution by default. Pass
`-Distribution <name>` if yours has a different name. Dependencies are installed
automatically on first run and cached in `~/.cache/impillar-homepage/bundle`
inside Ubuntu. Generated pages go into `_site/` and are ignored by Git.
The development configuration disables analytics and comments, uses local
navigation links, and includes future-dated publications for preview.

### First-time setup on another machine

Install Ubuntu WSL with `wsl --install -d Ubuntu-24.04` if needed. In Ubuntu, run:

```bash
sudo apt-get update
sudo apt-get install -y ruby-full build-essential zlib1g-dev libssl-dev pkg-config
sudo gem install bundler -v 4.0.0 --no-document
```

Ruby 3.2 or newer is required. On Linux, you can run
`bash scripts/preview.sh` directly, or `bash scripts/preview.sh build` for a
build only. Keep `Gemfile.lock` to use the tested dependency versions.

# Changelog -- bugfixes and enhancements

There is one logistical issue with a ready-to-fork template theme like academic pages that makes it a little tricky to get bug fixes and updates to the core theme. If you fork this repository, customize it, then pull again, you'll probably get merge conflicts. If you want to save your various .yml configuration files and markdown files, you can delete the repository and fork it again. Or you can manually patch. 

To support this, all changes to the underlying code appear as a closed issue with the tag 'code change' -- get the list [here](https://github.com/academicpages/academicpages.github.io/issues?q=is%3Aclosed%20is%3Aissue%20label%3A%22code%20change%22%20). Each issue thread includes a comment linking to the single commit or a diff across multiple commits, so those with forked repositories can easily identify what they need to patch.
