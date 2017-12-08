---
title: "컴파일러 오류 C2577 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2577
dev_langs: C++
helpviewer_keywords: C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: df2e681274c21b639c6b188346b355167de7ce03
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2577"></a>컴파일러 오류 C2577
'member': 소멸자/종료자는 반환 형식을 가질 수 없습니다  
  
 소멸자 또는 종료자의 값을 반환할 수 `void` 또는 기타 형식입니다. 제거는 `return` 소멸자 정의에서 문입니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2577 오류가 발생 합니다.  
  
```  
// C2577.cpp  
// compile with: /c  
class A {  
public:  
   A() {}  
   ~A(){  
      return 0;   // C2577  
   }  
};  
```