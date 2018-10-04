---
title: 会議ディレクトリを移動する
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: プールの使用を停止する前に、レガシ プール内に、会議ディレクトリごとに以下の手順を行う必要があります。
ms.openlocfilehash: b7526d8c3c032bf8b1f9052dce7da7e8a87b66b5
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372806"
---
# <a name="move-conference-directories"></a>会議ディレクトリを移動する

プールの使用を停止する前に、レガシ プール内に、会議ディレクトリごとに以下の手順を行う必要があります。
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>Skype をビジネス サーバー 2019 の会議ディレクトリを移動するには

1. Skype をビジネス サーバー管理シェルを開きます。
    
2. 組織内の会議ディレクトリの id を取得するには、次のコマンドを実行します。
    
   ```
   Get-CsConferenceDirectory
   ```

    上記のコマンドは、組織のすべての会議ディレクトリを返します。 このため、プールの使用を中止するのに結果を制限する可能性があります。 などの完全修飾ドメイン名 (FQDN) の pool01.contoso.net のプールを廃止する場合は、会議ディレクトリをそのプールから返されたデータを制限するのにはこのコマンドを使用します。
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    そのコマンドは、ServiceID プロパティが FQDN の pool01.contoso.net を含む会議ディレクトリのみを返します。
    
3. 会議ディレクトリを移動するには、プールで会議の各ディレクトリに対して次のコマンドを実行します。
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    たとえば、3 の会議ディレクトリを移動するに、TargetPool として、Skype のビジネス サーバー 2019 プールを指定する、このコマンドを使用します。
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    プール上のすべての会議ディレクトリを移動する場合は、次のようなコマンドを使用します。
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

従来のプールを使用停止に包括的なステップバイ ステップの手順については、 [Microsoft レガシーをアンインストールしてサーバーの役割を削除すること](https://go.microsoft.com/fwlink/p/?linkId=246227)をダウンロードします。
  
会議ディレクトリを移動するには、次のエラーが発生する可能性があります。
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

このエラーは、ビジネスのサーバー管理シェルの Skype は、更新されたタスクを完了するために Active Directory アクセス許可のセットを必要とする場合に通常発生します。 問題を解決するには、管理シェルの現在のインスタンスを閉じる、シェルの新しいインスタンスを開くし、会議ディレクトリを移動するコマンドを再実行します。
  

