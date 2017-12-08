---
title: "컴파일러 오류 C3849 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3849
dev_langs: C++
helpviewer_keywords: C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7fbe46ee4f83dc5477eeb67e0debf14fe4f9fad5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3849"></a>컴파일러 오류 C3849
함수 형식을 호출할 'type' 형식의 식에는 모든 숫자의 사용 가능한 연산자 오버 로드에 대 한 const 및/또는 volatile 한정자가 손실  
  
 지정 된 const volatile 형식의 변수에 호출할 수 있습니다 멤버 이상 const-volatile 한정자 사용 함수를 정의 합니다.  
  
 이 오류를 해결 하려면 적절 한 멤버 함수를 제공 합니다. 변환으로 인해 자격이 손실 변환을 const 또는 volatile 한정 된 개체에서 실행할 수 없습니다. 한정자를 얻을 수 있지만 경우 변환에는 한정자를 비워 둘 수 없는 합니다.  
  
 다음 샘플에서는 c3849:  
  
```  
// C3849.cpp  
void glbFunc3(int i, char c)  
{  
   i;  
}  
typedef void (* pFunc3)(int, char);  
  
void glbFunc2(int i)  
{  
   i;  
}  
  
typedef void (* pFunc2)(int);  
  
void glbFunc1()  
{  
}  
typedef void (* pFunc1)();  
  
struct S4  
{  
   operator ()(int i)  
   {  
      i;  
   }  
  
   operator pFunc1() const  
   {  
      return &glbFunc1;  
   }  
  
   operator pFunc2() volatile  
   {  
      return &glbFunc2;  
   }  
  
   operator pFunc3()  
   {  
      return &glbFunc3;  
   }  
  
   // operator pFunc1() const volatile  
   // {  
   //    return &glbFunc1;  
   // }  
};  
  
int main()  
{  
   // Cannot call any of the 4 overloads of "operator ()(.....)" and   
   // "operator pFunc()" because none is declared as "const volatile"  
   const volatile S4 s4;  // can only call cv member functions of S4  
   s4();   // C3849 to resolve, uncomment member function  
}  
```