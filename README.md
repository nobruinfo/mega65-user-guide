# MEGA65 User Guide

This is community effort to create a User Guide for the MEGA65 in the spirit of the original User Guide for the Commodore 64.

# Just show me the PDFs!

If you just want the typeset manuals, the latest pdf's from our build pipeline are available here:

- https://mega65.org/docs

(Location will be updated to files.mega65.org at a later stage when our automation permits it)

For official release increments of the documentation, hop over to the releases page at:

https://github.com/MEGA65/mega65-user-guide/releases

# Installation

## Cloning the repo

Use `git` to clone this project repo, with submodules:

```
git clone --recurse-submodules https://github.com/MEGA65/mega65-user-guide.git
```

If you cloned another way and still need submodules (e.g. the `mega65-core` subfolder is empty), initialize submodules:

```
git submodule update --init
```

## Installing LaTeX

This project uses the LaTeX typesetting system, specifically XeLaTeX. Select and install the package appropriate for your operating system.

- Windows: http://www.tug.org/texworks/
- Linux: [TeX Live](https://tug.org/texlive/), often available via package manager (e.g. `sudo apt install texlive`)
- macOS: [MacTeX](https://www.tug.org/mactex/)

## GCC and build tools

This project uses GNU Make for coordinating build logic, and also some supplemental tools written in C. The build uses a GCC-compatible C compiler to prepare some tools. For your operating system:

- Windows: MingW32 (tested on MinGW-6.3.0, and MinGW-8.1.0)
- Linux: GCC compiler suite, typically installed via the `build-essential` package
- macOS: Clang or GCC, typically installed via Xcode or [Homebrew](https://brew.sh)

# Usage

The User Guide project is defined using a Makefile to build.

> If you are using an environment like TeXworks, do not use the built in Build button. That is for single file building only.

For MingW32 users, use the `mingw32-make` command where `make` is indicate below. Linux and macOS users, simply use `make`.

`make` or `make all` will build all PDF manuals. You can also specify the name of the PDF file to build just one manual, like so:

```
make mega65-book.pdf
```

The complete list of guides that can be individually built are:

| Book                                                     | Build                             |
| :------------------------------------------------------- | :-------------------------------- |
| User Guide                                               | make mega65-userguide.pdf         |
| Chipset Reference                                        | make mega65-chipset-reference.pdf |
| Complete BASIC 65 Commands                               | make mega65-basic65-reference.pdf |
| For experimentation (don't commit)                       | make sandbox.pdf                  |
| Reference Guide                                          | make referenceguide.pdf           |
| Developer's Guide                                        | make mega65-developer-guide.pdf   |
| Guide to MEGA65 and FPGA Hardware                        | make hardwareguide.pdf            |
| All books combined                                       | make mega65-book.pdf              |
| As above but in CYMK for printing (Ghostscript required) | make mega65-book-cmyk.pdf         |

There is also a `sandbox.pdf` for experimenting with typesetting or components for the manuals. But it is not included in the makefile. Instead, it is able to be built directly using software like TeXworks. The sandbox is faster to build and test changes more quickly. You can then transfer your work directly to the userguide.

To delete all LaTeX-built files: `make clean`

To delete every generated file: `make realclean`

# Editors

## Visual Studio Code

Combined with the `LaTeX Workshop` extension, this is a great IDE for working with the project. However be careful of the using the built-in terminal for compiling the guides. It's a powershell-based terminal and won't work with the Makefile. Nor will Command Prompt. Use a more Unix styled terminal like Git Bash.

## Style Guide

If you wish to contribute to the MEGA65 literature, please try to read and follow the [style-guide](style-guide.md).
