
  patch_it $SOURCE_CACHE/$SOURCE2 1  &&

  if in_depends $MODULE perl; then
    PERL_ARCH=`arch` &&
    OPTS+=" -DPX_PERL_ARCH=$PERL_ARCH"
  fi &&

  default_cmake_build
