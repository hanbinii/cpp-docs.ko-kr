---
title: "컴파일러 오류 C2415 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2415
dev_langs:
- C++
helpviewer_keywords:
- C2415
ms.assetid: f225c913-2bea-46b1-b096-3d358ac94a15
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 68666ba203897b43fb1658525e1f342bcb923c09
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2415"></a>컴파일러 오류 C2415
잘못 된 피연산자 형식  
  
 Opcode이 형식의 피연산자를 사용 하지 않습니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  Opcode 사용 된 피연산자의 수를 지원 하지 않습니다. 피연산자의 정확한 수를 결정 하는 어셈블리 언어 참조 설명서를 확인 합니다.  
  
2.  최신 프로세서는 추가 형식 사용 하는 명령을 지원합니다. 조정 된 [/arch (최소 CPU 아키텍처)](../../build/reference/arch-minimum-cpu-architecture.md) 나중에 프로세서를 사용 하는 옵션입니다.