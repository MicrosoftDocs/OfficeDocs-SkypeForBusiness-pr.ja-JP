---
title: Skype for Business Server 2019 から Teams にユーザーを移動する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '概要: ユーザー設定を移行し、ユーザーを Teams に移動する方法について学習します。'
ms.openlocfilehash: 4a57d802d6405652724ce28ed2d26221dcc8db0f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110653"
---
# <a name="move-users-from-on-premises-to-teams"></a>オンプレミスから Teams にユーザーを移動する

ユーザーがオンプレミスから Teams Only に移動すると、ユーザーの Skype for Business ホームはオンプレミスからオンラインに移動され、ユーザーには mode=TeamsOnly を使用して TeamsUpgradePolicy が割り当てられます。  ユーザーをオンプレミスから TeamsOnly モードに移動した後は、次の方法を実行します。

- 他のユーザーからのすべての着信呼び出しとチャット (Skype for Business または Teams から送信された場合) は、ユーザーの Teams クライアントに送信されます。
- ユーザーは、Skype for Business を使用する他のユーザー (オンラインでもオンプレミスでも) と相互運用できます。
- ユーザーはフェデレーション組織のユーザーと通信できます。
- そのユーザーがスケジュールした新しい会議は Teams 会議です。
- ユーザーは引き続き Skype for Business 会議に参加できます。
- 将来予定されているユーザーの既存の会議は、オンプレミスから Teams に移行されます。
- オンプレミスに存在していた連絡先は、ユーザーが初めてログオンした直後に Teams で利用できます。
- ユーザーは、Skype for Business から通話やチャットを開始したり、Skype for Business で新しい会議をスケジュールしたりすることはできません。 Skype for Business クライアントを開く場合、以下に示すように Teams を使用するためにリダイレクトされます。 Teams クライアントがインストールされていない場合は、ブラウザーを使用して Web バージョンの Teams に送信されます。<br><br>
    ![Teams にユーザーをリダイレクトするメッセージ](../media/go-to-teams-page.png)

ユーザーを移動する前に、必ず前提条件を確認 [して](move-users-between-on-premises-and-cloud.md#prerequisites) 、ユーザーをクラウドに移動してください。 また、Teams と Skype for Business を組み合わせて使用する組織の移行と相互運用性に関する [ガイダンスも必ず確認してください](/microsoftteams/migration-interop-guidance-for-teams-with-skype)。


> [!NOTE]
> 連絡先を Teams に移動するには、統合連絡先ストアを On-prem SfB アカウントで無効にする必要があります。


ユーザーをオンプレミスから Teams に移動するには、次の 2 つの方法があります。

- Skype for Business Server 2015 CU8 より前のバージョンを使用している場合、移動には 2 つの手順が必要です (必要に応じて、1 つの手順として一緒にスクリプトを実行できます)。
  - [ユーザーを Skype for Business Server (オンプレミス) から Skype for Business Online に移動します](move-users-from-on-premises-to-skype-for-business-online.md)。
  - ユーザーが Skype for Business Online に参加したら、mode= TeamsOnly を使用してユーザー TeamsUpgradePolicy を割り当てる。 TeamsOnly モードを付与するには、Skype for Business Online PowerShell ウィンドウから次のコマンドレットを実行します。 `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Skype for Business Server 2015 CU8 以降の管理ツールがある場合は、上記の方法を使用するか、以下で説明するように 1 つの手順でこの移動を実行できます。 さらに、必要に応じて、Skype for Business クライアント内で通知を Teams Only に移動する前に通知を提供し、必要に応じて Teams クライアントを Skype for Business クライアントによってサイレント ダウンロードすることもできます。

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>オンプレミスの Skype for Business から Teams 専用にユーザーを直接移動する

Skype for Business Server 2015 と CU8 のオンプレミス管理ツール、および Skype for Business Server 2019 では、以下で説明するように、PowerShell の Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルのいずれかを使用して、オンプレミスから Teams Only モードにユーザーを移動できます。

### <a name="move-to-teams-using-move-csuser"></a>サーバーを使用して Teams に移動Move-CsUser

Move-CsUserは、オンプレミスの Skype for Business Management Shell PowerShell ウィンドウから利用できます。 以下の手順と必要なアクセス許可は、ユーザーを Skype for Business Online に移動する場合と同じですが、MoveToTeams スイッチも指定する必要があります。また、ユーザーに Teams のライセンス (Skype for Business Online に加えて) も付与されている必要があります。

「必須の管理資格情報」の説明に従って、オンプレミス環境とクラウド サービス (Microsoft 365 または Office 365) の両方で十分な特権を持っている [必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。 両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して、必要な管理役割を持つ `-Credential` Microsoft 365 または Office 365 アカウントの資格情報を指定できます。

Move-CsUser を使用してユーザーを Teams Only モードに移動するには、次のコマンドを実行します。

- パラメーターを使用して移動するユーザーを `Identity` 指定します。
- 値 "sipfed.online.lync" で -Target パラメーターを指定します。 <span>com」
- スイッチを指定 `MoveToTeams` します。
- オンプレミスとクラウド サービス (Microsoft 365 または Office 365) の両方に十分なアクセス許可を持つアカウントが 1 つない場合は、パラメーターを使用して、Office 365 で十分なアクセス許可を持つ `-credential` アカウントを指定します。
- Microsoft 365 または microsoft 365 または Office 365 のアクセス許可を持つアカウントが "onmicrosoft" で終了しない場合。 <span>com」の説明に従って、パラメーターを正しい値で指定 `-HostedMigrationOverrideUrl` [する必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。

次のコマンドレット シーケンスを使用して、ユーザーを TeamsOnly に移動し、Microsoft 365 または Office 365 資格情報が別のアカウントであり、Get-Credential プロンプトの入力として提供されたと見なします。

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> 異なるパラメーターが必要な状況が異なるので、ほとんどの場合の既定のコマンドは次のとおりです。

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用して Teams に移動する

1. Skype for Business Server コントロール パネル アプリを開きます。
2. 左側のナビゲーションで、[ユーザー] を **選択します**。
3. [ **検索]** を使用して、Teams に移動するユーザーを検索します。
4. ユーザーを選択し、リストの上にある **[** アクション] ドロップダウンから [選択したユーザーを Teams に移動する] **を選択します**。
5. ウィザードで、[ **次へ**] をクリックします。
6. メッセージが表示されたら、Microsoft 365 または Office 365 に .onmicrosoft.com で終了し、十分なアクセス許可を持つアカウントでサインインします。
7. [ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。
8. 成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Skype for Business オンプレミス ユーザーに Teams への今後の移行を通知する

Skype for Business Server 2015 と CU8、Skype for Business Server 2019 のオンプレミス管理ツールを使用すると、オンプレミスの Skype for Business ユーザーに Teams への移行を通知できます。 これらの通知を有効にした場合、ユーザーは Skype for Business クライアント (Win32、Mac、Web、およびモバイル) に以下のように通知を表示します。 ユーザーが [ **試す] ボタンを** クリックすると、Teams クライアントがインストールされている場合は起動されます。それ以外の場合、ユーザーはブラウザーで Web バージョンの Teams に移動します。 既定では、通知が有効な場合、Win32 Skype for Business クライアントは Teams クライアントをサイレント モードでダウンロードして、リッチ クライアントを Teams Only モードに移行する前にリッチ クライアントを使用できます。ただし、この動作を無効にできます。  通知は、オンプレミスバージョンの Win32 クライアント用にサイレント ダウンロードを使用して構成され、オンプレミスコマンドレット `TeamsUpgradePolicy` を介して制御 `TeamsUpgradeConfiguration` されます。

> [!TIP]
> 一部のサーバーでは、CU8 を使用して Skype for Business 2015 で動作するために再起動が必要な場合があります。

![Teams への今後の移行の通知](../media/teams-upgrade-notification.png)

オンプレミスのユーザーに Teams へのアップグレードが近い場合に通知するには、NotifySfBUsers=true を使用して TeamsUpgradePolicy の新しいインスタンスを作成します。 次に、ポリシーをユーザーに直接割り当てるか、サイト、プール、またはグローバル レベルでポリシーを設定して、通知するユーザーにポリシーを割り当てる。 次のコマンドレットは、ユーザー レベルのポリシーを作成して付与します。

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Skype for Business Win32 クライアントを介した Teams の自動ダウンロードは、DownloadTeams パラメーターを使用して、オンプレミスの TeamsUpgradeConfiguration コマンドレットを介して制御されます。 この構成は、グローバル レベル、サイト レベル、およびプール レベルで作成します。 たとえば、次のコマンドは、サイト Redmond1 の構成を作成します。

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

既定では、DownloadTeams の値は True です。ただし、指定した *ユーザーに* 対して NotifySfbUser = True の場合にのみ適用されます。

## <a name="see-also"></a>関連項目

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Skype for Business と共存する](/microsoftteams/coexistence-chat-calls-presence)