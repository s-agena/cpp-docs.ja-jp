---
title: hash_map::end (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_map::end
dev_langs:
- C++
helpviewer_keywords:
- end member [STL/CLR]
ms.assetid: bda12a48-cc2b-426f-a4e8-992c88f61736
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 230c5a68ef4f8564769801d71a0d9bf7b0d602b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hashmapend-stlclr"></a>hash_map::end (STL/CLR)
被制御シーケンスの末尾を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
iterator end();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、被制御シーケンスの最後の位置を指し示す双方向反復子を返します。 被制御シーケンスの末尾を指定する反復子を取得するのにために使用します。その状態は、被制御シーケンスの長さが変更された場合は変更されません。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_map_end.cpp   
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
  
// inspect last two items   
    Myhash_map::iterator it = c1.end();   
    --it;   
    --it;   
    System::Console::WriteLine("*-- --end() = [{0} {1}]",   
        it->first, it->second);   
    ++it;   
    System::Console::WriteLine("*--end() = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
```Output  
 [a 1] [b 2] [c 3]  
*-- --end() = [b 2]  
*--end() = [c 3]  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)   
 [hash_map::begin (STL/CLR)](../dotnet/hash-map-begin-stl-clr.md)