---
title: "밑 절을 사용 하 여 A.22 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a3fa4e62-1e92-4896-ae3f-be268067d917
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ec1cd9d6b716fbe39412ccd073c6183ccf52fd97
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="a22---using-the-defaultnone-clause"></a>A.22   default(none) 절 사용
다음 예제에서는 구별의 영향을 받는 변수는 `default(none)` 하지 않은 절:  
  
```  
// openmp_using_clausedefault.c  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int x, y, z[1000];  
#pragma omp threadprivate(x)  
  
void fun(int a) {  
   const int c = 1;  
   int i = 0;  
  
   #pragma omp parallel default(none) private(a) shared(z)  
   {  
      int j = omp_get_num_thread();  
             //O.K.  - j is declared within parallel region  
      a = z[j];       // O.K.  - a is listed in private clause  
                      //      - z is listed in shared clause  
      x = c;          // O.K.  - x is threadprivate  
                      //      - c has const-qualified type  
      z[i] = y;       // C3052 error - cannot reference i or y here  
  
      #pragma omp for firstprivate(y)  
         for (i=0; i<10 ; i++) {  
            z[i] = y;  // O.K. - i is the loop control variable  
                       // - y is listed in firstprivate clause  
          }  
       z[i] = y;   // Error - cannot reference i or y here  
   }  
}  
```  
  
 대 한 자세한 내용은 `default` 절 참조 [섹션 2.7.2.5](../../parallel/openmp/2-7-2-5-default.md) 페이지 28입니다.