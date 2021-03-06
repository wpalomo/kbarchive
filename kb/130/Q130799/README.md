---
layout: page
title: "Q130799: PRB: Dragmode=1 Stops Click and Other Mouse Events from Firing"
permalink: /kb/130/Q130799/
---

## Q130799: PRB: Dragmode=1 Stops Click and Other Mouse Events from Firing

{% raw %}

	Article: Q130799
	Product(s): Microsoft FoxPro
	Version(s): WINDOWS:3.0
	Operating System(s): 
	Keyword(s): kbcode
	Last Modified: 11-FEB-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, version 3.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	If the DRAGMODE property is set to 1, the click event or any of the other mouse
	events do not execute for that object.
	
	CAUSE
	=====
	
	When the DRAGMODE property is set to 1 for automatic mode, none of the mouse
	events fire. The mouse events affected are:
	
	     CLICK()
	     MOUSEMOVE()
	     MOUSEDOWN()
	     MOUSEUP()
	
	The DRAGMODE property allows the control to be dragged when the primary mouse
	button is pressed and held down, so all other mouse events for this control are
	disabled. This is by design.
	
	WORKAROUND
	==========
	
	To have more control over dragging, set the DRAGMODE property to zero for manual
	mode. Then in the MOUSEDOWN() event, call the CLICK() event and then call the
	DRAG() event passing a number one as a parameter to start the dragging
	operation.
	
	Step-by-Step Example
	--------------------
	
	1. Create a form, and place a check box and a text box on it.
	
	2. Add the following code to the MOUSEDOWN() event of the check box:
	
	     THIS.CLICK()
	     THIS.DRAG(1)
	
	3. Add the following code to the CLICK() event of the check box:
	
	     THIS.PARENT.TEXT1.VALUE="Click"
	
	4. Add the following code to the DRAGDROP() event of the text box:
	
	     THIS.VALUE=OSOURCE.CAPTION
	
	5. Run the form.
	
	Click the check box. In response, the text box should say "Click." Drag the check
	box on top of the text box. In response, the text box should say "Check1."
	
	STATUS
	======
	
	This behavior is by design.
	
	Additional query words: VFoxWin
	
	======================================================================
	Keywords          : kbcode 
	Technology        : kbVFPsearch kbAudDeveloper kbVFP300
	Version           : WINDOWS:3.0
	
	=============================================================================
	

{% endraw %}
