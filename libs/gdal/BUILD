
  patch_it $SOURCE2 2 &&

  CFLAGS+=" -fPIC" &&

# It gets confused about the location of ruby/config.h
  if in_depends $MODULE ruby ; then
    CFLAGS+=" $(pkg-config ruby --cflags)" &&
    sedit "s:puts Config:print RbConfig:g" swig/ruby/RubyMakefile.mk &&
    sedit "s:rrbconfig:r rbconfig:g" swig/ruby/RubyMakefile.mk
  fi &&

  mv configure.in configure.ac &&
  ./autogen.sh &&


# Do a little dance, make a little love, get Python tonight.
# The way their swig/Python scripts works, gdal needs to be
# installed cause of where their bindings look during the build.
  if in_depends $MODULE Python ; then
    OPTS+=" --without-python"
  fi &&

  default_build &&

  if in_depends $MODULE Python ; then
    cd swig/python &&
    python setup.py build &&
    python setup.py install --root=/
  fi &&

  if in_depends $MODULE Python-3 ; then
    python3 setup.py build &&
    python3 setup.py install --root=/
  fi
