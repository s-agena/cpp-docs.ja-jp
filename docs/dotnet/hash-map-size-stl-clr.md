---
title: hash_map::size (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::size
dev_langs:
- C++
helpviewer_keywords:
- size member [STL/CLR]
ms.assetid: 5eb91502-1b11-4703-b473-eb609c181b74
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c97d3f89bc26a7f50ab4dbbe175e3996cd7377f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hashmapsize-stlclr"></a>hash_map::size (STL/CLR)
要素の数をカウントします。  
  
## <a name="syntax"></a>構文  
  
```  
size_type size();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、被制御シーケンスの長さを返します。 これを使用するには、被制御シーケンス内の現在の要素の数を決定します。 シーケンスが参照してください、0 以外のサイズを持つかどうかは、関心のあるすべて場合[hash_map::empty (STL/CLR)](../dotnet/hash-map-empty-stl-clr.md)`()`です。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_map_size.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    c1.insert(Myhash_map::make_value(L'a', 1));   
    c1.insert(Myhash_map::make_value(L'b', 2));   
    c1.insert(Myhash_map::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_map::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.insert(Myhash_map::make_value(L'd', 4));   
    c1.insert(Myhash_map::make_value(L'e', 5));   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
size() = 0 after clearing  
size() = 2 after adding 2  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::empty (STL/CLR)](../dotnet/hash-map-empty-stl-clr.md)