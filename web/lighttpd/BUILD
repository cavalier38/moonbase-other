add_priv_user lighttpd:lighttpd -s /bin/false -c "lighttpd" &&

OPTS+=" --libdir=/usr/lib/lighttpd \
        --sysconfdir=/etc/lighttpd" &&

default_build &&

devoke_installwatch &&

mkdir -p /var/log/lighttpd &&
mkdir -p /srv/www/htdocs   &&
mkdir -p /var/lib/lighttpd &&
mkdir -p /etc/lighttpd/conf.d &&
chown lighttpd:lighttpd /srv/www /var/log/lighttpd &&

if [ ! -f /etc/lighttpd/lighttpd.conf ]; then
  install doc/config/lighttpd.conf /etc/lighttpd/
fi &&

if [ ! -f /etc/lighttpd/modules.conf ]; then
  install doc/config/modules.conf /etc/lighttpd/
fi &&

if [[ -z "$(ls -A /etc/lighttpd/conf.d/)" ]]; then
  install doc/config/conf.d/*.conf /etc/lighttpd/conf.d
fi

