---
title: "컴파일러 오류 C3036 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3036
dev_langs: C++
helpviewer_keywords: C3036
ms.assetid: 10c6993e-bc42-4a07-85c7-cdc34ac30906
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7682dc0aa8421c7febbc2c8eafe576867ed70ed3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3036"></a>컴파일러 오류 C3036
'operator': OpenMP 'reduction' 절에 잘못된 연산자 토큰이 있습니다.  
  
 [reduction](../../parallel/openmp/reference/reduction.md) 절을 올바르게 지정하지 않았습니다.  
  
 다음 샘플에서는 C3036을 생성합니다.  
  
```  
// C3036.cpp  
// compile with: /openmp  
static float a[1000], b[1000], c[1000];  
void test1(int first, int last) {  
   static float dp = 0.0f;  
   #pragma omp for nowait reduction(.:dp)   // C3036  
   // try the following line instead  
   // #pragma omp for nowait reduction(+: dp)  
   for (int i = first ; i <= last ; ++i)  
      dp += a[i] * b[i];  
}  
```