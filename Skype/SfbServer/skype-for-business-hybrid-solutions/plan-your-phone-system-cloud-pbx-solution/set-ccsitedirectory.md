---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Set-CcSiteDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルの設定ファイルが格納されるディレクトリを設定します。 フォルダーにはベース VHD および Cloud Connector の設定ファイルが含まれます。
ms.openlocfilehash: 1c03d0f91b3a724df6ce61d216138bb281fb0b87
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885583"
---
# <a name="set-ccsitedirectory"></a>Set-CcSiteDirectory
 
Set-CcSiteDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルの設定ファイルが格納されるディレクトリを設定します。 フォルダーにはベース VHD および Cloud Connector の設定ファイルが含まれます。
  
このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例では、サイトのルート ディレクトリを設定\\SiteShare\CloudConnector。
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

ゲートウェイの類似性と高可用性を提供するには、サイトでコネクタのクラウド アプライアンスを組み合わせて指定できます。 ユーザーは、クラウドのコネクタのアプライアンスではなくサイトに割り当てられます。 各サイトには、ベース VHD とクラウドのコネクタのインストール ファイルが格納される共有フォルダーがあります。 このフォルダーは、アプライアンスによって展開時に使用されます。 クラウド コネクタ サイト内の他のすべてのアプライアンスでは、このフォルダーを共有する必要があります。
  
既定のフォルダーは、C:\Users\%userprofile%\CloudConnector\SiteRoot。 このパスは Get-CcSiteDirectory コマンドレットを使用して表示できます。
  
## <a name="parameters"></a>パラメーター
<a name="DetailedDescription"> </a>

|**パラメーター**|**必須**|**型**|**説明**|
|:-----|:-----|:-----|:-----|
| Path <br/> | 必須 <br/> | System.String <br/> |クラウド コネクタ サイトのファイルを保存するフォルダーへのパスを提供します。  <br/> |
   
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 Set-CcSiteDirectory コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

なし
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Get-CcSiteDirectory](get-ccsitedirectory.md)
  

