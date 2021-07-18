SHELL = /bin/bash

deps:
	@echo "Checking for dependencies..."
ifeq ($(shell command -v pandoc),)
	@echo "'Pandoc' is required."
endif

create_output_dir:
	if ! [ -d "./dist" ]; then \
		mkdir ./dist; \
	fi

build: deps create_output_dir
	pandoc ./book.org -o ./dist/book.pdf
	echo "./dist/book.pdf generated!"

write:
	while true; do \
        make --silent build; \
        inotifywait -qre close_write .; \
    done
