# Install and enable the EPEL RPM package on Amazon Linux 2
yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm

# Install the RPM Fusion configuration package
yum install https://download1.rpmfusion.org/free/el/rpmfusion-free-release-7.noarch.rpm

# Install the Remi repository configuration package
yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm

# Install the yum-utils package (for the yum-config-manager command)
yum install yum-utils

# Enable Remi's RPM repository
yum-config-manager --enable remi

# Install libvips with HEIC support (+ development files and command-line tools)
yum install vips vips-heif vips-devel vips-tools