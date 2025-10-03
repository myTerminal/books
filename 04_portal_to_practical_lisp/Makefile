SHELL = /bin/bash

crater-get:
	@echo "Setting up Crater for temporary use..."
	git clone https://github.com/crater-space/cli /tmp/crater-cli

deps:
	@echo "Checking for dependencies..."
ifeq ($(shell command -v pandoc),)
	@echo "'Pandoc' is required!"
	@echo "Attempting to install pandoc using Crater..."
	/tmp/crater-cli/crater install pandoc
endif
ifeq ($(shell command -v pdflatex),)
	@echo "'texlive' is required!"
	@echo "Attempting to install texlive using Crater..."
	/tmp/crater-cli/crater install texlive
endif
ifeq ($(shell command -v xcf2png),)
	@echo "'xcftools' is required!"
	@echo "Attempting to install xcftools using Crater..."
	/tmp/crater-cli/crater install xcftools
endif
ifeq ($(shell command -v magick),)
	@echo "'ImageMagick' is required!"
	@echo "Attempting to install ImageMagick using Crater..."
	/tmp/crater-cli/crater install ImageMagick
endif
ifeq ($(shell command -v gs),)
	@echo "'ghostscript' is required!"
	@echo "Attempting to install ghostscript using Crater..."
	/tmp/crater-cli/crater install ghostscript
endif

crater-remove:
	@echo "Removing Crater..."
	rm -rf /tmp/crater-cli

create_output_dir:
	if ! [ -d "./dist" ]; then \
		mkdir ./dist; \
	fi

build_contents:
	pandoc ./book.org -o ./dist/01-contents.pdf
	echo "./dist/01-contents.pdf generated!"

write: deps create_output_dir
	while true; do \
        make --silent build_contents; \
        inotifywait -qre close_write .; \
    done

build_cover:
	xcf2png cover.xcf -o /tmp/cover.png
	magick /tmp/cover.png ./dist/00-cover.pdf

merge_into_one:
	gs -dBATCH -dNOPAUSE -sDEVICE=pdfwrite -sOutputFile=./dist/book.pdf -f ./dist/*.pdf

req: crater-get deps crater-remove

build: req create_output_dir build_contents build_cover merge_into_one
