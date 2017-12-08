---
title: "컴파일러 오류 C3719 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3719
dev_langs: C++
helpviewer_keywords: C3719
ms.assetid: d0d59d4e-babb-4480-9ef7-70cf1a28165c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 06cdce1925470ce8af8df78e50f069763addb150
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3719"></a>컴파일러 오류 C3719
'interface': COM 이벤트 인터페이스 기반된 이벤트 소스 에서만 사용할 수 있습니다  
  
 COM이 아닌 컨텍스트에서 인터페이스를 선언 합니다.  
  
 다음 샘플에서는 C3719 오류가 생성 됩니다.  
  
```  
// C3719a.cpp  
#define _ATL_ATTRIBUTES 1  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];  
  
[object]  
__interface I {  
   HRESULT func1();  
};  
  
[event_source(native), coclass]  
struct A {  
   __event __interface I;   // C3719  
  
   // try the following line instead  
   // __event func2();  
};  
  
int main() {  
}  
```  
  
 이 오류를 해결 하려면 적용는 [개체](../../windows/object-cpp.md), [coclass](../../windows/coclass.md), [event_source](../../windows/event-source.md), 및 [event_receiver](../../windows/event-receiver.md) 특성을 적절 하 게 확인 하는 COM 인터페이스 클래스를 사용 하는 클래스입니다. 예:  
  
```  
// C3719b.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[module(name="xx")];  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I {  
   HRESULT f();  
};  
  
[coclass, event_source(com) , uuid("00000000-0000-0000-0000-000000000002")]  
struct MyStruct {  
   __event __interface I;  
};  
  
[event_receiver(com)]  
struct MyStruct2 {  
   void f() {  
   }  
   MyStruct2(I* pB) {  
      __hook(&I::f, pB, &MyStruct2::f);  
   }  
};  
  
int main()  
{  
}  
```