---
title: condition_variable 클래스
ms.date: 11/04/2016
f1_keywords:
- condition_variable/std::condition
- condition_variable/std::condition_variable::condition_variable
- condition_variable/std::condition_variable::native_handle
- condition_variable/std::condition_variable::notify_all
- condition_variable/std::condition_variable::notify_one
- condition_variable/std::condition_variable::wait
- condition_variable/std::condition_variable::wait_for
- condition_variable/std::condition_variable::wait_until
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
helpviewer_keywords:
- std::condition
- std::condition_variable::condition_variable
- std::condition_variable::native_handle
- std::condition_variable::notify_all
- std::condition_variable::notify_one
- std::condition_variable::wait
- std::condition_variable::wait_for
- std::condition_variable::wait_until
ms.openlocfilehash: 52e64df7522c5e58fa64398f599bffa4614a2684
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212388"
---
# <a name="conditionvariable-class"></a>condition_variable 클래스

`unique_lock<mutex>` 형식의 `mutex`가 있는 경우 `condition_variable` 클래스를 사용하여 이벤트를 대기합니다. 이 형식의 개체는 [condition_variable_any<unique_lock\<mutex>>](../standard-library/condition-variable-any-class.md) 형식의 개체보다 성능이 더 나을 수 있습니다.

## <a name="syntax"></a>구문

```cpp
class condition_variable;
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[condition_variable](#condition_variable)|`condition_variable` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[native_handle](#native_handle)|Condition_variable 핸들을 나타내는 구현 관련 형식을 반환합니다.|
|[notify_all](#notify_all)|`condition_variable` 개체를 대기 중인 모든 스레드를 차단 해제합니다.|
|[notify_one](#notify_one)|`condition_variable` 개체를 대기 중인 스레드 중 하나를 차단 해제합니다.|
|[wait](#wait)|스레드를 차단합니다.|
|[wait_for](#wait_for)|스레드를 차단하고 스레드가 차단 해제되는 시간 간격을 설정합니다.|
|[wait_until](#wait_until)|스레드를 차단하고 스레드가 차단 해제되는 최대 시점을 설정합니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<condition_variable >

**네임스페이스:** std

## <a name="condition_variable"></a>  condition_variable::condition_variable 생성자

`condition_variable` 개체를 생성합니다.

```cpp
condition_variable();
```

### <a name="remarks"></a>설명

메모리가 부족한 경우 생성자에서 `not_enough_memory` 오류 코드가 있는 [system_error](../standard-library/system-error-class.md) 개체를 throw합니다. 몇 가지 다른 리소스를 사용할 수 없기 때문에 개체를 생성할 수 없는 경우 생성자에서 `resource_unavailable_try_again` 오류 코드가 있는 `system_error` 개체를 throw합니다.

## <a name="native_handle"></a>  condition_variable::native_handle

Condition_variable 핸들을 나타내는 구현 관련 형식을 반환합니다.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>반환 값

`native_handle_type`은 동시성 런타임 내부 데이터 구조에 대한 포인터로 정의됩니다.

## <a name="notify_all"></a>  condition_variable::notify_all

`condition_variable` 개체를 대기 중인 모든 스레드를 차단 해제합니다.

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a>  condition_variable::notify_one

`condition_variable` 개체를 기다리는 스레드 중 하나를 차단 해제합니다.

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a>  condition_variable::wait

스레드를 차단합니다.

```cpp
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```

### <a name="parameters"></a>매개 변수

*Lck*<br/>
[unique_lock\<mutex>](../standard-library/unique-lock-class.md) 개체입니다.

*pred*<br/>
반환 하는 식 **true** 하거나 **false**합니다.

### <a name="remarks"></a>설명

첫 번째 메서드는 `condition_variable` 개체에서 [notify_one](#notify_one) 또는 [notify_all](#notify_all)에 대한 호출을 통해 신호를 받을 때까지 차단합니다. 또한 의사적으로 대기 모드를 해제할 수도 있습니다.

사실 두 번째 방법은 다음 코드를 실행합니다.

```cpp
while(!Pred())
    wait(Lck);
```

## <a name="wait_for"></a>  condition_variable::wait_for

스레드를 차단하고 스레드가 차단 해제되는 시간 간격을 설정합니다.

```cpp
template <class Rep, class Period>
cv_status wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time);

template <class Rep, class Period, class Predicate>
bool wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time,
    Predicate Pred);
```

### <a name="parameters"></a>매개 변수

*Lck*<br/>
[unique_lock\<mutex>](../standard-library/unique-lock-class.md) 개체입니다.

*Rel_time*<br/>
스레드가 대기 모드를 해제하기 전까지의 시간을 지정하는 `chrono::duration` 개체입니다.

*pred*<br/>
반환 하는 식 **true** 하거나 **false**합니다.

### <a name="return-value"></a>반환 값

첫 번째 메서드는 반환 `cv_status::timeout` 대기가 종료 될 때 하는 경우 *Rel_time* 경과 합니다. 그렇지 않은 경우 메서드는 `cv_status::no_timeout`를 반환합니다.

값을 반환 하는 두 번째 방법은 *Pred*합니다.

### <a name="remarks"></a>설명

첫 번째 방법은 될 때까지 차단 합니다 `condition_variable` 개체를 호출 하 여 신호를 받는 [notify_one](#notify_one) 또는 [notify_all](#notify_all) 되거나 시간 간격 *Rel_time* 경과 합니다. 또한 의사적으로 대기 모드를 해제할 수도 있습니다.

사실 두 번째 방법은 다음 코드를 실행합니다.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a>  condition_variable::wait_until

스레드를 차단하고 스레드가 차단 해제되는 최대 시점을 설정합니다.

```cpp
template <class Clock, class Duration>
cv_status wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time);

template <class Clock, class Duration, class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

cv_status wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time);

template <class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time,
    Predicate Pred);
```

### <a name="parameters"></a>매개 변수

*Lck*<br/>
[unique_lock\<mutex>](../standard-library/unique-lock-class.md) 개체입니다.

*Abs_time*<br/>
[chrono::time_point](../standard-library/time-point-class.md) 개체입니다.

*pred*<br/>
반환 하는 식 **true** 하거나 **false**합니다.

### <a name="return-value"></a>반환 값

반환 하는 메서드를 `cv_status` 반환 형식 `cv_status::timeout` 대기가 종료 될 때 경우 *Abs_time* 경과 합니다. 그렇지 않으면 메서드는 `cv_status::no_timeout`을 반환합니다.

반환 하는 메서드를 **bool** 의 값을 반환 *Pred*합니다.

### <a name="remarks"></a>설명

첫 번째 메서드는 `condition_variable` 개체에서 [notify_one](#notify_one) 또는 [notify_all](#notify_all)에 대한 호출을 통해 신호를 받을 때까지 또는 `Abs_time`까지 차단합니다. 또한 의사적으로 대기 모드를 해제할 수도 있습니다.

사실 두 번째 방법은 다음 코드를 실행합니다.

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

세 번째와 네 번째 메서드는 `xtime` 형식의 개체에 대한 포인터를 사용하여 `chrono::time_point` 개체를 대체합니다. `xtime` 개체는 신호를 기다리는 최대 시간을 지정합니다.

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)<br/>
[<condition_variable>](../standard-library/condition-variable.md)<br/>
