
## Contents <!-- omit from toc -->

- [Initial Workspace Setup](#initial-workspace-setup)
- [Repo Package Setup](#repo-package-setup)
  - [Sphinx-Quickstart Output](#sphinx-quickstart-output)


## Initial Workspace Setup

> Should only need to do this once, or when you want to target a new python version

```bash
# Used python3.12 for this
python -m venv py312venv
# windows
py312venv/Scripts/activate 
# linux
source py312/venv/bin/activate
pip install poetry
poetry install
```

## Repo Package Setup

> Should not be needed, but good notes for anyone curious how I set this up. 
> Tried really hard not to manually touch the filesystem until needed
>
> In this use case, poetry is likely overkill, but it prevents manual file interaction, by design

```bash
poetry new --name hot-topics --src -n tmp
mv tmp/* .
rm tmp
poetry add sphinx make
```

### Sphinx-Quickstart Output
```bash
sphinx-quickstart docs
Welcome to the Sphinx 8.1.3 quickstart utility.

Please enter values for the following settings (just press Enter to
accept a default value, if one is given in brackets).

Selected root path: docs

You have two options for placing the build directory for Sphinx output.
Either, you use a directory "_build" within the root path, or you separate
"source" and "build" directories within the root path.
> Separate source and build directories (y/n) [n]: y

The project name will occur in several places in the built documentation.
> Project name: Hot Topics
> Author name(s): Zachary Haberman
> Project release []: 0

If the documents are to be written in a language other than English,
you can select a language here by its language code. Sphinx will then
translate text that it generates into that language.

For a list of supported codes, see
https://www.sphinx-doc.org/en/master/usage/configuration.html#confval-language.
> Project language [en]: en

Creating file C:\Code\hot-topics-docs\docs\source\conf.py.
Creating file C:\Code\hot-topics-docs\docs\source\index.rst.
Creating file C:\Code\hot-topics-docs\docs\Makefile.
Creating file C:\Code\hot-topics-docs\docs\make.bat.

Finished: An initial directory structure has been created.

You should now populate your master file C:\Code\hot-topics-docs\docs\source\index.rst and create other documentation
source files. Use the Makefile to build the docs, like so:
   make builder
where "builder" is one of the supported builders, e.g. html, latex or linkcheck.

```