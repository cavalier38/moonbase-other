scons -j${MAKES:=1} --build-dir=release $OPTS &&

prepare_install &&

# binaries
install -m755 {build/release,/usr/bin}/clingo &&
install -m755 {build/release,/usr/bin}/gringo &&
install -m755 {build/release,/usr/bin}/reify &&

# provide headers for libclingo.so
# yes it's ugly, yes upstream wants it that way (for now)...
cp -rv libclasp/clasp libclingo/clingo libgringo/gringo/ libprogram_opts/program_opts /usr/include &&

# libraries
install -m755 build/release/libclingo.so* /usr/lib/ &&

if in_depends $MODULE Python; then
  install -m755 {build/release/python,/usr/lib/python2.7/site-packages}/gringo.so
fi &&

if in_depends $MODULE lua; then
  install -m755 {build/release/lua,/usr/lib/lua}/gringo.so
fi &&

# documentation
gather_docs NOTES examples
