---
title: 'hash_multiset:: value_type (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multiset::value_type
dev_langs: C++
helpviewer_keywords: value_type member [STL/CLR]
ms.assetid: 8f9cd362-28e7-4916-af4e-c37e780e097c
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 351bb06f697fa896f12f38e76b9cbd24cbf7b96f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="hashmultisetvaluetype-stlclr"></a>hash_multiset::value_type(STL/CLR)
요소의 형식입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef generic_value value_type;  
```  
  
## <a name="remarks"></a>설명  
 이 형식은 `generic_value`의 동의어입니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_multiset_value_type.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" using value_type   
    for (Myhash_multiset::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in value_type object   
        Myhash_multiset::value_type val = *it;   
  
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
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)   
 [hash_multiset:: const_reference (STL/CLR)](../dotnet/hash-multiset-const-reference-stl-clr.md)   
 [hash_multiset:: key_type (STL/CLR)](../dotnet/hash-multiset-key-type-stl-clr.md)   
 [hash_multiset::reference(STL/CLR)](../dotnet/hash-multiset-reference-stl-clr.md)