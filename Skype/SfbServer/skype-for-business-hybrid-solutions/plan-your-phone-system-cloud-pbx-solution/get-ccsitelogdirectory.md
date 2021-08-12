---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: このGet-CcSiteLogDirectoryは、サイト レベルログが格納されている現在のディレクトリSkype for Business クラウド コネクタ エディション示します。
ms.openlocfilehash: 7c15d0b715384fd18522122571da69f58a83ed337d46420e83f7ac35cfd0c018
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349519"
---
# <a name="get-ccsitelogdirectory"></a>Get-CcSiteLogDirectory
 
このGet-CcSiteLogDirectoryは、サイト レベルログが格納されている現在のディレクトリSkype for Business クラウド コネクタ エディション示します。 
  
このコマンドレットは、Skype for Business クラウド コネクタ エディション 1.4.1、1.4.2 に適用されます。
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、クラウド コネクタ サイトのログ ファイルが格納されている現在のフォルダーを示しています。
  
```powershell
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

既定のフォルダーは C:\Users \% userprofile%\CloudConnector\SiteRoot\Logs です。 このコマンドレットを実行すると、フォルダーSet-CcSiteDirectoryできます。 サイト ディレクトリを変更せずにログ フォルダーの場所のみを変更する別のコマンドレットはありません。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このGet-CcSiteLogDirectoryは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

コマンドはファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

