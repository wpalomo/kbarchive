---
layout: page
title: "Q147948: FIX: Errors Occur Using DAO CLongBinary Data from Database"
permalink: /kb/147/Q147948/
---

## Q147948: FIX: Errors Occur Using DAO CLongBinary Data from Database

{% raw %}

	Article: Q147948
	Product(s): Microsoft C Compiler
	Version(s): 4.00 4.10
	Operating System(s): 
	Keyword(s): kbDAOsearch kbDatabase kbMFC kbVC kbVC420fix
	Last Modified: 03-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- The Microsoft Foundation Classes (MFC), included with:
	   - Microsoft Visual C++, 32-bit Editions, versions 4.0, 4.1 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Running an application that uses the MFC DAO classes from Visual C++ version 4.0
	or 4.1 to retrieve CLongBinary data from a database may result in one or more of
	the following behaviors when performing a recordset move or requery:
	
	  Access violations
	
	-or-
	
	  "Out of memory" exceptions
	
	CAUSE
	=====
	
	There is a programming error in the MFC code that can lead to this behavior:
	GlobalReAlloc is incorrectly used. The return value of GlobalReAlloc is not
	used, so the global handle embedded in the CLongBinary recordset member variable
	becomes invalid if GlobalReAlloc moves the virtual memory block. For more
	information, refer to the MFC source code in Daodfx.cpp of the Mfc\Src
	directory, and look at the use of GlobalReAlloc in the AllocLongBinary()
	function.
	
	RESOLUTION
	==========
	
	There are two steps to resolving this problem. Both must be performed in order
	to reliably work around this issue.
	
	Step 1
	------
	
	Make certain you have caching disabled in all DFX_LongBinary function calls.
	Caching is disabled if there is no fifth parameter specified in the
	DFX_LongBinary function call or if the value of the fifth parameter is the
	symbol AFX_DISABLE_FIELD_CACHE or the equivalent numeric value 0. This only
	applies to DFX_LongBinary function calls; no other DFX function calls need to be
	modified.
	
	Enabling caching for long binary fields is generally unwise anyway, and can be
	fatal due to the GlobalReAlloc misuse. Additionally, it is not a simple matter
	to work around the GlobalReAlloc issue as it pertains to caching, so the best
	solution is to simply not use caching for long binary fields.
	
	Step 2
	------
	
	A new implementation of DFX_LongBinary that avoids the defect in the MFC code is
	available to assist you in correcting this problem. Please note that this code
	does not fix caching for long binary fields. As Step 1 indicates, caching of
	long binary fields must be disabled.
	
	The following file is available for download from the Microsoft Software
	Library:
	
	  Daoclb.exe
	  (http://support.microsoft.com/download/support/mslfiles/Daoclb.exe)
	
	For more information about downloading files from the Microsoft Software Library,
	please see the following article in the Microsoft Knowledge Base:
	
	  Q119591 How to Obtain Microsoft Support Files from Online Services
	
	
	STATUS
	======
	
	Microsoft has confirmed this to be a bug in the Microsoft products listed at the
	beginning of this article. This problem was corrected in Visual C++, 32-bit
	Edition, version 4.2.
	
	Additional query words: kbVC400bug 4.00 4.10 4.20 softlib software library
	
	======================================================================
	Keywords          : kbDAOsearch kbDatabase kbMFC kbVC kbVC420fix 
	Technology        : kbAudDeveloper kbMFC
	Version           : 4.00 4.10
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
