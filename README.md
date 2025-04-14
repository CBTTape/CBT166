# CBT166
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. 
Due to amazing work by Alison Zhang and Jake Choi repos are no longer deleted.

```
//***FILE 166 is from VINH VU and contains a nice collection        *   FILE 166
//*           of utilities, exits, and REXX execs.  This file       *   FILE 166
//*           is worth a very good look.                            *   FILE 166
//*                                                                 *   FILE 166
//*       email:  Vinh Vu <vinhnvu@gmail.com>                       *   FILE 166
//*                                                                 *   FILE 166
//*    CONTENTS OF THIS PDS:                                        *   FILE 166
//*                                                                 *   FILE 166
//*      $ALIDEF  -  THIS EXEC MACRO CREATES THE IDCAMS DELETE AND  *   FILE 166
//*                  DEFINE ALIAS FOR A LIST OF DATASETS.  PARM     *   FILE 166
//*                  EXEPECTED IS CATALOG NAME, AND OPTIONAL 'O'    *   FILE 166
//*                  FOR (ONLY DEFINE, AND NO DELETE STATEMENTS     *   FILE 166
//*                  FOR THE ALIAS BEFORE RE-DEFINING IT).          *   FILE 166
//*                                                                 *   FILE 166
//*      $CAL     -  CLIST (EXEC) - WRITTEN IN TSO REXX.  THIS      *   FILE 166
//*                  EXEC DISPLAYS A QUICK POP-UP CALENDAR USING    *   FILE 166
//*                  ISPF PANEL.  CHECK IT OUT.                     *   FILE 166
//*                                                                 *   FILE 166
//*      $CATDEF  -  THIS EXEC MACRO CREATES THE IDCAMS DELETE AND  *   FILE 166
//*                  DEFINE STMTS FOR A LIST OF DATASETS.  PARM     *   FILE 166
//*                  EXEPECTED IS CATALOG NAME, VOLSER AND OPTIONAL *   FILE 166
//*                  'O' FOR (ONLY DEFINE, AND NO DELETE            *   FILE 166
//*                  STATEMENTS).                                   *   FILE 166
//*                                                                 *   FILE 166
//*      $CKOUT   -  CLIST (EXEC) - WRITTEN IN TSO REXX.  THIS      *   FILE 166
//*                  EXEC DISPLAYS PERTINENT INFORMATION ABOUT      *   FILE 166
//*                  YOUR TSO SESSION OR BATCH JOB, I.E. JOB/STEP   *   FILE 166
//*                  REGION SIZES, LIMITS, JOB/STEP TIME LIMITS,    *   FILE 166
//*                  MSGCLASS, ETC.. THIS CAN BE USED TO VERIFY     *   FILE 166
//*                  THE SETTINGS DONE BY THE LOCAL JES2 AND SMF    *   FILE 166
//*                  EXITS.                                         *   FILE 166
//*                                                                 *   FILE 166
//*      $CMDPFX  -  ASM - TO ASSIGN A COMMAND PREFIX TO A MVS      *   FILE 166
//*                  IMAGE OF A SYSPLEX.  RATHER THAN USING THE     *   FILE 166
//*                  'ROUTE' COMMAND, YOU CAN USE THIS PREFIX FOR   *   FILE 166
//*                  ROUTING A COMMAND TO THE APPROPRIATE SYSTEM.   *   FILE 166
//*                  THE PREFIX IS SPECFIED THROUGH PARM.           *   FILE 166
//*                                                                 *   FILE 166
//*      $CPU     -  CLIST (EXEC) - WRITTEN IN TSO REXX.  THIS IS   *   FILE 166
//*                  A CPU MONITOR DISPLAY.  THE CPU UTILIZATION    *   FILE 166
//*                  IS DISPLAYED IN GRAPHICAL FORMAT USING ISPF    *   FILE 166
//*                  PANELS WITH DYNAMIC COLOR.  THE DATA IS WRAPPED*   FILE 166
//*                  AROUND ON THE SCREEN FOR COMPARISON.  PRETTY   *   FILE 166
//*                  COLORS !!!!                                    *   FILE 166
//*                                                                 *   FILE 166
//*      $D       -  CLIST (EXEC) - WRITTEN IN TSO REXX.  THIS      *   FILE 166
//*                  DISPLAYS MVS CONTROL BLOCKS, I.E.              *   FILE 166
//*                  LINKLIST, APFLIST, SUBSYSTEM NAMES.            *   FILE 166
//*                                                                 *   FILE 166
//*      $DATE    -  CLIST (EXEC) - WRITTEN IN TSO REXX.            *   FILE 166
//*                  THIS REXX FUNCTION DOES DATE                   *   FILE 166
//*                  CONVERSIONS, INCLUDING RELATIVE DATE           *   FILE 166
//*                  USED FOR CALCULATION.                          *   FILE 166
//*                                                                 *   FILE 166
//*      $DO      -  CLIST (EXEC) - EDIT MACRO. THIS EXEC           *   FILE 166
//*                  VERIFIES THE 'DO/SELECT-END' PAIRINGS IN A     *   FILE 166
//*                  REXX EXEC.  ANY HANGING 'DO/SELECT-END' WILL   *   FILE 166
//*                  BE FLAGGED AS ERROR.  IT ALSO MARKS THE        *   FILE 166
//*                  BEGINNING AND END OF EACH 'DO/SELECT-END'      *   FILE 166
//*                  PAIR.  USEFUL IF YOU DO A LOT OF REXX          *   FILE 166
//*                  CODING.                                        *   FILE 166
//*                                                                 *   FILE 166
//*      $IEASYS  -  THIS EXEC DISPLAYS IEASYSXX VARIABLES.  IT     *   FILE 166
//*                  ALSO LISTS OUT THE PARMLIB WHERE THESE MEMBERS *   FILE 166
//*                  CAME FROM.  GREAT FOR DIAGNOSTICS AND CHASING  *   FILE 166
//*                  THROUGH WHAT PARM MEMBERS GOT PULLED BASED ON  *   FILE 166
//*                  IPL SPECFICATION.                              *   FILE 166
//*                                                                 *   FILE 166
//*      $INFO    -  CLIST (EXEC) - WRITTEN IN TSO REXX.  THIS IS A *   FILE 166
//*                  GENERAL SRM INFO DISPLAY.  THE CPU UTILIZATION *   FILE 166
//*                  PLUS ALL OTHER SRM INDICATORS ARE SHOWN. ANY   *   FILE 166
//*                  EXCEPTION CONDITION WILL CHANGE EITHER SOME    *   FILE 166
//*                  DISPLAY COLORS OR TEXT DISPLAY.  SOME OF THE   *   FILE 166
//*                  INFO INCLUDES PAGE FAULT RATE, MIGR AGE, AFQ,  *   FILE 166
//*                  UIC, ETC...  THE CPU UTIL IS ALSO DISPLAYED IN *   FILE 166
//*                  A GRAPHICAL FORMAT.  AGAIN, PRETTY COLORS !!!  *   FILE 166
//*                                                                 *   FILE 166
//*      $JAD     -  CLIST (EXEC) - WRITTEN IN TSO REXX.  THIS      *   FILE 166
//*                  EXEC GOES THROUGH THE ASCB CHAIN AND           *   FILE 166
//*                  DISPLAYS JOB ACTIVITY INFO USING ISPF TABLE    *   FILE 166
//*                  DISPLAY FACILITY, I.E. TCBTIME, EXCPTIME,      *   FILE 166
//*                  EXCP COUNT, STORAGE USAGE, ETC. IF AN          *   FILE 166
//*                  ADDRESS SPACE IS SELECTED, THEN ADDITIONAL     *   FILE 166
//*                  INFO WILL BE DISPLAYED, INCLUDING A PLOT       *   FILE 166
//*                  THAT SHOWS REAL & EXPANDED STORAGE, AND        *   FILE 166
//*                  ANOTHER WHICH SHOWS ITS STORAGE                *   FILE 166
//*                  DISTRIBUTION BASED ON UIC (KINDA SHOW YOU      *   FILE 166
//*                  HOW REAL MEMORY IS BEING USED AT THE TIME).    *   FILE 166
//*                  THE DISPLAY CAN BE SORTED AND FILTERED BY      *   FILE 166
//*                  SEVERAL DIFFERENT KEYS.                        *   FILE 166
//*                                                                 *   FILE 166
//*                  THIS WAS WRITTEN ORIGINALLY TO DISPLAY THE     *   FILE 166
//*                  TOTAL STORAGE USED, PLUS REAL AND EXPANDED,    *   FILE 166
//*                  SEPARATELY FOR THE ADDRESS SPACES. RMFWDM      *   FILE 166
//*                  (WORKLOAD DELAY MONITOR) ONLY GIVES YOU THE    *   FILE 166
//*                  TOTAL, NOT THE OTHER TWO, AND DOES NOT         *   FILE 166
//*                  ALLOW SORTING.  THIS EXEC, HOWEVER, GIVES      *   FILE 166
//*                  ALL TOTALS AND LET YOU DO ALL KIND OF          *   FILE 166
//*                  SORTING.  NOT ONLY THAT, IT ALSO GIVES YOU     *   FILE 166
//*                  ADDITIONAL INFO (WHILE I'M LOOKING AROUND      *   FILE 166
//*                  AT THE CONTROL BLOCKS...).                     *   FILE 166
//*                                                                 *   FILE 166
//*               ****** SEE $JADPGM ******  NOTE - 3/6/95 ******   *   FILE 166
//*               ****** SEE $JADPGM ******  NOTE - 3/6/95 ******   *   FILE 166
//*                                                                 *   FILE 166
//*      $JADPGM  -  ASM - ASSEMLER VERSION OF $JAD.  THIS WAS      *   FILE 166
//*                  WRITTEN AFTER $JAD IS FOUND TO BE TOO          *   FILE 166
//*                  SLOW, ESPCIALLY WHEN THE CPU IS CONSTANTLY     *   FILE 166
//*                  RUNNING ABOVE 100% (SRM CPU BUSY PCT).         *   FILE 166
//*                                                                 *   FILE 166
//*      $LLACOPY -  SOURCE - BATCH ASSEMBLER PROGRAM TO            *   FILE 166
//*                  SELECTIVELY REFRESH A LLA (VLF) MODULE.        *   FILE 166
//*                  RATHER THAN DOING A 'F LLA,REFRESH' WHICH      *   FILE 166
//*                  MAY TAKE A WHILE DEPENDING ON THE LIST OF      *   FILE 166
//*                  DATA SETS BEING MANAGED BY LLA, THIS           *   FILE 166
//*                  PROGRAM WILL UPDATE JUST THE MODULE(S) BEING   *   FILE 166
//*                  REFRESHED.                                     *   FILE 166
//*                                                                 *   FILE 166
//*      $MCOPY   -  THIS EXEC COPIES MEMBER(S) FROM ONE PDS TO     *   FILE 166
//*                  ANOTHER PDS USING ISPF SERVICES AND THEREFORE  *   FILE 166
//*                  MAINTAINS THE ENQ ACROSS. THE EXEC PROVIDES    *   FILE 166
//*                  SAME FUNCTION UNDER BATCH ISPF AS OPTION 3.3   *   FILE 166
//*                  UNDER ON-LINE ISPF.                            *   FILE 166
//*                                                                 *   FILE 166
//*      $MDEL    -  THIS EXEC DOES A DELETE OF A PDS MEMBER USING  *   FILE 166
//*                  ISPF DIALOG SERVICES AND THEREFORE MAINTAINS   *   FILE 166
//*                  THE ENQ ACROSS. THE EXEC DOES PROVIDE THE      *   FILE 166
//*                  SAME FUNCTION UNDER BATCH (RUNNING ISPF) AS    *   FILE 166
//*                  IN OPTION 3.1 FOR ONLINE ISPF.                 *   FILE 166
//*                                                                 *   FILE 166
//*      $MREN    -  THIS EXEC DOES A RENAME OF A PDS MEMBER USING  *   FILE 166
//*                  ISPF DIALOG SERVICES AND THEREFORE MAINTAINS   *   FILE 166
//*                  THE ENQ ACROSS.  THE EXEC PROVIDES SAME        *   FILE 166
//*                  FUNCTION UNDER BATCH ISPF AS OPTION 3.1 UNDER  *   FILE 166
//*                  ONLINE ISPF.                                   *   FILE 166
//*                                                                 *   FILE 166
//*      $MEM     -  THIS EXEC ALLOWS A MEMBER TO BE SEARCHED FROM  *   FILE 166
//*                  CONCATENATION OF SEVERAL PDS'S.  THESE PDS'S   *   FILE 166
//*                  CAN HAVE SPECIFIC VOLSER CODED.  ONLY THE      *   FILE 166
//*                  FIRST FOUND MEMBER IN THE CONCATENATION WILL   *   FILE 166
//*                  BE DISPLAYED (VIEW, BROWSE OR EDIT).  THIS IS  *   FILE 166
//*                  GOOD FOR LOOKING AT SYS1.XXX.PARMLIB MEMBERS.  *   FILE 166
//*                                                                 *   FILE 166
//*      $MPFREPL -  ASM - A GENERALIZED MPF EXIT.  THE MESSAGES    *   FILE 166
//*                  BEING HANDLED ARE CODED USING AN IN-LINE       *   FILE 166
//*                  MACRO.  PROCESSING CAN ALSO BE LIMITED TO      *   FILE 166
//*                  MESSAGES PRODUCED BY CERTAIN JOBNAMES          *   FILE 166
//*                  SPECIFIED BY THIS MACRO.                       *   FILE 166
//*                                                                 *   FILE 166
//*      $PARM    -  CLIST (EXEC) - WRITTEN IN TSO REXX.  THIS      *   FILE 166
//*                  EXEC TAKES IN THE PARMS AND DOES SUBSTITUTION  *   FILE 166
//*                  ON THE INPUT CARDS (FROM DDNAME INPUT) TO      *   FILE 166
//*                  PRODUCE OUTPUT DATA FOR SUBSEQUENT USAGE.      *   FILE 166
//*                  SEVERAL RESERVED SYMBOLS WILL BE SUBSTITUTED   *   FILE 166
//*                  AS WELL, I.E. ~JOBNAME~, ~SYSID~.  REXX        *   FILE 166
//*                  FUNCTIONS WILL ALSO BE EVALUATED TO PRODUCE    *   FILE 166
//*                  THE OUTPUT IF CODED (THIS CAN BE JUST ANOTHER  *   FILE 166
//*                  EXTERNAL REXX FUNCTION LIKE $DATE)             *   FILE 166
//*                                                                 *   FILE 166
//*      $POINT   -  TO GRAB THE DATA SET NAME AT WHERE THE CURSOR  *   FILE 166
//*                  IS AND BRINGS UP A PANEL SHOWING DATA SET      *   FILE 166
//*                  CHARACTERISTICS AND ALSO ALLOWS IT TO BE       *   FILE 166
//*                  EDITED, BROWSED, ETC... FOR THE DATA SET TYPES *   FILE 166
//*                  THAT ISPF CANNOT HANDLE, I.E. VSAM, LOADLIB,   *   FILE 166
//*                  FILEAID WILL BE INVOKED INSTEAD.               *   FILE 166
//*                                                                 *   FILE 166
//*      $Q       -  EDIT MACRO (REXX) - THIS MACRO TAKES A PARM    *   FILE 166
//*                  AS A TSO COMMAND TO BE ISSUED AND THE OUTPUT   *   FILE 166
//*                  WILL BE TRAPPED AND DISPLAYED AS ISPF EDIT     *   FILE 166
//*                  NOTE LINES.                                    *   FILE 166
//*                                                                 *   FILE 166
//*      $RXSYMBL -  AN ASSEMBLER PROGRAM TO USE THE ASASYMBP       *   FILE 166
//*                  MACRO TO RESOLVE AND SUBSTITUTE ALL SYSTEM     *   FILE 166
//*                  SYMBOLIC REFERENCES.  CALLED BY THE $SYMSUB    *   FILE 166
//*                  EXEC.                                          *   FILE 166
//*                                                                 *   FILE 166
//*      $SAVE    -  EDIT MACRO (REXX) - THIS MACRO SAVES DATA      *   FILE 166
//*                  BEING EDITED BY DOING UPDATE IN PLACE FOR A    *   FILE 166
//*                  PDS MEMBER.  EXTREMELY USEFUL IF               *   FILE 166
//*                  SYS1.PROCLIB IS FULL, AND YOU JUST NEED TO     *   FILE 166
//*                  MAKE MINIMUM CHANGES TO A PROC (UNLESS YOU     *   FILE 166
//*                  WANT TO GO AHEAD AND COMPRESS IT RIGHT THEN    *   FILE 166
//*                  AND THERE ...)                                 *   FILE 166
//*                                                                 *   FILE 166
//*      $SYMSUB  -  EDIT MACRO TO REPLACE SYSTEM SYMBOLICS WITH    *   FILE 166
//*                  THEIR ACTUAL VALUE.  NEEDS EXTERNAL REXX       *   FILE 166
//*                  $RXSYMBL TO ACTUALLY RESOLVE THE SYMBOLICS.    *   FILE 166
//*                                                                 *   FILE 166
//*      $SYSINFO -  DISPLAY SYSTEM INFORMATION USING A GRAPHIC     *   FILE 166
//*                  ISPF PANEL.                                    *   FILE 166
//*                                                                 *   FILE 166
//*      $SYSPRM  -  THIS EXEC WILL BRING BRING IN THE              *   FILE 166
//*                  CONCATENATION OF PARMLIB MEMBERS INTO A        *   FILE 166
//*                  TEMPORARY DATA SET, THEN INVOKE ISPF EDIT      *   FILE 166
//*                  WITH MACRO $SYMSUB TO REPLACE SYSTEM           *   FILE 166
//*                  SYMBOLICS WITH THE REAL VALUES.  THIS IS A     *   FILE 166
//*                  GOOD WAY TO SEE WHAT EACH PARM MEMBER          *   FILE 166
//*                  SPECIFICATION EXPANDS TO UNDER THE CURRENT     *   FILE 166
//*                  SYSTEM.                                        *   FILE 166
//*                                                                 *   FILE 166
//*      $VSAMIDX -  CLIST (EXEC) - WRITTEN IN TSO REXX.  THIS      *   FILE 166
//*                  EXEC CALCULATES THE OPTIMUM NUMBER OF          *   FILE 166
//*                  INDEX BUFFERS TO BE SPECIFIED FOR A VSAM       *   FILE 166
//*                  KSDS USED FOR RANDOM ACCESS.                   *   FILE 166
//*                                                                 *   FILE 166
//*      $VSAMIXA -  CLIST (EXEC) - THE DFSMS 1.X VERSION OF        *   FILE 166
//*                  $VSAMIDX.                                      *   FILE 166
//*                                                                 *   FILE 166
//*      $WHOHAS  -  CLIST (EXEC) - THIS REXX EXEC WILL LIST THE    *   FILE 166
//*                  ACCESS LISTS FOR RACF DATA SET PROFILES FOUND  *   FILE 166
//*                  UNDER DSN*.**.  THIS FUNCTION IS VERY MUCH     *   FILE 166
//*                  SIMILAR TO 'TSS WHOHAS DSN' COMMAND UNDER TOP  *   FILE 166
//*                  SECRET.  IF THE EXEC IS RUN IN BATCH, THE RACF *   FILE 166
//*                  COMMANDS USED TO RE-BUILD ALL OF THE PROFILES  *   FILE 166
//*                  AS DISPLAYED IN THE OUTPUT IS ALSO PRODUCED.   *   FILE 166
//*                                                                 *   FILE 166
//*      $X       -  EDIT MACRO (REXX) - THIS MACRO READS THE       *   FILE 166
//*                  MEMBER BEING EDITED AND EXECUTES IT AS A       *   FILE 166
//*                  CLIST/EXEC.  EXECUTION PARMS ARE ALLOWED AS    *   FILE 166
//*                  WELL.  THIS DOES NOT REQUIRED THE MEMBER TO    *   FILE 166
//*                  BE SAVED FIRST.  EXTREMELY USEFUL IF YOU'RE    *   FILE 166
//*                  DOING A LOT OF CLIST/EXEC CODING AND           *   FILE 166
//*                  DEBUGGING.                                     *   FILE 166
//*                                                                 *   FILE 166
//*      $6       -  CLIST (EXEC) - WRITTEN IN TSO REXX.  OFTEN     *   FILE 166
//*                  TIMES, YOU DO NEED TO ALLOCATE A NEW           *   FILE 166
//*                  LOADLIB AND EXECUTE TSO COMMANDS OUT OF        *   FILE 166
//*                  IT.  ONE WAY TO DO IT IS: GET OUT OF ISPF,     *   FILE 166
//*                  ALLOCATE IT AS ISPLLIB, AND GET BACK IN.       *   FILE 166
//*                  THE OTHER WAY (WITHOUT HAVING TO GET OUT       *   FILE 166
//*                  OF ISPF): EXECUTE THIS EXEC, AND THERE YOU     *   FILE 166
//*                  GO !!!                                         *   FILE 166
//*                                                                 *   FILE 166
//*      DALLOC   -  SOURCE - TSO CMD TO DISPLAY DYNAMIC            *   FILE 166
//*                  ALLOCATIONS.  I'VE GOT THE ORIGINAL SOURCE     *   FILE 166
//*                  FROM ONE OF THE VERY OLD CBT TAPE.  THIS       *   FILE 166
//*                  STOPPED WORKING WHEN OUR JES2 PGMR DECIDED     *   FILE 166
//*                  TO MOVE SWA ABOVE THE LINE.  I THEN            *   FILE 166
//*                  DECIDED TO FIX THIS PROGRAM USING MACRO        *   FILE 166
//*                  'SWAREQ' WHICH IS THE STANDARD WAY TO          *   FILE 166
//*                  ACCESS THE JFCB FROM TIOT PTR.                 *   FILE 166
//*                                                                 *   FILE 166
//*      DATE     -  THIS IS JES2 EXIT 1 (PAGE SEPARATOR),          *   FILE 166
//*                  BUT REALLY IT IS CSECT RBDDATE WHICH           *   FILE 166
//*                  IMPLEMENTS TABLELESS DATE CONVERSION           *   FILE 166
//*                                                                 *   FILE 166
//*      DYNALIST -  SOURCE - TSO COMMAND TO DISPLAY ALL UNIT       *   FILE 166
//*                  NAMES ON THE SYSTEM AND THE UCBS' (PLUS        *   FILE 166
//*                  VOLSERS) ASSOCIATED WITH THOSE UCBS.           *   FILE 166
//*                  DYNALIST IS AN OLD PROGRAM COMING OFF THE      *   FILE 166
//*                  CBT TAPE AND MODIFIED TO WORK WITH MVS 4.2     *   FILE 166
//*                  AND ABOVE.                                     *   FILE 166
//*                                                                 *   FILE 166
//*      ENQMON   -  SOURCE - ASM PROGRAM USED AS A STC TO          *   FILE 166
//*                  MONITOR AND DISPLAY GRS ENQ CONTENTION. THIS   *   FILE 166
//*                  PROGRAM DOES GQSCAN EVERY MINUTE, DISPLAYS     *   FILE 166
//*                  THE HOLDERS/WAITERS ON THE CONSOLE.  IF THE    *   FILE 166
//*                  HOLDER IS A TSO USER, A MESSAGE WILL BE SENT   *   FILE 166
//*                  TO NOTIFY THE USER.  EVERY MINUTE, THE         *   FILE 166
//*                  CONSOLE DISPLAYED MESSAGE WILL BE              *   FILE 166
//*                  UN-HILIGHTED, THE MINUTE INCREMENTS, AND A     *   FILE 166
//*                  NEW MESSAGE IS DISPLAYED.  THE WAITING JOB     *   FILE 166
//*                  WILL ALSO RECEIVE MESSAGES AS PART OF THE      *   FILE 166
//*                  JOBLOG.  THIS PROGRAM TRIES TO MIMICK MIM AS   *   FILE 166
//*                  MUCH AS POSSIBLE WITH THE EXCEPTION OF THE     *   FILE 166
//*                  JOB REQUEUE FUNCTION.                          *   FILE 166
//*                                                                 *   FILE 166
//*      FIND     -  SOURCE - TSO CMD TO DO QUICK SEARCH FOR        *   FILE 166
//*                  ANY CHARACTER STRING IN A PDS.  HAS A FEW      *   FILE 166
//*                  NICE OPTIONS.                                  *   FILE 166
//*                                                                 *   FILE 166
//*      IEFUTL   -  MULTI FUNCTION, SEMI-SMART, TABLE DRIVEN       *   FILE 166
//*                  TIMEOUT PROCESSOR                              *   FILE 166
//*                                                                 *   FILE 166
//*      IEFUTLTB -  THE TABLE IT USES                              *   FILE 166
//*                                                                 *   FILE 166
//*      JESXIT05 -  JES2 COMMAND EXIT TO DO THE FOLLOWING:         *   FILE 166
//*                                                                 *   FILE 166
//*                  $Q'XXX    -  DISPLAYS ALL JOBS PREFIXED        *   FILE 166
//*                               BY XXX                            *   FILE 166
//*                  $QAPF     -  DISPLAYS APF LIST                 *   FILE 166
//*                  $QLLT     -  DISPLAYS LINKLIST TABLE           *   FILE 166
//*                  $QDSN=XXX -  CATALOG SEARCH DSNAME XXX. THE    *   FILE 166
//*                               CATALOGED VOLUME IS ALSO SEARCHED *   FILE 166
//*                               TO MAKE SURE DATA SET DOES EXIST  *   FILE 166
//*                               THERE.                            *   FILE 166
//*                  $QVOL=YYY -  DISPLAYS UCB ADDR OF VOL=YYY.     *   FILE 166
//*                               IT'S NOT EASY TO FIND THIS OUT    *   FILE 166
//*                               USING NATIVE MVS COMMANDS.        *   FILE 166
//*                  $QSYSTEM  -  DISPLAYS ALL KIND OF INFO ABOUT   *   FILE 166
//*                               SYSTEM.  GOOD FOR US SYSTEMS      *   FILE 166
//*                               PROGRAMMERS.                      *   FILE 166
//*                  $Q        -  DISPLAYS AVAILABLE PARMS (AS      *   FILE 166
//*                               ABOVE)                            *   FILE 166
//*                                                                 *   FILE 166
//*          JES2 PARMS NEEDED:                                     *   FILE 166
//*                                                                 *   FILE 166
//*          *   LOADMOD(JESXIT05)                                  *   FILE 166
//*          *   EXIT(005) ROUTINE=EXIT5,STATUS=ENABLED,TRACE=NO    *   FILE 166
//*                                                                 *   FILE 166
//*      JESX006  -  JES2 INTERNAL TEXT SCAN, TABLE DRIVEN,         *   FILE 166
//*                  IMPLEMENTS CONTROLS ON NUMBER OF TAPE          *   FILE 166
//*                  DRIVES PER STEP.                               *   FILE 166
//*                                                                 *   FILE 166
//*      JSTAT    -  SOURCE - BATCH PROGRAM TO CHECK AND SEE IF     *   FILE 166
//*                  A JOB (OR STC OR TSU) IS CURRENTLY RUNNING     *   FILE 166
//*                  (USING THE 'STATUS' FUNCTION OF JES2).  IF     *   FILE 166
//*                  IT IS FOUND, THEN WTO'S WILL BE DONE USING     *   FILE 166
//*                  CONTROL CARDS IN 'FND'.  OTHERWISE,            *   FILE 166
//*                  CONTROL CARDS FROM 'NOTFND' DDNAME WILL BE     *   FILE 166
//*                  USED BY WTO'S.  IF 'RRFND' AND 'RRNOTFND'      *   FILE 166
//*                  ARE USED, A WTOR WILL BE DONE AFTER THE        *   FILE 166
//*                  WTO'S TO GIVE THE OPERATOR A CHANCE TO DO      *   FILE 166
//*                  SOMETHING ELSE BEFORE THE REPLY.  OF           *   FILE 166
//*                  COURSE, NONE OF THE DDNAMES HAS TO BE          *   FILE 166
//*                  PRESENT, IN WHICH CASE, THE APPROPRIATE        *   FILE 166
//*                  RETURN CODE WILL BE ISSUED BASED ON THE        *   FILE 166
//*                  JOB STATUS.  NOTE THAT SINCE THIS PROGRAM      *   FILE 166
//*                  DOES NOT GO THROUGH THE ASVT, AND              *   FILE 166
//*                  THEREFORE DOES WORK IN A JES2 SHARED SPOOL     *   FILE 166
//*                  ENVIRONMENT.                                   *   FILE 166
//*                                                                 *   FILE 166
//*      LOCKTERM -  TSO COMMAND TO LOCK A SCREEN WITH A            *   FILE 166
//*                  PASSWORD                                       *   FILE 166
//*                                                                 *   FILE 166
//*      SEEK     -  SOURCE - TSO CMD TO DO QUICK SEARCH FOR        *   FILE 166
//*                  ANY MODULE THAT RESIDES IN LPA                 *   FILE 166
//*                  (MLPT/FLPA/PLPA), LINKLIST, AND/OR             *   FILE 166
//*                  STEPLIB.  MODULE INFORMATION WILL BE           *   FILE 166
//*                  DISPLAYED ACCORDINGLY IF FOUND.                *   FILE 166
//*                                                                 *   FILE 166
//*      TSOINIT  -  SOURCE - TSO CMD TO CHECK FOR A FEW ISPF       *   FILE 166
//*                  DATA SETS AND ALLOCATE THEM AS 'NEW' IF        *   FILE 166
//*                  THEY ARE NOT FOUND IN THE CATALOGS.  THESE     *   FILE 166
//*                  DATA SET NAMES ARE RECORDED IN A TABLE OF      *   FILE 166
//*                  THIS PROGRAM.  THE FIRST DATA SET              *   FILE 166
//*                  QUALIFIER WILL BE THE SAME WITH THE            *   FILE 166
//*                  EXECUTING TSO ID.                              *   FILE 166
//*                                                                 *   FILE 166
//*   -*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*-*- *   FILE 166
//*                                                                 *   FILE 166
//*     WE DO NOT PROMISE TO MAKE ANY CORRECTIONS AND/OR            *   FILE 166
//*     MODIFICATIONS TO ANY OF THE PROGRAMS.  HOWEVER, WE DO       *   FILE 166
//*     ENCOURAGE ANY COMMENTS/IDEAS AND WILL ATTEMPT TO PROVIDE    *   FILE 166
//*     ANY FIXES AND/OR MODIFICATIONS AS TIME PERMITS.  ALL        *   FILE 166
//*     QUESTIONS/COMMENTS CAN BE DIRECTED TO:                      *   FILE 166
//*                                                                 *   FILE 166
//*          email:  Vinh Vu <vinhnvu@gmail.com>                    *   FILE 166
//*                                                                 *   FILE 166
```
