---
title: Skype for Business Online Connector から Teams PowerShell モジュールへの移行
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Skype for Business Online Connector から Teams PowerShell モジュールに移行してTeamsを管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdd6460e6a17a15193104a0871a57fa6dbff8105
ms.sourcegitcommit: 70c07a6b1be81681eec32a89872e2218d70c514d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866359"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Skype for Business Online Connector から Teams PowerShell モジュールへの移行

Teams PowerShell モジュールには、PowerShell コマンド ラインから直接Teamsを管理するためのコマンドレットの完全なセットが用意されています。 管理者は、Teams管理のために Skype For Business Online Connector を必要としません。

> [!NOTE]
> Teams管理者は、メッセージ センターの投稿 (MC244740、2021 年 3 月 16 日付け) を通じて通知されました。MC250940(2021 年 4 月 16 日付)
>
> Teams PowerShell モジュールでは先進認証が使用されますが、基本認証を許可するように基になるWindowsリモート管理 (WinRM) クライアントを構成する必要があります。 基本認証で WinRM を有効にする方法については、「[Windows PowerShellをダウンロードしてインストール](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)する」を参照してください。

## <a name="how-to-migrate"></a>移行する方法

Skype for Business Online Connector の使用から powerShell モジュールTeamsへの移行は簡単で簡単です。 次の手順では、これを行う方法について説明します。

1. 最新のTeams PowerShell モジュールをインストールします。 手順については、「[PowerShell Microsoft Teamsインストール](teams-powershell-install.md)する」を参照してください。

2. Business Online Connector のSkypeをアンインストールします。 これを行うには、コントロール パネルの **[プログラムと機能**] に移動し、[**Skype for Business オンライン]、[Windows PowerShell モジュール**] の順に選択し、[アンインストール] を選択 **します**。

3. PowerShell スクリプトで、参照 ```Import-Module``` 元のモジュール名を変更します。

    `SkypeOnlineConnector`または `LyncOnlineConnector` .`MicrosoftTeams`

    たとえば、 `Import-Module -Name SkypeOnlineConnector` `Import-Module -Name MicrosoftTeams`.

4. PowerShell モジュール 2.0 以降Teams使用する場合は、以下を参照`New-CsOnlineSession``Connect-MicrosoftTeams`するスクリプトを更新します。 `Import-PsSession`を使用`Connect-MicrosoftTeams`するときに暗黙的に行われるので、Skype for Business Online Remote PowerShell セッションを確立する必要はなくなりました。

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

[Teams PowerShell でTeamsを管理する](teams-powershell-managing-teams.md)

[PowerShell リリース ノートをTeamsする](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)
