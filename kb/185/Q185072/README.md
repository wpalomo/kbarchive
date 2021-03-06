---
layout: page
title: "Q185072: How to Configure Outlook 97 for Use with Multiple MSN Accounts"
permalink: /kb/185/Q185072/
---

## Q185072: How to Configure Outlook 97 for Use with Multiple MSN Accounts

{% raw %}

	Article: Q185072
	Product(s): The Microsoft Network
	Version(s): 2.5,2.51,2.52,2.6
	Operating System(s): 
	Keyword(s): kbmsnkbfaq
	Last Modified: 07-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- The Microsoft Network versions 2.5, 2.51, 2.52, 2.6 
	- Microsoft Outlook 97 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article describes how to configure Microsoft Outlook 97 for use with
	multiple accounts on MSN, The Microsoft Network.
	
	MORE INFORMATION
	================
	
	To configure Outlook 97 for use with multiple MSN accounts, there are three
	steps:
	
	1. Configure Outlook for Use With MSN
	
	2. Setting up Additional Mail Accounts on Outlook
	
	3. Sending and Receiving Additional Mail Accounts Using Outlook
	
	Part 1: Configure Outlook for Use With MSN
	------------------------------------------
	
	To configure Outlook 97 for use with multiple MSN accounts, you need to install
	the Internet Mail Enhancement Patch (IMEP), and then migrate (or convert) each
	MSN account to the new Internet e-mail service.
	
	For information about how to install the Internet Mail Enhancement Patch, please
	see the following article in the Microsoft Knowledge Base:
	
	  Q175880<A0> How to Configure Outlook 97 for Use with MSN 2.5 or MSN 2.6
	
	For additional information on mail migration (upgrading), please see the
	following article in the Microsoft Knowledge Base:
	
	  Q176276<A0> Frequently Asked Questions About Mail Migration on MSN
	
	Part 2: Setting up Additional Mail Accounts on Outlook
	------------------------------------------------------
	
	When you have installed IMEP and migrated each MSN account to the new Internet
	e-mail service, you can configure Outlook 97 to send and receive e-mail on
	multiple MSN accounts by first adding the MSN accounts to your Outlook client.
	To do this, follow these steps:
	
	1. Start Outlook 97.
	
	2. On the Tools menu, click Services.
	
	3. On the Services tab, click Add.
	
	4. In the Available Information Services box, click Internet E-Mail, and then
	  click OK.
	
	5. Click the General tab.
	
	6. Type a name for the MSN account you want to configure Outlook 97 to send and
	  receive e-mail on in the Mail Account box, type the name of the MSN account
	  holder in the Name box, and then type the MSN e-mail address in the E-Mail
	  Address box.
	
	7. Click the Servers tab.
	
	8. Type smtp.email.msn.com in the Outgoing Mail (SMTP) box, and then type
	  pop3.email.msn.com in the Incoming Mail (POP3) box.
	
	  NOTE: If you gain access to MSN through a third-party ISP or local area
	  network (LAN)--including DSL, Cable modem, or Satellite connection-- type
	  secure.smtp.email.msn.com in the Outgoing Mail (SMTP) box.
	
	9. Click Log on using Secure Password Authentication.
	
	10. Click the Connection tab, and then click I Connect Manually.
	
	11. Click OK.
	
	12. To configure Outlook 97 to send and receive e-mail on additional MSN
	  accounts, repeat steps 3-11. When you finish adding MSN accounts, click OK,
	  and then quit Outlook 97.
	
	Part 3: Sending and Receiving Additional Mail Accounts Using Outlook
	--------------------------------------------------------------------
	
	1. Start Outlook 97. If you have correctly configured Outlook 97 to connect
	  automatically to MSN, the MSN Sign-In screen appears. Type the MSN Member ID
	  and password for the account you want to send or receive e-mail on, and then
	  click Connect.
	
	2. On the Tools menu, click Check For New Mail On.
	
	3. Locate the MSN account you want to send or receive e-mail on, and then click
	  the check box for that account to select it. If the check box for any other
	  MSN account is selected, click the check box for that account to clear it.
	
	4. Click OK. If you are not already connected to MSN, the MSN Sign-In screen
	  appears. Type the Member ID and password for the MSN account you selected,
	  and then click Connect.
	
	5. When you finish sending and receiving e-mail on the first account, quit
	  Outlook 97 and all MSN-related programs, and then disconnect from MSN and
	  exit Outlook 97.
	
	6. To send and receive e-mail on other MSN accounts, repeat steps 1-5.
	
	Additional query words: msnet msnetwork microsoft-net m.s.n. email
	
	======================================================================
	Keywords          : kbmsn kbfaq
	Technology        : kbOutlookSearch kbMSNSearch kbOutlook97Search kbZNotKeyword3 kbMSN252 kbMSN251 kbMSN260 kbMSN250
	Version           : :2.5,2.51,2.52,2.6
	Issue type        : kbhowto kbinfo
	
	=============================================================================
	

{% endraw %}
