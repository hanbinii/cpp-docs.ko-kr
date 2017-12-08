---
title: "컴파일러 오류 C3485 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3485
dev_langs: C++
helpviewer_keywords: C3485
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cd49b93beb54776bf17a9ee2bc5c9816f0964451
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3485"></a>컴파일러 오류 C3485
람다 정의에 cv 한정자를 사용할 수 없습니다.  
  
 `const` 또는 `volatile` 한정자를 람다 식 정의의 일부로 사용할 수 없습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   람다 식 정의에서 `const` 또는 `volatile` 한정자를 제거합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `const` 한정자를 람다 식 정의의 일부로 사용하므로 C3485가 생성됩니다.  
  
```  
// C3485.cpp  
  
int main()  
{  
   auto x = []() const mutable {}; // C3485  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../cpp/lambda-expressions-in-cpp.md)