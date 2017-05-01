SRCDIR = wtdensity
BINDIR = ../bin
APPS = wtdensity \
       wtdensityPlain
FILES = wtdensity.css \
        wtdensity.xml

RVERSION = 3.4.0

all:
	. /etc/environ.sh; \
	    use -e -r R-${RVERSION}; \
	    cd ${SRCDIR}; \
	    make all

install:
	cd ${SRCDIR}; \
	    for i in $(APPS) ; do \
	        install --mode 0755 -D $$i ../${BINDIR}/$$i ; \
	    done; \
	    for i in $(FILES) ; do \
	        install --mode 0644 -D $$i ../${BINDIR}/$$i ; \
	    done; \
	    test -L ../${BINDIR}/resources || ln -s /usr/share/Wt/resources ../${BINDIR}/resources

clean:
	. /etc/environ.sh; \
	    use -e -r R-${RVERSION}; \
	    cd ${SRCDIR}; \
	    make clean; \

distclean: clean
	rm -f ${BINDIR}/resources
	if [ -d ${BINDIR} ] ; then \
	    cd ${BINDIR}; \
	        for i in $(APPS) ; do \
	            rm -f $$i ; \
	        done; \
	        for i in $(FILES) ; do \
	            rm -f $$i ; \
	        done; \
	fi
