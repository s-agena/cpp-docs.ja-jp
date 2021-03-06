---
title: raw_storage_iterator クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::raw_storage_iterator
- memory/std::raw_storage_iterator::element_type
- memory/std::raw_storage_iterator::iter_type
dev_langs:
- C++
helpviewer_keywords:
- std::raw_storage_iterator [C++]
- std::raw_storage_iterator [C++], element_type
- std::raw_storage_iterator [C++], iter_type
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d6c93bfc6525840343c64b8cd804ddb65f68dd5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="rawstorageiterator-class"></a>raw_storage_iterator クラス

アルゴリズムの結果を初期化されていないメモリに格納するために用意されたアダプター クラスです。

## <a name="syntax"></a>構文

```cpp
template <class OutputIterator, class Type>
class raw_storage_iterator
```

### <a name="parameters"></a>パラメーター

`OutputIterator` 格納されているオブジェクトの出力反復子を指定します。

*型*ストレージが割り当てられるオブジェクトの型。

## <a name="remarks"></a>コメント

このクラスは、生成するシーケンス内に **Type** 型のオブジェクトを構築する出力反復子を記述します。 `raw_storage_iterator`\< **ForwardIterator**, **Type**> クラスのオブジェクトは、オブジェクトを構築する際に指定した **ForwardIterator** クラスの前方反復子オブジェクトを介してストレージにアクセスします。 **ForwardIterator** クラスの最初のオブジェクトの場合、式 **&\*first** で、生成されたシーケンス内の次のオブジェクト (**Type** 型) に未構築のストレージを指定する必要があります。

このアダプター クラスは、メモリの割り当てとオブジェクトの構築を分離する必要がある場合に使用されます。 `raw_storage_iterator` は、`malloc` 関数を使用して割り当てられたメモリなど、初期化されていないストレージにオブジェクトをコピーするために使用できます。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[raw_storage_iterator](#raw_storage_iterator)|指定した基になる出力反復子を使用して、生のストレージの反復子を構築します。|

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[element_type](#element_type)|生のストレージ反復子によって格納される要素を記述する型を提供します。|
|[iter_type](#iter_type)|生のストレージ反復子の基になる反復子を記述する型を提供します。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator*](#op_star)|出力反復子式 * `ii` = `x` を実装するために使用される逆参照演算子。|
|[operator=](#op_eq)|生のストレージ反復子式 * `i` = `x` をメモリへの格納用に実装するために使用される代入演算子。|
|[operator++](#op_add_add)|生のストレージ反復子の前置インクリメント演算子と後置インクリメント演算子。|

## <a name="requirements"></a>要件

**ヘッダー:** \<memory>

**名前空間:** std

## <a name="element_type"></a>  raw_storage_iterator::element_type

生のストレージ反復子によって格納される要素を記述する型を提供します。

```cpp
typedef Type element_type;
```

### <a name="remarks"></a>コメント

この型は raw_storage_iterator クラス テンプレート パラメーター **Type** のシノニムです。

## <a name="iter_type"></a>  raw_storage_iterator::iter_type

生のストレージ反復子の基になる反復子を記述する型を提供します。

```cpp
typedef ForwardIterator iter_type;
```

### <a name="remarks"></a>コメント

この型は、テンプレート パラメーター **ForwardIterator** のシノニムです。

## <a name="op_star"></a>  raw_storage_iterator::operator*

生のストレージ反復子式 \* *ii* = *x* を実装するために使用される逆参照演算子。

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator*();
```

### <a name="return-value"></a>戻り値

生のストレージ反復子への参照

### <a name="remarks"></a>コメント

**ForwardIterator** の要件は、生のストレージ反復子で式 \* *ii* = *t* が有効であることを満たすことを必要とするのみで、**演算子**または `operator=` 自体については何も必要としないことです。 この実装のメンバー演算子は、**\*this** を返します。そのため、[operator=](#op_eq)( **constType**&) は、\* *ptr* = `val` など、式内で実際の格納を実行できます。

### <a name="example"></a>例

```cpp
// raw_storage_iterator_op_deref.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };

   Int &operator=(int i)
   {
      if (!bIsConstructed)
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl;
      x = i;
      return *this;
   };

   int x;

private:
   bool bIsConstructed;
};

int main( void)
{
   Int *pInt = ( Int* ) malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;
 *pInt = 5;
   raw_storage_iterator< Int*, Int > it( pInt );
 *it = 5;
}
\* Output:
Not constructed.
Copying 5
Constructing 5
*\
```

## <a name="op_eq"></a>  raw_storage_iterator::operator=

生のストレージ反復子式 \* *i* = *x* をメモリへの格納用に実装するために使用される代入演算子。

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator=(
    const Type& val);
```

### <a name="parameters"></a>パラメーター

`val` 型のオブジェクトの値**型**メモリに挿入します。

### <a name="return-value"></a>戻り値

この演算子は、メモリに `val` を挿入し、生のストレージ反復子への参照を返します。

### <a name="remarks"></a>コメント

**ForwardIterator** の要件は、生のストレージ反復子で式 \* *ii* = *t* が有効であることを満たすことを必要とするのみで、**演算子**または `operator=` 自体については何も必要としないことです。 これらのメンバー演算子は **\*this** を返します。

代入演算子は、placement new 式 **new** ( ( `void` \*)&\* **first**) **Type**( `val`) を評価することによって、格納された反復子の値 first を使用して出力シーケンス内に次のオブジェクトを構築します。

### <a name="example"></a>例

```cpp
// raw_storage_iterator_op_assign.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int( int i )
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if ( !bIsConstructed )
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl; x = i;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( void )
{
   Int *pInt = ( Int* )malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;

*pInt = 5;

   raw_storage_iterator<Int*, Int> it( pInt );
 *it = 5;
}
\* Output:
Not constructed.
Copying 5
Constructing 5
*\
```

## <a name="op_add_add"></a>  raw_storage_iterator::operator++

生のストレージ反復子の前置インクリメント演算子と後置インクリメント演算子。

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator++();

raw_storage_iterator<ForwardIterator, Type> operator++(int);
```

### <a name="return-value"></a>戻り値

生のストレージ反復子または生のストレージ反復子への参照。

### <a name="remarks"></a>コメント

最終的に最初の演算子は、関連付けられている入力ストリームから **CharType** 型のオブジェクトの抽出と格納を試行します。 2 つ目の演算子は、オブジェクトのコピーを作成して、オブジェクトをインクリメントしてから、そのコピーを返します。

最初の preincrement 演算子は格納されている出力反復子オブジェクトをインクリメントしてから、**\*this** を返します。

2 つ目の postincrement 演算子は **\*this** のコピーを作成し、格納されている出力反復子オブジェクトをインクリメントしてからコピーを返します。

コンストラクターは **first** を出力反復子オブジェクトとして格納します。

### <a name="example"></a>例

```cpp
// raw_storage_iterator_op_incr.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

int main( void )
{
   int *pInt = new int[5];
   std::raw_storage_iterator<int*,int> it( pInt );
   for ( int i = 0; i < 5; i++, it++ ) {
 *it = 2 * i;
};

   for ( int i = 0; i < 5; i++ ) cout << "array " << i << " = " << pInt[i] << endl;;

   delete[] pInt;
}
\* Output:
array 0 = 0
array 1 = 2
array 2 = 4
array 3 = 6
array 4 = 8
*\
```

## <a name="raw_storage_iterator"></a>  raw_storage_iterator::raw_storage_iterator

指定した基になる出力反復子を使用して、生のストレージの反復子を構築します。

```cpp
explicit raw_storage_iterator(ForwardIterator first);
```

### <a name="parameters"></a>パラメーター

`first` 基になるには、前方反復子、`raw_storage_iterator`構築されるオブジェクトします。

### <a name="example"></a>例

```cpp
// raw_storage_iterator_ctor.cpp
// compile with: /EHsc /W3
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if (!bIsConstructed)
         cout << "Error! I'm not constructed!\n";
      cout << "Copying " << i << endl;  x = i; return *this;
   };
   int x;
   bool bIsConstructed;
};

int main( void )
{
   std::list<int> l;
   l.push_back( 1 );
   l.push_back( 2 );
   l.push_back( 3 );
   l.push_back( 4 );

   Int *pInt = (Int*)malloc(sizeof(Int)*l.size( ));
   memset (pInt, 0, sizeof(Int)*l.size( ));
   // Hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ), pInt );  // C4996
   for (unsigned int i = 0; i < l.size( ); i++)
      cout << "array " << i << " = " << pInt[i].x << endl;;

   memset (pInt, 0, sizeof(Int)*l.size( ));
   // hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ),
      std::raw_storage_iterator<Int*,Int>(pInt));  // C4996
   for (unsigned int i = 0; i < l.size( ); i++ )
      cout << "array " << i << " = " << pInt[i].x << endl;

   free(pInt);
}
\* Output:
Error! I'm not constructed!
Copying 1
Error! I'm not constructed!
Copying 2
Error! I'm not constructed!
Copying 3
Error! I'm not constructed!
Copying 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
Constructing 1
Constructing 2
Constructing 3
Constructing 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
*\
```

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
