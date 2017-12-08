---
title: "컴파일러 오류 C2953 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2953
dev_langs:
- C++
helpviewer_keywords:
- C2953
ms.assetid: 8dbcfa24-8296-4e40-bdc4-5526c07d8892
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 147c5c837a40dd2a6b2507a576efe9046160e87c
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2953"></a>컴파일러 오류 C2953
'identifier': 클래스 템플릿이 이미 정의되었습니다.  
  
 소스 파일을 확인하고 다른 정의에 대한 파일을 포함합니다.  
  
 다음 샘플에서는 C2953을 생성합니다.  
  
```  
// C2953.cpp  
// compile with: /c  
template <class T>  class A {};  
template <class T>  class A {};   // C2953  
template <class T>  class B {};   // OK  
```