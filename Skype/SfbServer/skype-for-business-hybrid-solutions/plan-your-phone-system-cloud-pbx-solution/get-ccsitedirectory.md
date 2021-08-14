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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: このGet-CcSiteDirectoryは、サイト レベル構成ファイルが格納されている現在のディレクトリを示します。 フォルダーには、基本 VHD とインストール ファイルSkype for Business クラウド コネクタ エディションが含まれる。 このフォルダーは、クラウド コネクタ サイトの他のすべてのアプライアンスと共有する必要があります。
ms.openlocfilehash: 279afabbb88aab162be8445007772e24d24d06d935130d5f4f27a8755a2fd25c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343191"
---
# <a name="get-ccsitedirectory"></a>Get-CcSiteDirectory
 
このGet-CcSiteDirectoryは、サイト レベル構成ファイルが格納されている現在のディレクトリを示します。 フォルダーには、基本 VHD とインストール ファイルSkype for Business クラウド コネクタ エディションが含まれる。 このフォルダーは、クラウド コネクタ サイトの他のすべてのアプライアンスと共有する必要があります。
  
このコマンドレットは、クラウド コネクタ エディション 1.4.1、1.4.2 に適用されます。
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、Cloud Connector コンポーネントの構成ファイルと仮想マシン ファイルが格納されている現在のフォルダーを示しています。
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

ゲートウェイ アフィニティと高可用性を実現するために、クラウド コネクタ アプライアンスをサイトで組み合わせることができます。 ユーザーは、クラウド コネクタ アプライアンスではなくサイトに割り当てられます。 各サイトには、基本 VHD とクラウド コネクタのインストール ファイルが格納されている共有フォルダーがあります。 アプライアンスは展開中にこのフォルダーを使用します。 既定のフォルダーは C:\Users \% userprofile%\CloudConnector\SiteRoot です。 このコマンドレットを使用して、パスSet-CcSiteDirectoryできます。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このGet-CcSiteDirectoryは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

このコマンドは、ファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcSiteDirectory](set-ccsitedirectory.md)
  

