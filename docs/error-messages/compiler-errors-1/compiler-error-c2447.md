---
title: 컴파일러 오류 C2447
ms.date: 11/04/2016
f1_keywords:
- C2447
helpviewer_keywords:
- C2447
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
ms.openlocfilehash: 64dca8313af8b640b7b03c1ab27a1a31fa90de09
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638531"
---
# <a name="compiler-error-c2447"></a>컴파일러 오류 C2447

'{': 함수 헤더가 없습니다. 이전 스타일의 형식 목록입니까?

컴파일러가 전역 범위에서 예기치 않은 중괄호를 발견했습니다. 대부분의 경우 잘못된 형식의 함수 헤더, 위치가 잘못된 선언 또는 흩어진 세미콜론 때문입니다. 이 문제를 해결하려면 중괄호가 잘못된 형식의 함수 헤더 다음에 오고 선언 또는 흩어진 세미콜론이 앞에 오지 않는지 확인합니다.

이 오류는 이전 스타일의 C 언어 형식 인수 목록을 사용하는 경우에 발생할 수도 있습니다. 이 문제를 해결하려면 인수 목록을 리팩터링하여 현대적인 스타일을 사용하도록, 즉 괄호로 묶이도록 합니다.

다음 샘플에서는 C2447 오류가 생성 됩니다.

```
// C2447.cpp
int c;
{}       // C2447
```