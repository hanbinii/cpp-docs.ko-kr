---
title: 샘플 메이크파일
ms.date: 11/04/2016
ms.assetid: 8343ce71-5556-4ae0-8d1e-7efd82673070
ms.openlocfilehash: 79ca4e466d37880787260be5b8b4ec76a5bb092f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826877"
---
# <a name="sample-makefile"></a>샘플 메이크파일

이 항목에서는 샘플 메이크파일 포함 되어 있습니다.

## <a name="sample"></a>샘플

### <a name="code"></a>코드

```
# Sample makefile

!include <win32.mak>

all: simple.exe challeng.exe

.c.obj:
  $(cc) $(cdebug) $(cflags) $(cvars) $*.c

simple.exe: simple.obj
  $(link) $(ldebug) $(conflags) -out:simple.exe simple.obj $(conlibs) lsapi32.lib

challeng.exe: challeng.obj md4c.obj
  $(link) $(ldebug) $(conflags) -out:challeng.exe $** $(conlibs) lsapi32.lib
```

## <a name="see-also"></a>참고자료

[메이크파일의 내용](contents-of-a-makefile.md)
