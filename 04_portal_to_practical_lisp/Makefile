SHELL = /bin/bash

deps:
	@echo "Checking for dependencies..."
ifeq ($(shell command -v pandoc),)
	@echo "'Pandoc' is required!"
endif
ifeq ($(shell command -v pdflatex),)
	@echo "'texlive' is required!"
endif
ifeq ($(shell command -v xcf2png),)
	@echo "'xcftools' is required!"
endif
ifeq ($(shell command -v convert),)
	@echo "'ImageMagick' is required!"
endif
ifeq ($(shell command -v gs),)
	@echo "'ghostscript' is required!"
endif

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
	convert /tmp/cover.png ./dist/00-cover.pdf

merge_into_one:
	gs -dBATCH -dNOPAUSE -sDEVICE=pdfwrite -sOutputFile=./dist/book.pdf -f ./dist/*.pdf

build: deps create_output_dir build_contents build_cover merge_into_one
