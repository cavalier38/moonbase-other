  sedit "s:/games/:/:" configure &&
  sedit "s:xtra/icon/:icons/:" lib/icons/*.desktop &&

  OPTS+=" --with-setgid=games \
          --sysconfdir=/etc   \
          --docdir=/usr/doc/$MODULE  \
          --localstatedir=/var/games \
          --datarootdir=/usr/share/games" &&

  default_game_build  &&

  if in_depends "$MODULE" "SDL"; then
     install -Dm0644 lib/icons/angband-sdl.desktop /usr/share/applications/
  fi &&

  if in_depends "$MODULE" "libX11"; then
     install -Dm0644 lib/icons/angband-x11.desktop /usr/share/applications/
  fi
