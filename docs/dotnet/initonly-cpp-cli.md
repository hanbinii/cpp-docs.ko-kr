---
title: initonly (C + + /cli CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- initonly_cpp
- initonly
dev_langs: C++
helpviewer_keywords: initonly attribute [C++]
ms.assetid: f745d7fa-dc08-46f1-9b97-0977be58a008
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7957c92ca243a9055bfce62232067e51b3f395d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="initonly-ccli"></a>initonly(C++/CLI)
**initonly** 해당 변수 할당을 나타내는 상황에 맞는 키워드는 선언 또는 동일한 클래스의 정적 생성자의 일부로 서만 발생할 수 있습니다.  
  
 다음 예제에서는 `initionly`을 사용하는 방법을 보여 줍니다.  
  
```  
// mcpp_initonly.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int staticConst1;  
  
   initonly  
   static int staticConst2 = 0;  
  
   static Y1() {  
      staticConst1 = 0;  
   }  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [클래스 및 구조체](../windows/classes-and-structs-cpp-component-extensions.md)