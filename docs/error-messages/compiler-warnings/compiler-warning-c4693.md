---
title: "컴파일러 경고 C4693 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4693
dev_langs:
- C++
helpviewer_keywords:
- C4693
ms.assetid: 72d8db01-5e6f-4794-8731-76107e8f064a
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1bd881645b36e29be987850c1ceb9f3b4fd35b9d
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4693"></a>컴파일러 경고 C4693
'class': 봉인 추상 클래스는 인스턴스 멤버 'Test'를 포함할 수 없습니다.  
  
 형식이 표시 되어 있으면 [봉인](../../windows/sealed-cpp-component-extensions.md) 및 [추상](../../windows/abstract-cpp-component-extensions.md), 정적 멤버를 하나만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4693을 생성합니다.  
  
```  
// C4693.cpp  
// compile with: /clr /c  
public ref class Public_Ref_Class sealed abstract {  
public:  
   void Test() {}   // C4693  
   static void Test2() {}   // OK  
};  
```