---
title: is_placeholder クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::is_placeholder
dev_langs:
- C++
helpviewer_keywords:
- is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b577803f766d8f5cafa054e84b5b7ec0f152480b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="isplaceholder-class"></a>is_placeholder クラス

型がプレースホルダーであるかどうかをテストします。

## <a name="syntax"></a>構文

構造体 is_placeholder {static const int 値;} です。

## <a name="remarks"></a>コメント

型 `Ty` がプレース ホルダーではない場合、定数値 `value` は 0 となります。それ以外の場合、値は、バインドされる関数呼び出しの引数の位置になります。 これを使用して、N 番目のプレースホルダー `_N` の値 `N` を決定します。

## <a name="example"></a>例

```cpp
// std__functional__is_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

using namespace std::placeholders;

template<class Expr>
void test_for_placeholder(const Expr&)
{
    std::cout << std::is_placeholder<Expr>::value << std::endl;
}

int main()
{
    test_for_placeholder(3.0);
    test_for_placeholder(_3);

    return (0);
}
```

```Output
0
3
```

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[_1 オブジェクト](../standard-library/1-object.md)<br/>
