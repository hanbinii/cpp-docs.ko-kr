---
title: "컴파일러 오류 C3537 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3537
dev_langs:
- C++
helpviewer_keywords:
- C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f425ee0d93a277bac5dc1f0a798c1a7cc3ed3bac
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3537"></a>컴파일러 오류 C3537
'type': 'auto' 포함 하는 형식으로 캐스팅할 수 없습니다  
  
 에 포함 하기 때문에 변수 표시 된 형식으로 캐스팅할 수 없습니다는 `auto` 키워드 및 기본 [/zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) 컴파일러 옵션을 적용 합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 C3537 포함 하는 형식으로 캐스팅 하는 변수는 `auto` 키워드입니다.  
  
```  
// C3537.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int value = 123;  
   auto(value);                        // C3537  
   (auto)value;                        // C3537  
   auto x1 = auto(value);              // C3537  
   auto x2 = (auto)value;              // C3537  
   auto x3 = static_cast<auto>(value); // C3537  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)