---
title: "방법: 네이티브 c + + 클래스에서 Windows Forms 이벤트 싱크 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- event handling, managed/native interop
- event handling, sinking .NET in C++
- event handling, .NET/native interop
- event handling, Windows Forms in C++
ms.assetid: 6e30ddee-d058-4c8d-9956-2a43d86f19d5
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d51cc4caa7a1018e85cc880cf45894abc861d250
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-sink-windows-forms-events-from-native-c-classes"></a>방법: 네이티브 C++ 클래스에서 Windows Forms 이벤트 싱크
Windows Forms 컨트롤 또는 MFC 매크로 맵 형식의 다른 폼에서 발생 하는 관리 되는 이벤트의 콜백을 받을 수 있는 네이티브 c + + 클래스를 사용할 수 있습니다. 뷰 및 대화 상자에 이벤트 싱크 컨트롤에 대 한 동일한 작업을 수행 하는 것과 비슷합니다.  
  
 이 작업을 수행 하려면:  
  
-   연결 된 `OnClick` 이벤트 처리기를 사용 하 여 컨트롤 [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)합니다.  
  
-   사용 하 여 대리자 맵 만들기 [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map), [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map), 및 [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)합니다.  
  
 이 샘플에서 수행한 작업을 계속 [하는 방법: Windows Forms에서 DDX/DDV 데이터 바인딩 수행](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)합니다.  
  
 이제, MFC 컨트롤을 연결 합니다 (`m_MyControl`) 라는 관리 되는 이벤트 처리기 대리자와 `OnClick` 관리 되는 항목에 대 한 <xref:System.Windows.Forms.Control.Click> 이벤트입니다.  
  
### <a name="to-attach-the-onclick-event-handler"></a>OnClick 이벤트 처리기를 연결 합니다.  
  
1.  BOOL CMFC01Dlg::OnInitDialog의 구현에 다음 코드를 추가 합니다.  
  
    ```  
    m_MyControl.GetControl()->button1->Click += MAKE_DELEGATE( System::EventHandler, OnClick );  
    ```  
  
2.  CMFC01Dlg 클래스의 선언에 공개 섹션에 다음 코드를 추가: 공개 CDialog 합니다.  
  
    ```  
    // delegate map  
    BEGIN_DELEGATE_MAP( CMFC01Dlg )  
    EVENT_DELEGATE_ENTRY( OnClick, System::Object^, System::EventArgs^ )  
    END_DELEGATE_MAP()  
  
    void OnClick( System::Object^ sender, System::EventArgs^ e );  
    ```  
  
3.  마지막으로,에 대 한 구현을 추가 `OnClick` CMFC01Dlg.cpp에:  
  
    ```  
    void CMFC01Dlg::OnClick(System::Object^ sender, System::EventArgs^ e)  
    {  
        AfxMessageBox(_T("Button clicked"));  
    }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [MAKE_DELEGATE](../mfc/reference/delegate-and-interface-maps.md#make_delegate)   
 [BEGIN_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#begin_delegate_map)   
 [END_DELEGATE_MAP](../mfc/reference/delegate-and-interface-maps.md#end_delegate_map)   
 [EVENT_DELEGATE_ENTRY](../mfc/reference/delegate-and-interface-maps.md#event_delegate_entry)