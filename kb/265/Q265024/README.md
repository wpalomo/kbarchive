---
layout: page
title: "Q265024: WD97: Blank Page Printed Inserting Odd /Even Page Section Break"
permalink: /kb/265/Q265024/
---

## Q265024: WD97: Blank Page Printed Inserting Odd /Even Page Section Break

{% raw %}

	Article: Q265024
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): kbdta word8 word97 kblayout
	Last Modified: 14-NOV-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	After you insert an odd page section break or an even page section break, a new
	blank page may appear in print preview and when you print the document.
	
	In addition, you may observe the following problems:
	
	- If your Word document contains page numbers, the page numbers may skip a page
	  number.
	
	- The page number in your document may appear higher than you expect.
	
	- If your Word document contains a total number of pages field (a NUMPAGES
	  field), the total number of pages shown is greater than you expect.
	
	- The page number on the status bar may skip a page number when you page
	  through the document.
	
	- The total number of pages on the status bar may indicate a greater number of
	  pages than you expect.
	
	
	CAUSE
	=====
	
	This functionality is by design in Microsoft Word. When you insert an odd page
	section break on an odd-numbered page, or an even page section break on an
	even-numbered page, Word cannot move the following text to the next physical
	page. Instead, Word moves the text that follows the section break to the next
	appropriate odd page or even page of the document. To do this, Word has to
	insert a blank page after the section break.
	
	NOTE: The blank page that is inserted contains no header or footer. In addition,
	it may appear that you cannot type text on the blank page.
	
	RESOLUTION
	==========
	
	To prevent the blank page when you view the document in print preview, to allow
	the page numbers to be printed correctly for each page, and to use the page for
	additional text in the document, do one of the following:
	
	Method 1: Type Text or Press ENTER
	----------------------------------
	
	On the page that precedes the odd page section break or even page section break,
	move the insertion point to the end of the text on that page. Either type
	additional text to fill out that page and continue onto the blank page, or press
	ENTER until the insertion point is on the blank page. Then type the additional
	text that you want on the page.
	
	Method 2: Insert a Page Break
	-----------------------------
	
	Insert a page break immediately before the odd page section break or even page
	section break. To do this, follow these steps:
	
	1. On the View menu, click Normal.
	
	2. Move the insertion point to the end of the text that precedes the Section
	  Break (Odd Page) or Section Break (Even Page).
	
	3. Do one of the following:
	
	   - Press CTRL+ENTER to insert a manual (hard) page break.
	
	     -or-
	
	   - On the Insert menu, click Break. In the Break dialog box, click to select
	     "Page break", and then click OK.
	
	     -or-
	
	   - On the Insert menu, click Break. In the Break dialog box, click to select
	     Next Page (listed under "Section breaks"), and then click OK.
	
	REFERENCES
	==========
	
	For additional information, click the article numbers below to view the articles
	in the Microsoft Knowledge Base:
	
	  Q198592 WD97: Blank Page Is Printed with Different Even and Odd Headers and
	  Footers
	
	  Q195331 WD97: General Information About Section Breaks
	
	Additional query words: extra more pages empty
	
	======================================================================
	Keywords          : kbdta word8 word97 kblayout 
	Technology        : kbWordSearch kbWord97 kbWord97Search kbZNotKeyword2
	Version           : WINDOWS:97
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
