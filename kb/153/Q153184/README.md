---
layout: page
title: "Q153184: Bunyan and Koi: 32-bit Setup Doesn't Remove 16-bit Version"
permalink: /kb/153/Q153184/
---

## Q153184: Bunyan and Koi: 32-bit Setup Doesn't Remove 16-bit Version

{% raw %}

	Article: Q153184
	Product(s): Microsoft Home Kids Products
	Version(s): 1.0
	Operating System(s): 
	Keyword(s): kbsetup
	Last Modified: 08-NOV-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft P.J.'s Reading Adventures: Microsoft Koi and the Kola Nuts, version 1.0 
	- Microsoft P.J.'s Reading Adventures: Microsoft Paul Bunyan, version 1.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	If you have previously installed one of the Kids programs listed at the top of
	this article on a 16-bit operating system (for example, Microsoft Windows 3.1 or
	Windows for Workgroups 3.11), and then you install the same program under a
	32-bit operating system (for example, Windows 95 or Windows NT) on the same
	computer, the previous 16-bit version of the program is not removed.
	
	For example, if you were running the Kids program under Windows 3.1 and then
	upgraded to Windows 95 and installed the 32-bit version of the Kids program, the
	32-bit AND the 16-bit versions of the Kids program are installed on your hard
	drive.
	
	If you have both the 16-bit and 32-bit versions of the programs installed on your
	computer, you will have a set of the following folders on your hard drive, where
	C: is the drive on which you installed the program(s):
	
	   Paul Bunyan:
	        C:\Mskids\Bunyan (16 bit)
	           - and -
	        C:\Program Files\Microsoft Kids\Bunyan (32 bit)
	
	   Koi and the Kola Nuts:
	        C:\Mskids\Koi (16 bit)
	           - and -
	        C:\Program Files\Microsoft Kids\Koi (32 bit)
	
	RESOLUTION
	==========
	
	If you only want to use the program under the 32-bit operating system, manually
	remove the files installed by the 16-bit version. The location of these files is
	listed below, where C: is the drive on which you installed the program(s):
	
	            Paul Bunyan:   C:\Mskids\Bunyan
	
	  Koi and the Kola Nuts:   C:\Mskids\Koi
	
	How to Remove the Files
	-----------------------
	
	To remove the files, delete the program folder shown above.
	
	NOTE: The converse is true if you first installed the 32-bit version of the
	program and then installed the program under a 16-bit operating system. Please
	see the More Information section of this article for the list of files installed
	by the 32-bit version of the program.
	
	Windows 95:
	
	
	To remove the 16-bit version of the program, follow the instructions outlined
	below.
	
	1. Click the Start button, point to Programs, and then click Windows Explorer.
	
	2. Open your hard drive folder by double-clicking its folder icon.
	
	3. Open the Mskids folder by double-clicking its folder icon.
	
	4. Single-click the program folder to select it (for example, Bunyan or Koi).
	
	5. On the File menu, click Delete.
	
	6. Confirm deletion of the following files in the appropriate folder, where C:
	  is the drive on which you installed the program(s):
	
	     C:\Mskids\Bunyan          C:\Mskids\Koi
	       Bunyan.exe                Koi.exe
	       Bunyan.mdf                Koi.mdf
	       Bunyan.tdf                Koi.tdf
	       Bunyan.ini                Koi.ini
	       Bun_w31.hlp               Koi_w31.hlp
	
	After you complete the steps listed above, the 16-bit version of the
	corresponding program should be removed from your hard drive.
	
	Windows NT 3.51:
	
	To remove the 16-bit version of the program, follow the instructions outlined
	below:
	
	1. Run File Manager.
	
	2. Open your hard drive folder by double-clicking its folder icon.
	
	3. Open the Mskids folder by double-clicking its folder icon.
	
	4. Single-click the program folder (for example, Bunyan or Koi) to select it.
	
	5. On the File menu, click Delete.
	
	6. Confirm deletion of the following files in the appropriate folder, where C:
	  is the drive on which you installed the program(s):
	
	     Bunyan (C:\Mskids\Bunyan)          Koi (C:\Mskids\Koi)
	     -------------------------          -------------------
	
	     Bunyan.exe                         Koi.exe
	     Bunyan.mdf                         Koi.mdf
	     Bunyan.tdf                         Koi.tdf
	     Bunyan.ini                         Koi.ini
	     Bun_w31.hlp                        Koi_w31.hlp
	
	MORE INFORMATION
	================
	
	The Setup program for the 32-bit version of the program listed above does not
	check to see whether the 16-bit version of the program is installed. Because
	some computers may run both 16-bit and 32-bit operating systems, both versions
	of the program may be necessary.
	
	The 32-bit version of the program installs the following files onto your hard
	drive. To remove the 32-bit version of the program, run Add/Remove Programs from
	Control Panel. This should remove all files associated with the 32-bit program.
	
	If, for some reason, the Setup program fails to remove the program files, delete
	the program files manually.
	
	The program folders of the 32-bit version of the program are located in the
	following directory, where C: is the drive on which you installed the
	program(s):
	
	  Paul Bunyan
	  ---------------------------------------
	   C:\Program Files\Microsoft Kids\Bunyan
	       Bun_w95.cnt
	       Bun_w95.fts
	       Bun_w95.gid
	       Bun_w95.hlp
	       Bunyan.exe
	       \System <directory>
	           Bunyan.ini
	           Bunyan.mdf
	           Bunyan.tdf
	           Mscreate.dir <hidden>
	
	  Koi and the Kola Nuts
	  ------------------------------------
	   C:\Program Files\Microsoft Kids\Koi
	       Koi.exe
	       Koi_w95.cnt
	       Koi_w95.fts
	       Koi_w95.gid
	       Koi_w95.hlp
	       Mscreate.dir <hidden>
	       \System <directory>
	          Koi.ini
	          Koi.mdf
	          Koi.tdf
	          Mscreate.dir <hidden>
	
	Different versions of the program are necessary because each version (16 and 32
	bit) makes calls to different Dynamic Link Libraries (DLLs) when performing
	various operations. These DLLs, which are stored commands, are also either 16 or
	32 bit.
	
	
	Additional query words: kids mskids kbmm multimedia multi-media multi media 1.00 leo pj bunny bunion coy koy colanuts cola nuts Bunyon replace over
	
	======================================================================
	Keywords          : kbsetup 
	Technology        : _IKkbbogus kbKidsSearch kbPJPaulBunyan kbPJKoi
	Version           : :1.0
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
