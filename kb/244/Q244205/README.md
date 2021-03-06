---
layout: page
title: "Q244205: WD97: FileName Code Does Not Resolve Mapped NetWare Server Path"
permalink: /kb/244/Q244205/
---

## Q244205: WD97: FileName Code Does Not Resolve Mapped NetWare Server Path

{% raw %}

	Article: Q244205
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When multiple drives are mapped to the same NetWare server, Word may not resolve
	the path correctly when you use the FILENAME /p field. Instead of the correct
	drive, Word may display the path relative to another mapped drive to the NetWare
	server.
	
	Example:
	
	Result: The field resolves to "f:\user\'docname'"
	Expect: The field should resolve to "g:\'docname'"
	
	This occurs when the following conditions are both true:
	
	- There are multiple mapped connections to the same NetWare server but at
	  different levels.
	
	  Example:
	  f: is mapped to \\"netware server"\public
	  g: is mapped to \\"netware server"\public\user
	
	- DONTUSEUNC has been set in the registry.
	
	
	RESOLUTION
	==========
	
	To resolve the problem described in this article, obtain and install the latest
	Microsoft Word 97 update from the following Microsoft Web site:
	
	  http://office.microsoft.com/downloads/9798/Wd97mcrs.aspx
	
	IMPORTANT NOTE: Microsoft Word 97 post-service release fixes are cumulative. The
	latest update contains all of the fixes since Service Release 2. If you install
	the latest update for Word 97, you do not need to install any other updates
	after Service Release 2.
	
	For additional information about the fixes included in the latest update for Word
	97, click the article number below to view the article in the Microsoft
	Knowledge Base:
	
	  Q265374 WD97: Post Service Release Fixes for Word 97
	
	
	
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft products that are
	listed at the beginning of this article.
	
	Additional query words: qfe
	
	======================================================================
	Keywords          :  
	Technology        : kbWordSearch kbWord97 kbWord97Search kbZNotKeyword2
	Version           : WINDOWS:97
	Hardware          : ALPHA x86
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
