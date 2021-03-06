---
layout: page
title: "Q176535: HOWTO: Save Attachments to File with MSMAPI.VBX or MSMAPI.OCX"
permalink: /kb/176/Q176535/
---

## Q176535: HOWTO: Save Attachments to File with MSMAPI.VBX or MSMAPI.OCX

{% raw %}

	Article: Q176535
	Product(s): Microsoft Visual Basic for Windows
	Version(s): 
	Operating System(s): 
	Keyword(s): kbGrpDSVBDB
	Last Modified: 11-JAN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual Basic Learning Edition for Windows, version 6.0 
	- Microsoft Visual Basic Professional Edition for Windows, version 6.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 6.0 
	- Microsoft Visual Basic Control Creation Edition for Windows, version 5.0 
	- Microsoft Visual Basic Learning Edition for Windows, version 5.0 
	- Microsoft Visual Basic Professional Edition for Windows, version 5.0 
	- Microsoft Visual Basic Enterprise Edition for Windows, version 5.0 
	- Microsoft Visual Basic Standard Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 16-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Professional Edition, 32-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 16-bit, for Windows, version 4.0 
	- Microsoft Visual Basic Enterprise Edition, 32-bit, for Windows, version 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	The MAPIMessage Control has procedures to attach and remove attachments from a
	message, but nothing apparent to allow writing the attachment back out to a
	permanent file. This article contains a code sample demonstrating how this can
	be done.
	
	MORE INFORMATION
	================
	
	When a message that contains an attachment is opened, any attachments are
	written to the system's temp directory. The path and filename to this temporary
	file are stored in the AttachmentPathName property of the message.
	
	You can copy the file as desired using the Visual Basic FileCopy file function.
	
	NOTE: The filename is in 8.3 format, so long filenames will be lost.
	
	The following code sample demonstrates how to access the path and filename to the
	temporary file and copy the temporary file to the Root of drive C:
	
	     Sub Form_Load ()
	         mapisession1.Action = 1 'session_signon
	         mapimessages1.SessionID = mapisession1.SessionID
	         mapimessages1.FetchUnreadOnly = True
	         mapimessages1.Action = 1 'message_fetch
	         Dim i As Integer
	         For i = 0 To mapimessages1.AttachmentCount - 1
	             mapimessages1.AttachmentIndex = i
	             Dim intLenFileName As Integer
	             Dim intStrPos As Integer
	             intLenFileName = Len(mapimessages1.AttachmentPathName)
	             For intStrPos = intLenFileName To 1 Step -1
	                 If InStr(1, _
	                          Right$(mapimessages1.AttachmentPathName, _
	                                 intLenFileName - (intStrPos - 1)), _
	                          "\", 1) Then
	                     strNewFileName = _
	                        Right$(mapimessages1.AttachmentPathName, _
	                               intLenFileName - intStrPos)
	                     Exit For
	                 End If
	             Next
	             FileCopy mapimessages1.AttachmentPathName, _
	                      "c:\" & strNewFileName
	         Next
	     End Sub
	
	Additional query words: MAPI kbVBp400 kbVBp500 kbVBp600 kbMapi kbdse kbDSupport kbVBp
	
	======================================================================
	Keywords          : kbGrpDSVBDB 
	Technology        : kbVBSearch kbAudDeveloper kbZNotKeyword6 kbZNotKeyword2 kbVB500Search kbVB600Search kbVBA500Search kbVBA500 kbVBA600 kbVB500 kbVB600 kbVB400Search kbVB400 kbZNotKeyword3 kbVB16bitSearch
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
