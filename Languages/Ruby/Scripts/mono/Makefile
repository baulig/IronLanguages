SCRIPTS = igem iirb ir irdoc iri
BIN_SCRIPTS = gem irb rdoc ri

PREFIX = /usr/local/ironruby
MONO = /usr/bin/mono

%: %.in
	sed -e 's,@PREFIX@,$(PREFIX),g' -e 's,@MONO@,$(MONO),g' < $< > tmp && \
		mv tmp $@ && chmod 755 $@

all: $(SCRIPTS)
	
clean:
	-rm $(SCRIPTS)
	
install: $(SCRIPTS)
	mkdir -p $(PREFIX)/bin
	for f in $(SCRIPTS); do \
		cp $$f $(PREFIX)/bin; \
		chmod +x $(PREFIX)/bin/$$f; \
	done
	for f in $(BIN_SCRIPTS); do \
		cp ../bin/$$f $(PREFIX)/bin; \
		chmod +x $(PREFIX)/bin/$$f; \
	done

	

