---
title: スカラー型の初期化 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- initializing scalar types
- register variables
- initialization, scalar types
- initializing variables, scalar types
- scalar types
- static variables, initializing
- automatic storage class, initializing scalar types
- automatic storage class
- types [C], initializing
ms.assetid: 73c516f5-c3ad-4d56-ab3b-f2a82b621104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fef7356768a594694e0fcf3415c66ef63568a7cf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="initializing-scalar-types"></a>スカラー型の初期化
スカラー型を初期化すると、*assignment-expression* の値が変数に代入されます。 代入の変換規則が適用されます  (変換規則については、「[型変換](../c-language/type-conversions-c.md)」を参照)。  
  
## <a name="syntax"></a>構文  
 `declaration`:  
 *declaration-specifiers init-declarator-list* opt **;**  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *init-declarator-list*:  
 *init-declarator*  
  
 *init-declarator-list*  **,**  *init-declarator*  
  
 *init-declarator*:  
 *declarator*  
  
 *declarator*  **=**  *initializer* /* スカラー初期化用 \*/  
  
 *initializer*:  
 *assignment-expression*  
  
 次の規則に従って、あらゆる型の変数を初期化できます。  
  
-   ファイル スコープ レベルで宣言された変数は初期化できます。 外部レベルで明示的に変数を初期化しない場合、既定で 0 に初期化されます。  
  
-   **static** *storage-class-specifier* を指定して宣言されたすべてのグローバル変数は、定数式を使用して初期化できます。 **static** として宣言された変数は、プログラムの実行開始時に初期化されます。 グローバル **static** 変数を明示的に初期化しない場合は、既定で 0 に初期化され、ポインター型を持つすべてのメンバーに null ポインターが割り当てられます。  
  
-   **auto** または **register** のストレージ クラス指定子によって宣言された変数は、それらの変数が宣言されたブロックに実行制御が渡されるたびに初期化されます。 **auto** 変数または **register** 変数の宣言で初期化子を省略すると、変数の初期値が未定義になります。 自動値とレジスタ値では初期化子が定数に限定されていないため、定義済みの値や関数呼び出しを含む任意の式を指定できます。  
  
-   外部変数の宣言の初期値およびすべての **static** 変数 (外部変数または内部変数) の初期値は、定数式である必要があります (詳細については、「[定数式](../c-language/c-constant-expressions.md)」を参照)。外部宣言された変数または静的変数のアドレスは定数であるため、内部宣言された **static** ポインター変数の初期化に使用できます。 ただし、**auto** 変数のアドレスは、ブロックの実行ごとに異なる可能性があるため、静的初期化子として使用できません。 **auto** 変数と **register** 変数の初期化には、定数値または変数値のいずれも使用できます。  
  
-   識別子の宣言にブロック スコープが存在し、識別子に外部リンケージがある場合、宣言に初期化を含めることはできません。  
  
## <a name="examples"></a>使用例  
 次の例では初期化を示します。  
  
```  
int x = 10;   
```  
  
 整数変数 `x` は定数式 `10` に初期化されます。  
  
```  
register int *px = 0;  
```  
  
 ポインター `px` は 0 に初期化され、"null" ポインターが作成されます。  
  
```  
const int c = (3 * 1024);  
```  
  
 この例では定数式 `(3 * 1024)` を使用し、**const** キーワードによって `c` を変更できない定数値に初期化します。  
  
```  
int *b = &x;  
```  
  
 このステートメントは、`b` を別の変数 `x` のアドレスで初期化します。  
  
```  
int *const a = &z;  
```  
  
 ポインター `a` が `z` という名前の変数のアドレスで初期化されます。 ただし、変数 `a` は **const** と指定されているため、初期化はできますが変更はできません。 これは、常に同じ場所を指します。  
  
```  
int GLOBAL ;  
  
int function( void )  
{  
    int LOCAL ;  
    static int *lp = &LOCAL;   /* Illegal initialization */  
    static int *gp = &GLOBAL;  /* Legal initialization   */  
    register int *rp = &LOCAL; /* Legal initialization   */  
}  
```  
  
 グローバル変数 `GLOBAL` は外部レベルで宣言されるため、グローバル有効期間があります。 ローカル変数 `LOCAL` には **auto** ストレージ クラスがあり、このローカル変数を宣言する関数の実行中のみアドレスが存在します。 したがって、**static** ポインター変数 `lp` を `LOCAL` のアドレスで初期化することはできません。 `GLOBAL` のアドレスは常に同じであるため、**static** ポインター変数 `gp` をこのアドレスに初期化できます。 同様に、`*rp` がローカル変数であり、定数でない初期化子を指定できるため、`rp` は初期化できます。 ブロックが入力されるたびに `LOCAL` に新しいアドレスが割り当てられ、それが `rp` に割り当てられます。  
  
## <a name="see-also"></a>参照  
 [初期化](../c-language/initialization.md)