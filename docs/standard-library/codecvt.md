---
title: '&lt;codecvt&gt;'
ms.date: 11/04/2016
f1_keywords:
- codecvt
- <codecvt>
helpviewer_keywords:
- codecvt header
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
ms.openlocfilehash: 56cd4263d3dcddd23246a05466275b8b7d370b95
ms.sourcegitcommit: fe1e21df175cd004d21c6e4659082efceb649a8b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53978246"
---
# <a name="ltcodecvtgt"></a>&lt;codecvt&gt;

템플릿 클래스 [codecvt](../standard-library/codecvt-class.md)를 기반으로 하는 개체를 설명하는 여러 템플릿 클래스를 정의합니다. 이러한 개체 역할도 할 수 있습니다 [로캘 패싯](../standard-library/locale-class.md#facet_class) 형식의 값 시퀀스 간의 변환을 제어 하는 `Elem` 형식의 값 시퀀스 **char**합니다.

## <a name="syntax"></a>구문

```cpp
#include <codecvt>
```

## <a name="remarks"></a>설명

이 헤더에 선언된 로캘 패싯은 여러 문자 인코딩 간에 변환됩니다. 와이드 문자의 경우(프로그램 내에서 고정 크기의 정수로 저장됨):

- UCS-4는 프로그램 내에서 32비트 정수로 인코드된 유니코드(ISO 10646)입니다.

- UCS-2는 프로그램 내에서 16비트 정수로 인코드된 유니코드입니다.

- UTF-16은 프로그램 내에서 하나 또는 두 개의 16비트 정수로 인코드된 유니코드입니다. (표준 C 또는 표준 C++에 대한 유효한 와이드 문자 인코딩의 모든 요구 사항을 충족하지는 않습니다. 그럼에도 불구하고 매우 광범위하게 사용됩니다.)

바이트 스트림의 (파일에 저장, 바이트 시퀀스로 전송 되거나 배열 프로그램 내에서 저장 **char**):

- UTF-8은 바이트 스트림 내에서 결정적 바이트 순서를 가진 하나 이상의 8비트 바이트로 인코드된 유니코드입니다.

- UTF-16LE는 바이트 스트림 내에서 각 16비트 정수가 두 개의 8비트 바이트로 표현되며 덜 중요한 바이트가 먼저 표시되는 UTF-16으로 인코드된 유니코드입니다.

- UTF-16BE는 바이트 스트림 내에서 각 16비트 정수가 두 개의 8비트 바이트로 표현되며 더 중요한 바이트가 먼저 표시되는 UTF-16으로 인코드된 유니코드입니다.

### <a name="enumerations"></a>열거형

|||
|-|-|
|[codecvt_mode](../standard-library/codecvt-enums.md#codecvt_mode)|로캘 패싯에 대한 구성 정보를 지정합니다.|

### <a name="classes"></a>클래스

|클래스|설명|
|-|-|
|[codecvt_utf8](codecvt-utf8-class.md)|UCS-2 또는 UCS-4로 인코드된 와이드 문자와 UTF-8로 인코드된 바이트 스트림 간에 변환되는 로캘 패싯을 나타냅니다.|
|[codecvt_utf8_utf16](codecvt-utf8-utf16-class.md)|UTF-16으로 인코드된 와이드 문자와 UTF-8로 인코드된 바이트 스트림 간에 변환되는 로캘 패싯을 나타냅니다.|
|[codecvt_utf16](codecvt-utf16-class.md)|UCS-2 또는 UCS-4로 인코드된 와이드 문자와 UTF-16LE 또는 UTF-16BE로 인코드된 바이트 스트림 간에 변환되는 로캘 패싯을 나타냅니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<codecvt>

**네임스페이스:** std

## <a name="see-also"></a>참고 항목

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
