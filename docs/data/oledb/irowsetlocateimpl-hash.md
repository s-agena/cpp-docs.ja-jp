---
title: Irowsetlocateimpl::hash |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
dev_langs:
- C++
helpviewer_keywords:
- Hash method
ms.assetid: 7df4386d-80fb-4332-a85f-baae98cdc6e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 42076453cc8f32b56bfe354eaa2b883650d0f4f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetlocateimplhash"></a>IRowsetLocateImpl::Hash
指定されたブックマークの値のハッシュを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD (Hash )(HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmarks,  
   const DBBKMARK* rgcbBookmarks[],  
   const BYTE* rgpBookmarks[],  
   DBHASHVALUE rgHashValues[],  
   DBROWSTATUS rgBookmarkStatus[]);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hReserved`  
 [in]対応する`hChapter`パラメーターを[IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx)です。  
  
 その他のパラメーターを参照してください。 [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [IRowsetLocateImpl クラス](../../data/oledb/irowsetlocateimpl-class.md)