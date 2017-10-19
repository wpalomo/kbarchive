---
layout: page
title: "Q134704: HOWTO: Add Controls to a Form Generated by the Form Wizard"
permalink: kb/134/Q134704/
---

## Q134704: HOWTO: Add Controls to a Form Generated by the Form Wizard

	Article: Q134704
	Product(s): Microsoft FoxPro
	Version(s): 
	Operating System(s): 
	Keyword(s): kbwizard kbDesigner
	Last Modified: 20-AUG-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 3.0, 5.0, 6.0 
	- Microsoft Visual FoxPro for Macintosh, version 3.0b 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	You may sometimes need to add a control to a form generated by the Form Wizard.
	No additional coding is necessary if you're adding a text box. However, if
	you're adding another type of control, such as a combo box or a list box,
	additional coding is required.
	
	MORE INFORMATION
	================
	
	The Form Wizard uses the Wizstyle visual class library. Code for the navigation
	buttons is stored in this library. When a text box is added to the form, it
	functions exactly like the text boxes added by the wizard. It is enabled and
	disabled by the edit/revert and add/save buttons. However, if another control,
	such as a combo or list box, is added, it's not enabled or disabled by these
	buttons, so it remains enabled all the time.
	
	Listed below are two different methods to add this functionality. The first one
	works on combo and list boxes. The second method, which is not supported by
	Microsoft Technical Support applies to combo boxes only.
	
	Method 1 - List and Combo Box
	-----------------------------
	
	The list and combo box can be enabled and disabled in sync with the text boxes by
	setting the enabled property of list or combo box to false and adding the
	following code to the edit/revert and add/save buttons, assuming combo1 is the
	name of the added combo box and text1 is the name of an existing text box on the
	form:
	
	     txtbtns.cmdEdit::click     && cmdEdit will be cmdAdd for the Add button
	     thisform.combo1.enabled= thisform.text1.enabled   && See following NOTE
	     thisform.refresh
	
	NOTE: This code causes the combo box to become enabled and disabled in sync with
	the text box. The first line of code with the scope resolution operator ensures
	that the click method of the Edit button stored in the WIZSTYLE.VCX is
	executed.
	
	Method 2 - Combo Box
	--------------------
	
	NOTE: Modifications to WIZSTYLE.VCX are not supported by Microsoft FoxPro
	Technical Support. This information is provided for informational reasons only.
	
	Modify the SetAllProp method of the TxtBtns class in WIZSTYLE.VCX as follows:
	
	1. Change the line
	
	        CASE ATC(m.oControlParent.Controls[m.i].BaseClass,
	        "Checkbox,TextBox,OleBoun Control") # 0
	
	  to
	
	        CASE ATC(m.oControlParent.Controls[m.i].BaseClass,
	        "CheckBox,TextBox,OleBoun Control,ComboBox") # 0
	
	  NOTE: The CASE statements above should actually be continuous lines. They were
	  broken into two lines here for display purposes only.
	
	This will allow combo boxes added to any Form Wizard-generated forms to be
	enabled and disabled along with other objects, so long as the enabled property
	is initially set to .F. for each new control.
	
	Additional query words: combobox listbox Form Wizard
	
	======================================================================
	Keywords          : kbwizard kbDesigner 
	Technology        : kbHWMAC kbOSMAC kbVFPsearch kbAudDeveloper kbVFP300bMac kbVFP300 kbVFP500 kbVFP600
	Issue type        : kbhowto
	
	=============================================================================
	