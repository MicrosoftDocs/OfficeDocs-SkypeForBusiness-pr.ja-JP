---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Cloud Connector アプライアンスのバージョンを返します。 Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。
ms.openlocfilehash: b002b4a9f0cae34a2cdd7b8817e86a3e4ec2eb9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287252"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Cloud Connector アプライアンスのバージョンを返します。 Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>解説

インストールされている PowerShell スクリプト、およびアプライアンスディレクトリ内のファイル、ホストサーバーに展開されている仮想マシンに基づいて、クラウドコネクタアプライアンスのバージョンを返します。
  
## <a name="parameters"></a>パラメーター

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |省略可能  <br/> |System.String  <br/> |バージョンのタイプ。 パラメーターの値は、RunningScripts、RunningBits、BackupBits または All になります。 既定値は RunningScripts です。   <br/> |
   
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、開いている PowerShell コンソールで現在実行されているスクリプトのクラウドコネクタバージョンを示しています。
  
```
Get-CcVersion
```

### <a name="example-2"></a>例 2

次の例は、仮想マシンに展開されている現在実行されているバイナリのクラウドコネクタバージョンを示しています。 バージョンは、Hyper-v Manager において実行中の仮想マシンの名前から確認できます。
  
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
  

