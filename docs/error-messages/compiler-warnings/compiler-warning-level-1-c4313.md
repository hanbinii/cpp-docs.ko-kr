---
title: "컴파일러 경고 (수준 1) C4313 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4313
dev_langs: C++
helpviewer_keywords: C4313
ms.assetid: bcf64191-e2cf-452e-97b4-423fcec2d07c
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ea63b3a60d2fb3ba45175ae41fb629aac42894d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4313"></a>컴파일러 경고(수준 1) C4313
'function': 서식 문자열의 'format specifier'가 형식 'type'의 인수 번호와 충돌합니다.  
  
 지정된 서식과 전달 중인 값이 충돌합니다. 예를 들어 32비트 정수 매개 변수가 필요한 정규화되지 않은 %d 서식 지정자에 64비트 매개 변수를 전달했습니다. 이 경고는 코드가 64비트 대상에 대해 컴파일될 때만 적용됩니다.  
  
## <a name="example"></a>예제  
 다음 코드 샘플에서는 64비트 대상에 대해 컴파일할 경우 C4313 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4313.cpp  
// Compile by using: cl /W1 C4313.cpp  
#include <stdio.h>  
int main() {  
   int * pI = 0;  
   printf("%d", pI);   // C4313 on 64-bit platform code  
   // Try one of the following lines instead:  
   // printf("%p\n", pI);  
   // printf("%Id\n", pI);   // %I64d expects 64-bits of information  
}  
```