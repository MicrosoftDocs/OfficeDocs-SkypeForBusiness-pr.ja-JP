---
title: Skype for Business Online Connector から PowerShell モジュールへのTeams移行
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Skype for Business Online Connector から Teams PowerShell モジュールに移動して、Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdd6460e6a17a15193104a0871a57fa6dbff8105
ms.sourcegitcommit: 70c07a6b1be81681eec32a89872e2218d70c514d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866359"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Skype for Business Online Connector から PowerShell モジュールへのTeams移行

TeamsPowerShell モジュールは、PowerShell コマンド ラインから直接Teamsコマンドレットの完全なセットを提供します。 管理者は、ユーザー管理Skype For Business Online Connector を使用Teams必要があります。

> [!NOTE]
> Teamsセンターの投稿 (MC244740、2021 年 3 月 16 日付け) を通じて管理者に通知されました。この変更に関する MC250940 (2021 年 4 月 16 日付け)。
>
> TeamsPowerShell モジュールは最新の認証を使用しますが、基本認証Windows基になるリモート管理 (WinRM) クライアントを構成する必要があります。 WinRM [for Basic 認証を有効Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)方法については、ダウンロードとインストールに関するページを参照してください。

## <a name="how-to-migrate"></a>移行方法

Skype for Business Online Connector を使用Teams PowerShell モジュールへの移行は簡単で簡単です。 次の手順では、これを行う方法について説明します。

1. 最新の PowerShell モジュールTeamsインストールします。 手順については[、「PowerShell のインストール」Microsoft Teams参照してください](teams-powershell-install.md)。

2. For Business Online コネクタSkypeをアンインストールします。 これを行うには、コントロール パネルで [プログラムと機能] に移動し、[オンライン] **Skype for Business、[** モジュール] Windows PowerShell 選択し、[アンインストール] を **選択します**。 

3. PowerShell スクリプトで、 で参照されているモジュール名を ```Import-Module```

    `SkypeOnlineConnector` または `LyncOnlineConnector` `MicrosoftTeams` に設定します。

    たとえば、 に `Import-Module -Name SkypeOnlineConnector` 変更します `Import-Module -Name MicrosoftTeams` 。

4. PowerShell モジュール 2.0 Teamsを使用する場合は、 を参照するスクリプトを更新 `New-CsOnlineSession` します `Connect-MicrosoftTeams` 。 `Import-PsSession`を使用するときに暗黙的に行われるSkype for Businessオンライン リモート PowerShell セッションを確立する必要はなくなりました `Connect-MicrosoftTeams` 。

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="related-topics"></a>関連項目

[PowerShell Microsoft Teamsインストールする](teams-powershell-install.md)

[PowerShell Teamsを使用Teams管理する](teams-powershell-managing-teams.md)

[TeamsPowerShell のリリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)
