---
title: "컴파일러 오류 C3027 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3027
dev_langs: C++
helpviewer_keywords: C3027
ms.assetid: 6562a5c2-2f28-4b36-91ca-2a64c0f0501a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f5d1302b5572d145a30efcde0ed4bf12babd671d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3027"></a>컴파일러 오류 C3027
'clause': 산술 식 또는 포인터 식이 필요합니다.  
  
 산술 식 또는 포인터 식이 필요한 절에 다른 종류의 식이 전달되었습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3027을 생성합니다.  
  
```  
// C3027.cpp  
// compile with: /openmp /link vcomps.lib  
#include <stdio.h>  
#include "omp.h"  
  
struct MyStruct   
{  
    int x;  
} m_MyStruct;  
  
int main()   
{  
    int i;  
  
    puts("Test with class MyStruct:\n");  
    #pragma omp parallel for if(m_MyStruct)   // C3027  
    for (i = 1; i <= 2; ++i)  
        printf_s("Hello World - thread %d - iteration %d\n",  
                 omp_get_thread_num(), i);  
  
    puts("Test with int:\n");  
    #pragma omp parallel for if(9)   // OK  
    for (i = 1; i <= 2; ++i)  
        printf_s("Hello World - thread %d - iteration %d\n",  
                 omp_get_thread_num(), i);  
}  
```