enigma2 fork
------------

Build enigma2 for T4 using the SDK:

    source /opt/beyonwiz/beyonwizt4/17.5/environment-setup-mips32el-oe-linux
    autoreconf -i
    mkdir build
    cd build
    ../configure $CONFIGURE_FLAGS \
      BUILD_SYS=x86_64-linux \
      HOST_SYS=mipsel-oe-linux \
      STAGING_INCDIR=${SDKTARGETSYSROOT}/usr/include \
      STAGING_LIBDIR=${SDKTARGETSYSROOT}/usr/lib \
      PYTHON_VERSION=2.7 \
      PYTHON_CPPFLAGS=-I${SDKTARGETSYSROOT}/usr/include/python2.7 \
      PYTHON_LDFLAGS="-L${SDKTARGETSYSROOT}/usr/lib -lpython2.7" \
      PYTHON_SITE_PKG=${SDKTARGETSYSROOT}/usr/lib/python2.7/site-packages \
      --prefix=/usr \
      --libexecdir=/usr/lib/enigma2 \
      --sysconfdir=/etc \
      --localstatedir=/var \
      --enable-silent-rules \
      --enable-dependency-tracking \
      --with-gstversion=1.0 \
      --with-boxtype=inihdp \
      --with-bwlcd255 
    make

To build for other models, adjust the last two arguments.

