mkdir -p /var/lib/lynx &&

OPTS+=" --host=$BUILD            \
        --prefix=/usr            \
        --libdir=/var/lib/lynx   \
        --mandir=/usr/share/man  \
        --enable-cgi-links       \
        --enable-nsl-fork        \
        --enable-read-eta        \
        --enable-color-style     \
        --enable-scrollbar       \
        --with-screen=ncursesw   \
        --enable-widec           \
        --with-zlib              \
        --sysconfdir=/etc        \
        --enable-gzip-help"     &&

default_config &&

if in_depends $MODULE openssl; then
  sedit 's/.*USE_OPENSSL_INCL.*/#define USE_OPENSSL_INCL 1/' lynx_cfg.h
fi &&

default_make &&

make install-help &&
make install-doc  &&

cp -bp lynx.cfg /var/lib/lynx/lynx.cfg &&
ln -sf /var/lib/lynx/lynx.cfg /etc/lynx.cfg &&
rm -f /usr/bin/lynx.old
