---
title: "deque::begin(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "begin 멤버[STL/CLR]"
ms.assetid: e99d20d2-bb33-415f-9bd6-fe331d8c2ba2
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# deque::begin(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어되는 시퀀스의 시작을 지정합니다.  
  
## 구문  
  
```  
iterator begin();  
```  
  
## 설명  
 The member function returns a random\-access iterator that designates the first element of the controlled sequence, or just beyond the end of an empty sequence.  이를 통해 제어되는 시퀀스의 `current` 시작을 지정하는 반복기를 가져올 수 있지만 제어되는 시퀀스의 길이가 변경되면 상태가 변경될 수 있습니다.  
  
## 예제  
  
```  
// cliext_deque_begin.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    cliext::deque<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
  
// alter first two items and reinspect   
    *--it = L'x';   
    *++it = L'y';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **a b c**  
**\*begin\(\) \= a**  
**\*\+\+begin\(\) \= b**  
 **x y c**   
## 요구 사항  
 **Header:** \<cliext\/deque\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::end](../dotnet/deque-end-stl-clr.md)   
 [deque::front](../dotnet/deque-front-stl-clr.md)   
 [deque::front\_item](../dotnet/deque-front-item-stl-clr.md)