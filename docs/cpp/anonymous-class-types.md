---
title: 익명 클래스 형식
ms.date: 11/04/2016
helpviewer_keywords:
- class types [C++], anonymous
- anonymous class types
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
ms.openlocfilehash: 9cd27fb40522a07ce4591b654ee8a6dda53b4f28
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184474"
---
# <a name="anonymous-class-types"></a>익명 클래스 형식

클래스는 익명 일 수-없이 선언할 수 있습니다 즉, 한 *식별자*합니다. 클래스 이름을 바꿔야 하는 경우에 유용를 **typedef** 같이 이름:

```cpp
typedef struct
{
    unsigned x;
    unsigned y;
} POINT;
```

> [!NOTE]
>  이전 예제와 같이 익명 클래스를 사용하면 기존의 C 코드와 호환성을 유지하는 데 도움이 됩니다. 일부 C 코드에서 사용 **typedef** 익명 구조체와 함께에서 널리 사용 됩니다.

다음과 같이 클래스 멤버를 참조하여 별도의 클래스에 포함되지 않은 것처럼 나타내려는 경우에도 익명 클래스가 유용합니다.

```cpp
struct PTValue
{
    POINT ptLoc;
    union
    {
        int  iValue;
        long lValue;
    };
};

PTValue ptv;
```

위의 코드에서 `iValue` 개체 멤버 선택 연산자를 사용 하 여 액세스할 수 있습니다 (**.**) 다음과 같이 합니다.

```cpp
int i = ptv.iValue;
```

특정 제한이 익명 클래스에 적용됩니다. (익명 공용 구조체에 대 한 자세한 내용은 참조 하세요. [공용 구조체](../cpp/unions.md).) 익명 클래스:

- 생성자나 소멸자를 가질 수 없습니다.

- 타원을 사용하여 형식 검사를 통과하지 않으면 함수에 인수로 전달할 수 없습니다.

- 함수에서 반환 값으로 반환될 수 없습니다.

## <a name="anonymous-structs"></a>익명 구조체

### <a name="microsoft-specific"></a>Microsoft 전용

Microsoft C 확장을 사용하면 이름을 지정하지 않고 다른 구조체 내에서 구조체 변수를 선언할 수 있습니다. 이러한 중첩된 구조체를 익명 구조체라고 합니다. C++에서는 익명 구조체를 허용하지 않습니다.

포함하는 구조체의 멤버인 것처럼 익명 구조체의 멤버에 액세스할 수 있습니다.

```cpp
// anonymous_structures.c
#include <stdio.h>

struct phone
{
    int  areacode;
    long number;
};

struct person
{
    char   name[30];
    char   gender;
    int    age;
    int    weight;
    struct phone;    // Anonymous structure; no name needed
} Jim;

int main()
{
    Jim.number = 1234567;
    printf_s("%d\n", Jim.number);
}
//Output: 1234567
```

**Microsoft 전용 종료**