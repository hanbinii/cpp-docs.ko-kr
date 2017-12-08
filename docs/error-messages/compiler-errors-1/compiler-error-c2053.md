---
title: "컴파일러 오류 C2053 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2053
dev_langs:
- C++
helpviewer_keywords:
- C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1790a1b99493f4b10cc3193f11e63af6901a8d2c
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2053"></a>컴파일러 오류 C2053
'identifier': 와이드 문자열이 일치 하지 않습니다.  
  
 와이드 문자열은 호환 되지 않는 형식에 할당 됩니다.  
  
 다음 샘플에서는 C2053 오류가 생성 됩니다.  
  
```  
// C2053.c  
int main() {  
   char array[] = L"Rika";   // C2053  
}  
```