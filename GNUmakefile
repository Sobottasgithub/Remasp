JAVA_FMT   = google-java-format
JAVA_FILES = $(shell find . -name '*.java')
JAVA_CLASS = $(JAVA_FILES:.java=.class)
XML_FMT   = xmlindent
XML_FILES = $(shell find . -name '*.xml')

MAIN_CLASS = remasp.Remasp

remasp.jar: $(JAVA_FILES)
	javac $(JAVA_FILES)
	jar cfe $@ $(MAIN_CLASS) $$(find . -name '*.class')

.PHONY: fmt
fmt:
	@echo "Formatting all Java files..."
	@for f in $(JAVA_FILES); do \
		echo "  $$f"; \
		$(JAVA_FMT) -i $$f; \
	done

%.class: %.java
	javac $<
