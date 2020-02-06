---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Start-CcDownload コマンドレットは Skype for Business Cloud Connector エディションのビットと msi ファイルを同期してダウンロードします。
ms.openlocfilehash: 3298b02fbb792392860f05ebb15a9221b45e47b4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824181"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
Start-CcDownload コマンドレットは Skype for Business Cloud Connector エディションのビットと msi ファイルを同期してダウンロードします。
  
Cloud Connector バージョン 2.0 以降の場合、DownloadBitsOnly パラメーターも指定できます。
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、クラウドコネクタのパブリックダウンロードサイトからクラウドコネクタの bits と msi ファイルを同期的にダウンロードします。
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>例 2

次の例では、プライベートダウンロードサイトからクラウドコネクタの bits と msi ファイルを同期的にダウンロードします。
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>例 3

3 つ目の例では、Cloud Connector ビットおよび msi ファイルをプライベート ダウンロード サイトから同期的にダウンロードします。
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

ダウンロードサイトで利用可能な新しいバージョンがある場合は、ダウンロードサイトから msi ファイルをダウンロードしてインストールしてから、クラウドコネクタの bits を同期的にダウンロードします。 新しいバージョンの msi ファイルがない場合、Start-CcDownload によって Cloud Connector ビットのみがダウンロードされます。 Cloud Connector ビットが既にダウンロードされている場合、Start-CcDownload は実行されません。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**種類**|**説明**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot   <br/> | 省略可能 <br/> |System.String  <br/> | プライベートダウンロードサイト内の特定のバージョンのクラウドコネクタの完全な URL です。 このパラメーターは注意して使用してください。ダウンロードするクラウドコネクタのバージョンを確認してください。 <br/> |
|DownloadBitsOnly   <br/> |省略可能  <br/> |System.Management.Automation.SwitchParameter  <br/> |ダウンロード サイトから MSI をダウンロードおよびインストールする手順をスキップして、Cloud Connector ビットのみをダウンロードします。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 Start-CcDownload コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

