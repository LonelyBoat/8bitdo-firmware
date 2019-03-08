# Copyright (C) 2016 Richard Hughes <richard@hughsie.com>

VENDOR=8BitDo
PROJECT_NAME=N30_Pro2
VERSION=6.10
FIRMWARE_FILES=				\
	Pro2_Firmware_V6.10.dat
METAINFO_FILES=				\
	n30pro2.metainfo.xml	\

all: $(VENDOR)-$(PROJECT_NAME)-$(VERSION).cab

clean:
	rm *.cab

check: $(METAINFO_FILES)
	appstream-util validate-relax $(METAINFO_FILES)

%.cab: $(FIRMWARE_FILES) $(METAINFO_FILES)
	gcab --create --nopath $@ "$(FIRMWARE_FILES)" $(METAINFO_FILES)
	