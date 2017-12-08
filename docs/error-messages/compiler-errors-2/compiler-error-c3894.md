---
title: "컴파일러 오류 C3894 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3894
dev_langs:
- C++
helpviewer_keywords:
- C3894
ms.assetid: 6d5ac903-1dea-431d-8e3a-cebca4342983
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 46dffabb57e871e1635738434e7efb4812850379
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3894"></a>컴파일러 오류 C3894
'var': 'class' 클래스의 클래스 생성자 에서만 initonly 정적 데이터 멤버의 l 값 사용할 수는  
  
 정적 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버만 선언 또는 정적 생성자에서는 해당 지점에서 l-value로 사용할 수 있습니다.  
  
 인스턴스 (비정적) initonly 데이터 멤버 또는 인스턴스 (비정적) 생성자 선언 지점에서 l-value로 사용할 수 있습니다.  
  
 다음 샘플에서는 C3894 오류가 생성 됩니다.  
  
```  
// C3894.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly static int data_var = 0;  
  
public:  
   // class constructor  
   static Y1() {  
      data_var = 99;   // OK  
      System::Console::WriteLine("in static constructor");  
   }  
  
   // not the class constructor  
   Y1(int i) {  
      data_var = i;   // C3894  
   }  
  
   static void Test() {}  
  
};  
  
int main() {  
   Y1::data_var = 88;   // C3894  
   int i = Y1::data_var;  
   Y1 ^ MyY1 = gcnew Y1(99);  
   Y1::Test();  
}  
```