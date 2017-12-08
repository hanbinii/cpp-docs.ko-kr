---
title: "부호 있는 비트 연산 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- bitwise operations
- signed bitwise operations
ms.assetid: 1e5cf65b-ee32-41a0-a5c2-82c1854091f6
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9ffc5335bb28e619f166a524083937d17a59bb97
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="signed-bitwise-operations"></a>부호 있는 비트 연산
**ANSI 3.3** 부호 있는 정수에 대한 비트 연산의 결과  
  
 부호 있는 정수에 대한 비트 연산은 부호 없는 정수에 대한 비트 연산과 동일하게 작동합니다. 예를 들어, `-16 & 99`는 이진 형식으로 다음과 같이 표현될 수 있습니다.  
  
```  
  11111111 11110000  
& 00000000 01100011  
  _________________  
  00000000 01100000  
```  
  
 비트 AND의 결과는 96입니다.  
  
## <a name="see-also"></a>참고 항목  
 [정수](../c-language/integers.md)