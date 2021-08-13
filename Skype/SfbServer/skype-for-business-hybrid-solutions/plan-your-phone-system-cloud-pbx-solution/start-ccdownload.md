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
description: このStart-CcDownloadコマンドレットは、Skype for Business クラウド コネクタ エディションビットと msi ファイルを同期的にダウンロードします。
ms.openlocfilehash: 0447c75ac3e6df79a20d2c87b664bfb92cf7124fc7253c839a88fad1b335eaec
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351916"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
このStart-CcDownloadコマンドレットは、Skype for Business クラウド コネクタ エディションビットと msi ファイルを同期的にダウンロードします。
  
クラウド コネクタ バージョン 2.0 以降では、DownloadBitsOnly パラメーターを指定することもできます。
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、クラウド コネクタのパブリック ダウンロード サイトからクラウド コネクタ ビットと msi ファイルを同期的にダウンロードします。
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>例 2

次の例では、プライベート ダウンロード サイトからクラウド コネクタ ビットと msi ファイルを同期的にダウンロードします。
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>例 3

3 番目の例では、プライベート ダウンロード サイトからクラウド コネクタ ビットと msi ファイルを同期的にダウンロードします。
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

ダウンロード サイトに新しいバージョンがある場合、Start-CcDownload はダウンロード サイトから msi ファイルをダウンロードしてインストールし、クラウド コネクタ ビットを同期的にダウンロードします。 msi ファイルの新しいバージョンがない場合は、Start-CcDownloadコネクタ ビットのみをダウンロードします。 クラウド コネクタ ビットが既にダウンロードされている場合、Start-CcDownloadは実行されません。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | 省略可 <br/> |System.String  <br/> | プライベート ダウンロード サイト内の特定のバージョンの Cloud Connector の完全な URL。 このパラメーターは注意して使用します。ダウンロードするクラウド コネクタのバージョンを確認してください。 <br/> |
|DownloadBitsOnly  <br/> |省略可  <br/> |System.Management.Automation.SwitchParameter  <br/> |ダウンロード サイトから MSI をダウンロードしてインストールするには、手順を省略し、クラウド コネクタ ビットのみをダウンロードします。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このStart-CcDownloadは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

なし
  

