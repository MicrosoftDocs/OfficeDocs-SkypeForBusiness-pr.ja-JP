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
description: クラウド コネクタ アプライアンスのバージョンを返します。 Get-CCVersionは、クラウド コネクタのホスト コンピューターでのみ使用できます。
ms.openlocfilehash: d3da9813fd67228f8e198cd21edce3cc187ac9359617eb660a352b38c51a95ba
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349509"
---
# <a name="get-ccversion"></a>Get-CcVersion
 
クラウド コネクタ アプライアンスのバージョンを返します。 Get-CCVersionは、クラウド コネクタのホスト コンピューターでのみ使用できます。
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a>解説

インストールされている PowerShell スクリプト、アプライアンス ディレクトリ内のファイル、ホスト サーバーに展開された仮想マシンに基づいて、クラウド コネクタ アプライアンスのバージョンを返します。
  
## <a name="parameters"></a>パラメーター

|**パラメーター**|**Required**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|VersionType  <br/> |省略可  <br/> |System.String  <br/> |バージョンの種類。 パラメーターの値には、RunningScripts、RunningBits、BackupBits、または All を指定できます。 既定値は RunningScripts です。  <br/> |
   
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、開いている PowerShell コンソールで現在実行中のスクリプトのクラウド コネクタ バージョンを示しています。
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a>例 2

次の例は、仮想マシンに展開されている現在実行中のバイナリのクラウド コネクタ バージョンを示しています。 Hyper-v Manager で実行中の仮想マシン名でバージョンを確認できます。
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a>入力の種類
<a name="Examples"> </a>

なし。 このGet-CcVersionは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="Examples"> </a>

なし。
  
## <a name="see-also"></a>関連項目
<a name="Examples"> </a>

なし。
  

