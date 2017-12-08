---
title: "컴파일러 오류 C3723 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3723
dev_langs:
- C++
helpviewer_keywords:
- C3723
ms.assetid: ef0fb1ff-3f9a-4093-a6b6-894d1ab0c4b9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6406d664cea17b75fa9ff703ae15e26d7baf042c
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3723"></a>컴파일러 오류 C3723
'function': 이벤트를 확인할 수 없습니다.  
  
 `function`호출할 이벤트를 확인할 수 없습니다.  
  
 다음 샘플에서는 C3723 오류가 생성 됩니다.  
  
```  
// C3723.cpp  
struct A {  
   // To resolve, comment void f(int); and uncomment the __event function  
   void f(int);  
   // __event void f(int);  
   void f(float);  
  
};  
  
struct B {  
   void g(int);  
   B(A* a) {  
   __hook(&A::f, a, &B::g);   // C3723  
   }  
};  
  
int main() {  
}  
```  
  
 `__hook`및 `__unhook` /clr 프로그래밍와 호환 되지 않습니다.  + = 및-= 연산자를 대신 사용 합니다.  
  
 다음 샘플에서는 C3723 오류가 생성 됩니다.  
  
```  
// C3723b.cpp  
// compile with: /clr  
using namespace System;  
  
public delegate void delegate1();  
  
public ref class CPSource {  
public:  
   event delegate1^ event1;  
};  
  
public ref class CReceiver {  
public:  
   void Handler1() {  
   }  
  
   void UnhookAll(CPSource^ pSrc) {  
      __unhook(&CPSource::event1, pSrc, &CReceiver::Handler1); // C3723  
      // Try the following line instead.  
      // pSrc->event1 -= gcnew delegate1(this, &CReceiver::Handler1);  
   }  
};  
  
int main() {  
}  
```