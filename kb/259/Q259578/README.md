---
layout: page
title: "Q259578: XADM: Event ID 11/1023 Appear When Starting Exchange Event Svc"
permalink: /kb/259/Q259578/
---

## Q259578: XADM: Event ID 11/1023 Appear When Starting Exchange Event Svc

{% raw %}

	Article: Q259578
	Product(s): Microsoft Exchange
	Version(s): winnt:5.5
	Operating System(s): 
	Keyword(s): exc55
	Last Modified: 06-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, version 5.5 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	Event ID 11 is logged in the application event log soon after you start the
	Microsoft Exchange Event Service.
	
	Event ID 1023 is logged immediately after the Event Service starts. It may take
	approximately one minute for the Event ID 11 to appear in the application event
	log. In some cases, the Event 1023 and (or) 11 does not appear at all. The
	circumstances under which one or more of the events is not generated are listed
	in the "More Information" section of this article.
	
	The events look similar to the following:
	
	  Event ID: 1023
	  Source: MSExchangeIS Private
	  Type: Failure Audit
	  Category: Logons
	  Description:
	  Domain\ServiceAccount was validated as
	  /o=ORG1/ou=mysite/cn=Configuration/cn=Servers/cn=MBS-MAIL-03/cn=Microsoft
	  System Attendant but was unable to log on to
	  /o=ORG1/ou=mysite/cn=Recipients/cn=user-3.
	
	  Event ID: 11
	  Source: MSExchangeES
	  Type: Error
	  Category: General
	  Description:
	  A fatal error (0x8004011d) occurred in an IExchangeEventSink while processing
	  message [Subject = "xxx"].
	
	CAUSE
	=====
	
	The events are harmless and are generated when you delete a mailbox or public
	folder without first removing a published Event Script from the mailbox or
	public folder. For example, if you publish a script to the inbox of a mailbox,
	and you delete the mailbox without first removing the published script, Exchange
	continues attempting to monitor the inbox of this non-existent mailbox. Every
	time that you start the Event Service, Exchange searches the inbox of the
	non-existent mailbox. This causes the Event ID 11 and 1023 to occur.
	
	RESOLUTION
	==========
	
	To resolve this issue:
	
	- Remove and re-install the Exchange Event Service.
	
	  -or-
	
	- Use the Mdbvu32 program from the Exchange 5.5 CD-ROM to access the Event
	  Config folder for the server where the Event Service is installed. From the
	  Event Config folder, remove the published scripts and the references to the
	  non-existent folders where the scripts were originally published.
	
	Mdbvu32.exe can be found on the Exchange 5.5 CD-ROM in the
	Server\Support\Utils\I386 directory. You can run the tool directly from the
	CD-ROM or you can copy the following files to a specific directory and run
	Mdbvu32 from that directory: Mdbvu32.exe, Propvu32.dll, Statvu32.dll,
	Tblvu32.dll, Xvport.dll
	
	To keep the events from occurring, two types of messages must be deleted from the
	Event Config folder. One message contains the name of the folder where the
	script was published, and the other message contains the name given to the Agent
	that is running the script in this folder.
	
	Follow the steps below to purge the information in the Event Config folder which
	is causing the Event ID 11 to be generated. This tool can be run from any NT
	machine as long as the Microsoft Outlook client is installed:
	
	1. Log on to the NT server with the Exchange Service Account.
	
	2. Create an Outlook profile that logs on to a mailbox that resides on the
	  Exchange Server computer on which the Event Service is installed. Also, in
	  the Exchange Server Administrator program, go to Folders, System Folders,
	  Events Root, EventConfig_Servername (where servername is the name of the
	  server that the event service resides on). Highlight this folder, click File,
	  and then click Properties. On the General tab, click the Client Permissions
	  button. You must now assign the mailbox you chose Owner permissions for to
	  the folder.
	
	3. Double-click the Mdbvu32.exe program, and click OK to the
	  MAPILogonEx(MAPI_LOGON_UI) prompt that appears.
	
	4. Choose the appropriate Outlook profile to use, and click OK.
	
	5. From the MDB Viewer Test Application window, choose MDB\Open Message Store.
	
	6. Highlight Public Folders, and then click Open.
	
	7. Choose MDB\Open Root Folder, and click OK to the three error messages that
	  appear.
	
	8. Double-click NON_IPM_SUBTREE under Child Folders.
	
	9. Double-click Events Root under Child Folders.
	
	10. Click OK to the two error messages that appear.
	
	11. Double-click EventConfig Server_Name under Child Folders.
	
	12. Under Messages in Folder, you see the Display Names of the Agents/Scripts
	  and the folders where these scripts were published. For example, if a script
	  was published to the inbox of a mailbox, and the Agent/Script was given the
	  name of MB AGENT, you see the information listed as follows under Messages
	  in Folder. If the script was published to a public folder, you would see the
	  name of the public folder rather than "\Inbox":
	
	  \Inbox
	  MB AGENT
	
	13. If a script was published to the inbox of more than one mailbox, you see
	  multiple instances of "\Inbox." Also, if you have more than one Agent/Script
	  with the same name, you see more than one instance of this Agent name in the
	  list. To find out which entries belong to the non-existent mailbox, you must
	  double-click each entry to determine which mailbox it belongs to.
	
	14. Double-click the public folder name or name of the mailbox folder such as
	  "\Inbox" in the list. Under Message Properties, look for a hexadecimal value
	  of "0x3FF8." This value lists the Display Name of the mailbox being
	  referenced. If the Display Name matches the Display Name of the deleted
	  mailbox, choose Close, make sure the highlight is still on the selection
	  that you wish to delete, click the drop-down arrow next to Call Function,
	  choose the lpFld-> DeleteMessages() option, click the Call Function
	  button, and then click OK. The "\Inbox" entry should disappear from the
	  list. Follow the same procedures above for finding and deleting the
	  Agent/Script entry which references the deleted mailbox or public folder.
	
	15. To exit Mdbvu32, continue to choose Close until the MDB Viewer Test
	  Application window is displayed. Close this window, click OK to the
	  lpMDB->StoreLogoff() prompt, and then click OK to the very next prompt.
	
	If you purge all items that reference the non-existent public folder or mailbox,
	the Event ID 11 and 1023 will no longer occur.
	
	MORE INFORMATION
	================
	
	The Event ID 1023 only appear when a script has been published to a mailbox that
	is then deleted. The 1023 event is generated as a result of the System Attendant
	attempting to log in to the private information store of the deleted mailbox.
	
	In some cases, when a public folder has been deleted without first removing the
	script, the Event ID 11 will sometimes occur only once, not at all, or only the
	following event may be logged in the application log:
	
	  Event ID: 5
	  Source: MSExchangeES
	  Type: Error
	  Category: General
	  Description:
	  An unexpected MAPI error occurred. Error returned was (0x8004010f).
	
	Additional query words: Event ID 5
	
	======================================================================
	Keywords          : exc55 
	Technology        : kbExchangeSearch kbExchange550 kbZNotKeyword2
	Version           : winnt:5.5
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
