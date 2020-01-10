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
ms.openlocfilehash: a8b7e1b13302bec27c2fe784804f8f43fe2e023c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003397"
---
# <a name="get-ccappliancelogdirectory"></a>Get-CcApplianceLogDirectory
 
Get-CcApplianceLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスのログが保存されている現在のディレクトリを示します。
  
このコマンドレットは Skype for Business Cloud Connector エディション 1.4.1、1.4.2 に適用されます。
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a>パラメーター

なし
  
## <a name="examples"></a>例
<a name="Examples"> </a>

### <a name="example-1"></a>例 1

次の例は、Cloud Connector の現在のアプライアンスのログが保存されている現在のフォルダーを示しています。
  
```powershell
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
  

