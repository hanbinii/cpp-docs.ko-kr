---
title: "컴파일러 경고 C4956 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4956
dev_langs: C++
helpviewer_keywords: C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bad7fac98e81e39457f484960ee566c16b6fe5bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-c4956"></a>컴파일러 경고 C4956
'type': 이 형식은 확인할 수 없습니다.  
  
 이 경고는 [/clr: safe](../../build/reference/clr-common-language-runtime-compilation.md) 가 지정되고 코드에 확인할 수 없는 형식이 포함된 경우 생성됩니다.  
  
 자세한 내용은 참조 [순수형 및 안정형 코드 (C + + /cli CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md)합니다.  
  
 이 경고는 오류로 발생하며 [warning](../../preprocessor/warning.md) pragma 또는 [/wd](../../build/reference/compiler-option-warning-level.md) 컴파일러 옵션과 함께 사용하지 않도록 설정할 수 있습니다.  
  
 다음 샘플에서는 C4956을 생성합니다.  
  
```  
// C4956.cpp  
// compile with: /clr:safe  
int* p;   // C4956  
```