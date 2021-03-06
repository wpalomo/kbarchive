---
layout: page
title: "Q142959: FIX: YMD Date Format Causes Improper History Selection"
permalink: /kb/142/Q142959/
---

## Q142959: FIX: YMD Date Format Causes Improper History Selection

{% raw %}

	Article: Q142959
	Product(s): Microsoft SourceSafe
	Version(s): 4.0,5.0
	Operating System(s): 
	Keyword(s): kbYear2000 kbSSafe400bug kbSSafe500fix
	Last Modified: 01-OCT-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual SourceSafe, 16-bit, for Windows, versions 4.0, 5.0 
	- Microsoft Visual SourceSafe, 32-bit, for Windows 4.0 
	- Microsoft Visual SourceSafe for Windows, version 5.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Dates entered in the History Options dialog using a range of 2000-2039 are
	interpreted with the same day and month in the range of 1900-1939.
	
	RESOLUTION
	==========
	
	To correct the problem, install the VSS 5.0 Y2K Update from here:
	
	  http://msdn.microsoft.com/downloads/default.asp?url=/downloads/sample.asp?url=/MSDN-FILES/027/000/243/msdncompositedoc.xml
	
	STATUS
	======
	
	This bug has been fixed in the Visual SourceSafe 5.0 Year 2000 update.
	
	MORE INFORMATION
	================
	
	Steps to Reproduce Problem
	--------------------------
	
	1. From the Window system Control Panel, set the short date format to
	  "YY/MM/DD."
	
	
	1. From the Visual SourceSafe Explorer, select a project and either choose Show
	  History on the Tools menu, or right-click a project and select Show History.
	
	2. From the Project History Options dialog box, enter a range of dates in the
	  YY/MM/DD format that span into or are beyond the year 2000. No items will
	  appear in the list. Note that if no dates are entered, the entire history
	  list appears.
	
	
	For more information about how Microsoft products are affected by year 2000 (Y2K)
	issues, please see the following Microsoft World Wide Web site:
	
	  http://www.microsoft.com/technet/year2k/product/product.asp
	
	Additional query words:
	
	======================================================================
	Keywords          : kbYear2000 kbSSafe400bug kbSSafe500fix 
	Technology        : kbSSafeSearch kbAudDeveloper kbSSafe400 kbSSafe500 kbSSafe16bitSearch kbSSafe32bitSearch
	Version           : :4.0,5.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
