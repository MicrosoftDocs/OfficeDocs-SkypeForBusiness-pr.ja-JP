---
title: ユーザーを 2019 Skype for Business Serverから 2019 年Teams
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
description: '概要: ユーザー設定を移行し、ユーザーをユーザーに移動する方法についてTeams。'
ms.openlocfilehash: b9b21dafc2290dfff5522f5d54c0872121294dd9
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856306"
---
# <a name="move-users-from-on-premises-to-teams"></a>オンプレミスから Teams にユーザーを移動する

ユーザーをオンプレミスから Teams のみに移動すると、ユーザーの Skype for Business ホームはオンプレミスからオンラインに移動され、ユーザーには mode=TeamsOnly で TeamsUpgradePolicy が割り当てられます。  ユーザーをオンプレミスから TeamsOnly モードに移動した後は、次の方法を実行します。

- (Skype for Business または Teams から送信された) 他のユーザーからの着信通話とチャットはすべて、ユーザーのクライアントにTeamsされます。
- ユーザーは、オンラインかオンプレミスかを問Skype for Business他のユーザーと相互運用できます。
- ユーザーはフェデレーション組織のユーザーと通信できます。
- そのユーザーがスケジュールした新しい会議は、Teamsされます。
- ユーザーは引き続き任意の会議Skype for Businessできます。
- 将来予定されているユーザーの既存の会議は、オンプレミスから既存の会議に移行Teams。
- オンプレミスに存在していた連絡先は、ユーザーが初Teamsログオンした直後に、このサイトで利用できます。
- ユーザーは、ユーザーから通話やチャットを開始Skype for Business、また、会議で新しい会議をスケジュールSkype for Business。 クライアントを開くSkype for Business、次に示すようにTeamsリダイレクトされます。 クライアントがTeams場合は、ブラウザーを使用して web バージョンTeamsされます。<br><br>
    ![ユーザーをユーザーにリダイレクトするTeams](../media/go-to-teams-page.png)

ユーザーを移動する前に、必ず前提条件を確認 [して](move-users-between-on-premises-and-cloud.md#prerequisites) 、ユーザーをクラウドに移動してください。 また、移行を使用している組織の移行と相互運用性のガイダンスと、Teams[を確認Skype for Business。](/microsoftteams/migration-interop-guidance-for-teams-with-skype)


> [!NOTE]
> 連絡先をサーバーに移動するには、統合連絡先ストアを on-prem SfB アカウントで無効Teams。

> [!IMPORTANT]
>Move-CsUser を使用してユーザーをオンプレミスからクラウドに移動すると、ユーザーに TeamsOnly モードが自動的に割り当てられると、スイッチが実際に指定されたかどうかに関係なく、オンプレミスの会議が自動的に Teams 会議に変換されます。 `-MoveToTeams` (これには、切り替え前の Lync Server 2013 からの移行が含 `-MoveToTeams` まれます)。 以前は、このスイッチが指定されていない場合、ユーザーは Skype for Business Server オンプレミスのホームから Skype for Business Online に移行し、モードは変更されません。 これは最近、オンラインの退職に備えてSkype for Businessされています。


## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>オンプレミスからユーザーを直接Skype for Businessに移動Teamsのみ

Skype for Business Server および Lync Server 2013 のオンプレミス管理ツールを使用すると、以下で説明するように、PowerShell の Move-CsUser コマンドレットまたは Skype for Business Server コントロール パネルを使用して、1 つの手順でユーザーをオンプレミスから TeamsOnly モードに移動できます。 スイッチを指定する必要がなくなりました。また、使用する Skype for Business Server または Lync Server のバージョンに関係なく、オンプレミスから Teams Only に直接移動する動作が自動的に実行されます `-MoveToTeams` 。 

「必須の管理資格情報」の説明に従って、オンプレミス環境とクラウド サービス (Microsoft 365 または Office 365) の両方で十分な特権を持っている[必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。 両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミスの Skype for Business Server 管理シェル ウィンドウを起動し、パラメーターを使用して必要な管理役割を持つ Microsoft 365 の資格情報を指定できます。 `-Credential`

さらに、ユーザーにオンラインのライセンスが付与Teams必要があります (Skype for Businessします)。 オンライン ライセンスのSkype for Business無効にしない。

### <a name="move-to-teams-using-move-csuser"></a>[ファイルを使用してTeamsに移動Move-CsUser

Move-CsUserは、オンプレミスの管理シェル PowerShell ウィンドウSkype for Business Server Lync Server 管理シェル PowerShell ウィンドウから使用できます。 Move-CsUser を使用してユーザーを TeamsOnly モードに移動するには、次のコマンドを実行します。
- パラメーターを使用して移動するユーザーを `Identity` 指定します。
- `-Target`"sipfed.online.lync" という値のパラメーターを指定します。 <span>com」
- オンプレミスとクラウド サービス (Microsoft 365) の両方に十分なアクセス許可を持つアカウントが 1 つない場合は、パラメーターを使用して、Microsoft 365 で十分なアクセス許可を持つアカウント `-credential` を指定します。
- アクセス許可を持つアカウントが Microsoft 365 "onmicrosoft" で終了しない場合。 <span>com」の説明に従って、パラメーターを正しい値で指定 `-HostedMigrationOverrideUrl` [する必要があります](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)。

次のコマンドレット シーケンスを使用して、ユーザーを TeamsOnly に移動し、Microsoft 365 資格情報が別のアカウントであり、Get-Credential プロンプトの入力として提供されたと見なします。 動作は、スイッチが指定されている `-MoveToTeams` かどうかに関して同じです。

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> 異なるパラメーターが必要な状況が異なるので、ほとんどの場合の既定のコマンドは次のとおりです。

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>[コントロール パネル] Teamsを使用Skype for Business Serverに移動する

1. コントロール パネル アプリSkype for Business Server開きます。
2. 左側のナビゲーションで、[ユーザー] を **選択します**。
3. [**検索]** を使用して、ユーザーに移動するユーザーをTeams。
4. ユーザーを選択し、リストの上にある [アクション] ドロップダウンから 、[選択したユーザーを Teams に移動する] または **[** 選択したユーザーをオンラインにSkype for Business **します**。   どちらのオプションでも、ユーザーは TeamsOnly に直接移動します。
5. ウィザードで、[ **次へ**] をクリックします。
6. メッセージが表示されたら、.Microsoft 365で終わり、十分なアクセス許可を持つアカウントを使用して、onmicrosoft.com にサインインします。
7. [ **次へ]** をクリックし、[ **次** へ] をクリックしてもう 1 回ユーザーを移動します。
8. 成功または失敗に関する状態メッセージは、ウィザードではなく、メインのコントロール パネル アプリの上部に表示されます。
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>今後のSkype for Businessをオンプレミス のユーザーに通知Teams

cu8 と Skype for Business Server 2015 のオンプレミス管理ツール、および Skype for Business Server 2019 では、Teams への移行についてオンプレミス Skype for Business ユーザーに通知できます。 これらの通知を有効にした場合、ユーザーは次に示すように、Skype for Business クライアント (Win32、Mac、Web、およびモバイル) に通知を表示します。 ユーザーが [**試す**] ボタンをクリックするとTeamsクライアントがインストールされている場合に起動されます。それ以外の場合、ユーザーはブラウザーで web バージョンTeams移動されます。 既定では、通知を有効にすると、Win32 Skype for Business クライアントは Teams クライアントをサイレント モードでダウンロードして、リッチ クライアントを TeamsOnly モードに移行する前に利用できます。ただし、この動作を無効にできます。  通知は、オンプレミスバージョンの Win32 クライアント用にサイレント ダウンロードを使用して構成され、オンプレミスコマンドレット `TeamsUpgradePolicy` を介して制御 `TeamsUpgradeConfiguration` されます。

> [!TIP]
> 一部のサーバーでは、CU8 を使用して 2015 年 2015 年Skype for Business再起動する必要があります。

![今後の移行に関する通知Teams](../media/teams-upgrade-notification.png)

すぐに Teams にアップグレードされる予定のオンプレミス ユーザーに通知するには、NotifySfBUsers=true を使用して TeamsUpgradePolicy の新しいインスタンスを作成します。 次に、ポリシーをユーザーに直接割り当てるか、サイト、プール、またはグローバル レベルでポリシーを設定して、通知するユーザーにポリシーを割り当てる。 次のコマンドレットは、ユーザー レベルのポリシーを作成して付与します。

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Teams Win32 クライアントSkype for Businessの自動ダウンロードは、DownloadTeams パラメーターを使用して、オンプレミスの TeamsUpgradeConfiguration コマンドレットを介して制御されます。 この構成は、グローバル レベル、サイト レベル、およびプール レベルで作成します。 たとえば、次のコマンドは、サイト Redmond1 の構成を作成します。

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
