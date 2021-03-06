---
title: _strtoi64、_wcstoi64、_strtoi64_l、_wcstoi64_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _strtoi64
- _strtoi64_l
- _wcstoi64_l
- _wcstoi64
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _strtoi64
- strtoi64
- _stroi64_l
- _wcstoi64_l
- wcstoi64_l
- _wcstoi64
- wcstoi64
- strtoi64_l
dev_langs:
- C++
helpviewer_keywords:
- _strtoi64 function
- _wcstoi64 function
- _strtoi64_l function
- string conversion, to integers
- _wcstoi64_l function
- strtoi64_l function
- wcstoi64 function
- strtoi64 function
- wcstoi64_l function
ms.assetid: ea2abc50-7bfe-420e-a46b-703c3153593a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77997cd5a10a4f4b5f637bcf24730505ca4b9a6b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="strtoi64-wcstoi64-strtoi64l-wcstoi64l"></a>_strtoi64、_wcstoi64、_strtoi64_l、_wcstoi64_l

文字列を変換、 **_ _int64**値。

## <a name="syntax"></a>構文

```C
__int64 _strtoi64(
   const char *strSource,
   char **endptr,
   int base
);
__int64 _wcstoi64(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
__int64 _strtoi64_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
__int64 _wcstoi64_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*strSource*<br/>
NULL で終わる変換対象の文字列。

*endptr*<br/>
スキャンの終了位置を示す文字へのポインター。

*base*<br/>
使用する基数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_strtoi64**文字列で表される値を返します*strSource*オーバーフローを引き起こすよう、ときに場合を返します点を除いて、 **_I64_MAX**または **_I64_MIN**です。 この関数は、変換を実行できない場合には 0 を返します。 **_wcstoi64**戻り値を返します**strtoi64**です。

**_I64_MAX**と **_I64_MIN**制限で定義されます。H.

場合*strSource*は**NULL**または*基本*が 0 でないと、2 未満または 36 を超える**errno**に設定されている**EINVAL**.

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

**_Strtoi64**関数に変換*strSource*を **_ _int64**です。 どちらの関数は、文字列の読み取りを停止*strSource*数値の一部として認識できない最初の文字です。 大きいか等しいには、最初の数値文字がある可能性がありますか終端の null 文字あります*基本*です。 **_wcstoi64**のワイド文字バージョンは、 **_strtoi64**以外の場合はその*strSource*引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoi64**|**_strtoi64**|**_strtoi64**|**_wcstoi64**|
|**_tcstoi64_l**|**_strtoi64_l**|**_strtoi64_l**|**_wcstoi64_l**|

ロケールの**LC_NUMERIC**カテゴリの設定によっての小数点文字の認識 ** *; strSource*詳細については、次を参照してください。 [setlocale、_wsetlocale](setlocale-wsetlocale.md)です。 _L サフィックスが付いていない関数は現在のロケールを使用します。**_strtoi64_l**と **_wcstoi64_l**せず、対応する関数と同じでは、 **_l**サフィックスを代わりに渡されたロケール パラメーターを使用する点を除いて。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合*endptr*は**NULL**、スキャンを停止させた文字へのポインターが指す位置に格納されている*endptr*です。 変換を実行できない場合 (有効な数字が見つからないか無効な base を指定した) の値*strSource*が指す位置に格納されて*endptr*です。

**_strtoi64**が必要ですが*strSource*して次の形式の文字列を指します。

> [*空白*] [{**+** &#124; **-**}] [**0** [{ **x**&#124; **X** }] [*桁*&#124; *文字*]  

A*空白*は無視されますスペースやタブ文字で構成されている可能性があります。*桁*は 1 つ以上の 10 進数字です。*文字*1 つまたは複数の文字は、'a' から 'z' ('A' ~ 'Z')。  この形式に一致しない文字を見つけるとスキャンを停止します。 場合*基本*2 ~ 36 の間は、数値の基数として使用されます。 場合*基本*0 によって示される文字列の先頭の文字は、 *strSource*基数を判定するために使用します。 最初の文字が 0 で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 'a' ～ 'z' (または 'A' ～ 'Z') の文字には、10 ～ 35 の値が割り当てられています。*基数*よりも小さい値が割り当てられている文字のみ許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 たとえば場合、*基本*0 は、スキャンされた最初の文字が '0' と見なされます、8 進数と、'8' または '9' の文字は、スキャンは停止します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_strtoi64**、 **_strtoi64_l**|\<stdlib.h>|
|**_wcstoi64**、 **_wcstoi64_l**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod、_strtod_l、wcstod、_wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul、_strtoul_l、wcstoul、_wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
