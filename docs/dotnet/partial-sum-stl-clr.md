---
title: partial_sum (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::partial_sum
dev_langs: C++
helpviewer_keywords: partial_sum function [STL/CLR]
ms.assetid: 845badae-8519-4ac8-9ea7-2b921bac7c51
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d8a92858303af5050706849f7e688d08ad36f321
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="partialsum-stlclr"></a>partial_sum(STL/CLR)
일련의 첫 번째 요소를 통해 입력 범위의 합계를 계산 합니다.는 `i`th 요소 각 합계의 결과 저장 하 고 `i`번째 요소를 대상 범위로 하거나 일반화 된 절차 결과를 계산 합니다. 여기서 합 연산을 지정 된 다른 이진 연산으로 대체 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>설명  
 이 함수는 c + + 표준 라이브러리 숫자 함수와 동일 하 게 작동 `partial_sum`합니다. 자세한 내용은 참조 [partial_sum](../standard-library/numeric-functions.md#partial_sum)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/숫자 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [numeric(STL/CLR)](../dotnet/numeric-stl-clr.md)