---
layout: page
title: "Q316971: Pack Level Is Not Preserved When You Use the #import Directive"
permalink: /kb/316/Q316971/
---

## Q316971: Pack Level Is Not Preserved When You Use the #import Directive

{% raw %}

	Article: Q316971
	Product(s): Microsoft C Compiler
	Version(s): 6.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual C++, 32-bit Editions, version 6.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you use the pragma pack directive in an Interface Definition Language (IDL)
	file, or when you use the /Zp, /pack, or /align midl compiler switches to alter
	the structure member packing information stored in a type library, the pack
	level is not preserved when you use the #import directive to generate TLH and
	TLI files.
	
	RESOLUTION
	==========
	
	A supported fix is now available from Microsoft, but it is only intended to
	correct the problem described in this article and should be applied only to
	systems experiencing this specific problem. This fix may receive additional
	testing at a later time, to further ensure product quality. Therefore, if you
	are not severely affected by this problem, Microsoft recommends that you wait
	for the next service pack that contains this fix.
	
	To resolve this problem immediately, contact Microsoft Product Support Services
	to obtain the fix. For a complete list of Microsoft Product Support Services
	phone numbers and information about support costs, please go to the following
	address on the World Wide Web:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	NOTE: In special cases, charges that are normally incurred for support calls may
	be canceled, if a Microsoft Support Professional determines that a specific
	update will resolve your problem. Normal support costs will apply to additional
	support questions and issues that do not qualify for the specific update in
	question.
	
	The English-language version of this fix should have the following file
	attributes or later:
	
	+----------------------------------------------------------------------+
	| Date        | Time  | Version      | Size      | Name     | Platform | 
	+----------------------------------------------------------------------+
	| 04-Feb-2002 | 18:12 | 12.00.9496.0 | 1,220,659 | c1xx.dll | x86      | 
	+----------------------------------------------------------------------+
	
	
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft products that are
	listed at the beginning of this article.
	
	Additional query words:
	
	======================================================================
	Keywords          :  
	Technology        : kbVCsearch kbAudDeveloper kbVC600 kbVC32bitSearch
	Version           : :6.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
