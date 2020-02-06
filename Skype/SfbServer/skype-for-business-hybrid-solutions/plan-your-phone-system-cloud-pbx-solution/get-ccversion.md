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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Cloud Connector アプライアンスのバージョンを返します。 Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799847"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
Cloud Connector アプライアンスのバージョンを返します。 Get-CCVersion は Cloud Connector のホスト マシンでのみ使用できます。
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>解説

インストールされている PowerShell スクリプト、およびアプライアンスディレクトリ内のファイル、ホストサーバーに展開されている仮想マシンに基づいて、クラウドコネクタアプライアンスのバージョンを返します。
  
## <a name="parameters"></a>パラメーター

|**パラメーター**|**必須**|**種類**|**説明**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |省略可能  <br/> |System.String  <br/> |バージョンのタイプ。 パラメーターの値は、RunningScripts、RunningBits、BackupBits または All になります。 既定値は RunningScripts です。   <br/> |
   
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、開いている PowerShell コンソールで現在実行されているスクリプトのクラウドコネクタバージョンを示しています。
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>例 2

次の例は、仮想マシンに展開されている現在実行されているバイナリのクラウドコネクタバージョンを示しています。 バージョンは、Hyper-v Manager において実行中の仮想マシンの名前から確認できます。
  
```powershell
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
  

