---
title: "컴파일러 오류 C3153 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3153
dev_langs: C++
helpviewer_keywords: C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9d6a2ad948ae8d5517f7b98316b4e3c67bea5afb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3153"></a>컴파일러 오류 C3153
'interface': 인터페이스의 인스턴스를 만들 수 없습니다  
  
 인터페이스를 인스턴스화할 수 없습니다. 인터페이스의 멤버를 사용 하려면 인터페이스에서 클래스를 파생 인터페이스 멤버를 구현 하 고 멤버를 사용 합니다.  
  
 다음 샘플에서는 C3153 오류가 생성 됩니다.  
  
```  
// C3153.cpp  
// compile with: /clr  
interface class A {  
};  
  
int main() {  
   A^ a = gcnew A;   // C3153  
}  
```  