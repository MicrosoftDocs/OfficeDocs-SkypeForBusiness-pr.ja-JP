---
title: 会議ディレクトリを移動する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: プールの使用を停止する前に、従来のプールの各会議ディレクトリについて、次の手順を実行する必要があります。
ms.openlocfilehash: cc989e752e69db31f338b493c403b8b8d4c252cc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237738"
---
# <a name="move-conference-directories"></a>会議ディレクトリを移動する

プールを解除する前に、従来のプールの各会議ディレクトリに対して、次の手順を実行する必要があります。
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>会議ディレクトリを Skype for Business Server 2019 に移動するには

1. Skype for Business Server 管理シェルを開きます。
    
2. 組織内の会議ディレクトリの id を取得するには、次のコマンドを実行します。
    
   ```
   Get-CsConferenceDirectory
   ```

    上のコマンドは、組織内のすべての会議ディレクトリを返します。 そのため、廃棄されたプールに結果を制限することができます。 たとえば、完全修飾ドメイン名 (FQDN) pool01.contoso.net を使用してプールを廃止する場合は、このコマンドを使用して、返されるデータをそのプールの会議ディレクトリに制限します。
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    このコマンドは、ServiceID プロパティに FQDN pool01.contoso.net が含まれている会議ディレクトリだけを返します。
    
3. 会議ディレクトリを移動するには、プール内の各会議ディレクトリに対して、次のコマンドを実行します。
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    たとえば、会議ディレクトリ3を移動するには、次のコマンドを使用します。 Skype for Business Server 2019 プールを TargetPool として指定します。
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    プール上のすべての会議ディレクトリを移動する場合は、次のようなコマンドを使用します。
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

レガシプールを廃止するための包括的な手順については、「 [Microsoft レガシーをアンインストールし、サーバーの役割を削除](https://go.microsoft.com/fwlink/p/?linkId=246227)する」をダウンロードしてください。
  
会議ディレクトリを移動すると、次のようなエラーが発生する場合があります。
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

このエラーは通常、タスクを完了するために、Skype for Business Server の管理シェルで、更新された Active Directory のアクセス許可セットが必要な場合に発生します。 この問題を解決するには、管理シェルの現在のインスタンスを閉じてから、シェルの新しいインスタンスを開き、コマンドを再実行して会議ディレクトリを移動します。
  

