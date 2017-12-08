---
title: 'pair:: first_type (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::pair::first_type
dev_langs: C++
helpviewer_keywords: first_type member [STL/CLR]
ms.assetid: 8a7792ee-a2f6-4e17-9d0b-9c78007202d9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4c3f34659542e0d4a78c097a11b7ce1ac09e3e72
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="pairfirsttype-stlclr"></a>pair::first_type(STL/CLR)
첫 번째 래핑된 값의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef Value1 first_type;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 `Value1`의 동의어입니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_pair_first_type.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
```Output  
[x, 3]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/유틸리티 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [pair (STL/CLR)](../dotnet/pair-stl-clr.md)   
 [pair:: first (STL/CLR)](../dotnet/pair-first-stl-clr.md)   
 [pair:: second (STL/CLR)](../dotnet/pair-second-stl-clr.md)   
 [pair::second_type(STL/CLR)](../dotnet/pair-second-type-stl-clr.md)