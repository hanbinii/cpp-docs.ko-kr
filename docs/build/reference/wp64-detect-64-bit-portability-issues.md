---
title: /Wp64(64비트 이식성 문제 검색)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
ms.openlocfilehash: 5a3cdaf85fa4dc05ece54fc630cb69fc93650e6b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813944"
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64(64비트 이식성 문제 검색)

이 컴파일러 옵션은 더 이상 사용되지 않습니다. Visual Studio 2013 이전 버전에서는 [__w64](../../cpp/w64.md) 키워드로도 표시된 형식에서 64비트 이식성 문제를 검색합니다.

## <a name="syntax"></a>구문

```
/Wp64
```

## <a name="remarks"></a>설명

기본적으로 Visual Studio 2013, Visual Studio의 버전에서을 **/wp64** 32 비트 x86 빌드는 MSVC 컴파일러에서 컴파일러 옵션은 해제 되어 코드에서 MSVC 컴파일러에서를 작성 하는 64 비트, x64 및 코드.

> [!IMPORTANT]
>  [/Wp64](wp64-detect-64-bit-portability-issues.md) 컴파일러 옵션 및 [__w64](../../cpp/w64.md) 키워드는 Visual Studio 2010 및 Visual Studio 2012에서 더 이상 사용되지 않으며 Visual Studio 2013부터는 지원되지 않습니다. 이 스위치를 사용하는 프로젝트를 변환하면 변환 중에 스위치가 마이그레이션되지 않습니다. Visual Studio 2010 또는 Visual Studio 2012에서 이 옵션을 사용하려면 프로젝트 속성의 **명령줄** 섹션에서 **추가 옵션** 아래에 컴파일러 스위치를 입력해야 합니다. 명령줄에서 **/Wp64** 컴파일러 옵션을 사용하면 컴파일러에서 명령줄 경고 D9002를 표시합니다. 이 옵션과 키워드를 사용 하 여 64 비트 이식성 문제를 감지, 대신 64 비트 플랫폼을 대상으로 하는 MSVC 컴파일러를 사용 하 고 지정 된 [/w4](compiler-option-warning-level.md) 옵션입니다. 자세한 내용은 [64 비트 x64 프로젝트 구성 c + + 대상](../configuring-programs-for-64-bit-visual-cpp.md)합니다.

다음 유형의 변수는 64비트 운영 체제에서 사용되는 것처럼 32비트 운영 체제에서 테스트됩니다.

- int

- long

- 포인터

64 비트 x64를 작성 하는 컴파일러를 사용 하 여 응용 프로그램을 정기적으로 컴파일하는 경우 코드를 비활성화 하는 것 **/wp64** 에 32 비트 컴파일 64 비트 컴파일러가 모든 문제를 검색할 수 있으므로 합니다. 대상 Windows 64 비트 운영 체제 하는 방법에 대 한 자세한 내용은 참조 하세요. [64 비트 x64 프로젝트 구성 c + + 대상](../configuring-programs-for-64-bit-visual-cpp.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다.

   자세한 내용은 [Visual Studio에서 설정 c + + 컴파일러 및 빌드 속성](../working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. **명령줄** 속성 페이지를 클릭합니다.

1. **/Wp64** 를 포함하도록 **추가 옵션**상자의 내용을 수정합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[64 비트 x64에 대 한 c + + 프로젝트 구성 대상](../configuring-programs-for-64-bit-visual-cpp.md)
