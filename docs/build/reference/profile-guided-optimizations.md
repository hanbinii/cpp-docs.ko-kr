---
title: "프로필 기반 최적화 | Microsoft Docs"
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
  - "최적화, 프로필 기반[C++]"
  - "프로필 기반 최적화"
ms.assetid: 2225c307-d3ae-42c1-8345-a5a959d132dc
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# 프로필 기반 최적화
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

최적화 프로그램이 .exe 또는 .dll 파일의 테스트 실행 데이터를 사용하는 프로필 기반 최적화를 사용하면 출력 파일을 최적화할 수 있습니다.  데이터는 프로그램이 프로덕션 환경에서 수행될 가능성이 있는 방법을 나타냅니다.  
  
 프로필 기반 최적화는 x86 또는 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 네이티브 대상에서만 사용할 수 있습니다.  프로필 기반 최적화는 공용 언어 런타임에서 실행되는 출력 파일에 사용할 수 없습니다.  네이티브 코드와 관리 코드가 혼합된 어셈블리를 생성\(**\/clr**을 사용하여 컴파일\)하는 경우에도 네이티브 코드에서만 프로필 기반 최적화를 사용할 수 없습니다.  IDE에서 이러한 옵션 설정을 사용하여 프로젝트를 빌드하려고 시도하면 빌드 오류가 발생합니다.  
  
> [!NOTE]
>  프로파일링 테스트 실행에서 수집되는 정보는 **\/Ob**, **\/Os** 또는 **\/Ot**를 지정하는 경우 적용되는 최적화를 재정의합니다.  자세한 내용은 [\/Ob\(인라인 함수 확장\)](../../build/reference/ob-inline-function-expansion.md) 및 [\/Os, \/Ot\(크기 우선 코드, 속도 우선 코드\)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)를 참조하세요.  
  
 성능 및 진단 허브에서 Visual C\+\+ 플러그 인에 자동화된 프로필 기반 최적화를 사용하여 Visual Studio 내의 최적화 프로세스를 간소화하거나, Visual Studio 또는 명령줄에서 수동으로 최적화 단계를 수행할 수 있습니다.  플러그 인은 더 쉽게 사용할 수 있으므로 플러그 인을 권장합니다.  플러그 인을 가져와 앱 최적화에 사용하는 방법에 대한 자세한 내용은 [프로필 기반 최적화 플러그 인](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)을 참조하세요.  
  
 프로필 기반 최적화 플러그 인과 수동 프로필 기반 최적화 모두 다음 단계에 따라 앱을 최적화합니다.  
  
-   [\/GL](../../build/reference/gl-whole-program-optimization.md)을 사용하여 하나 이상이 소스 코드 파일을 컴파일합니다.  
  
     프로필 기반 최적화 테스트 실행 중 \/GL로 빌드된 각 모듈을 검사하여 런타임 동작을 캡처할 수 있습니다.  프로필 기반 최적화 빌드의 모든 모듈을 \/GL로 컴파일할 필요가 없습니다.  그러나 \/GL을 사용하여 컴파일한 모듈만 계측되어 나중에 프로필 기반 최적화에 사용할 수 있습니다.  
  
-   [\/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md)를 사용하여 연결합니다.  
  
     \/LTCG:PGINSTRUMENT는 빈 .pgd 파일을 만듭니다.  테스트 실행 데이터가 .pgd 파일에 추가된 후에는 다음 링크 단계\(최적화된 이미지 만들기\)에 대한 입력으로 사용할 수 있습니다.  \/LTCG:PGINSTRUMENT를 지정하는 경우 .pgd 파일의 기본값이 아닌 이름이나 위치를 사용하여 선택적으로 [\/PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)를 지정할 수 있습니다.  
  
-   응용 프로그램을 프로파일링합니다.  
  
     프로파일링된 EXE 세션이 종료되거나 프로파일링된 DLL이 언로드될 때마다 *appname*\! \#.pgc 파일이 만들어집니다.  .pgc 파일에는 특정 응용 프로그램 테스트 실행에 대한 정보가 포함됩니다.  \#은 1부터 시작하는 숫자이며 디렉터리에 있는 다른 *appname*\!\#.pgc 파일 수에 따라 증가합니다.  테스트 실행이 최적화하려는 시나리오를 나타내지 않는 경우 .pgc 파일을 삭제할 수 있습니다.  
  
     테스트 실행 중에는 [pgosweep](../../build/reference/pgosweep.md) 유틸리티를 사용하여 현재 열려 있는 .pgc 파일 닫기와 새 .pgc 파일 만들기를 강제로 수행할 수 있습니다\(예: 테스트 시나리오의 끝이 응용 프로그램 종료와 일치하지 않는 경우\).  
  
     응용 프로그램을 프로파일링하는 경우 `PogoSafeMode` 옵션을 사용할 수 있습니다.  이 옵션을 사용하면 응용 프로그램을 안전 모드로 프로파일링할지 빠른 모드로 프로파일링할지를 지정할 수 있습니다.  이러한 모드에 대한 자세한 내용은 [PogoSafeMode](../../build/reference/pogosafemode.md)를 참조하세요.  
  
-   \/LTCG:PGOPTIMIZE를 사용하여 연결합니다.  
  
     \/LTCG:PGOPTIMIZE는 최적화된 이미지를 만듭니다.  이 단계에서는 입력으로 .pgd 파일을 사용합니다.  자세한 내용은 [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)를 참조하세요.  
  
 최적화된 출력 파일을 만들고 나중에 보다 최적화된 이미지를 만드는 데 추가 프로파일링이 유용한지를 확인할 수 있습니다.  계측된 이미지와 해당 .pgd 파일을 사용할 수 있는 경우 추가 테스트 실행을 수행하고 최신 .pgd 파일로 최적화된 이미지를 다시 작성할 수 있습니다.  
  
 다음은 프로필 기반 최적화 목록입니다.  
  
-   **인라인 처리** – 예를 들어 함수 B를 자주 호출하는 함수 A가 있고 함수 B는 상대적으로 작은 경우 프로필 기반 최적화에서는 함수 A에서 함수 B를 인라인 처리합니다.  
  
-   **가상 호출 추론** – 가상 호출 또는 함수 포인터를 통한 호출이 종종 특정 함수를 대상으로 하는 경우 프로필 기반 최적화에서 조건부로 실행되는 직접 호출을 자주 대상이 되는 함수에 추가하고 직접 호출은 인라인 처리할 수 있습니다.  
  
-   **레지스터 할당** – 프로필 데이터를 사용하여 최적화하면 레지스터 할당이 향상됩니다.  
  
-   **기본 블록 최적화** – 기본 블록 최적화를 사용하면 지정된 프레임 내에서 일시적으로 실행되는 자주 실행되는 기본 블록을 동일한 페이지 집합에 배치할 수 있습니다\(지역\).  따라서 사용되는 페이지 수가 최소화되므로 메모리 오버헤드도 최소홥니다.  
  
-   **크기\/속도 최적화** – 프로그램에서 자주 사용되는 함수의 속도를 최적화할 수 있습니다.  
  
-   **함수 레이아웃** – 호출 그래프와 프로파일링된 호출자\/호출 수신자 동작에 따라 동일한 실행 경로를 따르는 경향이 있는 함수가 동일한 섹션에 배치됩니다.  
  
-   **조건부 분기 최적화** – 값 프로브를 사용하여 프로필 기반 최적화에서 switch 문에 지정된 된 값이 다른 값보다 더 자주 사용되는지 확인할 수 있습니다.  그런 다음 switch 문에서 이 값을 가져올 수 있습니다.  더 자주 true가 되는 블록에 따라 if 도는 else 블록이 먼저 배치되도록 최적화 프로그램에서 if\/else의 순서를 지정할 수 있는 if\/else 명령을 사용하여 동일한 작업을 수행할 수 있습니다.  
  
-   **데드 코드 분리** – 프로파일링 중에 호출되지 않는 코드를 섹션 집합의 끝에 추가되는 특별한 섹션으로 이동합니다.  그러면 이 섹션이 자주 사용되는 페이지에서 효과적으로 유지됩니다.  
  
-   **EH 코드 분리** – 프로필 기반 최적화는 예외가 예외 조건에서만 발생하는지를 확인할 수 있는 경우 예외적으로 실행되는 EH 코드를 별도의 섹션으로 종종 이동할 수 있습니다.  
  
-   **메모리 내장** – 내장 함수가 자주 호출되는지 확인할 수 있는 경우 내장 함수의 확장을 더 잘 결정할 수 있습니다.  또한 내장 함수는 이동 또는 복사의 블록 크기에 따라 최적화할 수 있습니다.  
  
 IDE 또는 명령줄에서 수동 최적화 수행에 대한 자세한 내용은 [연습: 프로필 기반 최적화 사용](http://msdn.microsoft.com/ko-kr/6e36421b-ec8c-4626-9c29-fa5ffb6f27f8)을 참조하세요.  
  
## 단원 내용  
 [프로필 기반 최적화 플러그 인](../../build/reference/profile-guided-optimization-in-the-performance-and-diagnostics-hub.md)  
  
 [프로필 기반 최적화 도구](../../build/reference/tools-for-manual-profile-guided-optimization.md)  
  
 [방법: 여러 개의 PGO 프로필을 단일 프로필로 병합](../../build/reference/how-to-merge-multiple-pgo-profiles-into-a-single-profile.md)  
  
## 참고 항목  
 [C\/C\+\+ 빌드 도구](../../build/reference/c-cpp-build-tools.md)