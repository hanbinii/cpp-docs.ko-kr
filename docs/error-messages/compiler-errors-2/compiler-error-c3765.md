---
title: "컴파일러 오류 C3765 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3765
dev_langs:
- C++
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 44311ab210a85b05d86eb48aebe8294c95bfb5ab
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3765"></a>컴파일러 오류 C3765
'event': event_receiver로 표시 된 'type' 클래스/구조체에는 이벤트를 정의할 수 없습니다  
  
 클래스에 표시 되는 경우는 [event_receiver](../../windows/event-receiver.md) 특성 클래스를 포함할 수 없습니다는 [__event](../../cpp/event.md) 선언 합니다.  
  
 다음 샘플에서는 C3765 오류가 생성 됩니다.  
  
```  
// C3765.cpp  
[event_receiver(native)]  
struct ER2 {  
   __event void f();   // C3765  
   __event void b(int);   // C3765  
};  
```