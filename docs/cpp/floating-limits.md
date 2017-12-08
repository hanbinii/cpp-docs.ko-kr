---
title: "부동 한계 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- FLOAT.H header file
- limits, floating-point constants
- floating-point numbers [C++]
- floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cb5257b9b70750172a79b4c22a7da6c728664807
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="floating-limits"></a>부동 한계
**Microsoft 전용**  
  
 다음 표에는 부동 소수점 상수의 값에 대한 제한이 나와 있습니다. 이러한 제한은 표준 헤더 파일 FLOAT.H에서도 정의됩니다.  
  
### <a name="limits-on-floating-point-constants"></a>부동 소수점 상수에 대한 제한  
  
|상수|의미|값|  
|--------------|-------------|-----------|  
|FLT_DIG DBL_DIG LDBL_DIG|소수 자릿수가 q인 부동 소수점 수가 부동 소수점 표현으로 반올림되고 정밀도의 손실 없이 다시 복원될 수 있는 자릿수 q입니다.|6 15 15|  
|FLT_EPSILON DBL_EPSILON LDBL_EPSILON|x + 1.0이 1.0과 같지 않은 가장 작은 양수 x입니다.|1.192092896e-07F 2.2204460492503131e-016 2.2204460492503131e-016|  
|FLT_GUARD||0|  
|FLT_MANT_DIG DBL_MANT_DIG LDBL_MANT_DIG|부동 소수점 유효 숫자에서 FLT_RADIX로 지정된 기수의 자릿수입니다. 기 수는 2입니다. 따라서 이러한 값이 비트를 지정 합니다.|24 53 53|  
|FLT_MAX DBL_MAX LDBL_MAX|최대 표현 가능한 부동 소수점 수입니다.|3.402823466e+38F 1.7976931348623158e+308 1.7976931348623158e+308|  
|FLT_MAX_10_EXP DBL_MAX_10_EXP LDBL_MAX_10_EXP|숫자에 10이 더해진 최대 정수는 표현 가능한 부동 소수점 숫자입니다.|38 308 308|  
|FLT_MAX_EXP DBL_MAX_EXP LDBL_MAX_EXP|FLT_RADIX를 해당 수만큼 거듭제곱한 값이 표현 가능한 부동 소수점 수인 최대 정수입니다.|128 1024 1024|  
|FLT_MIN DBL_MIN LDBL_MIN|최소 양수 값입니다.|1.175494351e-38F 2.2250738585072014 e-308 2.2250738585072014 e-308|  
|FLT_MIN_10_EXP DBL_MIN_10_EXP LDBL_MIN_10_EXP|숫자에 10이 더해진 최소 음의 정수는 표현 가능한 부동 소수점 숫자입니다.|-37<br /><br /> -307<br /><br /> -307|  
|FLT_MIN_EXP DBL_MIN_EXP LDBL_MIN_EXP|FLT_RADIX를 해당 수만큼 거듭제곱한 값이 표현 가능한 부동 소수점 수인 최소 음의 정수입니다.|-125<br /><br /> -1021<br /><br /> -1021|  
|FLT_NORMALIZE||0|  
|FLT_RADIX _DBL_RADIX _LDBL_RADIX|지수를 표현하는 기수입니다.|2 2 2|  
|FLT_ROUNDS _DBL_ROUNDS _LDBL_ROUNDS|추가할 수 있도록 부동 소수점 반올림 모드입니다.|1 (near) 1 (near) 1 (near)|  
  
> [!NOTE]
>  표의 정보는 제품의 이후 버전에서 달라질 수 있습니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [정수 제한](../cpp/integer-limits.md)