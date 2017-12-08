---
title: "메서드 추가 마법사 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.method.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메서드 추가 마법사[C++]"
  - "메서드[C++], 마법사를 사용한 추가"
ms.assetid: b9a71b0e-9ecf-40fa-9f86-4200cb23d671
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 메서드 추가 마법사
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 마법사를 사용하면 메서드를 인터페이스에 추가할 수 있습니다.  메서드를 추가할 프로젝트 형식이나 인터페이스 형식에 따라 마법사에 표시되는 옵션이 달라집니다.  
  
## 이름  
 **반환 형식**  
 메서드에서 반환되는 데이터 형식입니다.  `HRESULT`는 표준적인 방법으로 오류를 반환하므로 모든 인터페이스 형식에 이 형식을 사용하는 것이 좋습니다.  
  
|인터페이스 형식|설명|  
|--------------|--------|  
|이중 인터페이스|`HRESULT`.  변경할 수 없습니다.|  
|사용자 지정 인터페이스|`HRESULT`.  변경할 수 없습니다.|  
|로컬 사용자 지정 인터페이스|사용자 고유의 반환 형식을 지정하거나 목록에서 선택합니다.|  
|Dispinterface|사용자 고유의 반환 형식을 지정하거나 목록에서 선택합니다.|  
|MFC ActiveX 컨트롤 dispinterface|스톡 메서드를 구현하면 반환 형식이 적절한 값으로 설정되어 변경되지 않습니다.  **메서드 이름** 목록에서 메서드를 선택하고 **메서드 형식 선택**에서 **사용자 지정**을 클릭하는 경우에는 목록에서 반환 유형을 선택하십시오.|  
  
 **메서드 이름**  
 메서드의 이름을 설정합니다.  
  
|인터페이스 형식|설명|  
|--------------|--------|  
|ATL 이중 인터페이스, 사용자 지정 인터페이스 및 로컬 사용자 지정 인터페이스|사용자 고유의 메서드 이름을 지정합니다.|  
|MFC dispinterface|사용자 고유의 메서드 이름을 지정하거나 목록에 표시된 메서드 이름을 선택합니다.  목록에서 이름을 선택하면 **반환 형식** 상자에 적절한 값이 표시되고, 이 값은 변경할 수 없습니다.|  
|MFC ActiveX 컨트롤 dispinterface|사용자 고유의 메서드를 지정하거나 [DoClick](../Topic/COleControl::DoClick.md) 및 [Refresh](../Topic/COleControl::Refresh.md) 중 한 가지 스톡 메서드를 선택합니다.  자세한 내용은 [MFC ActiveX 컨트롤: 스톡 메서드 추가](../mfc/mfc-activex-controls-adding-stock-methods.md)를 참조하십시오.|  
  
 **메서드 형식**  
 MFC ActiveX 컨트롤에 대해서만 사용할 수 있습니다.  목록에서 메서드를 선택하지 않고 **메서드 이름** 상자에 메서드 이름을 지정하면 이 상자는 사용할 수 없습니다.  
  
 **메서드 이름** 목록에서 메서드 중 하나를 선택하려면 스톡 구현이나 사용자 지정 구현 중 하나를 선택합니다.  
  
|메서드 형식|설명|  
|------------|--------|  
|**스톡**|기본값입니다.  **메서드 이름** 목록에서 선택한 메서드의 스톡 구현을 삽입합니다.  **스톡**을 선택하면 **반환 형식**을 변경할 수 없습니다.|  
|**사용자 지정**|**메서드 이름** 목록에서 선택한 메서드의 스텁 구현을 삽입합니다.  사용자 지정 메서드 형식인 경우에는 사용자 고유의 반환 형식을 지정하거나 **반환 형식** 목록에서 반환 형식을 선택할 수 있습니다.|  
  
 **내부 이름**  
 MFC dispinterface에 추가된 사용자 지정 메서드에만 사용할 수 있습니다.  디스패치 맵, 헤더 파일\(.h\) 및 구현 파일\(.cpp\)에 사용할 이름을 설정합니다.  기본적으로 이 이름은 **메서드 이름**과 동일합니다.  MFC dispinterface로 작업하거나 MFC ActiveX 컨트롤 dispinterface에 사용자 지정 메서드를 추가할 경우에는 해당 메서드 이름을 바꿀 수 있습니다.  
  
|인터페이스 형식|설명|  
|--------------|--------|  
|ATL 이중 인터페이스, 사용자 지정 인터페이스 및 로컬 사용자 지정 인터페이스|사용할 수 없음|  
|MFC dispinterface|기본적으로, 메서드 이름으로 설정됩니다.  내부 이름은 편집할 수 있습니다.|  
|MFC ActiveX 컨트롤 dispinterface|사용자 지정 메서드에만 내부 이름을 설정할 수 있습니다.  스톡 메서드에는 내부 이름이 사용되지 않습니다.|  
  
 **매개 변수 특성**  
 **매개 변수 이름**에 지정된 매개 변수에 추가 특성을 설정합니다.  
  
|매개 변수 특성|설명|가능한 조합|  
|--------------|--------|------------|  
|**In**|호출하는 프로시저에서 호출된 프로시저로 매개 변수가 전달됩니다.|**in**만<br /><br /> **in** 및 **out**|  
|**out**|호출된 프로시저에서 호출하는 프로시저로\(서버에서 클라이언트로\) 포인터 매개 변수가 반환됩니다.|**out**만<br /><br /> **in** 및 **out**<br /><br /> **out** 및 **retval**|  
|**Retval**|매개 변수가 멤버의 반환 값을 받습니다.|**retval** 및 out|  
  
 **매개 변수 형식**  
 매개 변수의 데이터 형식을 설정합니다.  목록에서 형식을 선택합니다.  
  
 **매개 변수 이름**  
 메서드를 통해 전달할 매개 변수의 이름을 설정합니다.  이름을 입력한 다음 **추가**를 클릭하여 그 이름을 메서드를 통해 전달할 매개 변수 목록에 추가해야 합니다.  매개 변수 이름을 지정하지 않으면 마법사에서 선택한 매개 변수 특성\(ATL 전용\)이나 **매개 변수 형식**이 무시됩니다.  
  
 **추가**를 클릭하면 **매개 변수 목록**에 매개 변수 이름이 나타납니다.  
  
 **참고** 매개 변수 이름을 지정한 다음 **추가**를 클릭하기 전에 **마침**을 클릭하면 매개 변수가 메서드에 추가되지 않습니다.  사용자가 직접 메서드를 찾고 매개 변수를 삽입해야 합니다.  
  
 **Add**  
 **매개 변수 이름**에서 지정한 매개 변수와 그 형식 및 매개 변수 특성을 **매개 변수 목록**에 추가합니다.  매개 변수를 목록에 추가하려면 **추가**를 클릭해야 합니다.  
  
 **Remove**  
 **매개 변수 목록**에서 선택한 매개 변수를 목록에서 제거합니다.  
  
 **매개 변수 목록**  
 현재 메서드에 추가된 모든 매개 변수 및 매개 변수 한정자와 형식을 표시합니다.  매개 변수를 추가하면 마법사의 **매개 변수 목록**에 각 매개 변수 및 매개 변수 한정자와 형식이 업데이트되어 표시됩니다.  
  
## 참고 항목  
 [메서드 추가](../ide/adding-a-method-visual-cpp.md)   
 [메서드 추가 마법사, IDL 특성](../ide/idl-attributes-add-method-wizard.md)