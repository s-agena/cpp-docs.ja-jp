---
title: hash_multimap::hasher (STL/CLR) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::hash_multimap::hasher
dev_langs:
- C++
helpviewer_keywords:
- hasher member [STL/CLR]
ms.assetid: f92bf084-d9d0-4eca-b23c-c88e6568d267
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fb8fca2c99c76b8714a3022cf74eaa872f8df010
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hashmultimaphasher-stlclr"></a>hash_multimap::hasher (STL/CLR)
キーのハッシュのデリゲート。  
  
## <a name="syntax"></a>構文  
  
```  
Microsoft::VisualC::StlClr::UnaryDelegate<GKey, int>  
    hasher;  
```  
  
## <a name="remarks"></a>コメント  
 この型は、キーの値を整数に変換するデリゲートを表します。  
  
## <a name="example"></a>例  
  
```  
// cliext_hash_multimap_hasher.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    Myhash_multimap::hasher^ myhash = c1.hash_delegate();   
  
    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));   
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));   
    return (0);   
    }  
  
```  
  
```Output  
hash(L'a') = 1616896120  
hash(L'b') = 570892832  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/hash_map >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)   
 [hash_multimap::hash_delegate (STL/CLR)](../dotnet/hash-multimap-hash-delegate-stl-clr.md)