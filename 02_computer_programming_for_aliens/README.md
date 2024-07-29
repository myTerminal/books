# Computer Programming for Aliens

[![License: CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/80x15.png)](https://creativecommons.org/licenses/by-nc-sa/4.0)  
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/Y8Y5E5GL7)

To learn about the platforms you can find this book on, use one of these universal links: [computer-programming-for-aliens](https://books2read.com/computer-programming-for-aliens).

Otherwise, this book can be found on the following platforms at this point:

1. [Google Play](https://play.google.com/store/books/details?id=-fycEAAAQBAJ)
2. [Gumroad](https://myterminal.gumroad.com/l/computer-programming-for-aliens)

## Building the book

The book can be built using either of the two methods:

### Manual method

#### Contents of the book using Pandoc

Install [Pandoc](https://pandoc.org) either from your operating system's package manager or follow [this guide](https://github.com/jgm/pandoc/blob/master/INSTALL.md).

Run the below command in the root directory containing the book's source:

    pandoc ./book.org -o ./dist/book.pdf

*Note: The directory `./dist` needs to exist. If it isn't already present, you'll need to create the directory first.*

#### Cover using [Gimp](https://www.gimp.org)

The cover image can be exported from `cover.xcf` using [Gimp](https://www.gimp.org).

### Using **[Make](https://www.gnu.org/software/make)**

You need the following dependencies installed on the system:

1. [Pandoc](https://pandoc.org)
2. [xcftools](http://henning.makholm.net/software)
3. [ImageMagick](https://imagemagick.org)
4. [Ghostscript](https://www.ghostscript.com)

Once you have all the dependencies, run the following command at the root of the book's source:

    make build

A directory `./dist` will be created (if it doesn't exist) and the book will be placed inside it as "book.pdf".

## Note about image assets

Though the included image [assets](assets) are licensed under [Simplified Pixabay License](https://pixabay.com/service/license), they belong to their original authors and have been included in this project only to be treated as a dependency for this book.
