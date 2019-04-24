---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Skype for Business Cloud Connector エディションの構成を、Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。
ms.openlocfilehash: 8afca55e6727c84c579957de9e2010e84a72fb15
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234057"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Skype for Business Cloud Connector エディションの構成を、Skype for Business Cloud Connector エディションのホスト サーバー上のローカル ファイルにエクスポートします。
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、Path パラメータをフル ファイル パスで設定して、そのファイルに構成をエクスポートします。
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>解説
<a name="Examples"> </a>

Export-CcConfiguration コマンドレットを使用すると、Cloud Connector 構成を選択したパスのファイルに保存できます。 このコマンドは Cloud Connector Edition バージョン 2.0 で導入されました。
  
## <a name="parameters"></a>パラメーター
<a name="Examples"> </a>

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |必須  <br/> |System.String  <br/> |Cloud Connector 構成が保存されるフル ファイル パス。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="Examples"> </a>

なし。 Export-CcConfiguration コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="Examples"> </a>

なし。
  
## <a name="see-also"></a>関連項目
<a name="Examples"> </a>

Import-CcConfiguration
  

