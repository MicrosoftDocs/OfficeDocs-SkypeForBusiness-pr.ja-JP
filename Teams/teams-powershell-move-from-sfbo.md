---
title: Skype for Business オンライン コネクタから Teams PowerShell モジュールへの移行
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Skype for Business オンライン コネクタから Teams PowerShell モジュールに移行して Teams を管理する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 648ce1fb69f9e1641840f2e4b92acc1b98f4bbe8
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242291"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Skype for Business オンライン コネクタから Teams PowerShell モジュールへの移行

Teams PowerShell モジュールには、PowerShell コマンド ラインから直接 Teams を管理するためのコマンドレットの完全なセットが用意されています。 管理者は、Teams の管理に Skype For Business Online コネクタを必要としません。

> [!NOTE]
> Teams 管理者は、メッセージ センターの投稿 (MC244740、2021 年 3 月 16 日付) を通じて通知されました。MC250940(2021 年 4 月 16 日付)
>
> Teams PowerShell モジュールでは最新の認証が使用されますが、基本認証を許可するように基になる Windows リモート管理 (WinRM) クライアントを構成する必要があります。 基本的な認証で WinRM を有効にする方法については、「[Windows PowerShellのダウンロードとインストール](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)」を参照してください。

## <a name="how-to-migrate"></a>移行方法

Skype for Business オンライン コネクタから Teams PowerShell モジュールへの移行は簡単で簡単です。 次の手順では、これを行う方法について説明します。

1. 最新の Teams PowerShell モジュールをインストールします。 手順については、「[Microsoft Teams PowerShell のインストール](teams-powershell-install.md)」を参照してください。

2. Skype For Business Online コネクタをアンインストールします。 これを行うには、コントロール パネルで[**プログラムと機能**] に移動し、[オンラインSkype for Business] を選択 **し、[モジュール] をWindows PowerShell** して、[アンインストール] を選択 **します**。

3. PowerShell スクリプトで、 から参照 ```Import-Module``` されるモジュール名を変更します。

    `SkypeOnlineConnector` または `LyncOnlineConnector` を に設定します `MicrosoftTeams`。

    たとえば、 を に変更 `Import-Module -Name SkypeOnlineConnector` します `Import-Module -Name MicrosoftTeams`。

4. Teams PowerShell モジュール 2.0 以降を使用する場合は、 を`Connect-MicrosoftTeams`参照`New-CsOnlineSession`するスクリプトを更新します。 `Import-PsSession`は、を使用`Connect-MicrosoftTeams`するときに暗黙的に行われるSkype for Businessオンライン リモート PowerShell セッションを確立するために必要ではなくなりました。

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

[Teams PowerShell Microsoftインストールする](teams-powershell-install.md)

[Teams PowerShell を使用して Teams を管理する](teams-powershell-managing-teams.md)

[Teams PowerShell のリリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro)
