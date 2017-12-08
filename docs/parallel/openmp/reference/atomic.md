---
title: "원자성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: atomic
dev_langs: C++
helpviewer_keywords: atomic OpenMP directive
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 92804b2bdcc243bde6e536004cda73d7f5087b1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="atomic"></a>원자성(atomic)
지정 하는 원자적으로 업데이트할 수 있는 메모리 위치 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### <a name="parameters"></a>매개 변수  
 `expression`  
 여러 쓰기에 대 한 보호 하려는 해당 메모리 위치에서 lvalue를 포함 하는 문입니다. 올바른 식 양식에 대 한 자세한 내용은 OpenMP 사양을 참조 하십시오.  
  
## <a name="remarks"></a>설명  
 `atomic` 지시문 OpenMP 절을 지원 합니다.  
  
 자세한 내용은 참조 [2.6.4 atomic 생성](../../../parallel/openmp/2-6-4-atomic-construct.md)합니다.  
  
## <a name="example"></a>예제  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
```Output  
Number of threads: 10  
```  
  
## <a name="see-also"></a>참고 항목  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)