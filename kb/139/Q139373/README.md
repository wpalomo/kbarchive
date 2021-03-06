---
layout: page
title: "Q139373: INF: Sample ODBC.INF for ODBC Drivers Shipped in Access 7.0"
permalink: /kb/139/Q139373/
---

## Q139373: INF: Sample ODBC.INF for ODBC Drivers Shipped in Access 7.0

{% raw %}

	Article: Q139373
	Product(s): Open Database Connectivity (ODBC)
	Version(s): WINDOWS:2.5,3.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 26-AUG-1999
	
	2.50 3.00 3.5x 6.00
	WINDOWS
	kbusage kbinterop
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Open Database Connectivity, versions 2.5, 3.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Microsoft SQL Server Driver 2.50.0126, and Desktop Database Drivers 3.0.2111
	ship with Microsoft Access 7.0, but there is no ODBC 2.0-compliant ODBC.INF file
	in the package. This article gives a sample ODBC.INF designed for those drivers.
	
	MORE INFORMATION
	================
	
	  -------------------- Beginning of ODBC.INF --------------------------------
	
	  [Source Media Descriptions]
	     "1", "Jet Database Engine", "msjt3032.dll", "."
	
	  [ODBC Drivers]
	  "Microsoft Access Driver (*.mdb)" =
	  "Microsoft Dbase Driver (*.dbf)" =
	  "Microsoft Excel Driver (*.xls)" =
	  "Microsoft FoxPro Driver (*.dbf)" =
	  "Microsoft Paradox Driver (*.db )" =
	  "Microsoft Text Driver (*.txt; *.csv)" =
	  "SQL Server" =
	
	  [ODBC]
	  "Main"=1,odbccp32.dll,,,,1995-09-28,,,OLDER,,,,,,,91136,,,,02.50.30.06,
	  "Help"=1,odbcinst.hlp,,,,1994-09-28,,,OLDER,,,,,,,18321,,,,02.50.30.06,
	  "WinSysNT01"=1,ctl3d32.dll,,,,1995-09-28,,,OLDER,,,,,,SHARED,27136,,,,
	  2.31.00.0
	  0,
	  "CtlPnl"=1,odbccp32.cpl,,,,1995-09-28,,,OLDER,,,,,,,6656,,,,02.50.30.06,
	  "WinSysNT02"=1,msvcrt20.dll,,,,1995-09-
	  28,,,,,,,,,SHARED,253952,,,,02.11.00.0
	  0,
	  "Intl"=1,odbcint.dll,,,,1995-09-28,,,,,,,,,,32768,,,,02.50.30.06,
	  "ODBCAdmin"=1,odbcad32.exe,,,,1995-09-28,,,OLDER,,,,,,,7168,,,,2.50.30.6,
	
	  [ODBC Driver Manager]
	  "Driver"=1,odbc32.dll,,,,1999-09-28,,,OLDER,,,,,,,64512,,,,02.50.30.06,
	  "Cursor"=1,odbccr32.dll,,,,1995-09-28,,,OLDER,,,,,,,167936,,,,02.50.30.06,
	  "WinSysNT01"=1,ctl3d32.dll,,,,1995-09-28,,,OLDER,,,,,,SHARED,27136,,,,
	  2.31.00.0
	  0,
	  "WinSysNT02"=1,msvcrt20.dll,,,,1995-09-
	  28,,,,,,,,,SHARED,253952,,,,02.11.00.0
	  0,
	  "Intl"=1,odbcint.dll,,,,1995-09-28,,,,,,,,,,32768,,,,02.50.30.06,
	
	  [Generic Thunk ODBC]
	  "Thunk2" = 1, ds16gt.dll,,,, 1995-09-28,  ,,,  ,,,,,, 5024,,,, 2.10.23.23,
	  "Thunk1" = 1, ds32gt.dll,,,, 1995-09-28,  ,,,  ,,,,,, 6144,,,, 2.50.30.6,
	
	  [Generic Thunk ODBC Driver Manager]
	  "Thunk1" = 1, odbc32gt.dll,,,, 1995-09-28,  ,,,  ,,,,,, 8704,,,, 2.50.30.6,
	  "Thunk2" = 1, odbc16gt.dll,,,, 1995-09-28,  ,,,  ,,,,,, 24272,,,,
	  2.50.30.6,
	
	  [Microsoft Dbase Driver (*.dbf)]
	  "Setup" = 1, oddbse32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 5120,,,, 3.0.21.11,
	  "IIsam" = 1, msxb3032.dll,,,, 1995-09-28,  ,,,  ,,,,,, 260368,,,,
	  3.0.0.2120,
	
	  "Changes" = 1, odbcjtnw.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 27119,,,,,
	  "Engine" = 1, msjt3032.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  977680,,,, 3.0.0.2120,
	  "Tools" = 1, odbctl32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 76288,,,, 3.0.33.11,
	  "vba232.dll" = 1, vba232.dll,,,, 1995-09-28,  ,,,  ,,,,,,1046800,,,,
	  2.0.0.5524,
	  "ven2232.olb" = 1, ven2232.olb,,,, 1995-09-28,  ,,,  ,,,,,,37376,,,,
	  2.0.0.5524,
	  "vbajet32" = 1, vbajet32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  6416,,,, 2.0.0.5524,
	  "msjter32" = 1, msjter32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  23824,,,, 3.0.0.2120,
	  "msjtint32" = 1, msjint32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  35088,,,, 3.0.0.2120,
	  "Help" = 1, odbcjet.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 143830,,,,,
	  "Driver" = 1, odbcjt32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 378888,,,,
	  3.0.21.11,
	
	  "WinSysNT01"=1,ctl3d32.dll,,,,1995-09-28,,,OLDER,,,,,,SHARED,27136
	  ,,,, 2.31.00.0
	  0,
	  "WinSysNT02"=1,msvcrt20.dll,,,,1995-09-
	  28,,,,,,,,,SHARED,253952,,,,02.11.00.0
	  0,
	
	  [Microsoft Excel Driver (*.xls)]
	  "Setup" = 1, odexl32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 5120,,,, 3.0.21.11,
	  "IIsam" = 1, msxl3032.dll,,,, 1995-09-28,  ,,,  ,,,,,, 200976,,,,
	  3.0.0.2125,
	
	  "Changes" = 1, odbcjtnw.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 27119,,,,,
	  "Engine" = 1, msjt3032.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  977680,,,, 3.0.0.2120,
	  "Tools" = 1, odbctl32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 76288,,,, 3.0.33.11,
	  "vba232.dll" = 1, vba232.dll,,,, 1995-09-28,  ,,,  ,,,,,,1046800,,,,
	  2.0.0.5524,
	  "ven2232.olb" = 1, ven2232.olb,,,, 1995-09-28,  ,,,  ,,,,,,37376,,,,
	  2.0.0.5524,
	  "vbajet32" = 1, vbajet32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  6416,,,, 2.0.0.5524,
	  "msjter32" = 1, msjter32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  23824,,,, 3.0.0.2120,
	  "msjtint32" = 1, msjint32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  35088,,,, 3.0.0.2120,
	  "Help" = 1, odbcjet.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 143830,,,,,
	  "Driver" = 1, odbcjt32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 378888,,,,
	  3.0.21.11,
	
	  "WinSysNT01"=1,ctl3d32.dll,,,,1995-09-28,,,OLDER,,,,,,SHARED,27136,,,,
	  2.31.00.0
	  0,
	  "WinSysNT02"=1,msvcrt20.dll,,,,1995-09-
	  28,,,,,,,,,SHARED,253952,,,,02.11.00.0
	  0,
	
	  [Microsoft FoxPro Driver (*.dbf)]
	  "Setup" = 1, odfox32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 5120,,,, 3.0.21.11,
	  "IIsam" = 1, msxb3032.dll,,,, 1995-09-28,  ,,,  ,,,,,, 260368,,,,
	  3.0.0.2120,
	
	  "Changes" = 2, odbcjtnw.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 27119,,,,,
	  "Engine" = 1, msjt3032.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  977680,,,, 3.0.0.2120,
	  "Tools" = 1, odbctl32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 76288,,,, 3.0.33.11,
	  "vba232.dll" = 1, vba232.dll,,,, 1995-09-28,  ,,,  ,,,,,,1046800,,,,
	  2.0.0.5524,
	  "ven2232.olb" = 1, ven2232.olb,,,, 1995-09-28,  ,,,  ,,,,,,37376,,,,
	  2.0.0.5524,
	  "vbajet32" = 1, vbajet32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  6416,,,, 2.0.0.5524,
	  "msjter32" = 1, msjter32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  23824,,,, 3.0.0.2120,
	  "msjtint32" = 1, msjint32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  35088,,,, 3.0.0.2120,
	  "Help" = 1, odbcjet.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 143830,,,,,
	  "Driver" = 1, odbcjt32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 378888,,,,
	  3.0.21.11,
	
	  "WinSysNT01"=1,ctl3d32.dll,,,,1995-09-28,,,OLDER,,,,,,SHARED,27136,,,,
	  2.31.00.0
	  0,
	  "WinSysNT02"=1,msvcrt20.dll,,,,1995-09-
	  28,,,,,,,,,SHARED,253952,,,,02.11.00.0
	  0,
	
	  [Microsoft Paradox Driver (*.db )]
	  "Setup" = 1, odpdx32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 5120,,,, 3.0.21.11,
	  "IIsam" = 1, mspx3032.dll,,,, 1995-09-28,  ,,,  ,,,,,, 226576,,,,
	  3.0.0.2120,
	
	  "Changes" = 1, odbcjtnw.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 27119,,,,,
	  "Engine" = 1, msjt3032.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  977680,,,, 3.0.0.2120,
	  "Tools" = 1, odbctl32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 76288,,,, 3.0.33.11,
	  "vba232.dll" = 1, vba232.dll,,,, 1995-09-28,  ,,,  ,,,,,,1046800,,,,
	  2.0.0.5524,
	  "ven2232.olb" = 1, ven2232.olb,,,, 1995-09-28,  ,,,  ,,,,,,37376,,,,
	  2.0.0.5524,
	  "vbajet32" = 1, vbajet32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  6416,,,, 2.0.0.5524,
	  "msjter32" = 1, msjter32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  23824,,,, 3.0.0.2120,
	  "msjtint32" = 1, msjint32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  35088,,,, 3.0.0.2120,
	  "Help" = 1, odbcjet.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 143830,,,,,
	  "Driver" = 1, odbcjt32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 378888,,,,
	  3.0.21.11,
	
	  "WinSysNT01"=1,ctl3d32.dll,,,,1995-09-28,,,OLDER,,,,,,SHARED,27136,,,,
	  2.31.00.0
	  0,
	  "WinSysNT02"=1,msvcrt20.dll,,,,1995-09-
	  28,,,,,,,,,SHARED,253952,,,,02.11.00.0
	  0,
	
	  [Microsoft Text Driver (*.txt; *.csv)]
	  "Setup" = 1, odtext32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 5120,,,, 3.0.21.11,
	  "IIsam" = 1, mstx3032.dll,,,, 1995-09-28,  ,,,  ,,,,,, 114448,,,,
	  3.0.0.2120,
	
	  "Changes" = 1, odbcjtnw.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 27119,,,,,
	  "Engine" = 1, msjt3032.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  977680,,,, 3.0.0.2120,
	  "Tools" = 1, odbctl32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 76288,,,, 3.0.33.11,
	  "vba232.dll" = 1, vba232.dll,,,, 1995-09-28,  ,,,  ,,,,,,1046800,,,,
	  2.0.0.5524,
	  "ven2232.olb" = 1, ven2232.olb,,,, 1995-09-28,  ,,,  ,,,,,,37376,,,,
	  2.0.0.5524,
	  "vbajet32" = 1, vbajet32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  6416,,,, 2.0.0.5524,
	  "msjter32" = 1, msjter32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  23824,,,, 3.0.0.2120,
	  "msjtint32" = 1, msjint32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  35088,,,, 3.0.0.2120,
	  "Help" = 1, odbcjet.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 143830,,,,,
	  "Driver" = 1, odbcjt32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 378888,,,,
	  3.0.21.11,
	
	  "WinSysNT01"=1,ctl3d32.dll,,,,1995-09-28,,,OLDER,,,,,,SHARED,27136,,,,
	   2.31.00.0
	  0,
	  "WinSysNT02"=1,msvcrt20.dll,,,,1995-09-28,,,,,,,,,SHARED,253952,,,,
	  02.11.00.00,
	
	  [Microsoft Access Driver (*.mdb)]
	  "Setup" = 1, odbcjt32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 378888,,,,
	  3.0.21.11,
	
	  "IISAM" = 1, msrd2x32.dll,,,,1995-09-28,  ,,OLDER,  ,,,,,, 245520,,,,
	  3.0.0.2120,
	  "Changes" = 1, odbcjtnw.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 27119,,,,,
	  "Engine" = 1, msjt3032.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  977680,,,, 3.0.0.2120,
	  "Tools" = 1, odbctl32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 76288,,,, 3.0.33.11,
	  "vba232.dll" = 1, vba232.dll,,,, 1995-09-28,  ,,,  ,,,,,,1046800,,,,
	  2.0.0.5524,
	  "ven2232.olb" = 1, ven2232.olb,,,, 1995-09-28,  ,,,  ,,,,,,37376,,,,
	  2.0.0.5524,
	  "vbajet32" = 1, vbajet32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  6416,,,, 2.0.0.5524,
	  "msjter32" = 1, msjter32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  23824,,,, 3.0.0.2120,
	  "msjtint32" = 1, msjint32.dll,,,, 1995-09-28,  ,,OLDER,  ,,,,,,
	  35088,,,, 3.0.0.2120,
	  "Help" = 1, odbcjet.hlp,,,, 1995-09-28,  ,,,  ,,,,,, 143830,,,,,
	  "Driver" = 1, odbcjt32.dll,,,, 1995-09-28,  ,,,  ,,,,,, 378888,,,,
	  3.0.21.11,
	
	  "WinSysNT01"=1,ctl3d32.dll,,,,1995-09-28,,,OLDER,,,,,,SHARED,27136,,,,
	  2.31.00.0
	  0,
	  "WinSysNT02"=1,msvcrt20.dll,,,,1995-09-
	  28,,,,,,,,,SHARED,253952,,,,02.11.00.0
	  0,
	
	  [SQL Server]
	  "Setup"=1,sqlsrv32.dll,,,,1995-09-28,,,,,,,,,,211968,,,,2.50.1.26,
	  "Driver"=1,sqlsrv32.dll,,,,1995-09-28,,,,,,,,,,211968,,,,2.50.1.26,
	  "WinSysNT01"=1,ctl3d32.dll,,,,1995-09-28,,,OLDER,,,,,,SHARED,27136,,,,
	  2.31.00.0
	  0,
	  "WinSysNT02"=1,msvcrt20.dll,,,,1995-09-
	  28,,,,,,,,,SHARED,253952,,,,02.11.00.0
	  0,
	  "Help"=1,drvssrvr.hlp,,,,1995-09-28,,,,,,,,,,87427,,,,,
	  "Network"=1,dbnmpntw.dll,,,,1995-09-28,,,,,,,,,SHARED,17408,,,,1995.8.18.0,
	
	  [ODBC Translators]
	  "MS Code Page Translator"=
	
	  [MS Code Page Translator]
	  "Setup"=1,mscpxl32.dll,,,,1995-09-28,,,,,,,,,,15360,,,,02.50.01.21,
	  "Translator"=1,mscpxl32.dll,,,,1995-09-28,,,,,,,,,,15360,,,,02.50.01.21,
	  "Code Page 850"=1,12520850.cpx,,,,1995-09-28,,,,,,,,,,2233,,,,02.50.01.21,
	  "Code Page 437"=1,12520437.cpx,,,,1995-09-28,,,,,,,,,,2151,,,,02.50.01.21,
	  "WinSysNT01"=1,ctl3d32.dll,,,,1995-09-28,,,OLDER,,,,,,SHARED,27136,,,,
	   2.31.00.0
	  0,
	  "WinSysNT02"=1,msvcrt20.dll,,,,1995-09-
	  28,,,,,,,,,SHARED,253952,,,,02.11.00.0
	  0,
	
	  [Win95 QFE Installer]
	  "WinSys9501" =
	  1,qfeupd.exe,,,,1995-09-28,,1033,OLDER,,,,,,,159232,,,,4.0.0.954,
	
	  [Microsoft Access Driver (*.mdb)-Keys]
	  APILevel=1
	  ConnectFunctions=YYN
	  DriverODBCVer=02.50
	  FileUsage=2
	  FileExtns=*.mdb
	  SQLLevel=0
	
	  [Microsoft Dbase Driver (*.dbf)-Keys]
	  APILevel=1
	  ConnectFunctions=YYN
	  DriverODBCVer=02.50
	  FileUsage=1
	  FileExtns=*.dbf,*.ndx,*.mdx
	  SQLLevel=0
	
	  [Microsoft Excel Driver (*.xls)-Keys]
	  APILevel=1
	  ConnectFunctions=YYN
	  DriverODBCVer=02.50
	  FileUsage=1
	  FileExtns=*.xls
	  SQLLevel=0
	
	  [Microsoft FoxPro Driver (*.dbf)-Keys]
	  APILevel=1
	  ConnectFunctions=YYN
	  DriverODBCVer=02.50
	  FileUsage=1
	  FileExtns=*.dbf,*.cdx,*.idx,*.ftp
	  SQLLevel=0
	
	  [Microsoft Paradox Driver (*.db )-Keys]
	  APILevel=1
	  ConnectFunctions=YYN
	  DriverODBCVer=02.50
	  FileUsage=1
	  FileExtns=*.db
	  SQLLevel=0
	
	  [Microsoft Text Driver (*.txt; *.csv)-Keys]
	  APILevel=1
	  ConnectFunctions=YYN
	  DriverODBCVer=02.50
	  FileUsage=1
	  FileExtns=*.,*.asc,*.csv,*.tab,*.txt,*.csv
	  SQLLevel=0
	
	  [SQL Server-Keys]
	  Driver=sqlsrv32.dll
	  Setup=sqlsrv32.dll
	  SQLLevel=1
	  FileUsage=0
	  DriverODBCVer=02.50
	  ConnectFunctions=YYY
	  APILevel=2
	
	  ------------------------End of ODBC.INF -----------------------------------
	
	COMMENTS:
	
	1. All the files mentioned in an ODBC.INF file should be copied into the
	  redistribution package. Most of the files mentioned in the above sample
	  ODBC.INF can be found in the following directory on your Access 7.0 CD:
	
	  \OS\SYSTEM
	
	  You can search for the remaining file names in ACC95.INF, which will give you
	  the directory containing the file you are looking for.
	
	2. If you do not want to write your own driver setup program, you can "borrow"
	  _BOOTSTP.EXE, _MSSETUP.EXE, ODBCST32.EXE, SETUP.EXE, and SSETUP.LST from
	  SQLSRV32.EX via the following services:
	
	   - Anonymous FTP via the Internet
	
	   - ftp ftp.microsoft.com
	
	   - Change to /bussys/sql_odbc/odbc-public directory
	
	   - Get SQLSRV32.EXE
	
	
	3. Please refer to the "ODBC 2.0 Programmer's Reference and SDK Guide" for
	  documentation on ODBC.INF files.
	
	Additional query words: 2.50 sql6 3.5x install kbhowto
	
	======================================================================
	Keywords          :  
	Technology        : kbAudDeveloper kbODBCSearch kbODBC300 kbODBC250
	Version           : WINDOWS:2.5,3.0
	
	=============================================================================
	

{% endraw %}
