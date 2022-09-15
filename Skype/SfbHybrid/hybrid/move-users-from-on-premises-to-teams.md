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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.custom: ''
description: '概要: ユーザー設定を移行し、ユーザーを Teams に移動する方法について説明します。'
ms.openlocfilehash: d29fa49e3521e93cb1818c70adb37cfb5019660b
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2022
ms.locfileid: "67705846"
---
# <a name="move-users-from-on-premises-to-teams"></a>オンプレミスから Teams にユーザーを移動する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

ユーザーをオンプレミスから Teams のみに移動すると、ユーザーのSkype for Businessホームがオンプレミスからオンラインに移動され、ユーザーには mode=TeamsOnly を使用して TeamsUpgradePolicy が割り当てられます。  ユーザーをオンプレミスから TeamsOnly モードに移動した後：

- 他のユーザーからのすべての着信通話とチャット (Skype for Business または Teams から送信された場合) は、ユーザーの Teams クライアントに着信します。
- ユーザーは、Skype for Business を使用する他のユーザーと相互運用が可能になります(オンラインでもオンプレミスでも)。
- ユーザーはフェデレーション組織のユーザーと通信が可能になります。
- そのユーザーによってスケジュールされた新しい会議は、Teams 会議です。
- ユーザーは引き続き Skype for Business 会議に参加できます。 ただし、2022 年 10 月以降、ハイブリッド組織の TeamsOnly ユーザーは匿名で会議に参加Skype for Businessのみ可能になります。 詳細については、「 [退職後の予定」を](/microsoftteams/skype-for-business-online-retirement#what-to-expect-post-retirement)参照してください。
- 将来予定されているユーザーの既存の会議は、オンプレミスから Teams に移行されます。
- オンプレミスに存在していた連絡先は、ユーザーが初めてログオンした直後に、Teams で利用できます。
- ユーザーは、Skype for Businessから通話やチャットを開始したり、Skype for Businessで新しい会議をスケジュールしたりすることはできません。 Skype for Business クライアントを開こうとすると、次に示すように Teams を使用するようにリダイレクトされます。 Teams クライアントがインストールされていない場合は、ブラウザーを使用して Teams の Web バージョンに移動します。<br><br>
    ![Teams にユーザーをリダイレクトするメッセージ。](../media/go-to-teams-page.png)

ユーザーを移動する前に、ユーザーをクラウドに移動するための [前提条件](move-users-between-on-premises-and-cloud.md#prerequisites) を確認してください。 また、[Teams とSkype for Businessを組み合わせて使用する組織の移行と相互運用性に関するガイダンス](/microsoftteams/migration-interop-guidance-for-teams-with-skype)も確認してください。


> [!NOTE]
> 連絡先を Teams に移動するには、オンプレミスの SfB アカウントで統合連絡先ストアを無効にする必要があります。

> [!IMPORTANT]
>
> - Move-CsUser を使用してユーザーをオンプレミスからクラウドに移動すると、ユーザーには TeamsOnly モードが自動的に割り当てられ、スイッチが実際に指定されているかどうか `-MoveToTeams` に関係なく、オンプレミスからの会議は Teams 会議に自動的に変換されます。 (これには、切り替えがなかった Lync Server 2013 からの移行も`-MoveToTeams`含まれます)。 以前は、このスイッチが指定されていない場合、ユーザーはオンプレミスSkype for Business Serverホームから Skype for Business Online に移行し、モードは変更されませんでした。 これは、Skype for Business Online の廃止に備えて変更されました。
> - オンプレミスの展開と Teams の間でユーザーを移動するには、Skype for Business Online レガシ インフラストラクチャに依存しなくなった、Skype for Business Serverまたは Lync Server のいずれかのオンプレミス コンポーネントの最小バージョンを更新する *必要* があります。 詳細については、「 [前提条件」を参照してください](move-users-between-on-premises-and-cloud.md#prerequisites)。

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>ユーザーをオンプレミスのSkype for Businessから Teams のみに直接移動する

Skype for Business Serverおよび Lync Server 2013 のオンプレミス管理ツールを使用すると、次に示すように、PowerShell またはSkype for Business Server コントロール パネルのMove-CsUserコマンドレットを使用して、1 つの手順でユーザーをオンプレミスから TeamsOnly モードに移行できます。 どのバージョンのSkype for Business Serverまたは Lync Server が使用されているかに関係なく、スイッチを指定`-MoveToTeams`する必要はなくなりました。また、オンプレミスから Teams のみに直接移動する動作は自動になりました。 

必要[な管理者資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)の説明に従って、オンプレミス環境とクラウド サービス (Microsoft 365 またはOffice 365) の両方で十分な特権を持っている必要があります。 両方の環境で特権を持つ 1 つのアカウントを使用するか、オンプレミスの資格情報を使用してオンプレミス Skype for Business Server管理シェル ウィンドウを開始し、このパラメーターを`-Credential`使用して、必要な管理ロールを持つ Microsoft 365 の資格情報を指定できます。

さらに、(Skype for Business Online に加えて) ユーザーに Teams のライセンスが付与されていることを確認する必要があります。 Skype for Business Online ライセンスを無効にしないでください。

### <a name="move-to-teams-using-move-csuser"></a>Move-CsUserを使用してTeamsに移動する

Move-CsUserは、オンプレミス Skype for Business ServerManagement Shell PowerShell ウィンドウまたは Lync Server Management Shell PowerShell ウィンドウから連絡可能です。 Move-CsUser を使用して TeamsOnly モードにユーザーを移動するには:
- パラメーターを使用して移動するユーザーを `Identity` 指定します。
- `-Target`値 "sipfed.online.lync" でパラメーターを指定します。<span>com" (テナントが政府機関のクラウドの場合は同様の値)。
- オンプレミスとクラウド サービス (Microsoft 365) の両方に十分なアクセス許可を持つアカウントが 1 つもない場合は、このパラメーターを `-credential` 使用して、Microsoft 365 で十分なアクセス許可を持つアカウントを指定します。
- Microsoft 365 のアクセス許可を持つアカウントが "onmicrosoft.<span>com": 必須[の管理資格情報](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)に関する`-HostedMigrationOverrideUrl`説明に従って、パラメーターを正しい値で指定する必要があります。
- オンプレミス管理ツールを実行しているコンピューターが、お使いのバージョンの Skype for Business Server または Lync Server 2013 に対して最新の CU を使用していることを確認し、OAuth が認証に使用されていることを確認します。 

次のコマンドレット シーケンスは、ユーザーを TeamsOnly に移動するために使用でき、Microsoft 365 資格情報が別のアカウントであり、Get-Credential プロンプトの入力として提供されることを前提としています。 スイッチが指定されているかどうか `-MoveToTeams` は、動作は同じです。

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> さまざまなパラメーターを必要とする状況が異なるため、ほとんどの場合の既定のコマンドは次のとおりです。

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロール パネルを使用してTeamsに移動する

1. Skype for Business Server コントロール パネル アプリを開きます。
2. 左側のナビゲーションで、[ユーザー] を選択 **します**。
3. **検索** を使用して、Teamsに移動させたいユーザーを見つけます。
4. ユーザーを選択し、一覧の上にある **[ アクション]** ドロップダウンから **選択したユーザーを Teams に移動する** か **選択したユーザーを Skype for Business Skype for Businessに移動するかを選択します**。   どちらのオプションでも、ユーザーをTeamsOnly に直接移動できるようになりました。
5. ウィザードで、[ **次へ**] をクリックします。
6. メッセージが表示されたら、.onmicrosoft.com で終わり、十分なアクセス許可を持つアカウントでMicrosoft 365にサインインします。
7. **[次へ]** をクリックし、もう一度 **[次へ]** をクリックしてユーザーを移動します。
8. 成功または失敗に関する状態 メッセージは、ウィザードではなく、メイン コントロール パネル アプリの上部に表示されます。
    
    
## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Skype for Businessオンプレミス ユーザーに Teams への移行を通知する

2015 Skype for Business Server CU8 および 2019 Skype for Business Serverのオンプレミス管理ツールを使用すると、オンプレミスのSkype for Businessユーザーに Teams への移行を通知できます。 これらの通知を有効にすると、ユーザーのSkype for Business クライアント (Win32、Mac、Web、モバイル) に次のように通知が表示されます。 ユーザーが [ **試してみる** ] ボタンをクリックすると、Teams クライアントがインストールされている場合は起動されます。それ以外の場合、ユーザーはブラウザーで Web バージョンの Teams に移動されます。 既定では、通知が有効になっている場合、Win32 Skype for Business クライアントは、ユーザーを TeamsOnly モードに移行する前にリッチ クライアントを使用できるように、クライアントが自動的に Teams クライアントをダウンロードします。 ただし、この動作を無効にすることもできます。  通知はオンプレミス バージョンの `TeamsUpgradePolicy`バージョンを使用して構成され、Win32 クライアントのサイレント ダウンロードはオンプレミス `TeamsUpgradeConfiguration` コマンドレットを使用して制御されます。


![Teams への今後の移行の通知。](../media/teams-upgrade-notification.png)

間もなく Teams にアップグレードされることをオンプレミスのユーザーに通知するには、NotifySfBUsers=true を使用して TeamsUpgradePolicy の新しいインスタンスを作成します。 次に、ポリシーをユーザーに直接割り当てるか、サイト、プール、またはグローバル レベルでポリシーを設定して、通知するユーザーにそのポリシーを割り当てます。 次のコマンドレットは、ユーザー レベルのポリシーを作成して付与します。

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Skype for Business Win32 クライアントを使用した Teams の自動ダウンロードは、DownloadTeams パラメーターを使用してオンプレミスの TeamsUpgradeConfiguration コマンドレットを使用して制御されます。 この構成は、グローバル、サイト、プール レベルで作成します。 たとえば、次のコマンドを実行すると、サイト Redmond1 の構成が作成されます。

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

既定では、DownloadTeams の値は True です。ただし、特定のユーザーに対して NotifySfbUser = True の場合 *にのみ* 適用されます。

## <a name="see-also"></a>関連項目

[Move-CsUser](/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy
)

[Teams を Skype for Business と一緒に使用する組織向けの移行と相互運用に関するガイダンス](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Skype for Business と共存する](/microsoftteams/coexistence-chat-calls-presence)
