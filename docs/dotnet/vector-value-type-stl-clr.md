---
title: 'vector:: value_type (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector::value_type
dev_langs: C++
helpviewer_keywords: value_type member [STL/CLR]
ms.assetid: d8777470-5e7f-40d5-966c-a3c518d1f54c
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 937b02368e2faf2427460db3fe944f33b097511d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="vectorvaluetype-stlclr"></a>vector::value_type(STL/CLR)
요소의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef Value value_type;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 템플릿 매개 변수 `Value`의 동의어입니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_vector_value_type.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c" using value_type   
    for (cliext::vector<wchar_t>::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   // store element in value_type object   
        cliext::vector<wchar_t>::value_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/벡터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [vector (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [vector:: const_reference (STL/CLR)](../dotnet/vector-const-reference-stl-clr.md)   
 [vector::reference(STL/CLR)](../dotnet/vector-reference-stl-clr.md)