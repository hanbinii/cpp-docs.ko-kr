---
title: "operator&gt;= (pair)(STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::pair::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator>= 멤버[STL/CLR]"
ms.assetid: dcc2decf-3b2b-495d-9fd5-3daba27d5096
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&gt;= (pair)(STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pair greater than or equal comparison.  
  
## 구문  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator>=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### 매개 변수  
 left  
 Left pair to compare.  
  
 right  
 Right pair to compare.  
  
## 설명  
 The operator function returns `!(``left` `<` `right``)`.  You use it to test whether `left` is not ordered before `right` when the two pairs are compared element by element.  
  
## 예제  
  
```  
// cliext_pair_operator_ge.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] >= [x 3] is {0}",   
        c1 >= c1);   
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",   
        c1 >= c2);   
    return (0);   
    }  
  
```  
  
  **\[x, 3\]**  
**\[x, 4\]**  
**\[x 3\] \>\= \[x 3\] is True**  
**\[x 3\] \>\= \[x 4\] is False**   
## 요구 사항  
 **Header:** \<cliext\/utility\>  
  
 **Namespace:** cliext  
  
## 참고 항목  
 [pair](../dotnet/pair-stl-clr.md)   
 [operator\=\= \(pair\)](../dotnet/operator-equality-pair-stl-clr.md)   
 [operator\!\= \(pair\)](../dotnet/operator-inequality-pair-stl-clr.md)   
 [operator\< \(pair\)](../dotnet/operator-less-than-pair-stl-clr.md)   
 [operator\> \(pair\)](../dotnet/operator-greater-than-pair-stl-clr.md)   
 [operator\<\= \(pair\)](../dotnet/operator-less-or-equal-pair-stl-clr.md)