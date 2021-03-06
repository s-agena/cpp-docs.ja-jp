---
title: インライン アセンブリでのデータ ディレクティブと演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data directives [C++]
- __asm keyword [C++], referencing limitations
- MASM (Microsoft Macro Assembler), directives
- directives [C++], MASM
- MASM (Microsoft Macro Assembler), structures
- operators [MASM]
- inline assembly, operators
- inline assembly, data directives
- MASM (Microsoft Macro Assembler), operators
- structures [C++], MASM
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bd3bc686cc8cee1a02e9df936f80f542bec26bd
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>インライン アセンブリでのデータ ディレクティブと演算子
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 ただし、`__asm`ブロックは、C または C++ のデータ型およびオブジェクトを参照できる、MASM ディレクティブまたは演算子を持つデータ オブジェクトを定義できません。 具体的には、定義ディレクティブを使用することはできません**DB**、 `DW`、 **DD**、 `DQ`、 `DT`、および`DF`、か、または演算子`DUP`または**これは、**です。 MASM の構造とレコードもご利用いただけません。 インライン アセンブラーは、ディレクティブを受け取らない`STRUC`、 `RECORD`、**幅**、または**マスク**です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)