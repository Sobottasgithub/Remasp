JAVA_FMT   = google-java-format
JAVA_FILES = $(shell find . -name '*.java')
JAVA_CLASS = $(JAVA_FILES:.java=.class)
XML_FMT   = xmlindent
XML_FILES = $(shell find . -name '*.xml')

.PHONY: fmt
fmt:
	@echo "Formatting all Java files..."
	@for f in $(JAVA_FILES); do \
		echo "  $$f"; \
		$(JAVA_FMT) -i $$f; \
	done

remasp.jar: $(JAVA_CLASS)
	jar cf $@ $(JAVA_CLASS)

%.class: %.java
	javac $<
