
MAN1PAGES = bdfimplode.1 hex2bdf.1 hex2sfd.1 \
	hexbraille.1 hexdraw.1 hexmerge.1 johab2ucs2.1 \
	unibdf2hex.1 unibmp2hex.1 unicoverage.1 unidup.1 \
	unifontpic.1 unifontchojung.1 unifontksx.1 unigencircles.1 \
	unigenwidth.1 unihexgen.1 unihex2bmp.1 unipagecount.1

MAN5PAGES = unifont.5

#
# $(PREFIX) is defined in the top-level Makefile or on the command line
# to override the setting below.
#
PREFIX = /usr
INSTALLDIR = $(PREFIX)/share/man

#
# Set "COMPRESS = 0" to install uncompressed man pages (the default), or
# override on the command line.
#
# Set "COMPRESS = 1" or anything else non-zero to install gzipped man pages.
#
COMPRESS = 1

all:

install: $(MANPAGES)
	install -m0755 -d $(INSTALLDIR)
	install -m0755 -d $(INSTALLDIR)/man1
	install -m0755 -d $(INSTALLDIR)/man5
	for i in $(MAN1PAGES) ; do \
	   if [ $(COMPRESS) = 0 ] ; then \
	      install -m0644 $(MAN1PAGES) $(INSTALLDIR)/man1 ; \
	   else \
	      gzip -f -9 < $$i >$$i.gz ; \
	      chmod 644 $$i.gz ; \
	      mv $$i.gz $(INSTALLDIR)/man1 ; \
	   fi \
	done
	for i in $(MAN5PAGES) ; do \
	   if [ $(COMPRESS) = 0 ] ; then \
	      install -m0644 $(MAN5PAGES) $(INSTALLDIR)/man5 ; \
	   else \
	      gzip -f -9 < $$i >$$i.gz ; \
	      chmod 644 $$i.gz ; \
	      mv $$i.gz $(INSTALLDIR)/man5 ; \
	   fi \
	done

clean:

distclean:

.PHONY: all install clean distclean
