---
layout: page
title: "Q112588: Setting Smart Modems to Auto-Answer in Terminal"
permalink: /kb/112/Q112588/
---

## Q112588: Setting Smart Modems to Auto-Answer in Terminal

{% raw %}

	Article: Q112588
	Product(s): Microsoft Windows 95.x Retail Product
	Version(s): WINDOWS:3.0,3.0a,3.1,3.11
	Operating System(s): 
	Keyword(s): 
	Last Modified: 05-OCT-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows versions 3.0, 3.0a, 3.1, 3.11 
	- Microsoft Windows for Workgroups versions 3.1, 3.11 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	You may want to use the Terminal program included with Microsoft Windows
	versions 3.0 and 3.1 and Windows for Workgroups versions 3.1 and 3.11 to
	communicate between two stand-alone MS-DOS-based machines.
	
	To do this, you must set your modem for auto-answer, which usually requires that
	your modem have auto-answering capability. If it does not have this capability,
	you must manually enter the string "ATA" (without the quotation marks) when you
	receive a call before the modem can answer.
	
	Terminal version 3.0 in Windows 3.0 has the ability to answer the phone
	automatically by setting the Answer string in the Modem Setting dialog box.
	Modem Settings can be selected from the Settings menu.
	
	The Answer edit field has been removed from the Modem Commands dialog box in
	Terminal 3.1, which is included with Windows 3.1 and Windows for Workgroups 3.1
	and 3.11. However, the functionality has not been removed.
	
	
	MORE INFORMATION
	================
	
	Windows 3.1 and Windows for Workgroups 3.1, 3.11
	------------------------------------------------
	
	To configure Terminal to answer with Windows 3.1 or Windows for Workgroups 3.1
	and 3.11, use one of the following methods:
	
	Method 1:
	
	1. Start Terminal.
	
	2. At the prompt, type the following, which is considered the "answer command":
	
	  ATQ1E0S0=1
	
	  -or-
	
	  ATS0=1
	
	  NOTE: The "answer command" may vary depending on the command set that your
	  modem uses. Check the documentation included with your modem for information
	  on the correct "answer command." Note that both commands above end with a
	  zero (0), not the letter "o."
	
	With this method, you must manually enter the "answer command" every time you
	start Terminal and want the modem to answer automatically.
	
	Method 2:
	
	To save the above manual step, set the "answer command" in the Originate modem
	command control box.
	
	1. Choose Modem Commands from the Settings menu.
	
	2. Type the answer command ; for example, "ATQ1E0S0=1" (without the quotation
	  marks) in the Originate control box.
	
	3. Save this setting as a specific .TRM file, for example, ANSWER.TRM.
	
	4. Choose Dial from the Phone menu, then choose OK. You do not have to actually
	  enter a number to be dialed. The Dial dialog box will disappear, but the
	  Originate string is changed.
	
	Originate is a set of commands sent to the modem when Terminal is started. This
	is why you can use the Originate setting to answer an incoming call.
	
	When you start Terminal under Windows 3.1 with the default settings for
	Originate, you are in the standard configuration. To make use of the Originate
	string and the auto-answering feature, you must open the ANSWER.TRM file that
	was saved previously. Another option is to set up the Terminal icon to
	automatically open the ANSWER.TRM file as follows:
	
	1. Select the Terminal icon.
	
	2. From the File menu in Program Manager, choose Properties.
	
	3. On the Command Line, add the name of the file you want Terminal to open
	  automatically. The Command Line should appear similar to the following:
	
	  c:\windows\terminal.exe answer.trm
	
	Method 3:
	
	Set up a function key that when pressed enters the "answer command":
	
	1. From the Settings menu, choose Function Keys.
	
	2. For Key Name, enter "Auto-answer" (without the quotation marks).
	
	3. For Command, enter the "answer command," for example:
	
	  ATQ1E0S0=1
	
	4. Be sure the check box for Keys Visible is selected, then choose OK. You
	  should then be able to see the newly created function key at the bottom of
	  the Terminal display window.
	
	5. To save the function key, choose Save from the File menu, and type a filename
	  (for example, you could save it as ANSWER2.TRM).
	
	Windows 3.0
	-----------
	
	With Hayes or other compatible smart modems, the settings are controlled through
	software switches. Although Terminal doesn't provide an easy way to set the
	modem to auto-answer, you have the following three options:
	
	- Run the software that came with your modem to configure the modem to
	  auto-answer.
	
	  -or-
	
	- Type "ATA" (without the quotation marks) when the phone rings.
	
	  -or-
	
	- From the Settings menu, choose Modem Commands. In the Originate field, make
	  the string equal to 1 instead of 0. Choose OK and dial any number. This
	  triggers the modem to auto-answer. Once the modem is set to auto-answer,
	  reset the Originate field to 0. A subsequent call to your computer causes
	  Terminal to detect a carrier and make a connection. Note that you can record
	  a macro with Recorder and automate this procedure.
	
	KBCategory: kbsetup kbdisplay kbhw kb3rdparty
	KBSubcategory: win30 win31 wfw wfwg wincomm
	
	Additional query words: 3.00 3.0a 3.0 3.10 3.1 3.11 smartmodem
	
	======================================================================
	Keywords          :  
	Technology        : kbAudDeveloper kbWin3xSearch kbWFWSearch kbZNotKeyword3 kbWin300 kbWin300a kbWin310 kbWin311 kbWFW310 kbWFW311
	Version           : WINDOWS:3.0,3.0a,3.1,3.11
	
	=============================================================================
	

{% endraw %}
