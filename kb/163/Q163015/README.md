---
layout: page
title: "Q163015: Use of &quot;Already Verified&quot; APPC Security from Invoking TPs"
permalink: /kb/163/Q163015/
---

## Q163015: Use of &quot;Already Verified&quot; APPC Security from Invoking TPs

{% raw %}

	Article: Q163015
	Product(s): Microsoft SNA Server
	Version(s): WINDOWS:2.0,2.1,2.11,2.11 SP1,3.0
	Operating System(s): 
	Keyword(s): kbnetwork kbprogrammingkbbuglist
	Last Modified: 12-JUN-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft SNA Server, versions 2.0, 2.1, 2.11, 2.11 SP1, 3.0 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	Customers have often requested a capability for an invoking APPC transaction
	program (TP) to use security option "Already Verified", even in cases where the
	invoking TP was not invoked by some other APPC TP. This capability was always
	available in SNA Server, but somewhat inefficient in implementation. In SNA
	Server and other industry standard implementations of APPC, it is possible to
	implement a "pass through" TP, which could be invoked by the real invoking TP,
	and merely passes on the messages from the original invoking TP.
	
	For a trusted APPC application, it is inefficient to issue originating (that is,
	invoking) APPC conversations on behalf of multiple users using APPC "Already
	Verified" security.
	
	The direct approach would be to issue an [MC_]ALLOCATE APPC verb specifying both
	security=AP_SAME and an arbitrary username in the verb control block (VCB). The
	corresponding action in CPI-C would be to call cmscst(, CM_SECURITY_SAME,) and
	cmscsu( , <someUser> . . .), or provide this information in the symbolic
	destination definition. However, actually doing either of these results in an
	APPC conversation that ignores the value of the username parameter.
	
	CAUSE
	=====
	
	This limitation is behavior specified in version 1.2 of the WOSA WinAPPC and
	WinCPIC specifications. It has been implemented in other APPC libraries, such as
	Communications Manager 1.0.
	
	RESOLUTION
	==========
	
	The SNA Server WinAPPC and WinCPIC APIs will support an extension as follows:
	
	- A TP was invoked by another TP, and now initiates a conversation specifying
	  security type SAME: Any username that might be be specified in the VCB is
	  ignored, and the system will provide the already verified username under
	  which the TP was invoked, and set the "already verified" indicator in the
	  outgoing conversation request. This behavior is unchanged.
	
	- The TP was not invoked by another TP, issues a conversation startup request
	  with security type SAME, and provides a user name: The system will copy the
	  specified username into the outgoing conversation request and set the
	  "already verified" indicator.
	
	- The TP was not invoked by another TP, issues a conversation startup request
	  with security type SAME, but does not provide a user name: The system will
	  check for environment value: AP_SAMENOSUser. If this has a value starting
	  with Y, the system will provide the current logged- on user name in the
	  outgoing conversation request. If the environment value is not defined, or
	  has some other value, the system will provide *no* username in the outgoing
	  conversation request.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in SNA Server versions 2.0, 2.10,
	2.11 and 2.11 Service Pack 1 (SP1).
	
	
	A supported fix is now available, but has not been fully regression-tested and
	should be applied only to systems experiencing this specific problem. Unless you
	are severely impacted by this specific problem, Microsoft recommends that you
	wait for the next Service Pack that contains this fix. Contact Microsoft
	Technical Support for more information.
	
	
	This is a hotfix, and distribution requires manager approval. To receive the
	hotfix, customers must be encountering the bug as described above. You must
	track the customers you send this to and supply them with the next Service Pack
	when it becomes available.
	
	REFERENCES
	==========
	
	For more information on the UnverifiedAP_SAME registry entry (which has been
	replaced with the AP_SAMENOSUser registry entry in SNA Server version 3.0),
	please see the following article in the Microsoft Knowledge Base:
	
	  Q135316 Support for sending User ID on Attach when AP_SAME specified [sna]
	
	Additional query words: SNA APPC CPI-C Already Verified AP_SAME prodsna
	
	======================================================================
	Keywords          : kbnetwork kbprogramming kbbuglist
	Technology        : kbAudDeveloper kbSNAServSearch kbSNAServ300 kbSNAServ200 kbSNAServ211 kbSNAServ210 kbSNAServ211SP1
	Version           : WINDOWS:2.0,2.1,2.11,2.11 SP1,3.0
	
	=============================================================================
	

{% endraw %}
