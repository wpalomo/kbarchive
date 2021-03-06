---
layout: page
title: "Q173823: HOWTO: Aggregate a COM Object with ATL"
permalink: /kb/173/Q173823/
---

## Q173823: HOWTO: Aggregate a COM Object with ATL

{% raw %}

	Article: Q173823
	Product(s): Microsoft C Compiler
	Version(s): 2.1,3.0,5.0,6.0
	Operating System(s): 
	Keyword(s): kbActiveX kbATL210 kbCOMt kbVC500 kbVC600 kbATL300 kbGrpDSMFCATL kbArchitecture
	Last Modified: 12-JUN-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- The Microsoft Active Template Library (ATL), versions 2.1, 3.0, used with:
	   - Microsoft Visual C++, 32-bit Enterprise Edition, versions 5.0, 6.0 
	   - Microsoft Visual C++, 32-bit Professional Edition, versions 5.0, 6.0 
	   - Microsoft Visual C++, 32-bit Learning Edition, version 6.0 
	   - Microsoft Visual C++.NET (2002) 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	The following steps demonstrate how to aggregate a COM object in an ATL
	project:
	
	1. Add an IUnknown pointer to your class object and initialize it to NULL in the
	  constructor.
	
	2. Add the DECLARE_PROTECT_FINAL_CONSTRUCT macro to protect your object from
	  being deleted if (during FinalConstruct) the internal aggregated object
	  increments the reference count then decrements the count to 0.
	
	  NOTE: If you are using Visual C++.NET the Wizard adds this for you.
	
	3. Use the IUnknown pointer you defined as the second parameter to the
	  COM_INTERFACE_ENTRY_AGGREGATE macros. The first parameter is the IID of the
	  interface of the inner object that you want to expose.
	
	4. Override FinalConstruct() to create the aggregate.
	
	5. Override FinalRelease() to release the IUnknown pointer.
	
	MORE INFORMATION
	================
	
	If you use and release an interface from the aggregate during FinalConstruct,
	you should add the DECLARE_PROTECT_FINAL_CONSTRUCT macro to the definition of
	your class object.
	
	Here is a sample with all four of the steps done in the class definition. This is
	a simple object, COutObj, which aggregates another simple object, CInnObj.
	
	Sample Code
	-----------
	
	     class ATL_NO_VTABLE COutObj :
	           public CComObjectRootEx<CComSingleThreadModel>,
	           public CComCoClass<COutObj, &CLSID_OutObj>,
	           public IDispatchImpl<IOutObj, &IID_IOutObj, &LIBID_OUTEROBJLib>
	     {
	     public:
	        COutObj() : m_pInnerUnk(NULL) // Step 1
	        {
	        }
	        DECLARE_GET_CONTROLLING_UNKNOWN()
	        DECLARE_REGISTRY_RESOURCEID(IDR_OUTOBJ)
	        DECLARE_PROTECT_FINAL_CONSTRUCT() // Step 2
	
	        BEGIN_COM_MAP(COutObj)
	           COM_INTERFACE_ENTRY(IOutObj)
	           COM_INTERFACE_ENTRY(IDispatch)
	           COM_INTERFACE_ENTRY_AGGREGATE(IID_IInnObj, m_pInnerUnk) // Step 3
	        END_COM_MAP()
	
	        // Start of step 4
	        HRESULT FinalConstruct()
	        {
	           HRESULT hr;
	           CLSID   clsidInner;
	
	           hr = CLSIDFromProgID(L"InnObj.InnObj.1", &clsidInner);
	           if (hr == S_OK)
	              hr = CoCreateInstance(clsidInner, GetControllingUnknown(),
	                                    CLSCTX_INPROC_SERVER, IID_IUnknown,
	                                    (void**)&m_pInnerUnk);
	           return hr;
	        } // End of step 4
	
	        void FinalRelease(){m_pInnerUnk->Release();} // Step 5
	
	        // IOutObj
	     public:
	        STDMETHOD(Test)();
	     private:
	        LPUNKNOWN m_pInnerUnk; // Step 1
	     };
	
	If the inner object is in the same ATL server, then you can use the following
	code to create the inner object without CoCreateInstance:
	
	     HRESULT FinalConstruct()
	        {
	           return  CInnObj::_CreatorClass::CreateInstance(
	               GetControllingUnknown(), IID_IUnknown,
	               (void**)&m_pInnerUnk);
	
	        }
	
	REFERENCES
	==========
	
	Visual C++ Books Online: Visual C++ Books; C/C++ Language and C++ Library;
	Active Template Library; Articles; Introduction to COM and ATL; Introduction to
	COM; Aggregation
	
	Visual C++ Books Online: Visual C++ Books; C/C++ Language and C++ Library; Active
	Template Library; Articles; Fundamentals of ATL COM Objects; Creating an
	Aggregate
	
	(c) Microsoft Corporation 1997, All Rights Reserved.
	Contributions by Chuck Bell, Microsoft Corporation
	
	
	Additional query words: derive override kbATL210 kbATL300 kbctrl kbserver
	
	======================================================================
	Keywords          : kbActiveX kbATL210 kbCOMt kbVC500 kbVC600 kbATL300 kbGrpDSMFCATL kbArchitecture 
	Technology        : kbVCsearch kbAudDeveloper kbATLsearch
	Version           : :2.1,3.0,5.0,6.0
	Issue type        : kbhowto
	
	=============================================================================
	

{% endraw %}
