  python setup.py build &&
  prepare_install &&
  python setup.py install --optimize=1 --root=/ &&

  if in_depends $MODULE Python-3 ; then
      python3 setup.py build    &&
      prepare_install          &&
      python3 setup.py install --optimize=1
  fi
