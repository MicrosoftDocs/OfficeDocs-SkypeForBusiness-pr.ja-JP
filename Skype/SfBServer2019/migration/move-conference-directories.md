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
ms.localizationpriority: medium
description: プールを使用停止する前に、従来のプール内の各会議ディレクトリに対して次の手順を実行する必要があります。
ms.openlocfilehash: 5d4333f74c1d45e57e45c66c8de6f3e279cee01f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596151"
---
# <a name="move-conference-directories"></a>会議ディレクトリの移動

プールを使用停止する前に、従来のプール内の各会議ディレクトリに対して次の手順を実行する必要があります。
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>会議ディレクトリを 2019 Skype for Business Serverするには

1. 管理シェルSkype for Business Server開きます。
    
2. 組織内の会議ディレクトリの ID を取得するには、次のコマンドを実行します。
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    前のコマンドは、組織内のすべての会議ディレクトリを返します。 この理由から、使用停止中のプールに結果を制限することができます。 たとえば、完全修飾ドメイン名 (FQDN) pool01.contoso.net を使用してプールを使用停止する場合は、次のコマンドを使用して、返されるデータをそのプールの会議ディレクトリに制限します。
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    このコマンドは、ServiceID プロパティに FQDN ファイルが含まれている会議ディレクトリのみを pool01.contoso.net。
    
3. 会議ディレクトリを移動するには、プール内の会議ディレクトリごとに次のコマンドを実行します。
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    たとえば、会議ディレクトリ 3 を移動するには、次のコマンドを使用して、2019 プールSkype for Business Server TargetPool として指定します。
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    プール上のすべての会議ディレクトリを移動する場合は、次のようなコマンドを使用します。
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

従来 [のプールの使用停止に](https://go.microsoft.com/fwlink/p/?linkId=246227) 関する詳細な手順については、「Microsoft レガシのアンインストール」と「サーバーの役割の削除」をダウンロードしてください。
  
会議ディレクトリを移動すると、次のエラーが発生する可能性があります。
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

通常、このエラーは、タスクを完了するために、Skype for Business Server管理シェルが Active Directory アクセス許可の更新セットを必要とする場合に発生します。 問題を解決するには、管理シェルの現在のインスタンスを閉じてから、シェルの新しいインスタンスを開き、コマンドを再実行して会議ディレクトリを移動します。
  

