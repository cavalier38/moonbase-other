./autogen.sh &&

if module_installed systemd; then
  OPTS+=" --without-rcstop --without-rcstart --without-rclevels --without-rcdir"
fi &&

OPTS+=" --disable-static \
        --with-browseremoteprotocols=DNSSD,CUPS \
        --with-test-font-path=/usr/share/fonts/dejavu-ttf/DejaVuSans.ttf" &&

default_build &&

if module_installed systemd; then
  # add upstream systemd support file
  sedit "s:cups.service:org.cups.cupsd.service:g" utils/cups-browsed.service &&
  install -Dm644 utils/cups-browsed.service /usr/lib/systemd/system/cups-browsed.service
fi

# use lp group for cups
chgrp -R lp /etc/cups
