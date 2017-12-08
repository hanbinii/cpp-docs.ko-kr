---
title: "섹션 (C/C + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SECTIONS
dev_langs: C++
helpviewer_keywords: SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9d1564d068f4d69c3190b8bb24a32e7efb01dbef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="sections-cc"></a>SECTIONS(C/C++)
하나 이상의 섹션이 `definitions` 프로젝트의 출력 파일 섹션에에서 대 한 액세스 지정자는입니다.  
  
```  
SECTIONS  
definitions  
```  
  
## <a name="remarks"></a>설명  
 각 정의는 별도의 줄에 있어야 합니다. `SECTIONS` 키워드는 앞의 줄 또는 첫 번째 정의와 동일한 줄에 있을 수 있습니다. .Def 파일 하나 이상 포함할 수 있습니다 `SECTIONS` 문.  
  
 이 `SECTIONS` 문은 이미지 파일에 하나 이상의 섹션에 대 한 특성을 설정 하며는 섹션의 각 형식에 대 한 기본 특성을 재정의 하는 데 사용할 수 있습니다.  
  
 형식은 `definitions` 됩니다.  
  
 `.section_name specifier`  
  
 여기서 `.section_name` 프로그램 이미지의 섹션의 이름 및 `specifier` 하나 이상의 다음 액세스 한정자:  
  
|한정자|설명|  
|--------------|-----------------|  
|`EXECUTE`|섹션을 실행할 수 있습니다.|  
|`READ`|데이터에서 읽을 수 있습니다.|  
|`SHARED`|이미지를 로드 하는 모든 프로세스에서 섹션을 공유 합니다.|  
|`WRITE`|데이터에 쓸 수 있습니다.|  
  
 식별자 이름은 공백으로 구분 합니다. 예:  
  
```  
SECTIONS  
.rdata READ WRITE  
```  
  
 `SECTIONS`섹션의 목록의 시작을 표시 `definitions`합니다. 각 `definition` 별도 줄에 있어야 합니다. `SECTIONS` 키워드 첫 번째와 같은 줄에 있을 수 있습니다 `definition` 앞의 줄 또는 합니다. .Def 파일 하나 이상 포함할 수 있습니다 `SECTIONS` 문. `SEGMENTS` 키워드는의 동의어로 지원 `SECTIONS`합니다.  
  
 이전 버전의 Visual c + + 지원 됩니다.  
  
```  
section [CLASS 'classname'] specifier  
```  
  
 `CLASS` 키워드 호환성을 위해 지원 되지만 무시 됩니다.  
  
 섹션 특성 지정 하는 해당 하는 방법은 [/section](../../build/reference/section-specify-section-attributes.md) 옵션입니다.  
  
## <a name="see-also"></a>참고 항목  
 [모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)