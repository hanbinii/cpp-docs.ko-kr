---
title: 컴파일러 경고(수준 1) C4311
ms.date: 11/04/2016
f1_keywords:
- C4311
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
ms.openlocfilehash: 5f9b8ce710879913fdad1be5c0f22f8e3f4ed9d7
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518166"
---
# <a name="compiler-warning-level-1-c4311"></a>컴파일러 경고(수준 1) C4311

'variable' : 'type'에서 'type'(으)로 포인터가 잘립니다.

이 경고는 64비트 포인터 잘림 문제를 검색합니다. 예를 들어 코드가 64비트 아키텍처에 대해 컴파일된 경우 포인터(64비트)의 값을 `int`(32비트)에 할당하면 값이 잘립니다. 자세한 내용은 [포인터를 사용 하 여 규칙](/windows/desktop/WinProg64/rules-for-using-pointers)합니다.

C4311 경고의 일반적인 원인에 대 한 추가 정보 참조 [일반적인 컴파일러 오류](/windows/desktop/WinProg64/common-compiler-errors)합니다.

다음 코드 예제는 64비트 대상에 대해 컴파일할 경우 C4311 경고가 발생하며, 해결 방법을 보여 줍니다.

```
// C4311.cpp
// compile by using: cl /W1 C4311.cpp
int main() {
   void* p = &p;
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets
   unsigned long long j = (unsigned long long) p;   // OK
}
```