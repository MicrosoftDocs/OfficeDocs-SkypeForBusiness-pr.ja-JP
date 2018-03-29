---
title: Get CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Get-CcSiteDirectory コマンドレットは、サイト レベルの設定ファイルが格納されている現在のディレクトリを示します。 フォルダーにはベース VHD および Skype for Business Cloud Connector エディションのインストール ファイルが含まれます。 クラウド コネクタ サイトの他のすべてのアプライアンスでは、このフォルダーを共有する必要があります。
ms.openlocfilehash: e75e20a18960510bf75a8ca4cfc97ffd9daa894f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitedirectory"></a>Get CcSiteDirectory
 
Get-CcSiteDirectory コマンドレットは、サイト レベルの設定ファイルが格納されている現在のディレクトリを示します。 フォルダーにはベース VHD および Skype for Business Cloud Connector エディションのインストール ファイルが含まれます。 クラウド コネクタ サイトの他のすべてのアプライアンスでは、このフォルダーを共有する必要があります。
  
このコマンドレットは Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、クラウドのコネクタ コンポーネントの構成と仮想マシンのファイルが保存されている現在のフォルダーを示しています。
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

ゲートウェイの類似性と高可用性を提供するには、サイトでコネクタのクラウド アプライアンスを組み合わせて指定できます。 ユーザーは、クラウドのコネクタのアプライアンスではなくサイトに割り当てられます。 各サイトには、ベース VHD および Cloud Connector のインストール ファイルが格納された共有フォルダーがあります。 アプライアンスでは、展開時にこのフォルダーを使用します。 既定のフォルダーは、C:\Users\%userprofile%\CloudConnector\SiteRoot。 このパスは Set-CcSiteDirectory コマンドレットを使用して変更できます。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Get-CcSiteDirectory コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

このコマンドはファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[セット CcSiteDirectory](set-ccsitedirectory.md)
  

