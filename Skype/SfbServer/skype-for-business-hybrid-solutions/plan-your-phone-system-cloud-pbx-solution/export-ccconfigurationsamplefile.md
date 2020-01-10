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
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Export-CcConfigurationSampleFile コマンドレットは、Skype for Business Cloud Connector エディションのサンプル構成ファイル (.ini) を Cloud Connector アプライアンスのアプライアンス ディレクトリにエクスポートします。このファイルの名前は、お使いの展開での使用に合わせて変更できます。
ms.openlocfilehash: b62d5d7ffa9e8f10aeae509201c5aa0a1e7fa0a4
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003427"
---
# <a name="export-ccconfigurationsamplefile"></a>Export-CcConfigurationSampleFile
 
Export-CcConfigurationSampleFile コマンドレットは、Skype for Business Cloud Connector エディションのサンプル構成ファイル (.ini) を Cloud Connector アプライアンスのアプライアンス ディレクトリにエクスポートします。このファイルの名前は、お使いの展開での使用に合わせて変更できます。
  
このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、Microsoft サイトからサンプルの構成ファイルをダウンロードし、クラウドコネクタのアプライアンスの appliance ディレクトリに書き込みます。
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Cloud Connector の現在のバージョンでは、.ini ファイルにいくつかのパラメーターを指定する必要があります。たとえば、クラウドコネクタコンポーネントの仮想マシンの IP アドレス、コンポーネント名、ゲートウェイパラメーターなどのパラメーターがあります。
  
このコマンドレットは、クラウドコネクタのホストコンピューターで実行すると、Microsoft サイトの構成例と共にサンプルの .ini ファイルをダウンロードします。 このコマンドレットは、クラウドコネクタアプライアンスのアプライアンスディレクトリにファイルを書き込みます。 アプライアンス ディレクトリは Set-CcApplianceDirectory コマンドレットを使用して指定されます。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Export-CcConfigurationSampleFile　コマンドレットはパイプライン入力を受け入れません。 
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

