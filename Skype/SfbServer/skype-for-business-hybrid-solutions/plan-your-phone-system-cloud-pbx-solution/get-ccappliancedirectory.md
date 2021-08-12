---
title: Get-CcApplianceDirectory
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
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: このGet-CcApplianceDirectoryコマンドレットは、ホスト サーバー上の作業ディレクトリSkype for Business クラウド コネクタ エディションします。 すべての展開ファイルは、このディレクトリに格納されます。
ms.openlocfilehash: 9be21029aaf582ce080b85af87b8d3f02be11ffea3b615f2b003bb6aeb29002d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347592"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
このGet-CcApplianceDirectoryコマンドレットは、ホスト サーバー上の作業ディレクトリSkype for Business クラウド コネクタ エディションします。 すべての展開ファイルは、このディレクトリに格納されます。 
  
このコマンドレットは、Skype for Business クラウド コネクタ エディション 1.4.1、1.4.2 に適用されます。
  
```powershell
Get-CcApplianceDirectory
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、Cloud Connector コンポーネントの構成ファイルと仮想マシン ファイルが格納されている現在のフォルダーを示しています。
  
```powershell
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

このGet-CcApplianceDirectoryは、すべての構成ファイル、仮想マシン ファイル、ログ、および外部証明書がクラウド コネクタ アプライアンスに格納されている場所を示します。
  
各クラウド コネクタ アプライアンスには、仲介サーバー、中央管理ストア、エッジ サーバー、およびドメイン コントローラーの 4 つのコンポーネントがあります。 既定のフォルダーは C:\Users \% userprofile%\CloudConnector\ApplianceRoot です。 このフォルダーは、このコマンドレットを使用してSet-CCApplianceDirectoryできます。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。 このGet-CCApplianceDirectoryは、パイプライン処理された入力を受け付け取らない。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

コマンドはファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

