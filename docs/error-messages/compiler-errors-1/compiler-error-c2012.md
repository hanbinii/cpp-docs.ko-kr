---
title: 컴파일러 오류 C2012
ms.date: 11/04/2016
f1_keywords:
- C2012
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
ms.openlocfilehash: 85c3ad1d127dcabeeed0c5727ba6bbbca86f7898
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499660"
---
# <a name="compiler-error-c2012"></a>컴파일러 오류 C2012

'<' 다음에 이름이 없습니다.

`#include` 지시문에 필요한 파일 이름이 없습니다.

다음 샘플에서는 C2012를 생성합니다.

```
// C2012.cpp
#include <   // C2012 include the filename to resolve
```

해결 방법:

```
// C2012b.cpp
// compile with: /c
#include <stdio.h>
```