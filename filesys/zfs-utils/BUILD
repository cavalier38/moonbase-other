OPTS+=" --with-linux=$BUILD_DIRECTORY/linux \
        --with-linux-obj=$BUILD_DIRECTORY/linux \
        --with-config=user \
        --with-spl=$BUILD_DIRECTORY/spl \
        --with-spl-obj=$BUILD_DIRECTORY/spl \
        --disable-sysvinit \
        --disable-static"

default_config &&
make &&
make DESTDIR=$SOURCE_DIRECTORY/__pkg install &&
prepare_install &&
cd $SOURCE_DIRECTORY/__pkg &&
tar cf - . | (cd / && tar xvf -)
