---
title: 'hash_multiset:: to_array (STL/CLR) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::hash_multiset::to_array
dev_langs: C++
helpviewer_keywords: to_array member [STL/CLR]
ms.assetid: fc28b42a-a8fe-4953-887b-8a12957d4778
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 36e52be2a66b019a5f6487daf0c01106e1b8a40b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="hashmultisettoarray-stlclr"></a>hash_multiset::to_array(STL/CLR)
제어 되는 새 배열에 복사합니다.  
  
## <a name="syntax"></a>구문  
  
```  
cli::array<value_type>^ to_array();  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수는 제어 되는 시퀀스를 포함 하는 배열을 반환 합니다. 배열 형식으로 제어 되는 시퀀스의 복사본을 사용 하면 됩니다.  
  
## <a name="example"></a>예제  
  
```  
// cliext_hash_multiset_to_array.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// copy the container and modify it   
    cli::array<wchar_t>^ a1 = c1.to_array();   
  
    c1.insert(L'd');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
a b c d  
a b c  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/hash_set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [hash_multiset(STL/CLR)](../dotnet/hash-multiset-stl-clr.md)