---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: ホスト サーバー Skype for Business クラウド コネクタ エディションローカル ファイルに、サーバー構成をSkype for Business クラウド コネクタ エディションします。
ms.openlocfilehash: f34f8454dfc3129be50b26114f71fdeee4a4b633f66ca9f80dc621c51c5af6ad
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288842"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
ホスト サーバー Skype for Business クラウド コネクタ エディションローカル ファイルに、サーバー構成をSkype for Business クラウド コネクタ エディションします。
  
```powershell
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、Path パラメーターを完全なファイル パスとして設定し、そのファイルに構成をエクスポートします。
  
```powershell
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>解説
<a name="Examples"> </a>

このExport-CcConfigurationを使用すると、クラウド コネクタ構成を選択したパス内のファイルに保存できます。 このコマンドは、Cloud Connector Edition バージョン 2.0 で導入されました。
  
## <a name="parameters"></a>パラメーター
<a name="Examples"> </a>

|**パラメーター**|**Required**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|Path  <br/> |必須  <br/> |System.String  <br/> |クラウド コネクタ構成が格納される完全なファイル パス。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="Examples"> </a>

なし。 このExport-CcConfigurationは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="Examples"> </a>

なし。
  
## <a name="see-also"></a>関連項目
<a name="Examples"> </a>

Import-CcConfiguration
  

