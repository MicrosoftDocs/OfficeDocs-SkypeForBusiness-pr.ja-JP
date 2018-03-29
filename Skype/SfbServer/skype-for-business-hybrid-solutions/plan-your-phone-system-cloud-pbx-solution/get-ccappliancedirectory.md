---
title: Get CcApplianceDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Get-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを取得します。すべての展開ファイルはこのディレクトリに保存されます。
ms.openlocfilehash: c5c445e6017d8af81b681b70bbabcf2ba8bedd78
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancedirectory"></a>Get CcApplianceDirectory
 
Get-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを取得します。すべての展開ファイルはこのディレクトリに保存されます。 
  
このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の使用例は、クラウドのコネクタ コンポーネントの構成と仮想マシンのファイルが保存されている現在のフォルダーを示しています。
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Get CcApplianceDirectory コマンドレットは、クラウドのコネクタのアプライアンスのすべての構成および仮想マシン ・ ファイル、ログ、および外部の証明書を保存する場所を示します。
  
各コネクタのクラウド アプライアンスには 4 つのコンポーネント: 仲介サーバー、中央管理ストア、エッジ サーバー、およびドメイン コント ローラーです。 既定のフォルダーは、C:\Users\%userprofile%\CloudConnector\ApplianceRoot。 Set-CCApplianceDirectory コマンドレットを使用してこのフォルダーを変更できます。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Get-CCApplianceDirectory コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

このコマンドはファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[セット CcApplianceDirectory](set-ccappliancedirectory.md)
  

