---
layout: page
title: "Q171333: WD97: Skip Numbering and Stop Numbering Not on Shortcut Menu"
permalink: /kb/171/Q171333/
---

## Q171333: WD97: Skip Numbering and Stop Numbering Not on Shortcut Menu

{% raw %}

	Article: Q171333
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): kbui word97 kbnumbering
	Last Modified: 14-NOV-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you right-click on a numbered paragraph in Microsoft Word 97, the Skip
	Numbering and Stop Numbering commands are no longer available on the shortcut
	menu.
	
	This is a change from earlier versions of Word, in which these options are
	available on the shortcut menu.
	
	CAUSE
	=====
	
	This behavior is by design. The Skip Numbering and Stop Numbering commands are
	no longer needed because the Numbering button on the Formatting toolbar provides
	equivalent functionality.
	
	WORKAROUND
	==========
	
	How to Remove Numbering from a Numbered Item
	--------------------------------------------
	
	To perform the equivalent of the Skip Numbering command, use either of the
	following methods:
	
	1. Place the insertion point within the numbered item.
	
	2. On the Formatting toolbar, click Numbering to remove the number.
	
	  -or-
	
	3. Place the insertion point at the beginning of the numbered item.
	
	4. Press BACKSPACE to remove the number.
	
	Word removes both the number and the indent from the paragraph. To retain the
	indent, place the insertion point at the beginning of the paragraph and press
	TAB.
	
	How to Stop the Numbering of Numbered Items
	-------------------------------------------
	
	To perform the equivalent of the Stop Numbering command, follow these steps:
	
	1. Remove the numbering from the chosen item as described in the "How To Remove
	  Numbering from a Numbered Item" section of this article.
	
	2. Right-click the numbered item for which you want to change numbering.
	
	3. On the shortcut menu, click Bullets and Numbering.
	
	4. Click to select Restart Numbering.
	
	  -or-
	
	  To specify a starting number other than one, click Customize, change the Start
	  At number, and then click OK.
	
	How to Add the Skip Numbering Command to the Shortcut Menu
	----------------------------------------------------------
	
	You can add the Skip Numbering command to the shortcut menu for numbered
	paragraphs. To do this, follow these steps:
	
	1. On the Tools menu, click Customize.
	
	2. On the Toolbars tab, scroll to the bottom of the list and click to select the
	  Shortcut Menus check box.
	
	  NOTE: A Shortcut Menus toolbar is displayed.
	
	3. Click the Commands tab.
	
	4. Under Categories, click to select All Commands.
	
	5. Under Commands, click to select SkipNumbering, and then drag SkipNumbering to
	  the Text menu on the Shortcut Menus toolbar. In the Text menu, point to Lists
	  and then drop SkipNumbering into position on the shortcut menu.
	
	  NOTE: Because Word may not always use the Lists shortcut menu, you may also
	  want to add SkipNumbering to the Spelling shortcut menu.
	
	6. In the Customize dialog box, click Close.
	
	For additional information about customizing the toolbars, please see the
	following article in the Microsoft Knowledge Base:
	
	  Q163547 WD97: How to Create Custom Toolbars and Toolbar Buttons
	
	MORE INFORMATION
	================
	
	In earlier versions of Word, the Stop Numbering command (RemoveBulletsNumbers)
	removes numbering from the selected paragraphs, and then restarts numbering at
	one for the next numbered paragraph. In Word 97, the equivalent command does not
	restart numbering at one, but continues the previous numbering sequence.
	
	REFERENCES
	==========
	
	For additional information about numbering, please see the following articles in
	the Microsoft Knowledge Base:
	
	  Q159943 WD97: General Information About Bullets and Numbering
	
	  Q162895 WD97: How to Use the ListNum Field in Word
	
	Or, click the Office Assistant, type "numbering" (without the quotation marks),
	click Search, and then click one of the topics.
	
	NOTE: If the Assistant is hidden, click the Office Assistant button on the
	Standard toolbar. If Word Help is not installed on your computer, please see the
	following article in the Microsoft Knowledge Base:
	
	  Q120802 Office: How to Add/Remove a Single Office Program or Component
	
	Additional query words: 8.0
	
	======================================================================
	Keywords          : kbui word97 kbnumbering 
	Technology        : kbWordSearch kbWord97 kbWord97Search kbZNotKeyword2
	Version           : WINDOWS:97
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
