---
title: CMFCToolTipInfo クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 325650f35d097b54eda160bbdbbd5c877dbd0242
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfctooltipinfo-class"></a>CMFCToolTipInfo クラス
ツールヒントの外観に関する情報を格納します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCToolTipInfo  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolTipInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|ツールヒントの外観をバルーンにするかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|ツールヒントのラベルを太字のフォントで表示するかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|ツールヒントに説明を含めるかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|ツールヒントにアイコンを含めるかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|ツールヒントのラベルとツールヒントの説明の間に区切り記号を表示するかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|ツールヒントの角を丸くするかどうかを示すブール値変数。|  
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|ビジュアル マネージャーで、ツールヒントの外観を制御する必要があるかどうかを示すブール値変数 (を参照してください[CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md))。|  
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|ツールヒントの境界線の色。|  
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|ツールヒントの背景の色。|  
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|ツールヒントのグラデーション塗りの色。|  
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|ツールヒントのテキストの色。|  
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|ツールヒントのグラデーション塗りの角度。|  
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|ツールヒントの説明で可能な最大幅 (ピクセル)。|  
  
## <a name="remarks"></a>コメント  
 使用して[CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)、 `CMFCToolTipInfo`、および[CTooltipManager クラス](../../mfc/reference/ctooltipmanager-class.md)アプリケーションでカスタマイズされたツールヒントを実装します。 これらのツールヒントのクラスを使用する方法の例は、次を参照してください。、 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)トピックです。  
  
## <a name="example"></a>例  
 次の例では、`CMFCToolTipInfo` クラスのさまざまなメンバー変数の値を設定する方法を示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtooltipctrl.h  
  
##  <a name="m_bballoontooltip"></a>  CMFCToolTipInfo::m_bBalloonTooltip  
 すべてのツールヒントの表示スタイルを指定します。  
  
```  
BOOL m_bBalloonTooltip;  
```  
  
### <a name="remarks"></a>コメント  
 `TRUE` ツールヒントがバルーン形式を使用することを示します`FALSE`ツールヒントが四角形のスタイルを使用することを示します。  
  
##  <a name="m_bboldlabel"></a>  CMFCToolTipInfo::m_bBoldLabel  
 ツールヒントのテキストのフォントが太字かどうかを指定します。  
  
```  
BOOL m_bBoldLabel;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーを設定`TRUE`太字のフォントのツールヒント テキストを表示するのにまたは`FALSE`ラベルを表示するツールヒントにフォントが太字以外です。  
  
##  <a name="m_bdrawdescription"></a>  CMFCToolTipInfo::m_bDrawDescription  
 各ツールヒントが説明テキストを表示するかどうかを指定します。  
  
```  
BOOL m_bDrawDescription;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーを設定`TRUE`、説明を表示または`FALSE`説明を非表示にします。 呼び出して、ツールヒントの説明を指定できる[CMFCToolTipCtrl::SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)  
  
##  <a name="m_bdrawicon"></a>  CMFCToolTipInfo::m_bDrawIcon  
 すべてのツールヒントにアイコンを表示するかどうかを指定します。  
  
```  
BOOL m_bDrawIcon;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーを設定`TRUE`各ツールヒントにアイコンが表示または`FALSE`アイコンなしのツール ヒントを表示します。  
  
##  <a name="m_bdrawseparator"></a>  CMFCToolTipInfo::m_bDrawSeparator  
 各ツールヒントのラベルとその説明の間の区切り記号かどうかを指定します。  
  
```  
BOOL m_bDrawSeparator;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーを設定`TRUE`ツールヒントのラベルと説明、間の区切り記号を表示するか、`FALSE`区切り記号なしでツールヒントを表示します。  
  
##  <a name="m_broundedcorners"></a>  CMFCToolTipInfo::m_bRoundedCorners  
 すべてのツールヒントの角が丸いかどうかを指定します。  
  
```  
BOOL m_bRoundedCorners;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーを設定`TRUE`、ツールヒントの角の丸いを表示するか、`FALSE`四角形の角のツールヒントを表示します。  
  
##  <a name="m_clrborder"></a>  CMFCToolTipInfo::m_clrBorder  
 すべてのツールヒントの境界線の色を指定します。  
  
```  
COLORREF m_clrBorder;  
```  
  
##  <a name="m_clrfill"></a>  CMFCToolTipInfo::m_clrFill  
 ツールヒントの背景の色を指定します。  
  
```  
COLORREF m_clrFill;  
```  
  
### <a name="remarks"></a>コメント  
 場合[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) -1 で、ツールヒントの背景色が`m_clrFill`です。 それ以外の場合、`m_clrFill`グラデーションの最初の色を指定し、`m_clrFillGradient`グラデーションの最後の色を指定します。 [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)グラデーションの方向を決定します。  
  
##  <a name="m_clrfillgradient"></a>  CMFCToolTipInfo::m_clrFillGradient  
 ツールヒントのグラデーションの背景の最後の色を指定します。  
  
```  
COLORREF m_clrFillGradient;  
```  
  
### <a name="remarks"></a>コメント  
 場合`m_clrFillGradient`-1 で、グラデーションがありません。 それ以外の場合、初期のグラデーションの色がで指定された[CMFCToolTipInfo::m_clrFill](#m_clrfill)しグラデーションの終了色を指定`m_clrFillGradient`です。 [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)グラデーションの方向を決定します。  
  
##  <a name="m_clrtext"></a>  CMFCToolTipInfo::m_clrText  
 すべてのツールヒントのテキストの色を指定します。  
  
```  
COLORREF m_clrText;  
```  
  
##  <a name="m_ngradientangle"></a>  CMFCToolTipInfo::m_nGradientAngle  
 ツールヒントの背景に描画されるグラデーションの角度を指定します。  
  
```  
int m_nGradientAngle;  
```  
  
### <a name="remarks"></a>コメント  
 `m_nGradientAngle` ツールヒントの背景のグラデーションの水平方向のオフセットを度単位の角度を指定します。 場合`m_nGradientAngle`が 0 の場合、グラデーションは左から右に描画します。 場合`m_nGradientAngle`は 1 ~ 360 の場合は、間、グラデーションが右回りに回転、その角度。 場合`m_nGradientAngle`-1 で、既定値は、グラデーションは上から下に描画します。 これは、設定と同じ`m_nGradientAngle`を 90 にします。  
  
 [CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill`グラデーションの最初の色を指定し、 [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient`グラデーションの最後の色を指定します。 場合`m_clrFillGradient`-1 で、グラデーションがありません。  
  
##  <a name="m_nmaxdescrwidth"></a>  CMFCToolTipInfo::m_nMaxDescrWidth  
 各ヒントに表示される説明の最大の幅を指定します。 説明の幅は、指定した値を超えている場合、テキストが折り返されます。  
  
```  
int m_nMaxDescrWidth;  
```  
  
##  <a name="m_bvislmanagertheme"></a>  CMFCToolTipInfo::m_bVislManagerTheme  
 アプリケーションのビジュアル マネージャーがすべてのツールヒントの外観を制御するかどうかを指定します。  
  
```  
BOOL m_bVislManagerTheme;  
```  
  
### <a name="remarks"></a>コメント  
 場合`m_bVislManagerTheme`は`TRUE`、すべてのツール ヒントを新しい要求[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)画面に表示し、そのオブジェクトの外観を決定する値を使用する前に、アプリケーションのビジュアル マネージャーからです。 他のメンバー、 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)は無視されます。  
  
##  <a name="operator_eq"></a>  CMFCToolTipInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `src`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CTooltipManager クラス](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)
