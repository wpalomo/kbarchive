---
layout: page
title: "Q148687: FIX: Clipboard Assistant - Paste Fails or Causes Hard Break"
permalink: kb/148/Q148687/
---

## Q148687: FIX: Clipboard Assistant - Paste Fails or Causes Hard Break

	Article: Q148687
	Product(s): Microsoft C Compiler
	Version(s): 4.0 4.1 4.2
	Operating System(s): 
	Keyword(s): kbcode kbProgramming kbtool kbide kbVC kbGrpDSToolskbbuglist kbfixlist
	Last Modified: 03-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual C++, versions 4.0, 4.1 
	- Microsoft Visual C++, 32-bit Enterprise Edition, version 4.2 
	- Microsoft Visual C++, 32-bit Professional Edition, version 4.2 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Code generated by the Clipboard Assistant for a Custom Clipboard Format may
	cause the following problems:
	
	- Copying to the clipboard fails to replace what was previously placed on the
	  clipboard.
	
	- An access violation occurs with a message similar to the following:
	
	  Exception: access violation (0xc0000005),
	  Address: 0x5f82cf37
	
	- An unexpected memory overwrite occurs after several clipboard operations.
	
	- On the Checked build of Windows NT, a Cut, Copy, or Paste operation causes a
	  hard-coded breakpoint to be encountered and a trace message similar to the
	  following to be generated:
	
	  BASE: GlobalFree called with a locked object.
	
	
	CAUSE
	=====
	
	The first three problems can occur because of the OnEditPaste function generated
	by the Clipboard Assistant. The code is not correct because it frees the HGLOBAL
	that it retrieves from the clipboard when doing a paste operation. This memory
	should not be freed because the Clipboard will free it when necessary. The code
	also fails to call CloseClipboard for all possible calls to OpenClipboard.
	
	The fourth problem is caused by a separate bug in the CSharedFile::Detach()
	function. For more details on this problem, please see the following article in
	the Microsoft Knowledge Base:
	
	  Q148455 CSharedFile::Detach() Does Not Call GlobalUnlock()
	
	RESOLUTION
	==========
	
	The sample code in this article shows new versions of the OnEditCopy, OnEditCut,
	and OnEditPaste functions. You should use this code to replace the versions
	previously generated by the Clipboard Assistant.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a bug in the Microsoft products listed at the
	beginning of this article. This problem has been fixed in Visual C++ version
	5.0.
	
	MORE INFORMATION
	================
	
	Sample Code to Resolve Problem
	------------------------------
	
	     /* Compile options needed: Default AppWizard options  */ 
	     void CMyView::OnEditCopy()
	     {
	     // CG: This block was added by the Clipboard Assistant component
	       {
	         CSharedFile memFile;
	         CArchive ar(&memFile, CArchive::store|CArchive::bNoFlushOnDelete);
	         // serialize data to archive object
	         DoCutCopyPaste(ar, FALSE);
	         ar.Flush();
	         HGLOBAL hData = memFile.Detach();
	         //Resolution for CSharedFile::Detach() problem
	         //Check <LINK TYPE="ARTICLE" VALUE="Q148455">Q148455</LINK> for current status.
	         // _MFC_VER might need to be updated.
	         #if _MFC_VER <= 0x0420
	           ::GlobalUnlock(hData);
	         #endif
	         if (OpenClipboard())
	         {
	           ::SetClipboardData(m_nClipboardFormat, hData);
	           CloseClipboard();
	         }
	         else
	           AfxMessageBox(CG_IDS_CANNOT_OPEN_CLIPBOARD);
	       }
	     }
	     void CMyView::OnEditCut()
	     {
	       // CG: This block was added by the Clipboard Assistant component
	       {
	         CSharedFile memFile;
	         CArchive ar(&memFile, CArchive::store|CArchive::bNoFlushOnDelete);
	         // Serialize data to archive object
	         DoCutCopyPaste(ar, TRUE);
	         ar.Flush();
	         HGLOBAL hData = memFile.Detach();
	         //Resolution for CSharedFile::Detach() problem
	         //Check <LINK TYPE="ARTICLE" VALUE="Q148455">Q148455</LINK> for current status.
	         // _MFC_VER might need to be updated.
	         #if _MFC_VER <= 0x0420
	           ::GlobalUnlock(hData);
	         #endif
	         if (OpenClipboard())
	         {
	           ::SetClipboardData(m_nClipboardFormat, hData);
	           CloseClipboard();
	         }
	         else
	           AfxMessageBox(CG_IDS_CANNOT_OPEN_CLIPBOARD);
	       }
	     }
	     void CMyView::OnEditPaste()
	     {
	       // CG: This block was added by the Clipboard Assistant component
	       {
	         if (OpenClipboard())
	         {
	           HANDLE hData = ::GetClipboardData(m_nClipboardFormat);
	           if (hData != NULL)
	           {
	             CSharedFile memFile;
	             memFile.SetHandle(hData,FALSE);
	             CArchive ar(&memFile, CArchive::load);
	             // Serialize data to document
	             DoCutCopyPaste(ar, FALSE);
	             ar.Close();
	             //Resolution for CSharedFile::Detach() problem
	             //Check <LINK TYPE="ARTICLE" VALUE="Q148455">Q148455</LINK> for current status.
	             // _MFC_VER might need to be updated.
	             #if _MFC_VER <= 0x0420
	               ::GlobalUnlock(memFile.Detach());
	             #else
	               memFile.Detach();
	             #endif
	           }
	           else
	             AfxMessageBox(CG_IDS_CANNOT_GET_CLIPBOARD_DATA);
	           CloseClipboard();
	         }
	         else
	           AfxMessageBox(CG_IDS_CANNOT_OPEN_CLIPBOARD);
	       }
	     }
	
	Additional query words:
	
	======================================================================
	Keywords          : kbcode kbProgramming kbtool kbide kbVC kbGrpDSTools kbbuglist kbfixlist
	Technology        : kbVCsearch kbVC400 kbAudDeveloper kbVC410 kbVC420 kbVC32bitSearch
	Version           : 4.0 4.1 4.2
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	