VERSION=0.8.2
COMPONENT=tachyon-meter
SUFFIX:=$(shell echo $(SUFFIX))
BASENAME:=$(COMPONENT)-$(VERSION)$(SUFFIX)
.PHONY: package clean

package:
	cp install.sh $(BASENAME)
	cd ../../dist && tar -cf ../rel/pkg/$(BASENAME).tar $(COMPONENT)
	uuencode $(BASENAME).tar $(BASENAME).tar >> $(BASENAME)
	-rm $(BASENAME).gz $(BASENAME).tar || true
	gzip -9 $(BASENAME)

clean:
	-rm *.gz
