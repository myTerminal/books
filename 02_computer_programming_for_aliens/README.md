# Computer Programming for Aliens

[![License: CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/80x15.png)](https://creativecommons.org/licenses/by-nc-sa/4.0)

To learn about the platforms you can find this book on, use one of these universal links: [computer-programming-for-aliens](https://books2read.com/computer-programming-for-aliens) or [u/mB2QaA](https://books2read.com/u/3LVM5J).

Otherwise, this book can be found on the following platforms at this point:

1. [Google Play](https://play.google.com/store/books/details?id=-fycEAAAQBAJ)

## Building from source

### Book

The book can be built using either of the two methods:

1. **Building with Pandoc**

    Install [Pandoc](https://pandoc.org) either from your operating system's package manager or follow [this guide](https://github.com/jgm/pandoc/blob/master/INSTALL.md).

    Run the below command in the root directory containing the book's source:

        pandoc ./book.org -o ./dist/book.pdf

    *Note: The directory `./dist` needs to exist. If it isn't already present, you'll need to create the directory first.*

2.  **Building with Make**

    Assuming you have [GNU Make](https://www.gnu.org/software/make) installed on your system, run the below command at the root of the book's source:

        make build

    A directory `./dist` will be created (if it doesn't exist) and the book will be placed inside it as "book.pdf".

    *Note: You still need to have Pandoc installed on the system.*

### Cover

The cover image can be exported from `cover.xcf` using [Gimp](https://www.gimp.org).

## Note about image assets

Though the included image [assets](assets) are licensed under [Simplified Pixabay License](https://pixabay.com/service/license), they belong to their original authors and have been included in this project only to be treated as a dependency for this book.
