#*
#****************************************************************
#*	Makefile para o programa "xcoremap"			*
#****************************************************************
#*
ROOT	=
DIR	= $ROOT/usr/etc
PGM	= xcoremap
PROT	= a+x
MAN	= cmd
CC	= cc
DEF	=

.virtual	lint cp cmp cmpq cmpqcp unld man modif zipto zipfrom

$PGM:		$PGM.c
		$CC $DEF -u -s -O -o $PGM $PGM.c -lx.o
		size $PGM
		ls -l $PGM

lint:
		$CC $DEF -T $PGM.c

cp:		$PGM
		cp -f $PGM $DIR
		chmod $PROT $DIR/$PGM
		ls -L $DIR/$PGM

cmp:
		-cmpobj $PGM $DIR

cmpq:
		-cmpobj -q $PGM $DIR

cmpqcp:
		-cmpobj -q $PGM $DIR || make cp

unld:
		-rm -f $PGM

man:		man.r
		sroff man.r >$mandir/$MAN/$PGM
		chmod a+r $mandir/$MAN/$PGM
		man $PGM

modif:		modif.r
		sroff modif.r >$mandir/modif/$MAN/$PGM
		modif $PGM

zipto:
		-cmptree -sg . /zip$cmd/map/$PGM
		-forldiff /zip$cmd/map/$PGM
		-rm garfield

zipfrom:
		cd /zip$cmd/map/$PGM &&		\
		cmptree -sg . $cmd/map/$PGM;	\
		forldiff $cmd/map/$PGM;		\
		rm /zip$cmd/map/$PGM/garfield
