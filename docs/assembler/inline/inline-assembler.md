---
title: "인라인 어셈블러 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "어셈블러[C++]"
  - "어셈블러[C++], 인라인"
  - "어셈블리 언어[C++], 인라인"
  - "인라인 어셈블러[C++]"
  - "인라인 어셈블리[C++]"
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 인라인 어셈블러
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 어셈블리 언어는 프로그램 속도 향상, 메모리 요구 사항 감소, 하드웨어 제어 등의 다양한 용도로 사용됩니다.  인라인 어셈블러를 사용하여 추가 어셈블리 및 링크 단계 없이 C 및 C\+\+ 소스 프로그램에 어셈블리 언어 명령을 직접 포함하도록 할 수 있습니다.  인라인 어셈블러가 컴파일러에 내장되어 있어 MASM\(Microsoft Macro Assembler\)과 같은 별도의 어셈블러는 필요하지 않습니다.  
  
> [!NOTE]
>  인라인 어셈블러 코드를 포함하는 프로그램은 다른 하드웨어 플랫폼에 완벽하게 이식할 수 없습니다.  이식성을 위해 디자인할 경우 인라인 어셈블러를 사용하지 마십시오.  
  
 인라인 어셈블리는 ARM 및 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 프로세서에서는 지원되지 않습니다.  다음 항목에서는 x86 프로세서에서 Visual C\/C\+\+ 인라인 어셈블러를 사용하는 방법을 설명합니다.  
  
-   [인라인 어셈블러 개요](../../assembler/inline/inline-assembler-overview.md)  
  
-   [인라인 어셈블리의 장점](../../assembler/inline/advantages-of-inline-assembly.md)  
  
-   [\_\_asm](../../assembler/inline/asm.md)  
  
-   [\_\_asm 블록에서 어셈블리 언어 사용](../../assembler/inline/using-assembly-language-in-asm-blocks.md)  
  
-   [\_\_asm 블록에서 C 또는 C\+\+ 사용](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)  
  
-   [인라인 어셈블리에서 레지스터 사용 및 유지](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)  
  
-   [인라인 어셈블리에서 레이블로 점프](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)  
  
-   [인라인 어셈블리에서 C 함수 호출](../../assembler/inline/calling-c-functions-in-inline-assembly.md)  
  
-   [인라인 어셈블리에서 C\+\+ 함수 호출](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)  
  
-   [\_\_asm 블록을 C 매크로로 정의](../../assembler/inline/defining-asm-blocks-as-c-macros.md)  
  
-   [인라인 어셈블리 최적화](../../assembler/inline/optimizing-inline-assembly.md)  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [컴파일러 내장 및 어셈블리 언어](../../intrinsics/compiler-intrinsics-and-assembly-language.md)   
 [C\+\+ 언어 참조](../../cpp/cpp-language-reference.md)