# Specify where the TigerVNC source is installed so we can find the
# source man pages
TIGERVNC_DIR =

PAGES = \
	vncconfig.html \
	vncpasswd.html \
	vncsession.html \
	vncviewer.html \
	x0vncserver.html \
	Xvnc.html

.PHONY: all
all: $(PAGES)

CONVERT = groff -mandoc -Thtml -P-l

vncconfig.html: $(TIGERVNC_DIR)/unix/vncconfig/vncconfig.man
	$(CONVERT) "$<" > "$@"

vncpasswd.html: $(TIGERVNC_DIR)/unix/vncpasswd/vncpasswd.man
	$(CONVERT) "$<" > "$@"

# vncsession.man is generated, so a proper build needs to have been done
vncsession.html: $(TIGERVNC_DIR)/unix/vncserver/vncsession.man
	$(CONVERT) "$<" > "$@"

vncviewer.html: $(TIGERVNC_DIR)/vncviewer/vncviewer.man
	$(CONVERT) "$<" > "$@"

x0vncserver.html: $(TIGERVNC_DIR)/unix/x0vncserver/x0vncserver.man
	$(CONVERT) "$<" > "$@"

Xvnc.html: $(TIGERVNC_DIR)/unix/xserver/hw/vnc/Xvnc.man
	$(CONVERT) "$<" > "$@"

clean:
	rm -f $(PAGES)
