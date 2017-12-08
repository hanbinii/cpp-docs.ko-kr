---
title: "bad_weak_ptr 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: memory/std::bad_weak_ptr
dev_langs: C++
helpviewer_keywords:
- bad_weak_ptr
- bad_weak_ptr class
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5cd4d1b82b4736b49c476d2f336a4b03db27bd51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="badweakptr-class"></a>bad_weak_ptr 클래스
불량 weak_ptr 예외를 보고합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class bad_weak_ptr : public std::exception 
 {  
public:  
    bad_weak_ptr();
    const char *what() throw();
 };  
```  
  
## <a name="remarks"></a>설명  
 이 클래스는 [weak_ptr 클래스](../standard-library/weak-ptr-class.md) 형식의 인수를 사용하는 [shared_ptr 클래스](../standard-library/shared-ptr-class.md) 생성자에서 throw될 수 있는 예외를 설명합니다. 멤버 함수 `what`에서 `"bad_weak_ptr"`을 반환합니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// std__memory__bad_weak_ptr.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
 
int main()
{
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int);
        wp = sp;
    }

    try
    {
        std::shared_ptr<int> sp1(wp); // weak_ptr has expired   
    }
    catch (const std::bad_weak_ptr&)
    {
        std::cout << "bad weak pointer" << std::endl;
    }
    catch (...)
    {
        std::cout << "unknown exception" << std::endl;
    }

    return (0);
}
```  
  
```Output  
bad weak pointer  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<memory>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [weak_ptr 클래스](../standard-library/weak-ptr-class.md)