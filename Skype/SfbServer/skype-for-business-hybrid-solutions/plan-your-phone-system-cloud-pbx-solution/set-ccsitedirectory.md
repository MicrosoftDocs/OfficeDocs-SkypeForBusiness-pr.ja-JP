---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: このSet-CcSiteDirectoryは、サイト レベルの構成ファイルが格納されるディレクトリSkype for Business クラウド コネクタ エディション設定します。 フォルダーには、基本 VHD とクラウド コネクタ構成ファイルが含まれる。
ms.openlocfilehash: e5685ac8c203338365141a4a7ba59daa82a06ef0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610534"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
このSet-CcSiteDirectoryは、サイト レベルの構成ファイルが格納されるディレクトリSkype for Business クラウド コネクタ エディション設定します。 フォルダーには、基本 VHD とクラウド コネクタ構成ファイルが含まれる。
  
このコマンドレットは、Skype for Business クラウド コネクタ エディション 1.4.1、1.4.2 に適用されます。
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、サイト ルート ディレクトリを \\ SiteShare\CloudConnector に設定します。
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

ゲートウェイ アフィニティと高可用性を実現するために、クラウド コネクタ アプライアンスをサイトで組み合わせることができます。 ユーザーは、クラウド コネクタ アプライアンスではなくサイトに割り当てられます。 各サイトには、基本 VHD とクラウド コネクタのインストール ファイルが格納されている共有フォルダーがあります。 アプライアンスは展開中にこのフォルダーを使用します。 このフォルダーは、クラウド コネクタ サイト内の他のすべてのアプライアンスと共有する必要があります。
  
既定のフォルダーは C:\Users \% userprofile%\CloudConnector\SiteRoot です。 パスは、このコマンドレットを使用してGet-CcSiteDirectoryできます。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**Required**|**Type**|**説明**|
|:-----|:-----|:-----|:-----|
| パス <br/> | 必須 <br/> | System.String <br/> |クラウド コネクタ サイト ファイルが格納されるフォルダーへのパスを提供します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このSet-CcSiteDirectoryは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

