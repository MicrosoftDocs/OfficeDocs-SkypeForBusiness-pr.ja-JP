---
title: 移動ユーザーがチームを設置
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: '概要: は、ユーザー設定を移行し、チームにユーザーを移動する方法を説明します。'
ms.openlocfilehash: 6bee0562b38ce3119306e23b11ea50ebdb8ac3e9
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244033"
---
# <a name="move-users-from-on-premises-to-teams"></a>移動ユーザーがチームを設置

会社のホームに移動した設置型のオンラインと、ユーザー モードでは TeamsUpgradePolicy に割り当てられます、ユーザーが Skype のユーザーに移動した場合の社内チームだけに、TeamsOnly を = します。  ユーザー後から移動設置型 TeamsOnly モードにします。

- すべての着信を呼び出し、他のユーザー (ビジネスやチームのために、Skype から送信) かどうかのチャット ユーザーのチームのクライアントで着陸します。
- ユーザーは (オンラインまたは設置型) かどうかは、ビジネスの Skype を使用している他のユーザーと相互運用することになります。 
- ユーザーはフェデレーション組織のユーザーと通信することになります。
- そのユーザーが予定されている新規の会議は、チームの会議です。
- ユーザーは、ビジネス会議のため、Skype にも参加できます。
- Skype にはオンライン ビジネスの未来に予定されているユーザーの既存の会議を設置型から移行されます。
- 施設内に存在していた連絡先は、最初にユーザーがログオンした後にすぐにチームで使用できます。
- ユーザーが呼び出しまたはビジネス用の Skype のチャットを開始できませんも、ビジネスの Skype の新しい会議をスケジュールできます。 ビジネス クライアント用の Skype を開くしようとする場合は、チームを使用して、次のようにリダイレクトされます。 チームのクライアントがインストールされていない場合が、ブラウザーを使用するチームの web バージョンに表示されます。<br><br>
    ![チームにユーザーをリダイレクトするメッセージ](../media/go-to-teams-page.png)

すべてのユーザーを移動する前に必ずユーザーをクラウドに移行する[前提条件](move-users-between-on-premises-and-cloud.md#prerequisites)を確認してください。 必ず[チームと、ビジネス用の Skype を使用する組織の移行と相互運用性](/microsoftteams/migration-interop-guidance-for-teams-with-skype)を確認してください。

社内のチームからユーザーを移動する方法は 2 つです。

- ビジネス サーバー 2015 CU8 の Skype より前のバージョンを使用している場合、移動には、2 つの手順が必要な場合は、1 つのステップとして実行するスクリプト化できる) が必要です。
    - [ビジネス上のサーバー (設置型) ビジネス オンラインの Skype に Skype からユーザーを移動](move-users-from-on-premises-to-skype-for-business-online.md)します。
    - 取引をオンラインでは、TeamsUpgradePolicy モードでのユーザーを割り当てるために、Skype でユーザーのホームとは、TeamsOnly を = します。 TeamsOnly モードを許可するには、ビジネス オンラインの PowerShell ウィンドウで、Skype から次のコマンドレットを実行します。`Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Skype ビジネス サーバー 2015 CU8 またはそれ以降の管理ツールを使っている場合、上記のメソッドを使用することができますか、次のように 1 つの手順では、この移動を行うことができます。 さらに、する、必要に応じてチームのみに移動する前にクライアントをビジネスの Skype 内で通知を提供するとともに必要に応じてビジネス クライアント用の Skype でサイレント モードでダウンロードしたチームのクライアントがあります。

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>設置型のビジネス用の Skype から直接チームのみにユーザーを移動します。

CU8 を持つサーバー 2015 のビジネス用の Skype と Skype のビジネス サーバー 2019、設置管理ツールを使用すると、ビジネス Se の PowerShell で移動 CsUser コマンドレット、または、Skype のいずれかを使用して 1 つの手順でモードのチームだけに、設置型からユーザーを移動するにはした rver コントロール パネルで、次のようにします。

### <a name="move-to-teams-using-move-csuser"></a>Csuser からの移動を使用するチームに移動します。

Csuser からの移動を指定する場合は、オンプレミス Skype のビジネス管理シェルの PowerShell ウィンドウで実行できます。 次の手順と必要なアクセス許可は、MoveToTeams スイッチを指定することもする必要があり、ユーザーも付与されているライセンス (ビジネス用の Skype の他のチームのことを確認する必要がありますが、ビジネス オンラインの Skype をユーザーの移動と同じオンライン)。

[管理者の資格情報が必要な](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)の説明に従って、オンプレミス環境と、Office 365 テナントの両方に十分な特権が必要です。 両方の環境で権限のある単一のアカウントを使用することができますか、または設置型の資格情報を持つビジネス サーバー管理シェル ウィンドウに、オンプレミス Skype を起動し、使用できます、 `-Credential` 、Office 365 の資格情報を指定するパラメーター必要な Office 365 管理者の役割を持つアカウント。

Csuser からの移動を使用するモードのチームだけにユーザーを移動します。

- 使用して移動するユーザーを指定します`Identity`パラメーター。
- 指定ターゲット パラメーターを指定する値"sipfed.online.lync。<span>com"します。
- 指定の`MoveToTeams`を切り替えます。
- 設置型および Office 365 の両方のための十分なアクセス許可を持つ 1 つのアカウントがないを使用して、 `-credential` Office 365 のための十分な権限を持つアカウントを指定するパラメーターです。
- 」On.microsoft で Office 365 にアクセス許可を持つアカウントが終わっていない場合。<span>com」、指定する必要があります、`-HostedMigrationOverrideUrl`で説明されているが[管理者の資格情報を必要](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)と正しい値を持つパラメーターです。

次のコマンドレットのシーケンスでは、TeamsOnly にユーザーを移動する使用することができ、Office 365 の資格情報は別のアカウントであり、取得の資格情報のプロンプトへの入力として提供されたと仮定しています。

    ```
    $cred=Get-Credential
    $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
    ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>ビジネス サーバーのコントロール パネルの Skype を使用するチームに移動します。

1.  ビジネス サーバー管理のため、Skype を開くパネルのアプリケーション。
2.  左側のナビゲーションでは、**ユーザー**を選択します。
3.  チームに移動したいユーザーを検索するには、**検索**を使用します。
4.  、ユーザーを選択して、**アクション**ドロップダウン リストの上からクリックして**チームを選択したユーザーを移動**します。
5.  ウィザードで、[**次へ**] クリックします。
6.  メッセージが表示されたらにサインイン、Office 365 で終了するアカウントを使用しています。 onmicrosoft.com 十分なアクセス許可とします。
7.  ユーザーを移動するのには**次へ**、し、[**次へ**1 つのより多くの時間をクリックします。
8. ウィザードではなく、メインのコントロール パネルの [アプリケーションの上部に成功または失敗に関連するステータス メッセージが提供されることに注意してください。

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>チームへの移行は今後のビジネス、オンプレミスのユーザーは、Skype に通知します。

CU8 を持つサーバー 2015 のビジネス用の Skype と Skype のビジネス サーバー 2019、設置管理ツールを使用すると、設置の Skype の予定を移動して、チームのビジネス ユーザー向けに通知します。 これらの通知を有効にすると、ユーザーは次のように (Win32、Mac、web、およびモバイル) のビジネス クライアント用の Skype に通知が表示されます。 インストールされている場合にチームのクライアントを起動する場合は、ユーザーが**それを実行してください**] をクリックしてそれ以外の場合、ユーザーは、自分のブラウザーのチームの web バージョンに移動します。 既定では、通知を有効にすると、Win32 の Skype ビジネス クライアントのサイレント モードでクライアントをダウンロード チーム チームのみのモードは、ユーザーを移動する前に利用可能なリッチ クライアントになるようただし、この現象も無効にすることができます。  設置型バージョンを使用して通知が構成されて`TeamsUpgradePolicy`、および Win32 クライアントのサイレント ダウンロードは、設置型を使用して制御`TeamsUpgradeConfiguration`コマンドレットです。

![チームへの今後の移行の通知](../media/teams-upgrade-notification.png)

NotifySfBUsers と TeamsUpgradePolicy の新しいインスタンスを作成することではすぐにアップグレードするチームに、オンプレミスのユーザーに通知、true です。 ポリシーをユーザーに直接割り当てるか、サイト、プール、またはグローバル レベルでポリシーを設定することにより、通知を使用するユーザーにそのポリシーを割り当てます。 次のコマンドレットでは、作成し、ユーザー レベルのポリシーを付与します。

```
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

ビジネス Win32 クライアントの Skype を使用してチームの自動ダウンロードは、DownloadTeams パラメーターを使用して、オンプレミスの TeamsUpgradeConfiguration コマンドレットを使用して制御されます。 このグローバル構成、サイト、およびプールのレベルを作成します。 たとえば、次のコマンドでは、サイト Redmond1 の構成が作成されます。

`New-CsTeamsUpgradeConfiguration -Identity “site:redmond1”`

既定では、DownloadTeams の値は、True です。ただしは*のみ*場合は優先順位を付ける NotifySfbUser 特定のユーザーを指定します。


## <a name="see-also"></a>関連項目

[Csuser からの移動](https://docs.microsoft.com/en-us/powershell/module/skype/move-csuser)

[許可 CsTeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy
)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Skype for Business と共存する](/microsoftteams/coexistence-chat-calls-presence)
