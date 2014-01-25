Btree-source-code
=================

A working project for High-concurrency B-tree source code in C

There are four major code sets in the standard btree source code:

btree2q.c       Single Threaded/MultiProcess with latching supplied by advisory file locking.  Works with network file systems.

threads2h.c     Multi-Threaded/Multi-Process with latching implemented with pthreads/SRW latches in a latch manager.

threads2i.c     Multi-Threaded/Multi-Process with latching implemented with test & set locks in the btree pages with thread yield  system calls during contention.

threads2j.c     Multi-Threaded/Multi-Process with latching implemented with test & set locks in the btree pages with Linux futex system calls duriing contention.

The Foster set includes three types of latching:

Fosterbtreee.c  Multi-Threaded/Single Process with latching implemented with pthreads/SRW latches in a latch manager.

Fosterbtreef.c  Multi-Threaded/Multi-Process with latching implemented with test & set locks in the btree pages with thread yield  system calls during contention.

Fosterbtreeg.c  Multi-Threaded/Multi-Process with latching implemented with test & set locks in the btree pages with Linux futex system calls duriing contention.

Compilation is achieved on linux or Windows by:

gcc -D STANDALONE threads2h.c -lpthread

or

cl /Ox /D STANDALONE threads2h.c

Please see the project wiki page for documentation
