---
layout: page
title: "Q161832: HOWTO: Export an Embedded .bmp Image into a File"
permalink: /kb/161/Q161832/
---

## Q161832: HOWTO: Export an Embedded .bmp Image into a File

{% raw %}

	Article: Q161832
	Product(s): Microsoft FoxPro
	Version(s): 
	Operating System(s): 
	Keyword(s): kbole kbnokeyword kbHWMAC kbvfp300 kbvfp500 kbvfp600
	Last Modified: 12-AUG-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 3.0, 3.0b, 5.0, 6.0 
	- Microsoft FoxPro for Macintosh, versions 2.5b, 2.5c, 2.6a 
	- Microsoft Visual FoxPro for Macintosh, version 3.0b 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	The command "APPEND GENERAL <General field name> FROM
	<filename>.bmp" imports a BMP image from a file and places it into a
	general field. But there is no reverse command like "Copy General To," which can
	export an embedded BMP image into a .bmp file. The following steps offer a
	workaround specially designed for embedded .bmp files only, other data formats
	can be easily exported if the storage structure of an OLE object is
	recognizable.
	
	MORE INFORMATION
	================
	
	The following steps and sample program can be used to save an embedded bitmap
	file to a physical file on disk:
	
	1. Go to the record number of a table that you would like the associated BMP
	  image exported to.
	
	2. Copy the general field (Name "Picture") of the record to a temporary file
	  (Name "Temp"). So the newly created Temp.dbf file contains one general field
	  "Picture" and one record only. The syntax for this follows:
	
	        COPY TO temp FIELDS picture NEXT 1
	
	3. Execute the following code, assuming the file name for the output BMP image
	  is "Test.Bmp":
	
	        *** Open two files, "temp.fpt" contains the physical BMP data.
	        *** and Create a file handle for the output file "Test.Bmp"
	        handlein=FOPEN("temp.fpt")
	        handleout=FCREATE("test.bmp")
	
	        *** To determine the length of the Input file "Temp.fpt"
	        gnEnd = FSEEK(handlein, 0, 2)
	        gnTop = FSEEK(handlein, 0)
	
	        *** Store the whole file into a string "str1"
	        str1 = FREAD(handlein, gnEnd)
	
	        ***  Offset 599 bytes from Str1 and save it to "str2"
	        str2=RIGHT(str1,LEN(str1)-599)
	
	        *** Write "Str2" into the BMP file "Test.BMP"
	        n=FWRITE(handleout,str2)
	
	        *** Close both opened files
	        =FCLOSE(handlein)
	        =FCLOSE(handleout)
	
	NOTE: If the BMP is placed into a General field by Edit/Paste from Clipboard, the
	data stored in general field is 599 bytes of header bytes plus the actual BMP
	data.
	
	If the .bmp file is embedded in a general field by "Insert Object" or "Append
	General," then FoxPro creates presentation data plus the actual .bmp file data
	into the general field, which may result in the size of the FTP file being twice
	as big as the original .bmp data and if this is the case, 599 may not be the
	correct offset.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbole kbnokeyword kbHWMAC kbvfp300 kbvfp500 kbvfp600 
	Technology        : kbHWMAC kbOSMAC kbVFPsearch kbAudDeveloper kbFoxproSearch kbFoxPro250bMac kbFoxPro260aMac kbFoxPro250cMac kbVFP300bMac kbVFP300 kbVFP300b kbVFP500 kbVFP600
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
