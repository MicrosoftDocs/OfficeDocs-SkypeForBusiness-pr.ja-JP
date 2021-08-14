---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: このExport-CcConfigurationSampleFileコマンドレットは、Skype for Business クラウド コネクタ エディション構成ファイル (.ini) をクラウド コネクタ アプライアンスのアプライアンス ディレクトリにエクスポートします。 展開に使用するファイルを変更して名前を変更できます。
ms.openlocfilehash: f59e93cf241ca762dcb41cf23d617017a62581b453cb84cebc915b1703f5a019
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326263"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
このExport-CcConfigurationSampleFileコマンドレットは、Skype for Business クラウド コネクタ エディション構成ファイル (.ini) をクラウド コネクタ アプライアンスのアプライアンス ディレクトリにエクスポートします。 展開に使用するファイルを変更して名前を変更できます。
  
このコマンドレットは、Skype for Business クラウド コネクタ エディション 1.4.1、1.4.2 に適用されます。
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、Microsoft サイトから構成ファイルのサンプルをダウンロードし、クラウド コネクタ アプライアンスのアプライアンス ディレクトリに書き込みます。
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

現在のバージョンの Cloud Connector では、ファイル内に複数のパラメーターを指定する.iniがあります。たとえば、Cloud Connector コンポーネントの仮想マシンの IP アドレス、コンポーネント名、ゲートウェイ パラメーターなどのパラメーター。
  
このコマンドレットは、クラウド コネクタのホスト コンピューターで実行する場合、Microsoft サイトから構成例.iniファイルをダウンロードします。 このコマンドレットは、クラウド コネクタ アプライアンスのアプライアンス ディレクトリにファイルを書き込みます。 アプライアンス ディレクトリは、このコマンドレットを使用してSet-CcApplianceDirectoryされます。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このExport-CcConfigurationSampleFileは、パイプライン処理された入力を受け付け取らない。 
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

