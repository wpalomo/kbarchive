---
layout: page
title: "Q65392: Cannot Initialize Union Containing Nameless Struct Member"
permalink: /kb/065/Q65392/
---

## Q65392: Cannot Initialize Union Containing Nameless Struct Member

{% raw %}

	Article: Q65392
	Product(s): See article
	Version(s): 6.00   | 6.00
	Operating System(s): MS-DOS | OS/2
	Keyword(s): ENDUSER | buglist6.00 | mspl13_c
	Last Modified: 31-AUG-1990
	
	Initializing a union containing a nameless struct as one of its
	members will cause the following compiler errors:
	
	   error C2097:   illegal initialization
	
	   error C2078:   too many initializers
	
	The sample code shown below reproduces the problem:
	
	union
	{
	   struct
	   {
	      int a;
	      int b;
	   };            // Add a name here to allow initialization
	   long c;
	} x = {{ 0,0 }};
	
	The only workarounds available are to either name the struct or to
	leave the union uninitialized.
	
	Microsoft has confirmed this to be a problem with Microsoft C version
	6.00. We are researching this problem and will post new information
	here as it becomes available.

{% endraw %}
