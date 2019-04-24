---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Cloud Connector アプライアンスのバージョンを返します。 Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。
ms.openlocfilehash: 5e5428e53d53eec66bafa9eb566059ef1b5a5833
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233758"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Cloud Connector アプライアンスのバージョンを返します。 Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>解説

アプライアンス ディレクトリ、およびホスト サーバーに配置される仮想マシンのクラウド コネクタ アプライアンス ・ ベースの PowerShell スクリプトがインストールされている、ファイルのバージョンを返します。
  
## <a name="parameters"></a>パラメーター

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |省略可能  <br/> |System.String  <br/> |バージョンのタイプ。 パラメーターの値は、RunningScripts、RunningBits、BackupBits または All になります。 既定値は RunningScripts です。   <br/> |
   
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、PowerShell コンソールを開くに現在実行中のスクリプトのクラウドのコネクタのバージョンを示しています。
  
```
Get-CcVersion
```

### <a name="example-2"></a>例 2

次の例では、現在実行中の仮想マシンに展開バイナリのクラウドのコネクタのバージョンを示します。 バージョンは、Hyper-v Manager において実行中の仮想マシンの名前から確認できます。
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>入力の種類
<a name="Examples"> </a>

なし。 Get-CcVersion コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="Examples"> </a>

なし。
  
## <a name="see-also"></a>関連項目
<a name="Examples"> </a>

なし。
  

