---
title: 開始 CcDownload
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Start-CcDownload コマンドレットは Skype for Business Cloud Connector エディションのビットと msi ファイルを同期してダウンロードします。
ms.openlocfilehash: aec8d5c1848e7e55d6ed4b7e4d3633942f74ab55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="start-ccdownload"></a>開始 CcDownload
 
Start-CcDownload コマンドレットは Skype for Business Cloud Connector エディションのビットと msi ファイルを同期してダウンロードします。
  
Cloud Connector バージョン 2.0 以降の場合、DownloadBitsOnly パラメーターも指定できます。
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例をダウンロード、クラウドのコネクタのビットと msi ファイル同期的にクラウド コネクタのパブリックのダウンロード サイトから。
  
```
Start-CcDownload
```

### <a name="example-2"></a>例 2

次の使用例、クラウドのコネクタのビットとダウンロード msi ファイル同期的に秘密のダウンロード サイトから。
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>例 3

3 つ目の例では、Cloud Connector ビットおよび msi ファイルをプライベート ダウンロード サイトから同期的にダウンロードします。
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

ダウンロード サイトでは、新しいバージョンが利用可能な開始 CcDownload はダウンロードし、ダウンロード サイトから msi ファイルをインストールしてクラウド コネクタのビットを同期的にダウンロードします。 新しいバージョンの msi ファイルがない場合、Start-CcDownload によって Cloud Connector ビットのみがダウンロードされます。 Cloud Connector ビットが既にダウンロードされている場合、Start-CcDownload は実行されません。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**タイプ**|**説明**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | 省略可能 <br/> |System.String  <br/> | プライベート クラウドのコネクタの特定のバージョンの完全な URL は、サイトをダウンロードします。 注意してこのパラメーターを使用して、クラウドのコネクタのバージョンをダウンロードするのに気付いていることを確認します。 <br/> |
|DownloadBitsOnly  <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |ダウンロード サイトから MSI をダウンロードおよびインストールする手順をスキップして、Cloud Connector ビットのみをダウンロードします。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 Start-CcDownload コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

