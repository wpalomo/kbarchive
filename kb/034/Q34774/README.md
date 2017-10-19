---
layout: page
title: "Q34774: FIX: FWAIT Prefixes Generated for Processor Control Instructions"
permalink: kb/034/Q34774/
---

## Q34774: FIX: FWAIT Prefixes Generated for Processor Control Instructions

	Article: Q34774
	Product(s): Microsoft Macro Assembler
	Version(s): 5.1,5.1a
	Operating System(s): 
	Keyword(s): 
	Last Modified: 06-MAY-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Macro Assembler (MASM), versions 5.1, 5.1a 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	For a 80287 or 80387 processor, MASM should not be generating FWAIT prefixes for
	processor control instructions that do not have no-wait forms, including the
	following:
	
	  FLDCW, FLDENV, FRSTOR, FINCSTP, FDECSTP, FFREE, and FNOP
	
	STATUS
	======
	
	Microsoft has confirmed this to be problem in MASM versions 5.10 and 5.10a. This
	problem was corrected in MASM version 6.00.
	
	MORE INFORMATION
	================
	
	The following is an example of the wait incorrectly generated by MASM for the
	FLDCW instruction. The fldcw generates the opcodes "9B D9 2D" when it should
	only generate "D9 2D" without the "9B" wait.
	
	Sample Code
	-----------
	
	  ; Assemble options needed: none
	
	     .386
	     .387
	     .model small
	     .data
	
	  d1 DW 0
	
	     .code
	  fldcw d1
	
	     END
	
	Additional query words: 5.10 buglist5.10 buglist5.10a fixlist6.00
	
	======================================================================
	Keywords          :  
	Technology        : kbMASMsearch kbAudDeveloper kbMASM510 kbMASM510a
	Version           : :5.1,5.1a
	Solution Type     : kbfix
	
	=============================================================================
	