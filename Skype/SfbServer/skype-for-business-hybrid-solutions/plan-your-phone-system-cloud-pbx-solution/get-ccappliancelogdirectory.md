---
title: Get CcApplianceLogDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: Get-CcApplianceLogDirectory コマンドレットは、Skype for Business Cloud Connector エディションのアプライアンスのログが保存されている現在のディレクトリを示します。
ms.openlocfilehash: 9b7d4853deb9ab16c7ae61279a20a30778774072
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccappliancelogdirectory"></a>Get CcApplianceLogDirectory
 
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

クラウド コネクタの現在のアプライアンスは、ログが保存されている現在のフォルダーを次の例に示します。
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a>解説
<a name="DetailedDescription"> </a>

Get CcApplianceLogDirectory コマンドレットでは、コネクタのクラウド アプライアンスは、ログが保存されている現在のディレクトリを示しています。 既定のフォルダーは、C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs。 
  
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

[セット CcApplianceDirectory](set-ccappliancedirectory.md)
  

