---
title: 컴파일러 경고(수준 1) C4178
ms.date: 11/04/2016
f1_keywords:
- C4178
helpviewer_keywords:
- C4178
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
ms.openlocfilehash: 76e2b0e6ee42e8f32eb462336721d860cff006a5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540090"
---
# <a name="compiler-warning-level-1-c4178"></a>컴파일러 경고(수준 1) C4178

'constant' case 상수가 switch 식의 형식에는 너무 큽니다.

`switch` 식의 case 상수가 할당된 형식에 맞지 않습니다.

## <a name="example"></a>예제

```
// C4178.cpp
// compile with: /W1
int main()
{
    int i;  // maximum size of unsigned long int is 4294967295
    switch( i )
    {
        case 4294967295:   // OK
            break;
        case 4294967296:   // C4178
            break;
    }
}
```