---
title: OMP_DYNAMIC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OMP_DYNAMIC
dev_langs: C++
helpviewer_keywords: OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b5c416919678cd7b0f80bd1299c7682fe159cd19
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ompdynamic"></a>OMP_DYNAMIC
실행 시간 OpenMP 병렬 영역에 있는 스레드의 수를 조정할 수 있는지 여부를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>설명  
 `OMP_DYNAMIC` 환경 변수 재정의 될 수 있습니다는 [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) 함수입니다.  
  
 OpenMP 표준의 Visual c + + 구현에서 기본값은 `OMP_DYNAMIC=FALSE`합니다.  
  
 자세한 내용은 참조 [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md)합니다.  
  
## <a name="example"></a>예제  
 다음 명령 집합의 `OMP_DYNAMIC` 환경 변수를 true로:  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 다음 명령은의 현재 설정을 표시는 `OMP_DYNAMIC` 환경 변수:  
  
```  
set OMP_DYNAMIC  
```  
  
## <a name="see-also"></a>참고 항목  
 [환경 변수](../../../parallel/openmp/reference/openmp-environment-variables.md)