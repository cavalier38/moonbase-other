(
   bad_flags ALL &&
   sedit "s:prefix?=/opt/diet:prefix=/opt/lunar/diet:" Makefile &&
   default_make &&
   cp /opt/lunar/diet/man/man1/diet.1 /usr/share/man/man1 &&
   cp /opt/lunar/diet/bin/diet /usr/bin/diet
   
) > $C_FIFO 2>&1
