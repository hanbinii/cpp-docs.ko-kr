---
title: 컴파일러 오류 C3007
ms.date: 11/04/2016
f1_keywords:
- C3007
helpviewer_keywords:
- C3007
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
ms.openlocfilehash: 551fb458ee02e29ae54aeb3382b2016da731808a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630456"
---
# <a name="compiler-error-c3007"></a>컴파일러 오류 C3007

'arg': OpenMP 'directive' 지시문의 절이 인수를 사용하지 않습니다.

OpenMP 지시문에 인수가 있지만 지시문에서 인수를 사용하지 않습니다.

다음 샘플에서는 C3007을 생성합니다.

```
// C3007.c
// compile with: /openmp
int main()
{
   #pragma omp parallel for ordered(2)   // C3007
}
```