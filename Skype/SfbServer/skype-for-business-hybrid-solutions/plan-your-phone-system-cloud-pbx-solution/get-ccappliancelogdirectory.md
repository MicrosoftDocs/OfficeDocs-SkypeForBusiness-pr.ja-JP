---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Get-CcApplianceLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスのログが保存されている現在のディレクトリを示します。
ms.openlocfilehash: 675e89f49c7c1384edc7cfa5944c8aee3f236c79
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287371"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Get-CcApplianceLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスのログが保存されている現在のディレクトリを示します。
  
このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、Cloud Connector の現在のアプライアンスのログが保存されている現在のフォルダーを示しています。
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

CcApplianceLogDirectory コマンドレットは、クラウドコネクタアプライアンスのログが保存されている現在のディレクトリを示しています。 既定のフォルダーは C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs. 
  
このディレクトリは、Set-CcApplianceDirectory コマンドレットを使用して変更できます。 
  
メモ: アプライアンス ディレクトリを変更することなく、ログ フォルダーの場所のみを変更するコマンドレットはありません。
  
## <a name="input-types"></a>入力の種類
<a name="InputTypes"> </a>

なし。Get-CcApplianceLogDirectory コマンドレットはパイプライン入力を受け入れません。
  
## <a name="return-types"></a>戻り値の種類
<a name="ReturnTypes"> </a>

このコマンドはファイル パスを返します。
  
## <a name="see-also"></a>関連項目
<a name="ReturnTypes"> </a>

[Set-CcApplianceDirectory](set-ccappliancedirectory.md)
  

