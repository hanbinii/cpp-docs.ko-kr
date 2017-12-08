---
title: "방법: CLR 콘솔 응용 프로그램 만들기(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "콘솔 응용 프로그램, 템플릿"
  - "CLR 콘솔 응용 프로그램, 프로젝트 템플릿"
ms.assetid: e89bce3c-706f-4ae0-8a90-cb1a0f674e70
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: CLR 콘솔 응용 프로그램 만들기(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

콘솔 응용 프로그램 템플릿을 사용하여 이미 필수 프로젝트 참조 및 파일이 있는 콘솔 응용 프로그램 프로젝트를 만들 수 있습니다.  
  
 일반적으로 콘솔 응용 프로그램은 독립 실행형 실행 파일로 컴파일되지만 그래픽 사용자 인터페이스가 없습니다. 사용자가 명령 프롬프트에서 콘솔 응용 프로그램을 실행하고 명령 프롬프트를 사용하여 실행 중인 응용 프로그램에 지침을 적용합니다. 또한 명령 프롬프트에서 응용 프로그램이 출력 정보를 제공합니다. 콘솔 응용 프로그램의 즉각성은 사용자 인터페이스 구현에 관계없이 프로그래밍 기법을 배우는 것에 매우 유용합니다.  
  
 콘솔 응용 프로그램 템플릿을 사용하여 프로젝트를 만들려면 이러한 참조 및 파일을 자동으로 추가합니다.  
  
-   이러한.NET Framework 네임스페이스에 대한 참조:  
  
    -   [System](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx) \- 일반적으로 사용되는 값과 참조 데이터 형식, 이벤트와 이벤트 처리기, 인터페이스, 특성 및 처리 예외 등을 정의하는 기본 클래스가 포함됩니다.  
  
    -   mscorlib \- .NET Framework 개발을 지원하는 DLL 어셈블리입니다.  
  
-   소스 파일:  
  
    -   콘솔\(.cpp 파일\) \- 방금 만든 응용 프로그램에 대한 주 소스 파일과 진입점입니다. 프로젝트 .dll 파일과 프로젝트 네임스페이스를 식별합니다. 이 파일에 사용자 고유의 코드를 제공합니다.  
  
    -   AssemblyInfo.cpp \- 프로젝트의 어셈블리 메타데이터를 수정하는 데 사용할 수 있는 특성, 파일, 리소스, 형식, 버전 정보, 서명 정보 등을 포함합니다. 자세한 내용은 [어셈블리 콘텐츠](../Topic/Assembly%20Contents.md)을 참조하세요.  
  
    -   Stdafx.cpp \- Win32.pch라는 미리 컴파일된 헤더 파일과 StdAfx.obj라는 미리 컴파일된 형식 파일을 빌드하는 데 사용됩니다.  
  
-   헤더 파일:  
  
    -   Stdafx.h \- Win32.pch라는 미리 컴파일된 헤더 파일과 StdAfx.obj라는 미리 컴파일된 형식 파일을 빌드하는 데 사용됩니다.  
  
    -   resource.h \- app.rc용으로 생성된 포함 파일입니다.  
  
-   리소스 파일:  
  
    -   app.rc \- 프로그램의 리소스 스크립트 파일입니다.  
  
    -   app.ico \- 프로그램의 아이콘 파일입니다.  
  
-   ReadMe.txt \- 프로젝트에 있는 파일을 설명합니다.  
  
## CLR\(공용 언어 런타임\) 콘솔 응용 프로그램 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
2.  **새 프로젝트** 대화 상자의 **설치되어 있는 템플릿** 아래에서 **Visual C\+\+** 노드를 선택하고 **CLR** 노드를 선택한 다음 콘솔 응용 프로그램 템플릿을 선택합니다.  
  
3.  **이름** 상자에 응용 프로그램의 고유 이름을 입력합니다.  
  
     다른 프로젝트 및 솔루션 설정을 지정할 수 있지만 필요하지 않습니다.  
  
4.  **확인** 단추를 선택합니다.  
  
## 참고 항목  
 [NOTINBUILD 방법: CLR 콘솔 응용 프로그램 만들기](http://msdn.microsoft.com/ko-kr/b8af4197-e65f-4b17-b18e-b9e92965d026)   
 [CLR 프로젝트](../ide/files-created-for-clr-projects.md)   
 [NIB: 프로젝트의 항목 관리](http://msdn.microsoft.com/ko-kr/762e606b-7f44-4b66-97a1-e30a703654a0)