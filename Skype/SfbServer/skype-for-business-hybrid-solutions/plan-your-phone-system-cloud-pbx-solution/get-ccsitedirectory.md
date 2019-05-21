---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Get-CcSiteDirectory コマンドレットは、サイト レベルの設定ファイルが格納されている現在のディレクトリを示します。 フォルダーにはベース VHD および Skype for Business Cloud Connector エディションのインストール ファイルが含まれます。 このフォルダーは、クラウドコネクタサイトの他のすべてのアプライアンスと共有する必要があります。
ms.openlocfilehash: e0b8a793f0210535a726b0bed19f240bf8b30dd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287301"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
Get-CcSiteDirectory コマンドレットは、サイト レベルの設定ファイルが格納されている現在のディレクトリを示します。 フォルダーにはベース VHD および Skype for Business Cloud Connector エディションのインストール ファイルが含まれます。 このフォルダーは、クラウドコネクタサイトの他のすべてのアプライアンスと共有する必要があります。
  
このコマンドレットは Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、クラウドコネクタコンポーネントの configuration ファイルと virtual machines ファイルが保存されている現在のフォルダーを示しています。
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

ゲートウェイのアフィニティと高可用性を実現するには、クラウドコネクタのアプライアンスをサイトで組み合わせることができます。 ユーザーは、クラウドコネクタアプライアンスの代わりにサイトに割り当てられます。 各サイトには、基本 VHD とクラウドコネクタのインストールファイルが保存されている共有フォルダーがあります。 このフォルダーは、アプライアンスによって展開時に使用されます。 既定のフォルダーは C:\Users\%userprofile%\CloudConnector\SiteRoot. このパスは Set-CcSiteDirectory コマンドレットを使用して変更できます。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Get-CcSiteDirectory コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

このコマンドはファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

