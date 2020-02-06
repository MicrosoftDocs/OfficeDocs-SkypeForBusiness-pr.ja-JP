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
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Set-CcSiteDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルの設定ファイルが格納されるディレクトリを設定します。 フォルダーにはベース VHD および Cloud Connector の設定ファイルが含まれます。
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824191"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Set-CcSiteDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルの設定ファイルが格納されるディレクトリを設定します。 フォルダーにはベース VHD および Cloud Connector の設定ファイルが含まれます。
  
このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、サイトのルート\\ディレクトリを SiteShare\CloudConnector に設定します。
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

ゲートウェイのアフィニティと高可用性を実現するには、クラウドコネクタのアプライアンスをサイトで組み合わせることができます。 ユーザーは、クラウドコネクタアプライアンスの代わりにサイトに割り当てられます。 各サイトには、基本 VHD とクラウドコネクタのインストールファイルが保存されている共有フォルダーがあります。 このフォルダーは、アプライアンスによって展開時に使用されます。 このフォルダーは、クラウドコネクタサイト内の他のすべてのアプライアンスと共有する必要があります。
  
既定のフォルダーは C:\Users\%userprofile%\CloudConnector\SiteRoot. このパスは Get-CcSiteDirectory コマンドレットを使用して表示できます。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**種類**|**説明**|
|:-----|:-----|:-----|:-----|
| Path <br/> | 必須 <br/> | System.String <br/> |クラウドコネクタサイトファイルが保存されるフォルダーのパスを指定します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 Set-CcSiteDirectory コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

