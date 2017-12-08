---
title: "에이전트 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agent
- AGENTS/concurrency::agent
- AGENTS/concurrency::agent::agent
- AGENTS/concurrency::agent::cancel
- AGENTS/concurrency::agent::start
- AGENTS/concurrency::agent::status
- AGENTS/concurrency::agent::status_port
- AGENTS/concurrency::agent::wait
- AGENTS/concurrency::agent::wait_for_all
- AGENTS/concurrency::agent::wait_for_one
- AGENTS/concurrency::agent::done
- AGENTS/concurrency::agent::run
dev_langs:
- C++
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 1e6e23e742137bffd9035ecf69ecc32d199ca0c5
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="agent-class"></a>에이전트 클래스
모든 독립 에이전트에 대한 기본 클래스로 사용되는 클래스입니다. 다른 에이전트로부터 상태를 숨기고 메시지 전달을 사용하여 상호 작용하는 데 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```
class agent;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[에이전트](#ctor)|오버로드됨. 에이전트를 생성 합니다.|  
|[~ agent 소멸자](#dtor)|에이전트를 삭제합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[취소](#cancel)|에이전트에서 이동 하는 `agent_created` 또는 `agent_runnable` 상태는 `agent_canceled` 상태입니다.|  
|[start](#start)|에이전트에서 이동 된 `agent_created` 상태는 `agent_runnable` 상태 이며 실행을 예약 합니다.|  
|[status](#status)|동기 하는 원본 에이전트에서 상태 정보입니다.|  
|[status_port](#status_port)|비동기 소스는 에이전트의 상태 정보입니다.|  
|[대기](#wait)|에이전트 작업을 완료 하기를 기다립니다.|  
|[wait_for_all](#wait_for_all)|모든 작업을 완료 하려면 지정 된 에이전트에 대 한 대기 합니다.|  
|[wait_for_one](#wait_for_one)|작업을 완료 하기 지정한 에이전트 중 하나를 기다립니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[작업 수행](#done)|이동에 에이전트는 `agent_done` 에이전트가 완료 되었음을 나타내는 상태입니다.|  
|[run](#run)|에이전트의 주요 작업을 나타냅니다. `run`파생된 클래스에서 재정의 하 고 에이전트에서 수행 해야 할 작업을 지정 합니다. 이미 시작 되었습니다.|  
  
## <a name="remarks"></a>주의  
 자세한 내용은 참조 [비동기 에이전트](../../../parallel/concrt/asynchronous-agents.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `agent`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** agents.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="ctor"></a>에이전트 

 에이전트를 생성 합니다.  
  
```
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PScheduler`  
 `Scheduler` 개체 내 에이전트의 실행 작업이 예약 됩니다.  
  
 `_PGroup`  
 `ScheduleGroup` 개체 내 에이전트의 실행 작업이 예약 됩니다. 사용된 `Scheduler` 개체는 일정 그룹에서 암시됩니다.  
  
### <a name="remarks"></a>주의  
 런타임에서 지정 하지 않은 경우 기본 스케줄러를 사용 하 여 `_PScheduler` 또는 `_PGroup` 매개 변수입니다.  
  
##  <a name="dtor"></a>~ 에이전트 

 에이전트를 삭제합니다.  
  
```
virtual ~agent();
```  
  
### <a name="remarks"></a>주의  
 오류가 발생 한 터미널 상태에 있지 않은 에이전트를 제거 (하거나 `agent_done` 또는 `agent_canceled`). 이 에이전트에서 상속 되는 클래스의 소멸자에 터미널 상태에 도달할 때까지 대기 하 여 방지할 수는 `agent` 클래스입니다.  
  
##  <a name="cancel"></a>취소 

 에이전트에서 이동 하는 `agent_created` 또는 `agent_runnable` 상태는 `agent_canceled` 상태입니다.  
  
```
bool cancel();
```  
  
### <a name="return-value"></a>반환 값  
 `true`에이전트 취소 된 경우 `false` 그렇지 않은 경우. 이미 실행을 시작 하거나 이미 완료 된 경우 에이전트를 취소할 수 없습니다.  
  
##  <a name="done"></a>작업 수행 

 이동에 에이전트는 `agent_done` 에이전트가 완료 되었음을 나타내는 상태입니다.  
  
```
bool done();
```  
  
### <a name="return-value"></a>반환 값  
 `true`에이전트로 이동 하는 경우는 `agent_done` 상태 `false` 그렇지 않은 경우. 에이전트는 취소 되었습니다.로 이동할 수 없는 `agent_done` 상태입니다.  
  
### <a name="remarks"></a>주의  
 끝에이 메서드를 호출 해야는 `run` 에이전트의 실행을 알고 있는 경우 메서드를 완료 합니다.  
  
##  <a name="run"></a>실행 

 에이전트의 주요 작업을 나타냅니다. `run`파생된 클래스에서 재정의 하 고 에이전트에서 수행 해야 할 작업을 지정 합니다. 이미 시작 되었습니다.  
  
```
virtual void run() = 0;
```  
  
### <a name="remarks"></a>설명  
 에이전트 상태가으로 변경 `agent_started` 이 메서드를 호출 하기 전에 오른쪽입니다. 메서드를 호출 해야 `done` 반환 하기 전에 적절 한 상태로 에이전트에서 하며 예외를 throw 하지 않을 수 있습니다.  
  
##  <a name="start"></a>시작 

 에이전트에서 이동 된 `agent_created` 상태는 `agent_runnable` 상태 이며 실행을 예약 합니다.  
  
```
bool start();
```  
  
### <a name="return-value"></a>반환 값  
 `true`에이전트가 올바르게 시작 하는 경우 `false` 그렇지 않은 경우. 취소 된 에이전트를 시작할 수 없습니다.  
  
##  <a name="status"></a>상태 

 동기 하는 원본 에이전트에서 상태 정보입니다.  
  
```
agent_status status();
```  
  
### <a name="return-value"></a>반환 값  
 에이전트의 현재 상태를 반환합니다. 이 반환 되는 상태 즉시 변경할 수 있습니다 반환 되는 참고 합니다.  
  
##  <a name="status_port"></a>status_port 

 비동기 소스는 에이전트의 상태 정보입니다.  
  
```
ISource<agent_status>* status_port();
```  
  
### <a name="return-value"></a>반환 값  
 에이전트의 현재 상태에 대 한 메시지를 보낼 수 있는 메시지 소스를 반환 합니다.  
  
##  <a name="wait"></a>대기 

 에이전트 작업을 완료 하기를 기다립니다.  
  
```
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>매개 변수  
 `_PAgent`  
 대기 하는 에이전트에 대 한 포인터입니다.  
  
 `_Timeout`  
 최대 시간 (밀리초) 대기할입니다.  
  
### <a name="return-value"></a>반환 값  
 `agent_status` 대기가 완료 되 면 에이전트입니다. 이 수 `agent_canceled` 또는 `agent_done`합니다.  
  
### <a name="remarks"></a>설명  
 에이전트에 들어가면 에이전트 작업이 완료 되는 `agent_canceled` 또는 `agent_done` 상태입니다.  
  
 경우 매개 변수 `_Timeout` 상수 이외의 값이 `COOPERATIVE_TIMEOUT_INFINITE`, 예외 [operation_timed_out](operation-timed-out-class.md) 에이전트에서 해당 작업이 완료 되기 전에 특정된 기간 동안 만료 된 경우 throw 됩니다.  
  
##  <a name="wait_for_all"></a>wait_for_all 

 모든 작업을 완료 하려면 지정 된 에이전트에 대 한 대기 합니다.  
  
```
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>매개 변수  
 `count`  
 에이전트 포인터는 배열에 있는 수 `_PAgents`합니다.  
  
 `_PAgents`  
 에이전트에 대 한 대기에 대 한 포인터의 배열입니다.  
  
 `_PStatus`  
 에이전트 상태에 대해 알아보려면 배열에 대 한 포인터입니다. 메서드가 반환 될 때 각 상태 값은 해당 에이전트의 상태를 나타냅니다.  
  
 `_Timeout`  
 최대 시간 (밀리초) 대기할입니다.  
  
### <a name="remarks"></a>주의  
 에이전트에 들어가면 에이전트 작업이 완료 되는 `agent_canceled` 또는 `agent_done` 상태입니다.  
  
 경우 매개 변수 `_Timeout` 상수 이외의 값이 `COOPERATIVE_TIMEOUT_INFINITE`, 예외 [operation_timed_out](operation-timed-out-class.md) 에이전트에서 해당 작업이 완료 되기 전에 특정된 기간 동안 만료 된 경우 throw 됩니다.  
  
##  <a name="wait_for_one"></a>wait_for_one 

 작업을 완료 하기 지정한 에이전트 중 하나를 기다립니다.  
  
```
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>매개 변수  
 `count`  
 에이전트 포인터는 배열에 있는 수 `_PAgents`합니다.  
  
 `_PAgents`  
 에이전트에 대 한 대기에 대 한 포인터의 배열입니다.  
  
 `_Status`  
 에이전트 상태를 저장할 변수 참조입니다.  
  
 `_Index`  
 변수 에이전트 인덱스 배치 될 위치에 대 한 참조입니다.  
  
 `_Timeout`  
 최대 시간 (밀리초) 대기할입니다.  
  
### <a name="remarks"></a>주의  
 에이전트에 들어가면 에이전트 작업이 완료 되는 `agent_canceled` 또는 `agent_done` 상태입니다.  
  
 경우 매개 변수 `_Timeout` 상수 이외의 값이 `COOPERATIVE_TIMEOUT_INFINITE`, 예외 [operation_timed_out](operation-timed-out-class.md) 에이전트에서 해당 작업이 완료 되기 전에 특정된 기간 동안 만료 된 경우 throw 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
