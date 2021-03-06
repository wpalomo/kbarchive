---
layout: page
title: "Q258241: BUG: SYS(1271) Used in Property of a Class Crashes Visual FoxPro"
permalink: /kb/258/Q258241/
---

## Q258241: BUG: SYS(1271) Used in Property of a Class Crashes Visual FoxPro

{% raw %}

	Article: Q258241
	Product(s): Microsoft FoxPro
	Version(s): WINDOWS:5.0,5.0a,6.0
	Operating System(s): 
	Keyword(s): kbvfp500 kbvfp500a kbvfp600 kbvfp600bug kbXBase kbGrpDSFox kbDSupport kbCodeSnippet
	Last Modified: 14-APR-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 5.0, 5.0a, 6.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Using the SYS(1271) function in the property of a class causes Visual FoxPro to
	crash with the following error message:
	
	  The instruction at "memory address" referenced memory at "memory address".
	  The memory could not be "written".
	
	CAUSE
	=====
	
	The SYS(1271) function requires that a parameter be passed that references the
	form of which a specified instantiated object is a member. If the parameter
	syntax, when used outside the SYS(1271) function as follows:
	
	  <ClassProperty> = ThisForm
	
	produces the following error:
	
	  Data type is invalid for this property.
	
	then use of the preceding syntax as a parameter within the SYS(1271) function can
	cause Visual FoxPro to crash.
	
	RESOLUTION
	==========
	
	The purpose of the SYS(1271) function is to return the name of the .scx file in
	which the specified instantiated object is stored. Due to the order of object
	instantiation, the SYS(1271) function is unable to return its expected value
	until the form itself is fully instantiated. Therefore, using the SYS(1271)
	function directly within a property, whether that of an object or of the form
	itself, does not produce its intended result.
	
	The proper use of the SYS(1271) function is to call it from within a method. If
	you want to store the name of the instantiated object's host .scx file to a
	property, that can be done from the Init Event of the class as demonstrated in
	the following example:
	
	1. Create a new class based on Custom, name it "MyCustom" (without the quotation
	  marks), and then store it in Class Library MyClass.
	
	2. Add a new property to the MyCustom class called "MyProperty" (without the
	  quotation marks).
	
	3. Add the following code to the Init Event of the MyCustom class:
	
	  This.MyProperty = SYS(1271,ThisForm)
	
	4. Close and save the MyCustom class.
	
	5. Create a new form.
	
	6. Add a command button to the form.
	
	7. From the View Classes interface of the Form Controls toolbar, add the MyClass
	  Visual Class Library.
	
	8. Add the MyCustom class to the form.
	
	9. Add the following code to the click event of the command button:
	
	  WAIT WINDOW ThisForm.MyCustom1.MyProperty
	
	10. Run the form, saving it as whatever you wish.
	
	11. Click the Command1 command button, and note that it produces a WAIT WINDOW
	  message that contains the name and full path of the form.
	
	STATUS
	======
	
	Microsoft has confirmed that this is a bug in the Microsoft products that are
	listed at the beginning of this article.
	
	
	MORE INFORMATION
	================
	
	Steps to Reproduce Behavior
	---------------------------
	
	In order to avoid losing unsaved work or data, take the the following steps in a
	new session of Microsoft Visual FoxPro:
	
	1. Create a new class based on any class.
	
	2. Add a new property to the class.
	
	3. In the newly added property, add the following code:
	
	  =SYS(1271,ThisForm)
	
	This produces the following error message:
	
	  The instruction at "memory address" referenced memory at "memory address".
	  The memory could not be "written".
	
	Additional query words:
	
	======================================================================
	Keywords          : kbvfp500 kbvfp500a kbvfp600 kbvfp600bug kbXBase kbGrpDSFox kbDSupport kbCodeSnippet 
	Technology        : kbVFPsearch kbAudDeveloper kbVFP500 kbVFP600 kbVFP500a
	Version           : WINDOWS:5.0,5.0a,6.0
	Issue type        : kbbug
	Solution Type     : kbpending
	
	=============================================================================
	

{% endraw %}
