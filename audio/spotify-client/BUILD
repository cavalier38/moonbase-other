
cd $SOURCE_DIRECTORY/opt/spotify/spotify-client &&
./linklibs-fedora.sh &&
./linklibs.sh &&
find . -maxdepth 1 -type l | xargs -i cp -P {} Data/ &&
prepare_install &&
install -d -m 0755 /usr/libexec/spotify-client &&
install -d -m 0755 /usr/share/doc/spotify-client &&
cp -r $SOURCE_DIRECTORY/opt/spotify/spotify-client/* /usr/libexec/spotify-client/ &&
ln -s /usr/libexec/spotify-client/spotify /usr/bin/spotify &&
ln -s /usr/lib/libudev.so /usr/libexec/spotify-client/libudev.so.0 &&
cp $SOURCE_DIRECTORY/usr/share/doc/spotify-client/copyright /usr/share/doc/spotify-client/
