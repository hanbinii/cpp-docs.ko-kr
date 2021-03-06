---
title: task_options 클래스(동시성 런타임)
ms.date: 11/04/2016
f1_keywords:
- ppltasks/concurrency::task_options
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
ms.openlocfilehash: c832ce759c556765fa412b2ef77333bc6612b8c3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265212"
---
# <a name="taskoptions-class-concurrency-runtime"></a>task_options 클래스(동시성 런타임)

작업을 만드는 데 사용할 수 있는 옵션을 나타냅니다.

## <a name="syntax"></a>구문

```
class task_options;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[task_options:: task_options 생성자 (동시성 런타임)](#ctor)|오버로드됨. 작업 생성 옵션의 기본 목록|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[task_options:: get_cancellation_token 메서드 (동시성 런타임)](#get_cancellation_token)|취소 토큰을 반환합니다.|
|[task_options:: get_continuation_context 메서드 (동시성 런타임)](#get_continuation_context)|연속 컨텍스트를 반환합니다.|
|[task_options:: get_scheduler 메서드 (동시성 런타임)](#get_scheduler)|스케줄러를 반환합니다.|
|[task_options:: has_cancellation_token 메서드 (동시성 런타임)](#has_cancellation_token)|사용자가 취소 토큰을 지정했는지 여부를 나타냅니다.|
|[task_options:: has_scheduler 메서드 (동시성 런타임)](#has_scheduler)|사용자가 스케줄러 n을 지정했는지 여부를 나타냅니다.|
|[task_options:: set_cancellation_token 메서드 (동시성 런타임)](#set_cancellation_token)|옵션에서 지정된 토큰을 설정합니다.|
|[task_options:: set_continuation_context 메서드 (동시성 런타임)](#set_continuation_context)|옵션에서 지정된 연속 컨텍스트를 설정합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`task_options`

## <a name="requirements"></a>요구 사항

**헤더:** ppltasks.h

**네임스페이스:** 동시성

##  <a name="get_cancellation_token"></a>  task_options:: get_cancellation_token 메서드 (동시성 런타임)

취소 토큰을 반환합니다.

```
cancellation_token get_cancellation_token() const;
```

### <a name="return-value"></a>반환 값

##  <a name="get_continuation_context"></a>  task_options:: get_continuation_context 메서드 (동시성 런타임)

연속 컨텍스트를 반환합니다.

```
task_continuation_context get_continuation_context() const;
```

### <a name="return-value"></a>반환 값

##  <a name="get_scheduler"></a>  task_options:: get_scheduler 메서드 (동시성 런타임)

스케줄러를 반환합니다.

```
scheduler_ptr get_scheduler() const;
```

### <a name="return-value"></a>반환 값

##  <a name="has_cancellation_token"></a>  task_options:: has_cancellation_token 메서드 (동시성 런타임)

사용자가 취소 토큰을 지정했는지 여부를 나타냅니다.

```
bool has_cancellation_token() const;
```

### <a name="return-value"></a>반환 값

##  <a name="has_scheduler"></a>  task_options:: has_scheduler 메서드 (동시성 런타임)

사용자가 스케줄러 n을 지정했는지 여부를 나타냅니다.

```
bool has_scheduler() const;
```

### <a name="return-value"></a>반환 값

##  <a name="set_cancellation_token"></a>  task_options:: set_cancellation_token 메서드 (동시성 런타임)

옵션에서 지정된 토큰을 설정합니다.

```
void set_cancellation_token(cancellation_token _Token);
```

### <a name="parameters"></a>매개 변수

`_Token`

##  <a name="set_continuation_context"></a>  task_options:: set_continuation_context 메서드 (동시성 런타임)

옵션에서 지정된 연속 컨텍스트를 설정합니다.

```
void set_continuation_context(task_continuation_context _ContinuationContext);
```

### <a name="parameters"></a>매개 변수

`_ContinuationContext`

##  <a name="ctor"></a>  task_options:: task_options 생성자 (동시성 런타임)

작업 생성 옵션의 기본 목록

```
task_options();

task_options(
    cancellation_token _Token);

task_options(
    task_continuation_context _ContinuationContext);

task_options(
    cancellation_token _Token,
    task_continuation_context _ContinuationContext);

template<typename _SchedType>
task_options(
    std::shared_ptr<_SchedType> _Scheduler);

task_options(
    scheduler_interface& _Scheduler);

task_options(
    scheduler_ptr _Scheduler);

task_options(
    const task_options& _TaskOptions);
```

### <a name="parameters"></a>매개 변수

`_SchedType`

`_Token`

`_ContinuationContext`

`_Scheduler`

`_TaskOptions`

## <a name="see-also"></a>참고자료

[concurrency 네임스페이스](concurrency-namespace.md)
