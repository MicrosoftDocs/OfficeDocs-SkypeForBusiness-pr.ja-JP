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
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Get-CcApplianceDirectory コマンドレットは、Skype for Business Cloud Connector エディションのホスト サーバーでの作業ディレクトリを取得します。すべての展開ファイルはこのディレクトリに保存されます。
ms.openlocfilehash: ada1b587b738d882f81557e61438d6642aa03fff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287392"
---
# <a name="get-ccappliancedirectory"></a>Get-CcApplianceDirectory
 
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

次の例は、クラウドコネクタコンポーネントの構成ファイルと仮想マシンファイルが保存されている現在のフォルダーを示しています。
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

CcApplianceDirectory コマンドレットは、クラウドコネクタアプライアンスのすべての構成ファイル、仮想マシンのファイル、ログ、外部証明書が保存されている場所を示します。
  
各クラウドコネクタアプライアンスには、仲介サーバー、中央管理ストア、エッジサーバー、ドメインコントローラーという4つのコンポーネントがあります。 既定のフォルダーは C:\Users\%userprofile%\CloudConnector\ApplianceRoot. Set-CCApplianceDirectory コマンドレットを使用してこのフォルダーを変更できます。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Get-CCApplianceDirectory コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

このコマンドはファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

