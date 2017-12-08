---
title: "C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "격리된 응용 프로그램[C++]"
  - "WinSxS[C++]"
  - "네이티브 어셈블리 캐시[C++]"
  - "빌드[C++], 격리된 응용 프로그램"
  - "side-by-side 응용 프로그램[C++]"
  - "빌드[C++], side-by-side 어셈블리"
ms.assetid: 9465904e-76f7-48bd-bb3f-c55d8f1699b6
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ 격리된 응용 프로그램 및 side-by-side 어셈블리 빌드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+은 [격리된 응용 프로그램](http://msdn.microsoft.com/library/aa375190) 및 [side\-by\-side 어셈블리](_win32_side_by_side_assemblies) 아이디어를 기반으로 Windows 클라이언트 응용 프로그램의 배포 모델을 지원합니다. 기본적으로 Visual C\+\+은 모든 네이티브 C\/C\+\+ 응용 프로그램을 [매니페스트](http://msdn.microsoft.com/library/aa375365)를 사용하여 Visual C\+\+ 라이브러리에 대한 종속성을 설명하는 격리된 응용 프로그램으로 빌드합니다.  
  
 C\/C\+\+ 프로그램을 격리된 응용 프로그램으로 빌드하면 여러 가지 이점을 얻을 수 있습니다. 예를 들어 격리된 응용 프로그램은 다른 C\/C\+\+ 응용 프로그램이 Visual C\+\+ 라이브러리를 설치 또는 제거하는 경우 영향을 받지 않습니다. 격리된 응용 프로그램에서 사용하는 Visual C\+\+ 라이브러리는 응용 프로그램의 로컬 폴더에 재배포하거나 네이티브 어셈블리 캐시\(WinSxS\)를 설치하여 재배포할 수 있습니다. 그러나 [게시자 구성 파일](http://msdn.microsoft.com/library/aa375680)을 사용하여 이미 배포된 응용 프로그램에 대한 Visual C\+\+ 라이브러리 서비스를 간소화할 수 있습니다. 이러한 격리된 응용 프로그램 배포 모델을 사용하면 특정 컴퓨터에서 실행 중인 C\/C\+\+ 응용 프로그램이 가장 최신 버전의 Visual C\+\+ 라이브러리 사용을 보다 쉽게 보장함과 동시에 시스템 관리자 및 응용 프로그램 작성자가 자신의 종속 DLL에 대한 명시적 버전 바인딩을 제어할 수 있는 가능성을 열어 둘 수 있습니다.  
  
 이 섹션에서는 C\/C\+\+ 응용 프로그램을 격리된 응용 프로그램으로 빌드하는 방법과 해당 응용 프로그램이 매니페스트를 사용하여 Visual C\+\+ 라이브러리로 바인딩되도록 보장하는 방법에 대해 설명합니다. 이 섹션의 정보는 주로 네이티브 또는 관리되지 않는 Visual C\+\+ 응용 프로그램에 적용됩니다. Visual C\+\+로 빌드된 네이티브 응용 프로그램 배포에 대한 자세한 내용은 [Visual C\+\+ 파일 재배포](../ide/redistributing-visual-cpp-files.md)를 참조하세요.  
  
## 단원 내용  
 [격리된 응용 프로그램 및 side\-by\-side 어셈블리 개념](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)  
  
 [C\/C\+\+ 격리된 응용 프로그램 빌드](../build/building-c-cpp-isolated-applications.md)  
  
 [C\/C\+\+ side\-by\-side 어셈블리 빌드](../build/building-c-cpp-side-by-side-assemblies.md)  
  
 [방법: 등록이 필요 없는 COM 구성 요소 빌드](../build/how-to-build-registration-free-com-components.md)  
  
 [방법: COM 구성 요소를 사용하는 격리된 응용 프로그램 빌드](../build/how-to-build-isolated-applications-to-consume-com-components.md)  
  
 [C\/C\+\+ 프로그램의 매니페스트 생성 이해](../build/understanding-manifest-generation-for-c-cpp-programs.md)  
  
 [문제 해결](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
  
## 관련 단원  
 [격리된 응용 프로그램 및 side\-by\-side 어셈블리](http://msdn.microsoft.com/library/dd408052)  
  
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)