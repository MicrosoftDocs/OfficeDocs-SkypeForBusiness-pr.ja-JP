---
title: Get CcSiteLogDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Get-CcSiteLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルのログが格納されている現在のディレクトリを示します。
ms.openlocfilehash: 68d89200ac8bf2aec32db45752d62d7ae205b830
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitelogdirectory"></a>Get CcSiteLogDirectory
 
Get-CcSiteLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのサイト レベルのログが格納されている現在のディレクトリを示します。 
  
このコマンドレットは、Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

クラウド コネクタ サイトのログ ファイルが保存されている現在のフォルダーを次の例に示します。
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

既定のフォルダーは、C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs。 Set-CcSiteDirectory コマンドレットを実行することで、このフォルダーを変更できます。 サイト ディレクトリを変更せずにログ フォルダーの場所のみを変更するコマンドレットはありません。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Get-CcSiteLogDirectory コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

このコマンドはファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[セット CcSiteDirectory](set-ccsitedirectory.md)
  

