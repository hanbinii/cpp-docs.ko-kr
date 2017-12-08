---
title: "원격 Linux 컴퓨터에 연결 | Microsoft Docs"
ms.custom: 
ms.date: 11/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6dce0c1c190854b7927c6e023edd76c9d1cb5645
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2017
---
# <a name="connect-to-your-remote-linux-computer"></a>원격 Linux 컴퓨터에 연결

빌드할 때 Linux 코드가 원격 Linux 컴퓨터에 복사되어 Visual Studio에서 선택한 설정에 따라 해당 시스템에서 컴파일됩니다.  이 원격 연결을 설정하려면

1. 처음으로 프로젝트를 빌드하거나 **도구 > 옵션**을 선택한 다음 **플랫폼 간 > 연결 관리자** 노드를 열고 **추가** 단추를 클릭하여 수동으로 새 항목을 만듭니다.

   ![연결 관리자](media/settings_connectionmanager.png)

   두 경우 모두에, **원격 시스템에 연결** 창이 표시됩니다.
   
   ![원격 시스템에 연결](media/connect.png)

1. 다음 정보를 입력합니다.

   | 입력 | 설명
   | ----- | ---
   | **호스트 이름**           | 대상 장치의 이름 또는 IP 주소
   | **포트**                | SSH 서비스가 실행되는 포트(일반적으로 22)
   | **사용자 이름**           | 인증할 사용자
   | **인증 형식** | 암호 또는 개인 키가 모두 지원됨
   | **암호**            | 입력한 사용자 이름의 암호
   | **개인 키 파일**    | SSH 연결을 위해 생성된 개인 키
   | **암호**          | 위에서 선택한 개인 키와 함께 사용된 암호

1. **연결** 단추를 클릭하여 원격 컴퓨터에 대한 연결을 시도합니다.  연결이 실패하면 변경해야 하는 입력 상자에 빨간색 윤곽선이 표시됩니다.

   ![연결 관리자 오류](media/settings_connectionmanagererror.png)