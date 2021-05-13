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
ms.openlocfilehash: e788fc8cd31bd6e8754e410132e02829eaa2cad8
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469719"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Skype for Business Online Connector から PowerShell モジュールへのTeams移行

TeamsPowerShell モジュールには、PowerShell コマンド ラインから直接管理Teamsコマンドレットの完全なセットが提供されます。 管理者は、ユーザー管理Skype For Business Online Connector を使用Teams必要とします。

> [!NOTE]
> Teamsセンターの投稿 (MC244740、2021 年 3 月 16 日付け) を通じて管理者に通知されました。この変更に関する MC250940 (2021 年 4 月 16 日付け)。
>
> TeamsPowerShell モジュールは最新の認証を使用しますが、基本認証Windows基になるリモート管理 (WinRM) クライアントを構成する必要があります。 WinRM [for Basic 認証を有効Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)方法については、ダウンロードとインストールに関するページを参照してください。

> [!WARNING]
> Skype for Businessオンライン コネクタ接続は、2021 年 5 月 17 日から拒否されます。 PowerShell モジュールへの移行については、Microsoft サポートTeams問い合わせください。

## <a name="how-to-migrate"></a>移行方法

Skype for Business Online Connector を使用して PowerShell モジュールTeamsに移行するのは簡単で簡単です。 次の手順では、これを行う方法について説明します。

1. 最新の PowerShell モジュールTeamsインストールします。 手順については[、「PowerShell のインストール」Microsoft Teams参照してください](teams-powershell-install.md)。
2. For Business Online コネクタSkypeをアンインストールします。 これを行うには、コントロール パネルで [プログラムと機能]**に移動** し、[オンライン] **Skype for Business、[** モジュール] の順Windows PowerShell選択し、[アンインストール] を **選択します**。
3. PowerShell スクリプトで、 で参照されているモジュール名を ```Import-Module```

    `SkypeOnlineConnector` または `LyncOnlineConnector` `MicrosoftTeams` に設定します。

    たとえば、 に `Import-Module -Name SkypeOnlineConnector` 変更します `Import-Module -Name MicrosoftTeams` 。

4. PowerShell モジュール 2.0 Teamsを使用する場合は、 を参照するスクリプトを更新 `New-CsOnlineSession` します `Connect-MicrosoftTeams` 。 `Import-PsSession`を使用するときに暗黙的に行われるSkype for Businessオンライン リモート PowerShell セッションを確立する必要はなくなりました `Connect-MicrosoftTeams` 。

    ```powershell
       # When using the Skype for Business online connector
         Import-Module SkypeForBusinessConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
       # Example getting tenant details
         Get-csTenant
    
       # When using Teams PowerShell Module 2.0 or later
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
       # Example getting tenant details
         Get-csTenant
    
       # Closing the Session when using the Skype for Business online connector
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # Disconnecting from Teams PowerShell Module 
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a>オンライン サポート

サービス要求をオンラインで開始することで時間を節約できます。 ソリューションの検索やテクニカル サポートへの接続をお手伝いします。
1.  [https://admin.microsoft.com](https://admin.microsoft.com) で管理センターにアクセスします。 このページにアクセスしたり、この操作を実行したりするためのアクセス許可が付与されていないというメッセージが表示された場合は、管理者ではない場合があります。Whoは、私のビジネスで管理者アクセス許可を持っていますか?
2.  [ヘルプが **必要ですか?] を選択します**。ボタンをクリックします。
3.  「ヘルプ **が必要ですか?」を参照してください**。ウィンドウで、ヘルプが必要な情報を入力し、Enter キーを押します。
4.  結果が問題ない場合は、[サポートに問い合わせ **] を選択します**。
5.  問題の説明を入力し、連絡先番号とメール アドレスを確認し、希望する連絡方法を選び、[連絡してください] **を選択します**。 予想される待機時間は、「ヘルプが必要ですか?」に示されています。ウィンドウに移動します。

## <a name="related-topics"></a>関連トピック

[PowerShell Microsoft Teamsインストールする](teams-powershell-install.md)

[PowerShell Teamsを使用Teams管理する](teams-powershell-managing-teams.md)

[TeamsPowerShell のリリース ノート](teams-powershell-release-notes.md)

[Microsoft Teams コマンドレット リファレンス](/powershell/teams/?view=teams-ps)

[Skype for Business コマンドレット リファレンス](/powershell/skype/intro?view=skype-ps)
