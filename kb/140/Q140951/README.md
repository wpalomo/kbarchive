---
layout: page
title: "Q140951: XFOR: DXA Generates Multiple SMTP Proxies for PCMail"
permalink: /kb/140/Q140951/
---

## Q140951: XFOR: DXA Generates Multiple SMTP Proxies for PCMail

{% raw %}

	Article: Q140951
	Product(s): Microsoft Exchange
	Version(s): 3.x,4.0
	Operating System(s): 
	Keyword(s): kbusage
	Last Modified: 19-FEB-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, version 4.0 
	- Microsoft Mail for PC Networks, version 3.x 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	The Microsoft Exchange DXA creates multiple SMTP proxy addresses for PC Mail
	addresses when using the DXA registry settings to use the Addr_map.cfg file.
	
	MORE INFORMATION
	================
	
	The two proxies that are generated are derived from the SMTPDomain registry
	setting and the Addr_map.cfg file. In order to use the Addr_map.cfg file with
	the DXA, you need to specify a domain for the SMTPDomain registry setting. The
	SMTPDomain registry setting acts like a switch to enable this additional
	functionality.
	
	The first proxy that will be generated uses the network/postoffice name in
	conjunction with the value specified for the SMTPDomain registry setting. The
	second proxy generated is the domain specified for the postoffice in the
	Addr_map.cfg file.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Microsoft Exchange Server
	version 4.0. This problem was corrected in Microsoft Exchange Server 4.0 U.S.
	Service Pack 2. For information on obtaining the service pack, query on the
	following word in the Microsoft Knowledge Base (without the spaces):
	
	  S E R V P A C K
	
	With the new DXA, only the proxy(s) specified for the postoffice in the
	Addr_map.cfg file will be generated for the PC Mail addresses when the
	SMTPPrimaryProxy registry value has been set to 3. However, a value still needs
	to be specified for the SMTPDomain registry setting for this functionality to be
	enabled. The domain specified for this registry setting will not be included in
	the SMTP proxy that is actually generated.
	
	Here is an example of a properly configured dirsync system:
	
	  Registry Settings:
	
	      SMTPDomain = xyz.com
	      AddressMappingFileName = c:\exchsrvr\imcdata\addr_map.cfg
	      SMTPPrimaryProxy = 3
	
	  Addr_map.cfg:
	
	      net1/po1 abc.com
	      net2/po2 def.com
	
	  All SMTP proxys generated by dirsync for mailboxes on net1\po1 will
	  appear similar to the following:
	
	      paulbon@abc.com
	
	Extra care must be used when manually editing the Addr_map.cfg file. Make sure
	that there is a single carriage return at the end of the Addr_map.cfg file so
	that the cursor is resting on a new line just below the last proxy specified in
	the file. The file will appear as follows in the editor where the cursor is
	shown as a "|":
	
	  net1/po1 abc.com
	  net2/po2 def.com
	
	If there are too many line feeds at the end of the Addr_map.cfg file, the DXA
	might not start and might give the following error:
	
	  Could not start the Microsoft Exchange Directory Synchronization service on
	  \\WOLVERINE. Error 2140 an internal Windows NT error occurred.
	
	If the cursor is located at the end of the previous line of the Addr_map.cfg
	file, the proxy addresses generated might be missing characters as follows:
	
	  leannem@def.co
	
	In addition, the Microsoft Exchange Directory Synchronization service needs to be
	stopped and restarted in order for the registry and Addr_map.cfg file changes to
	take effect.
	
	
	Additional query words:
	
	======================================================================
	Keywords          : kbusage 
	Technology        : kbExchangeSearch kbExchange400 kbZNotKeyword2 kbMailSearch kbZNotKeyword3 kbMailPCN3xSearch
	Version           : :3.x,4.0
	
	=============================================================================
	

{% endraw %}
