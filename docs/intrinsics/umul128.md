---
title: _umul128 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __umul128
dev_langs:
- C++
helpviewer_keywords:
- __umul128 intrinsic
ms.assetid: 13684df3-3ac7-467c-b258-a0e93bc490b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6998b51be8fd11092c4266fa7eee7434be8e5b1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="umul128"></a>_umul128
**Microsoft 固有の仕様**  
  
 最初の 2 つの引数で渡された 2 つの 64 ビット符号なし整数を乗算し、その積の上位 64 ビットを `HighProduct` の指す 64 ビットの符号なし整数に格納して、積の下位 64 ビットを返します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned __int64 _umul128(   
   unsigned __int64 Multiplier,   
   unsigned __int64 Multiplicand,   
   unsigned __int64 *HighProduct   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `Multiplier`  
 乗算する最初の 64 ビット整数。  
  
 [入力] `Multiplicand`  
 乗算する 2 番目の 64 ビット整数。  
  
 [出力] `HighProduct`  
 積の上位 64 ビット。  
  
## <a name="return-value"></a>戻り値  
 積の下位 64 ビット。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|Header|  
|---------------|------------------|------------|  
|`_umul128`|ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h>|  
  
## <a name="example"></a>例  
  
```  
// umul128.c  
// processor: IPF, x64  
  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_umul128)  
  
int main()  
{  
    unsigned __int64 a = 0x0fffffffffffffffI64;  
    unsigned __int64 b = 0xf0000000I64;  
    unsigned __int64 c, d;  
  
    d = _umul128(a, b, &c);  
  
    printf_s("%#I64x * %#I64x = %#I64x%I64x\n", a, b, c, d);  
}  
```  
  
```Output  
0xfffffffffffffff * 0xf0000000 = 0xeffffffffffffff10000000  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)