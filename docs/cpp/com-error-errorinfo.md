---
title: _com_error::ErrorInfo |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::ErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fbc735dfae1b30209eccfd14f1170826fb07680
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="comerrorerrorinfo"></a>_com_error::ErrorInfo
**Microsoft 固有の仕様**  
  
 取得、 **IErrorInfo**オブジェクト コンス トラクターに渡されます。  
  
## <a name="syntax"></a>構文  
  
```  
  
IErrorInfo * ErrorInfo( ) const throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 Raw **IErrorInfo**項目が、コンス トラクターに渡されます。  
  
## <a name="remarks"></a>コメント  
 カプセル化された取得**IErrorInfo**内の項目、`_com_error`オブジェクト、または**NULL**いない場合**IErrorInfo**項目が記録されます。 呼び出し元が呼び出す必要があります**リリース**完了すると、返されたオブジェクトで使用します。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_com_error クラス](../cpp/com-error-class.md)