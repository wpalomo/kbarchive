---
layout: page
title: "Q192932: XFOR: PROFS Does Not Retain File Extension of Attachment"
permalink: /kb/192/Q192932/
---

## Q192932: XFOR: PROFS Does Not Retain File Extension of Attachment

{% raw %}

	Article: Q192932
	Product(s): Microsoft Exchange
	Version(s): 3.2,5.5
	Operating System(s): 
	Keyword(s): exc55sp2fix
	Last Modified: 20-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- LinkAge Message Exchange, version 3.2 
	- Microsoft Exchange Server, version 5.5 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	When a file is sent from CMS (PROFS) to Exchange, the file is converted and
	delivered as an attachment, and the file's extension is changed.
	
	CAUSE
	=====
	
	Attachment names designated in the appropriate TBL file will have the extension
	replaced with TXT when converting to ASCII.
	
	RESOLUTION
	==========
	
	LinkAge Message Exchange 3.2
	----------------------------
	
	A supported fix that corrects this problem is now available from Microsoft, but
	has not been fully regression-tested and should be applied only to systems
	experiencing this specific problem. If you are not severely affected by this
	specific problem, Microsoft recommends that you wait for the next service pack
	that contains this fix.
	
	To resolve this problem immediately, contact Microsoft Product Support Services
	to obtain the fix. For a complete list of Microsoft Product Support Services
	phone numbers and information on support costs, please go to the following
	address on the World Wide Web:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	The English version of this fix should have the following file attributes or
	later:
	
	  File Name    Date
	  --------------------
	  Lsvmhc.dll   4/30/98
	
	
	Exchange Server 5.5
	-------------------
	
	To resolve this problem, obtain the latest service pack for Exchange Server
	version 5.5. For more information, please see the following article in the
	Microsoft Knowledge Base:
	
	  Q191014 XGEN: How to Obtain the Latest Exchange Server 5.5 Service Pack
	
	
	The English version of this fix should have the following file attributes or
	later:
	
	  Component: Exchange PROFS Connector
	
	  File Name    Version
	  -----------------------
	  Lsvmhc.dll   5.5.2319.0
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in LinkAge Message Exchange version
	3.2 and Microsoft Exchange Server version 5.5. This problem was first corrected
	in Exchange Server 5.5 Service Pack 2.
	
	
	MORE INFORMATION
	================
	
	Events in the LinkAge browser log:
	
	  1998/04/15 11:41:18- LME-PROFS-VMDIA(01fa) 4 23703:NJE client starts
	  receiving
	   >> njeclnt(3002)
	  1998/04/15 11:41:18- LME-PROFS-VMDIA(01fa) 4 23709:Host session
	  allocated
	   >> rscsclnt(541)
	  1998/04/15 11:41:19- LME-PROFS-VMDIA(01fa) 4 23711:JOB HEADER record
	  received - host job number 5455
	   >> rscsclnt(566)
	  1998/04/15 11:41:19- LME-PROFS-VMDIA(01fa) 4 40510:Received an OV/VM
	  distribution
	   >> vm2dia(1300)
	  1998/04/15 11:41:19- LME-PROFS-VMDIA(01fa) 4 44401:Start transforming
	  an OV/VM distribution to SNA/DIA format
	   >> vm2dia(1354)
	  1998/04/15 11:41:20- LME-PROFS-VMDIA(01fa) 4 23713:DATA SET HEADER
	  record received
	   >> rscsclnt(824)
	  1998/04/15 11:41:20- LME-PROFS-VMDIA(01fa) 4 23919:No more data set
	  header received
	   >> rscsclnt(801)
	  1998/04/15 11:41:20- LME-PROFS-VMDIA(01fa) 4 40518:Starting to parse
	  the OV/VM distribution
	   >> vm2dia(1529)
	  1998/04/15 11:41:20- LME-PROFS-VMDIA(01fa) 4 40941:Found NETDATA INMR01
	  record
	   >> netdata(643)
	  1998/04/15 11:41:20- LME-PROFS-VMDIA(01fa) 4 40941:Found NETDATA INMR02
	  record
	   >> netdata(643)
	  1998/04/15 11:41:20- LME-PROFS-VMDIA(01fa) 4 40941:Found NETDATA INMR03
	  record
	   >> netdata(643)
	  1998/04/15 11:41:20- LME-PROFS-VMDIA(01fa) 4 40920:Created temporary
	  file 'C:\exchsrvr\CONNECT\Exchconn\TEMP\c8a340db.tmp' for storing data
	  records
	   >> netdata(691)
	  1998/04/15 11:41:20- LME-PROFS-VMDIA(01fa) 4 40941:Found NETDATA data
	  record
	   >> netdata(648)
	  1998/04/15 11:41:20- LME-PROFS-VMDIA(01fa) 4 40941:Found NETDATA INMR06
	  record
	   >> netdata(643)
	  1998/04/15 11:41:20- LME-PROFS-VMDIA(01fa) 4 40578:Finished parsing the
	  OV/VM distribution
	   >> vm2dia(1535)
	  1998/04/15 11:41:20- LME-PROFS-VMDIA(01fa) 4 44794:Mapped VM/CMS
	  distribution correlation
	   >> ndt2dia(1622)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44776:Mapped VM/CMS
	  distribution sender: 'SERVERNAME'
	   >> ndt2dia(877)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44700:Adding USER1 to the
	  list of recipients
	   >> ndt2dia(696)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44774:Mapped VM/CMS
	  distribution recipients
	   >> ndt2dia(715)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44772:Mapped VM/CMS
	  distribution sent timestamp: '1998 4 15 11:41:54'
	   >> ndt2dia(636)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44770:Mapped VM/CMS
	  distribution subject: 'NO SUBJECT'
	   >> ndt2dia(558)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44792:Mapped VM/CMS
	  distribution attachment file name: 'TEST LOG A'
	   >> ndt2dia(1561)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44790:Mapped VM/CMS
	  distribution last change timestamp: '1998 4 13 17:13:55'
	   >> ndt2dia(1410)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 3 44701:Received TEST LOG A
	  19980413211355000000 from SERVERNAME
	   >> ndt2dia(298)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44796:Mapped VM/CMS
	  distribution attributes
	   >> ndt2dia(1702)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44768:Mapped VM/CMS
	  distribution document type: '0xff07'
	   >> ndt2dia(1784)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44784:Mapped VM/CMS
	  distribution host file attributes
	   >> ndt2dia(1152)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 50084:Mapped distribution
	  object file name: 'q\objects\c8a340e6.ATT'
	   >> dcobject(114)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44002:Transformed a
	  NETDATA distribution
	   >> netdata(2786)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 04107:Queue vm2mex.in has
	  been opened (physical location is q\vm2mex.in)
	   >> qm(1884)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 04110:New queue item
	  q\vm2mex.in\xx000001.new has been created in queue vm2mex.in
	   >> qm(2564)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 04118:New queue item
	  q\vm2mex.in\50000001.rdy has been committed in queue vm2mex.in
	   >> qm(3075)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 04108:Queue vm2mex.in has
	  been closed
	   >> qm(2003)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 23919:No more data set
	  header received
	   >> rscsclnt(801)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 40511:Finished with OV/VM
	  distribution
	   >> vm2dia(1575)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 40618:Deleted OV/VM
	  distribution
	   >> vm2dia(1601)
	  1998/04/15 11:41:21- LME-PROFS-DIAMEX(01bb) 4 04113:Queue item
	  q\vm2mex.in\50000001.rdy has been opened in queue vm2mex.in
	   >> qm(3480)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 23705:NJE client finishes
	  receiving
	   >> njeclnt(3186)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 23714:Host session
	  deallocated
	   >> rscsclnt(672)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 44402:Finish transforming
	  an OV/VM distribution to SNA/DIA format
	   >> vm2dia(1632)
	  1998/04/15 11:41:21- LME-PROFS-VMDIA(01fa) 4 40628:Waiting for an OV/VM
	  distribution
	   >> vm2dia(1290)
	  1998/04/15 11:41:21- LME-PROFS-DIAMEX(01bb) 4 00020:Warning {Not found}
	  - Could not obtain the value of the ADHOCID keyword in the
	  LME-PROFS-DIAMEX section.  Using the default value 'ADHOC'
	   >> dia2mex(1697)
	  1998/04/15 11:41:25- LME-PROFS-DIAMEX(01bb) 3 31500:Sender: SERVERNAME,
	  Size: 1162, Message ID: c=US;a=
	  ;p=ORG;l=2FDB85F726CFD1118C7200C04FB67969 1998/04/15 11:41:21
	  PROFS:CIMPDEMO
	   >> mexe(3274)
	  1998/04/15 11:41:28- LME-PROFS-DIAMEX(01bb) 4 56150:Created and saved a
	  correlation table entry with key '2FDB85F726CFD1118C7200C04FB67969'
	   >> dia2mex(3450)
	  1998/04/15 11:41:28- LME-PROFS-DIAMEX(01bb) 4 04114:Queue item
	  q\vm2mex.in\50000001.rdy has been dequeued from queue vm2mex.in
	   >> qm(3731)
	  1998/04/15 11:41:30- LME-PROFS-MEXIN(0231) 3 31500:Sender: SERVERNAME,
	  Size: 1162, Message ID: c=US;a=
	  ;p=ORG;l=2FDB85F726CFD1118C7200C04FB67969 1998/04/15 11:41:21 Microsoft
	  Exchange
	   >> mexe(3274)
	
	
	Additional query words:
	
	======================================================================
	Keywords          : exc55sp2fix 
	Technology        : kbZNotKeyword6 kbExchangeSearch kbExchange550 kbZNotKeyword2 kbLinkAgeSearch kbLinkAge320
	Version           : :3.2,5.5
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
