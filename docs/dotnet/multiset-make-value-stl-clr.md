---
title: "multiset::make_value(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multiset::make_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_value 멤버[STL/CLR]"
ms.assetid: 385ded5b-65bf-4806-8c3d-a4129a05f612
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# multiset::make_value(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Constructs a value object.  
  
## 구문  
  
```  
static value_type make_value(key_type key);  
```  
  
#### 매개 변수  
 key  
 Key value to use.  
  
## 설명  
 The member function returns a `value_type` object whose key is `key`.  You use it to compose an object suitable for use with several other member functions.  
  
## 예제  
  
```  
// cliext_multiset_make_value.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(Mymultiset::make_value(L'a'));   
    c1.insert(Mymultiset::make_value(L'b'));   
    c1.insert(Mymultiset::make_value(L'c'));   
  
// display contents " a b c"   
    for each (Mymultiset::value_type elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**   
## 요구 사항  
 **Header:** \<cliext\/set\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::key\_type](../dotnet/multiset-key-type-stl-clr.md)   
 [multiset::value\_type](../dotnet/multiset-value-type-stl-clr.md)