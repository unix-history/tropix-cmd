#*
#****************************************************************
#*	Makefile para o programa "dd"				*
#****************************************************************
#*
ROOT	=
DIR	= $ROOT/usr/bin
PGM	= dd
PROT	= a+x
MAN	= cmd
CC	= cc

.virtual	lint cp cmp cmpq cmpqcp unld man modif prman gar gara

$PGM:		$PGM.o convtb.o
		$CC -u -s -O -o $PGM $PGM.o convtb.o
		size $PGM
		ls -l $PGM

$PGM.o:		$PGM.c
		$CC -c -O $PGM.c

convtb.o:	convtb.c
		$CC -c -O convtb.c

lint:
		$CC -T $PGM.c convtb.c

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
		man $PGM

modif:		modif.r
		sroff modif.r >$mandir/modif/$MAN/$PGM
		modif $PGM

prman:
		sroff man.r | lpr

gar:
		cd ..; gar -ovs0 $PGM
		cd ..; gar -icv0

gara:
		cd ..; gar -avs0 $PGM
		cd ..; gar -icv0
