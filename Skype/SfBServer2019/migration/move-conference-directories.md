---
title: 会議ディレクトリの移動
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: プールを使用停止にする前に、従来のプール内の会議ディレクトリごとに次の手順を実行する必要があります。
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752499"
---
# <a name="move-conference-directories"></a>会議ディレクトリの移動

プールを使用停止にする前に、従来のプール内の会議ディレクトリごとに次の手順を実行する必要があります。
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>会議ディレクトリを Skype for Business Server 2019 に移動するには

1. Skype for Business Server 管理シェルを開きます。
    
2. 組織内の会議ディレクトリの id を取得するには、次のコマンドを実行します。
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    上記のコマンドは、組織内のすべての会議ディレクトリを返します。 そのため、廃棄されたプールに対して結果を制限する必要がある場合があります。 たとえば、完全修飾ドメイン名 (FQDN) pool01.contoso.net でプールを使用停止にする場合は、次のコマンドを使用して、返されるデータをそのプールからの会議ディレクトリに制限します。
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    このコマンドは、ServiceID プロパティに FQDN pool01.contoso.net が含まれている会議ディレクトリのみを返します。
    
3. 会議ディレクトリを移動するには、プール内の会議ディレクトリごとに次のコマンドを実行します。
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    たとえば、会議ディレクトリ3を移動するには、次のコマンドを使用します。 Skype for Business Server 2019 プールを TargetPool として指定します。
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    プール上のすべての会議ディレクトリを移動する場合は、次のようなコマンドを使用します。
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

レガシプールを使用停止にするための包括的な手順については、「 [Microsoft レガシーのアンインストールとサーバーの役割の削除](https://go.microsoft.com/fwlink/p/?linkId=246227)」をダウンロードしてください。
  
会議ディレクトリを移動するときに、次のエラーが発生することがあります。
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

通常、このエラーは、Skype for Business Server 管理シェルで、タスクを完了するために、更新された Active Directory のアクセス許可セットが必要な場合に発生します。 この問題を解決するには、管理シェルの現在のインスタンスを閉じてから、シェルの新しいインスタンスを開き、コマンドを再実行して会議ディレクトリを移動します。
  

