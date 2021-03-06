---
layout: page
title: "Q256066: HOWTO: Use the StatusBar ActiveX Control in Visual FoxPro"
permalink: /kb/256/Q256066/
---

## Q256066: HOWTO: Use the StatusBar ActiveX Control in Visual FoxPro

{% raw %}

	Article: Q256066
	Product(s): Microsoft FoxPro
	Version(s): WINDOWS:5.0,5.0a,6.0
	Operating System(s): 
	Keyword(s): kbActiveX kbCtrl kbvfp500 kbvfp500a kbvfp600 kbGrpDSFox kbDSupport
	Last Modified: 14-MAR-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 5.0, 5.0a, 6.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article shows how to programmatically access the most common properties and
	methods of the StatusBar ActiveX control using Visual FoxPro.
	
	MORE INFORMATION
	================
	
	A StatusBar control provides a window, usually at the bottom of a parent form,
	through which an application can display various kinds of status data. The
	StatusBar control can be divided up into a maximum of sixteen Panel objects that
	are contained in a Panels collection.
	Running the following code illustrates some of the most common usages for the
	StatusBar ActiveX control. To use this code, copy it into a new program in
	Visual FoxPro and run it.
	
	  Public frmOLETest
	  Local lnPanels
	
	  frmOLETest = CREATEOBJECT('Form') && Create Instance of the Form
	
	  With frmOLETest 	&& Set Default Values for the Form
	  	.CAPTION = 'StatusBar Control Test Form'
	  	.WIDTH = 800
	  	.HEIGHT = 200
	  	.VISIBLE = .T.
	  	.ADDOBJECT('OCXTest','StatusBarControl', ;
	  		'MSComctlLib.sBarCtrl.2') && Create Instance of the StatusBar Control
	  Endwith
	
	  With frmOLETest.OCXTest 	&& Set Values and options of the StatusBar Control
	  *!* Default Panel
	  	.Panels(1).TEXT = "Sample Text" 	&& Default Text For Panel 1
	  	.Panels(1).TOOLTIPTEXT = "Panel 1"
	  	.Panels(1).STYLE = 0
	
	  *!* Additional Panels
	  	For lnPanels = 2 TO 8
	                .Panels.ADD()							&& Adds Panels 2 to 8
	                .Panels(lnPanels).STYLE = lnPanels - 1	&& Show each Panel Style
	  *!* Style 0 = Text or Bitmap
	  *!* 	 1 = Caps Lock
	  *!*	 2 = Num Lock
	  *!*	 3 = Insert
	  *!*	 4 = Scroll Lock
	  *!*	 5 = System Time
	  *!*	 6 = System Date
	  *!*	 7 = Kana entry (Japanese characters)
	                .Panels(lnPanels).TOOLTIPTEXT = "Panel " + ;
	  			ALLTRIM(STR(lnPanels))
	  	Endfor
	  Endwith
	
	  Define CLASS StatusBarControl AS OLECONTROL
	  	Visible = .T.
	  	Height = 25
	  Enddefine
	
	REFERENCES
	==========
	
	For additional information, visit the MSDN Web site and search under: FoxPro
	StatusBar Control at: http://msdn.microsoft.com Microsoft Developer Network
	
	The "StatusBar Control" section in CMCTL198.CHM. This Help file is usually
	located in the MSDN directory under a Visual Studio 98 installation.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbActiveX kbCtrl kbvfp500 kbvfp500a kbvfp600 kbGrpDSFox kbDSupport 
	Technology        : kbVFPsearch kbAudDeveloper kbVFP500 kbVFP600 kbVFP500a
	Version           : WINDOWS:5.0,5.0a,6.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
