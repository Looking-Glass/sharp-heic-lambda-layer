# Library Versions
WEBP_VERSION=1.3.2
LIBDE265_VERSION=1.0.12
LIBHEIF_VERSION=1.12.0
VIPS_VERSION=8.12.2
SHARP_VERSION=0.30.7

PREFIX_PATH=/opt

export PKG_CONFIG_PATH=$(PREFIX_PATH)/lib/pkgconfig

build-SharpHEICLayer:
	yum remove -y libwebp

	# Install and enable the EPEL RPM package on Amazon Linux 2
	yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm

	# Install the RPM Fusion configuration package
	yum install -y https://download1.rpmfusion.org/free/el/rpmfusion-free-release-7.noarch.rpm

	# Install the Remi repository configuration package
	yum install -y http://rpms.remirepo.net/enterprise/remi-release-7.rpm

	# Install the yum-utils package (for the yum-config-manager command)
	yum install -y yum-utils

	# Enable Remi's RPM repository
	yum-config-manager --enable remi

	# Install libvips with HEIC support (+ development files and command-line tools)
	yum install -y vips vips-heif vips-devel vips-tools

	mkdir -p "$(ARTIFACTS_DIR)/bin"
	mkdir -p "$(ARTIFACTS_DIR)/nodejs/node16"

	cp /usr/bin/vips /usr/bin/vipsedit /usr/bin/vipsheader /usr/bin/vipsprofile /usr/bin/vipsthumbnail $(ARTIFACTS_DIR)/bin

	pkg-config --modversion vips-cpp
	SHARP_IGNORE_GLOBAL_LIBVIPS=1 npm --prefix $(ARTIFACTS_DIR)/nodejs/node16/ install --os=linux --cpu=x64 sharp@0.32.6