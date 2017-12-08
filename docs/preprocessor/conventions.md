---
title: "규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "전처리기"
  - "전처리기, 규칙"
ms.assetid: 469ce448-dc6c-4d0e-ba2b-e2e7a10155e1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 규칙
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

규칙은 구문의 여러 구성 요소에 대해 여러 글꼴 특성을 사용합니다.  기호 및 글꼴은 다음과 같습니다.  
  
|특성|설명|  
|--------|--------|  
|*nonterminal*|기울임꼴은 비터미널을 나타냅니다.|  
|\#include|굵게 표시된 터미널은 다음과 같이 입력해야 할 리터럴 예약어 및 기호입니다.  이 컨텍스트의 문자는 항상 대\/소문자를 구분합니다.|  
|opt|뒤에 opt가 오는 비터미널은 항상 선택 사항입니다.|  
|default typeface|이 서체에서 설명하거나 나열된 집합의 문자를 C 문의 터미널로 사용될 수 있습니다.|  
  
 비터미널 뒤에 오는 콜론\(:\)은 정의를 지정합니다.  다른 정의는 별도의 줄에 나열됩니다.  
  
## 참고 항목  
 [문법 요약](../preprocessor/grammar-summary-c-cpp.md)