.PHONY: examples generate

CC = xelatex
PYTHON = python3
EXAMPLES_DIR = examples
CV_DIR = examples/cv
CV_SRCS = $(shell find $(CV_DIR) -name '*.tex')
GENERATED_DIR = generated
GENERATED_TEX = generated_cv.tex

examples: cv.pdf

generate:
	$(PYTHON) generate_cv.py

cv.pdf: $(EXAMPLES_DIR)/cv.tex $(CV_SRCS)
	$(CC) -output-directory=$(EXAMPLES_DIR) $<

generated_cv.pdf: generate
	$(CC) -output-directory=$(GENERATED_DIR) $(GENERATED_TEX)

clean:
	rm -rf $(EXAMPLES_DIR)/*.pdf $(GENERATED_DIR)/*.pdf $(GENERATED_DIR)/*.aux $(GENERATED_DIR)/*.log $(GENERATED_DIR)/*.out $(GENERATED_DIR)/missfont.log
