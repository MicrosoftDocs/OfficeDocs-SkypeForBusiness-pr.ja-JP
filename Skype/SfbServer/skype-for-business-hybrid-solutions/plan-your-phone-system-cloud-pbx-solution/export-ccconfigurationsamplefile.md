---
title: エクスポート CcConfigurationSampleFile
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Export-CcConfigurationSampleFile コマンドレットは、Skype for Business Cloud Connector エディションのサンプル構成ファイル (.ini) を Cloud Connector アプライアンスのアプライアンス ディレクトリにエクスポートします。このファイルの名前は、お使いの展開での使用に合わせて変更できます。
ms.openlocfilehash: f91b9c7eb8ade4e5edcf1c83c5ddef205e0f3721
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfigurationsamplefile"></a>エクスポート CcConfigurationSampleFile
 
Export-CcConfigurationSampleFile コマンドレットは、Skype for Business Cloud Connector エディションのサンプル構成ファイル (.ini) を Cloud Connector アプライアンスのアプライアンス ディレクトリにエクスポートします。このファイルの名前は、お使いの展開での使用に合わせて変更できます。
  
このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、マイクロソフトのサイトからサンプルの構成ファイルをダウンロードし、コネクタのクラウド アプライアンスのアプライアンスのディレクトリに書き込みます。
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

クラウド コネクタの現在のバージョンでは、.ini ファイル内のいくつかのパラメーターを指定する必要があります。クラウド コネクタ コンポーネント、コンポーネント名、ゲートウェイ パラメーター、およびなどの仮想マシンの IP アドレスなどのパラメーターなど。
  
クラウドのコネクタのホスト マシン上で実行すると、このコマンドレットでは、マイクロソフトのサイトから、サンプル .ini ファイルの構成の例をダウンロードします。 コマンドレットでは、コネクタのクラウド アプライアンスのアプライアンスのディレクトリにファイルを書き込みます。 アプライアンス ディレクトリは Set-CcApplianceDirectory コマンドレットを使用して指定されます。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Export-CcConfigurationSampleFile　コマンドレットはパイプライン入力を受け入れません。 
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[セット CcApplianceDirectory](set-ccappliancedirectory.md)
  

