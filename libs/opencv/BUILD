if in_depends $MODULE qt4; then
  . /etc/profile.d/qt4.rc
fi &&

# bug: examples have to be build, if they (the sources) will be installed
if [[ "`get_module_config EXAMPLES`" = "y" ]]; then
  OPTS+=" -DBUILD_EXAMPLES=ON"
else
  OPTS+=" -DBUILD_EXAMPLES=OFF"
fi &&

OPTS+=" -DBUILD_WITH_DEBUG_INFO=OFF -DBUILD_TESTS=OFF -DBUILD_PERF_TESTS=OFF" &&

default_cmake_build
