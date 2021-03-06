---
layout: page
title: "Q201470: XFOR: SMTP Address Incorrect If At Sign @ Is In Site Name"
permalink: /kb/201/Q201470/
---

## Q201470: XFOR: SMTP Address Incorrect If At Sign @ Is In Site Name

{% raw %}

	Article: Q201470
	Product(s): Microsoft Exchange
	Version(s): winnt:5.5
	Operating System(s): 
	Keyword(s): exc55
	Last Modified: 06-AUG-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, version 5.5 
	-------------------------------------------------------------------------------
	
	
	SUMMARY
	=======
	
	If there is an at sign (@) in a site name (or organization name), the SMTP proxy
	addresses that are generated for the users are unexpected and random. The
	problem also occurs if you use the Move Server Wizard to move a server to a site
	that has an @ in its name, and the problem manifests itself in inexplicable and
	inaccurate SMTP proxy addresses for the users on the server that you moved.
	Random characters are added to the SMTP proxy addresses.
	
	MORE INFORMATION
	================
	
	The problem may occur in either of the following scenarios:
	
	- You want to add a server to a site that has an @ in its name.
	
	  You install a new server (server1) in a site that has an @ in its name, for
	  example, "test @ microsoft." The Exchange Server organization name is "org."
	
	  You create several mailboxes on the newly installed server.
	
	  If you check the SMTP proxy address for a user on the server, for example,
	  user1, the proxy address that is generated may look like
	  "test6@microsoft.server1.com" instead of the expected address
	  "user1@test@microsoft.org.com."
	
	  The incorrect SMTP proxy address contains the server name and a randomly
	  generated number that is added to the site name, instead of being in the
	  standard SMTP proxy address format (<alias>@<site
	  name>.<organization name>.com).
	
	- You want to move a server (by using the Move Server Wizard) to a site that
	  has an @ in its name.
	
	  You want to move another server (server2) that is in a different site (site2)
	  to a site that has an @ in its name (in this example, "test @ microsoft").
	  The Exchange Server organization name is "org." Before the move, if you check
	  the SMTP proxy address for a user, user2, for example, on server2, it looks
	  like "user2@site2.org.com."
	
	  You run the Move Server Wizard on server2 to join that server to the "test @
	  microsoft" site.
	
	  After the move, the primary proxy address for user2 may look like
	  "testfd3f0@microsoft.server2.com," instead of the expected address
	  "user2@test@microsoft.org.com."
	
	  The incorrect SMTP proxy address contains the server name and a randomly
	  generated number that is added to the site name, instead of being in the
	  standard SMTP proxy address format (<alias>@<site
	  name>.<organization name>.com). The Move Server Wizard does not
	  cause the generation of the inaccurate proxy addresses.
	
	You may not want to remove the @ from the site name, because using the sign in
	the site name (or organization name) may be more important to you than
	automatically generating accurate SMTP addresses.
	
	To work around the problem, you can manually repair the SMTP proxy addresses in
	the Site Addressing object.
	
	Additional query words: Pilgrim, spurious
	
	======================================================================
	Keywords          : exc55 
	Technology        : kbExchangeSearch kbExchange550 kbZNotKeyword2
	Version           : winnt:5.5
	Issue type        : kbinfo
	
	=============================================================================
	

{% endraw %}
