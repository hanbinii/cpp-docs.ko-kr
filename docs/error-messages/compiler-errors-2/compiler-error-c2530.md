---
title: "컴파일러 오류 C2530 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2530
dev_langs: C++
helpviewer_keywords: C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f9438937ad99e66d9e623e1e3703dc6496f8153a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2530"></a>컴파일러 오류 C2530
'identifier': 참조를 초기화 합니다  
  
 초기화 해야 대 한 참조를 선언할 때 이미 선언 되지 않은:  
  
-   키워드와 함께 [extern](../../cpp/using-extern-to-specify-linkage.md)합니다.  
  
-   클래스, 구조체 또는 공용 구조체의 멤버로 (및 생성자에서 초기화).  
  
-   매개 변수로 함수 선언 또는 정의 합니다.  
  
-   으로 함수의 반환 형식입니다.  
  
 다음 샘플에서는 C2530 오류가 생성 됩니다.  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```