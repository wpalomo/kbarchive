---
layout: page
title: "Q101458: SMTP: Mail SMTPPUT.EXE Version 3.04.1 Update"
permalink: /kb/101/Q101458/
---

## Q101458: SMTP: Mail SMTPPUT.EXE Version 3.04.1 Update

{% raw %}

	Article: Q101458
	Product(s): Microsoft Mail For PC Networks
	Version(s): MS-DOS:3.0
	Operating System(s): 
	Keyword(s): kbgraphxlinkcritical
	Last Modified: 21-DEC-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Mail Gateway to SMTP, version 3.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	Microsoft provides a replacement for the SMTPPUT.EXE file that is included with
	version 3.0 of Microsoft Mail Gateway to SMTP. It corrects a condition wherein
	duplicate message or nondelivery reports appear when backboning Microsoft Mail
	postoffices by means of SMTP.
	
	For complete information about obtaining and installing the SMTPPUT.EXE file, see
	the following sections:
	
	- To download the updated file
	
	- To update your SMTPPUT.EXE file
	
	MORE INFORMATION
	================
	
	This update contains SMTPPUT.EXE, a replacement file for the SMTPPUT.EXE file
	that is included with version 3.0 of Microsoft Mail Gateway to SMTP. This
	replacement file corrects a problem where duplicate message or nondelivery
	reports may appear when backboning Microsoft Mail postoffices via SMTP.
	
	To download the updated file
	----------------------------
	
	The following file is available for download from the Microsoft Download Center:
	
	  DownloadDownload Putupd.exe now
	  (http://download.microsoft.com/download/pcmail/Update/17/WIN/EN-US/Putupd.exe)
	
	For additional information about how to download Microsoft Support files, click
	the article number below to view the article in the Microsoft Knowledge Base:
	
	  Q119591 How to Obtain Microsoft Support Files from Online Services
	
	Microsoft used the most current virus detection software available on the date of
	posting to scan this file for viruses. Once posted, the file is housed on secure
	servers that prevent any unauthorized changes to the file.
	
	After you download PUTUPD.EXE to a clean directory, run it (by typing "putupd"
	(without the quotation marks) at the MS-DOS prompt) to extract the contents of
	the file. You should receive the following files:
	
	  SMTPPUT.EXE (66,751 bytes, dated 04-19-93, 11:26 A.M.)
	  README.TXT
	
	To update your SMTPPUT.EXE file
	-------------------------------
	
	At the MS-DOS command prompt, type the following and press ENTER
	
	  " copy <path>:\smtpput.exe <destination> " (without the quotation
	  marks)
	
	where <path> is the drive and directory where you ran the self- extracting
	PUTUPD.EXE file and <destination> is the drive and directory where your
	SMTPPUT.EXE file currently resides. For example, if you ran the self-extracting
	file from the TEST directory on drive D, and your SMTPPUT.EXE file is located in
	the MAILEXE directory on drive C, type the following command:
	
	  " copy d:\test\smtpput.exe c:\mailexe " (without the quotation marks)
	
	NOTE: SMTPPUT.EXE is typically installed on the postoffice server in the MAILEXE
	directory as well as on the computer running the SMTP gateway software. Make
	sure you update all copies of SMPTPUT.EXE.
	
	Additional query words: 3.00 wga
	
	======================================================================
	Keywords          : kbgraphxlinkcritical 
	Technology        : kbMailSearch kbMailGateSearch kbZNotKeyword3 kbMailGateSMTP300
	Version           : MS-DOS:3.0
	
	=============================================================================
	

{% endraw %}
