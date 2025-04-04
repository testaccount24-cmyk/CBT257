# CBT257
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. GitHub repos will be deleted and created during this period...

```
//***FILE 257 is from Sam Golob, and contains zaps to fix the       *   FILE 257
//*           old linkage editor (even if it is part of DFSMS),     *   FILE 257
//*           so that it will read object decks that are blocked    *   FILE 257
//*           bigger than 3200 bytes per block.  For your perusal   *   FILE 257
//*           and pleasure....  (Block size max set to 32720.)      *   FILE 257
//*                                                                 *   FILE 257
//*    *  -  *  -  *  -  *  -  *  -  *  -  *  -  *  -  *  -  *      *   FILE 257
//*                                                                 *   FILE 257
//*   The newer linkage editors (PGM=HEWL) do not seem to have      *   FILE 257
//*   this problem.  I assembled and linkedited a program with      *   FILE 257
//*   an object deck having BLKSIZE=32720 on a z/OS 2.4 system,     *   FILE 257
//*   and everything worked perfectly.  This was only a problem     *   FILE 257
//*   that existed "before the binder".                             *   FILE 257
//*                                                                 *   FILE 257
//*   However, the older linkage editor still exists as load        *   FILE 257
//*   module HEWLKED, and these zaps still apply to it.  For        *   FILE 257
//*   z/OS 2.4, member HDZ11C0 fits exactly to the existing         *   FILE 257
//*   program HEWLKED.  Unchanged in z/OS 2.5 as well.              *   FILE 257
//*                                                                 *   FILE 257
//*   A non-SMP install was included for up to z/OS 3.1 as member   *   FILE 257
//*   RUNZAP.  RUNZAP1 uses the DLIB SYS1.AOS04.                    *   FILE 257
//*                                                                 *   FILE 257
//*    *  -  *  -  *  -  *  -  *  -  *  -  *  -  *  -  *  -  *      *   FILE 257
//*                                                                 *   FILE 257
//*   FIXING YOUR OLD LINKAGE EDITOR  (IN DFSMS/MVS TOO)            *   FILE 257
//*                                                                 *   FILE 257
//*   EVEN UNDER DFSMS/MVS, WITH HEWL AND IEWL BEING THE NEW        *   FILE 257
//*   'BINDER', YOU CAN STILL RUN THE OLD LINKAGE EDITOR IF YOU     *   FILE 257
//*   SAY EXEC PGM=HEWLKED.  IBM HAS KEPT A VERSION OF THE OLD      *   FILE 257
//*   LINKAGE EDITOR AROUND.  HOWEVER, WITH THE BINDER, IBM HAS     *   FILE 257
//*   REMOVED THE OLD (NOW STUPID) RESTRICTION THAT OBJECT DECKS    *   FILE 257
//*   CAN'T BE BLOCKED GREATER THAN 3200 BYTES, OR 40 RECORDS       *   FILE 257
//*   PER BLOCK.  THERE WERE MEMORY RESTRICTIONS ONCE, THAT ARE     *   FILE 257
//*   NOW LONG GONE.  BUT WITH THE OLD LINKAGE EDITOR, THEY         *   FILE 257
//*   HAVEN'T REMOVED THE RESTRICTION, AND NOW IT IS "FUNCTIONALLY  *   FILE 257
//*   STABILIZED" FOR ALL PRACTICAL PURPOSES.                       *   FILE 257
//*                                                                 *   FILE 257
//*   I'VE LOOKED AT MY COPIES OF THE OLD LINKAGE EDITOR            *   FILE 257
//*   HEWLKED IN DFSMS, AND BEHOLD, THE OLD RESTRICTION HASN'T      *   FILE 257
//*   BEEN LIFTED OR CURED.  IT IS SO EASY TO DO!  WE HAD A         *   FILE 257
//*   USERMOD ONCE, WHICH I AM BRINGING TO YOU NOW.  I HAVE TWO     *   FILE 257
//*   VERSIONS OF THIS MOD, ONE FOR DFSMS 1.0, AND ANOTHER FOR      *   FILE 257
//*   DFSMS 1.3.  BOTH ARE THE SAME AS EACH OTHER, AND YOU          *   FILE 257
//*   SHOULDN'T HAVE ANY TROUBLE FITTING THIS MOD TO ANY VERSION    *   FILE 257
//*   OF THE OLD LINKAGE EDITOR, YOUNG OR RECENT.  I HAVE ALSO      *   FILE 257
//*   INCLUDED ZAPS FOR ALL VERSIONS OF THE LINKAGE EDITOR WHICH    *   FILE 257
//*   I HAD LYING AROUND AT OUR INSTALLATION, AS WELL AS I COULD    *   FILE 257
//*   DETERMINE.                                                    *   FILE 257
//*                                                                 *   FILE 257
//*               VERSION TABLE:                                    *   FILE 257
//*                                                                 *   FILE 257
//*                  HDQ1102    -   MVS/370   DFP 1.1               *   FILE 257
//*                  HDP2230    -   MVS/XA    DFP 2.3               *   FILE 257
//*                  HDP2240    -   MVS/XA    DFP 2.4               *   FILE 257
//*                  JDZ1110    -   DFSMS/MVS  1.1.0                *   FILE 257
//*                  HDZ11C0    -   DFSMS/MVS  1.3.0                *   FILE 257
//*                  MVS38      -   MVS 3.8j                        *   FILE 257
//*                  MVT        -   OS/360 Release 21.8             *   FILE 257
//*                                                                 *   FILE 257
//*   We have also included here, the actual linkage editors from   *   FILE 257
//*   old IBM systems, modified to take object decks that were      *   FILE 257
//*   blocked up to 32720 bytes in blocksize.                       *   FILE 257
//*                                                                 *   FILE 257
//*   The MVS 3.8j linkage editor, modified to accept 32720 byte    *   FILE 257
//*   object module blocksize, has been included here as member     *   FILE 257
//*   MVS38HEW.  This is allowed because MVS 3.8 was still either   *   FILE 257
//*   public domain, or IBM allows it to be given out for free.     *   FILE 257
//*   The MVT linkage editor, similarly modified to take 32720      *   FILE 257
//*   byte object module block sizes, has been included here also,  *   FILE 257
//*   as member MVTIEWL.                                            *   FILE 257
//*                                                                 *   FILE 257
//*    If you have any questions, I'm (hopefully) at:               *   FILE 257
//*                                                                 *   FILE 257
//*    Sam Golob                                                    *   FILE 257
//*    P.O. Box 702            email:  sbgolob@cbttape.org          *   FILE 257
//*    Pomona,  NY  10970                                           *   FILE 257
//*                                                                 *   FILE 257
```
