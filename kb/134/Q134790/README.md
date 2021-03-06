---
layout: page
title: "Q134790: How to Add Code to Wizard-Generated Command Buttons"
permalink: /kb/134/Q134790/
---

## Q134790: How to Add Code to Wizard-Generated Command Buttons

{% raw %}

	Article: Q134790
	Product(s): Microsoft FoxPro
	Version(s): 3.00    | 3.00b
	Operating System(s): 
	Keyword(s): 
	Last Modified: 26-AUG-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, version 3.0 
	- Microsoft Visual FoxPro for Macintosh, version 3.0b 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	You can add code to command buttons created by the Form Wizard and still have
	the command buttons function properly.
	
	MORE INFORMATION
	================
	
	The command buttons created by the Form Wizard are based on classes defined in
	the Vfp\Wizards\Wizstyle.vcx visual class library.
	
	All of the command buttons are contained in one of three classes, depending on
	which style of buttons was used:
	
	class Name      Button Style
	--------------------------------
	txtbtns         Horizontal; text
	verttxtbtns     Vertical; text
	picbtns         Horizontal; picture
	
	Each button is assigned an individual name, following recommended Visual FoxPro
	naming conventions:
	
	  cmdPrev
	  cmdNext
	  cmdTop
	  cmdEnd
	  cmdFind
	  cmdPrint
	  cmdAdd
	  cmdEdit
	  cmdDelete
	  cmdExit
	
	The code for each button is contained in the class definition, not in each button
	on the form. If method code is entered in an event, such as the click event,
	which also has code defined in the parent class, the new code will override the
	parent class code. The parent class code must be explicitly called within the
	method.
	
	You can add code to the buttons in a generated screen, as long as the code in the
	parent class is called using the scope resolution operator, as in this example:
	
	     txtbtns.cmdAdd::Click
	     WAIT WINDOW "I just called the parent click code"
	
	If you want the additional code to be processed prior to the default button
	behavior, place it before the line that calls the parent method. If you want the
	additional to be processed after the default button behavior, place it after the
	line that calls the parent method.
	
	Additional query words: VFoxMac VFoxWin
	
	======================================================================
	Keywords          :  
	Technology        : kbHWMAC kbOSMAC kbVFPsearch kbAudDeveloper kbVFP300bMac kbVFP300
	Version           : 3.00    | 3.00b
	
	=============================================================================
	

{% endraw %}
