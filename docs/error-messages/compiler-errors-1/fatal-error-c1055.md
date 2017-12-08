---
title: "심각한 오류 C1055 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1055
dev_langs:
- C++
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 68b9dc5ac8a574111a678086a03e2760941e766f
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1055"></a>심각한 오류 C1055
컴파일러 한계: 키가 부족  
  
 소스 파일에 너무 많은 기호가 있습니다. 컴파일러는 기호 테이블에 대 한 해시 키 부족합니다.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>아래의 해결 방법 따라 수정합니다.  
  
1.  소스 파일을 더 작은 파일로 분할 합니다.  
  
2.  불필요 한 헤더 파일을 제거 합니다.  
  
3.  새 계정을 만드는 대신 임시 및 전역 변수를 다시 사용 합니다.