---
title: "컴파일러 오류 C3010 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3010
dev_langs: C++
helpviewer_keywords: C3010
ms.assetid: e959d038-bba6-432a-9c0a-0470474de7d9
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cb72ab844831c277271b5f531bd240ed35744d64
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3010"></a>컴파일러 오류 C3010
'label': OpenMP 구조화된 블록 내부에서 외부로 점프할 수 없습니다.  
  
 코드가 OpenMP 블록 안이나 밖으로 점프할 수 없습니다.  
  
 다음 샘플에서는 C3010을 생성합니다.  
  
```  
// C3010.c  
// compile with: /openmp  
int main() {  
   #pragma omp parallel   
   {  
      #pragma omp parallel  
      {  
         goto lbl3;  
      }  
   }  
   lbl3:;   // C3010  
}  
```