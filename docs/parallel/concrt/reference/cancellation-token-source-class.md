---
title: "cancellation_token_source 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancellation_token_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::cancel
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::create_linked_source
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_source::get_token
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_source class
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: f41a4a21af5bc37ab612221152b8311a5a91d914
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="cancellationtokensource-class"></a>cancellation_token_source 클래스
`cancellation_token_source` 클래스는 일부 취소 가능한 작업을 취소하는 기능을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
class cancellation_token_source;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[cancellation_token_source](#ctor)|오버로드됨. 새 `cancellation_token_source`를 생성합니다. 소스는 일부 취소할 수 있는 작업의 취소 플래그를 설정하는 데 사용할 수 있습니다.|  
|[~ cancellation_token_source 소멸자](#dtor)||  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[취소](#cancel)|토큰을 취소합니다. 토큰을 이용하는 `task_group`, `structured_task_group` 또는 `task`는 이 호출 시 취소되며 다음 중단점에서 예외를 throw합니다.|  
|[create_linked_source](#create_linked_source)|오버로드됨. 제공된 토큰이 취소된 경우 취소되는 `cancellation_token_source`를 만듭니다.|  
|[get_token](#get_token)|이 소스와 연결된 취소 토큰을 반환합니다. 반환된 토큰은 취소를 폴링하거나 취소가 발생할 경우 콜백을 제공할 수 있습니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[operator!=](#operator_neq)||  
|[operator=](#operator_eq)||  
|[operator==](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `cancellation_token_source`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** pplcancellation_token.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="dtor"></a>~ cancellation_token_source 

```
~cancellation_token_source();
```  
  
##  <a name="cancel"></a>취소 

 토큰을 취소합니다. 토큰을 이용하는 `task_group`, `structured_task_group` 또는 `task`는 이 호출 시 취소되며 다음 중단점에서 예외를 throw합니다.  
  
```
void cancel() const;
```  
  
##  <a name="ctor"></a>cancellation_token_source 

 새 `cancellation_token_source`를 생성합니다. 소스는 일부 취소할 수 있는 작업의 취소 플래그를 설정하는 데 사용할 수 있습니다.  
  
```
cancellation_token_source();

cancellation_token_source(const cancellation_token_source& _Src);

cancellation_token_source(cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
  
##  <a name="create_linked_source"></a>create_linked_source 

 제공된 토큰이 취소된 경우 취소되는 `cancellation_token_source`를 만듭니다.  
  
```
static cancellation_token_source create_linked_source(
    cancellation_token& _Src);

template<typename _Iter>
static cancellation_token_source create_linked_source(_Iter _Begin, _Iter _End);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Iter`  
 `_Src`  
 취소 시 반환된 토큰 소스가 취소되는 토큰입니다. 반환된 토큰 소스 역시 이 매개 변수에 포함된 소스와 별도로 취소될 수 있습니다.  
  
 `_Begin`  
 해당 되는 c + + 표준 라이브러리 반복기 토큰 범위의 시작 부분으로의 취소에 대 한 수신 대기 하도록 합니다.  
  
 `_End`  
 C + + 표준 라이브러리 반복기 토큰의 범위 끝에 해당의 취소에 대 한 수신 대기 하도록 합니다.  
  
### <a name="return-value"></a>반환 값  
 `cancellation_token_source` 매개 변수에서 제공된 토큰이 취소된 경우 취소되는 `_Src`입니다.  
  
##  <a name="get_token"></a>get_token 

 이 소스와 연결된 취소 토큰을 반환합니다. 반환된 토큰은 취소를 폴링하거나 취소가 발생할 경우 콜백을 제공할 수 있습니다.  
  
```
cancellation_token get_token() const;
```  
  
### <a name="return-value"></a>반환 값  
 이 소스와 연결된 취소 토큰입니다.  
  
##  <a name="operator_neq"></a>연산자! = 

```
bool operator!= (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="operator_eq"></a>연산자 = 

```
cancellation_token_source& operator= (const cancellation_token_source& _Src);

cancellation_token_source& operator= (cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
  
### <a name="return-value"></a>반환 값  
  
##  <a name="operator_eq_eq"></a>연산자 = = 

```
bool operator== (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>매개 변수  
 `_Src`  
  
### <a name="return-value"></a>반환 값  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
