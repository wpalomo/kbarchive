---
layout: page
title: "Q66129: Use of the shflag with sopen()"
permalink: /kb/066/Q66129/
---

## Q66129: Use of the shflag with sopen()

{% raw %}

	Article: Q66129
	Product(s): See article
	Version(s): 6.00
	Operating System(s): MS-DOS
	Keyword(s): ENDUSER | S_QUICKC | mspl13_c
	Last Modified: 17-OCT-1990
	
	The shflag used with the sopen() function can be one of five manifest
	constants (defined in FCNTL.H). The following lists the constants and
	their uses:
	
	SH_COMPAT   Sets compatibility mode. Other programs can open the file
	            and perform read or write operations as long as no process
	            specifies any sharing mode other than compatibility mode.
	            This is the sharing mode used in the open function under
	            MS-DOS. This sharing code is not available under OS/2.
	
	SH_DENYRW   Deny all. Other programs cannot open the file.
	
	SH_DENYWR   Deny write. Other programs cannot open the file in
	            compatibility mode or with write access.
	
	SH_DENYRD   Deny read. Other program cannot open the file in
	            compatibility mode or with read access.
	
	SH_DENYNO   Deny none. Other programs can open the file and perform
	            both read and write operations but cannot open the file in
	            compatibility mode. This is the sharing mode used in the
	            open function under OS/2.
	
	In a network environment under MS-DOS, it is recommended that the
	SH_COMPAT mode be used if the file is to be shared for reading and
	writing. For further information about file modes, see the "MS-DOS
	Encyclopedia," Article 7, "File and Record Management".

{% endraw %}
