---
title: _get_printf_count_output | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_printf_count_output
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_printf_count_output
- _get_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 216df8d973f391db2b6114d9bbcb50dcf509c5b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="getprintfcountoutput"></a>_get_printf_count_output

示すかどうか[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)-ファミリの関数のサポート、 **%n**形式です。

## <a name="syntax"></a>構文

```C
int _get_printf_count_output();
```

## <a name="return-value"></a>戻り値

ゼロ以外の場合 **%n**はサポートされている場合は 0 **%n**はサポートされていません。

## <a name="remarks"></a>コメント

場合 **%n**はサポートなし (既定値) が発生して **%n**のいずれかの書式指定文字列で、 **printf** 」の説明に従って、関数は、無効なパラメーター ハンドラーを呼び出しますが[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 場合 **%n**サポートが有効になっている (を参照してください[_set_printf_count_output](set-printf-count-output.md)) し、 **%n** 」の説明に従って動作[書式指定構文: printf および wprintf関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_get_printf_count_output**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

例については「[_set_printf_count_output](set-printf-count-output.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[_set_printf_count_output](set-printf-count-output.md)<br/>
