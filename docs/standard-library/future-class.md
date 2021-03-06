---
title: future クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::future
- future/std::future::future
- future/std::future::get
- future/std::future::share
- future/std::future::valid
- future/std::future::wait
- future/std::future::wait_for
- future/std::future::wait_until
dev_langs:
- C++
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::future [C++]
- std::future [C++], future
- std::future [C++], get
- std::future [C++], share
- std::future [C++], valid
- std::future [C++], wait
- std::future [C++], wait_for
- std::future [C++], wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: 31490578b1f1d9b6028b3fa2cdcc5769d3a53935
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="future-class"></a>future クラス

*非同期のリターン オブジェクト*を記述します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
class future;
```

## <a name="remarks"></a>コメント

各標準*非同期プロバイダー*は、このテンプレートのインスタンス化の型を持つオブジェクトを返します。 `future` オブジェクトは、関連付けられている非同期プロバイダーへのアクセスのみを提供します。 同じ非同期プロバイダーに関連付けられている複数の非同期リターン オブジェクトが必要な場合は、`future` オブジェクトを [shared_future](../standard-library/shared-future-class.md) オブジェクトにコピーします。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[future](#future)|`future` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get](#get)|関連付けられた非同期状態に格納されている結果を取得します。|
|[share](#share)|オブジェクトを `shared_future` に変換します。|
|[valid](#valid)|オブジェクトが空でないかどうかを指定します。|
|[wait](#wait)|関連付けられた非同期状態が準備できるまで、現在のスレッドをブロックします。|
|[wait_for](#wait_for)|関連付けられた非同期状態が準備できるまで、または指定した時間が経過するまでブロックします。|
|[wait_until](#wait_until)|関連付けられた非同期状態が準備できるまで、または指定した時点までブロックします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[future::operator=](#op_eq)|指定したオブジェクトから関連付けられた非同期状態を転送します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<将来 >

**名前空間:** std

## <a name="future"></a>  future::future コンストラクター

`future` オブジェクトを構築します。

```cpp
future() noexcept;
future(future&& Other) noexcept;
```

### <a name="parameters"></a>パラメーター

`Other` A`future`オブジェクト。

### <a name="remarks"></a>コメント

1 つ目のコンストラクターは、関連付けられた非同期状態がない `future` オブジェクトを構築します。

2 つ目のコンストラクターは、`future` オブジェクトを構築し、`Other` から関連付けられた非同期状態を転送します。 `Other` に関連付けられた非同期状態は既にありません。

## <a name="get"></a>  future::get

関連付けられた非同期状態に格納されている結果を取得します。

```cpp
Ty get();
```

### <a name="return-value"></a>戻り値

結果が例外の場合は、そのメソッドが再スローします。 それ以外の場合、結果が返されます。

### <a name="remarks"></a>コメント

結果を取得する前に、このメソッドは、関連付けられた非同期状態が準備できるまで、現在のスレッドをブロックします。

部分的特殊化 `future<Ty&>` では、格納されている値は、実質的には非同期プロバイダーに戻り値として渡されたオブジェクトへの参照です。

特殊化 `future<void>` には格納されている値がないため、このメソッドは `void` を返します。

その他の特殊化では、メソッドは、格納されている値からその戻り値を移動します。 そのため、このメソッドを 1 回だけ呼び出します。

## <a name="op_eq"></a>  future::operator=

関連付けられた非同期状態から、指定したオブジェクトを転送します。

```cpp
future& operator=(future&& Right) noexcept;
```

### <a name="parameters"></a>パラメーター

`Right` A`future`オブジェクト。

### <a name="return-value"></a>戻り値

`*this`

### <a name="remarks"></a>コメント

転送の後、`Right` に関連付けられた非同期状態は既にありません。

## <a name="share"></a>  future::share

オブジェクトを [shared_future](../standard-library/shared-future-class.md) オブジェクトに変換します。

```cpp
shared_future<Ty> share();
```

### <a name="return-value"></a>戻り値

`shared_future(move(*this))`

## <a name="valid"></a>  future::valid

オブジェクトが関連付けられた非同期状態であるかどうかを指定します。

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>戻り値

オブジェクトが関連付けられた非同期状態である場合は `true` を返します。それ以外の場合は `false` を返します。

## <a name="wait"></a>  future::wait

関連付けられた非同期状態が *ready* になるまで、現在のスレッドをブロックします。

```cpp
void wait() const;
```

### <a name="remarks"></a>コメント

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ *ready* になります。

## <a name="wait_for"></a>  future::wait_for

関連付けられた非同期状態が *ready* になるまで、または指定した時間が経過するまでブロックします。

```cpp
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>パラメーター

`Rel_time` A [:duration](../standard-library/duration-class.md)最大時間間隔を指定するオブジェクトをそのスレッドはブロックされます。

### <a name="return-value"></a>戻り値

呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status)。

### <a name="remarks"></a>コメント

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ準備完了になります。

## <a name="wait_until"></a>  future::wait_until

関連付けられた非同期状態が *ready* になるまで、または指定した時点後まで現在のスレッドをブロックします。

```cpp
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>パラメーター

`Abs_time` A [chrono::time_point](../standard-library/time-point-class.md)するまで、スレッド ブロックを解除できます時間を指定するオブジェクト。

### <a name="return-value"></a>戻り値

呼び出し側に戻る理由を示す [future_status](../standard-library/future-enums.md#future_status)。

### <a name="remarks"></a>コメント

関連付けられている非同期状態は、非同期プロバイダーが戻り値を格納した場合か例外を格納した場合のみ *ready* になります。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
