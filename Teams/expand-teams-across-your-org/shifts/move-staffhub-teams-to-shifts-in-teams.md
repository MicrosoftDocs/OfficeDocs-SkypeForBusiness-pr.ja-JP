---
title: 'StaffHub teams を Microsoft Teams の Shifts に移動する '
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub teams を移動して、Microsoft Teams のシフトにデータをスケジュールする方法について説明します。
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cef8c6fbfd5ed0b19d6762b7508b311413d11066
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233285"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Microsoft Teams で Microsoft StaffHub teams をシフトに移行する

> [!IMPORTANT]
> 2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。 Microsoft Teams で StaffHub 機能を構築しています。 現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。 2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。 StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。

Teams のシフトアプリは、スケジュールを管理するための簡単なアプローチを提供します。また、1日のうちに発生するシフト交換とキャンセルの流れを定期的に行うことができます。 チームメンバーは、アプリやデバイス間で直接、スケジュールとシフト情報にアクセスして、ユーザー設定の設定、スケジュールの管理、休暇のリクエストを行うことができます。

この記事では、組織の StaffHub teams を移動して、チーム内のシフトにデータをスケジュールする方法について説明します。 次の内容について説明します。

- [Teams への移行について知っておくべきこと](#what-you-need-to-know-about-the-move-to-teams)
- [備える](#prepare)
- [パイロットの実施](#conduct-a-pilot) 
- [パイロット以外の場所に移動して、すべての StaffHub teams を移動する](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [チームの利用状況を監視する](#monitor-teams-usage)
- [トラブルシューティング](#troubleshooting)

1人または2人の StaffHub チームを持つ小規模企業でも、数百人の StaffHub teams を持つ大企業でも、チームへの移行を成功させるために必要な管理ガイダンスが記載されています。

この記事の手順を実行するには、グローバル管理者である必要があります。 まだインストールしていない場合は、 [StaffHub 定年](microsoft-staffhub-to-be-retired.md)に関する faq を参照して、お客様からの質問に回答してください。

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Teams への移行について知っておくべきこと

### <a name="when-to-move-to-teams"></a>Teams に移動する場合

2019年10月1日、StaffHub は廃止されます。 今すぐ Teams の使用を開始して、組織のチームとユーザーを StaffHub から移行することをお勧めします。 StaffHub でスケジュール管理が最も一般的に使用される機能である場合は、チームでのシフトアプリの使用を進めることをお勧めします。

### <a name="what-is-moved-to-teams"></a>Teams に移動されるもの

StaffHub チームを移動すると、チームメンバーシップ、ユーザーの詳細、チームのスケジュール、チャットデータが Teams に移動します。 StaffHub チームを移動すると、ファイルが移動されません。 StaffHub チームに、teams にも移動するファイルが含まれている場合は、ファイルを別の手順で移動します。

すべての StaffHub チームには、対応する Office 365 グループが必要です。 StaffHub チームに Office 365 グループが関連付けられていない場合は、移行をサポートするために、1つが自動的に作成されます。 Teams と StaffHub の間でのチームとグループの名前の違いにより、Teams に異なるチーム名が表示されることがあります。

チームを StaffHub から Teams に移行すると、ユーザーは StaffHub のスケジュールにアクセスできなくなり、Teams のシフトにリダイレクトされます。 この変更を組織全体で伝達することをお勧めします。中断を最小限に抑え、ユーザーにチームの採用と検討を促します。 Azure AD Premium を使用している場合は、[レポートを実行](run-report-to-show-staffhub-usage.md)して、この変更について知っておく必要がある、組織内の StaffHub ユーザーの一覧を取得できます。  

StaffHub チームを Teams に移動しても、ロールバックオプションはありません。

### <a name="user-experience-when-you-move-a-team"></a>チームを移動するときのユーザーエクスペリエンス

チームの StaffHub からシフトへの切り替えが発生した場合、ユーザーに対してダウンタイム (1 秒未満) が最小限に抑えられます。 チームへの移動が完了するまで、ユーザーは StaffHub を引き続き使用することができます。 移動が完了すると、チームメンバーにメッセージが表示され、チームのスケジュールにアクセスするためにチームのシフトの使用を開始する必要があることがわかります。 ここでは、StaffHub チームが Teams に移動した後に StaffHub に表示されるメッセージの例を示します。

![ユーザーに表示されるメッセージの例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "StaffHub チームが Teams に移動した後に StaffHub に表示されるメッセージの例")

## <a name="prepare"></a>備える

ここでは、Teams への移行を準備する方法について説明します。

### <a name="check-that-prerequisites-are-met"></a>前提条件が満たされていることを確認する

StaffHub チームを Teams に移動する前に、次のことを確認してください。

- サインインしたユーザーはグローバル管理者です。
- チームは、テナント内のすべてのユーザーに対して有効になっています。
- テナントで Office 365 グループの作成が有効になっています。
- StaffHub teamId が有効です。
- StaffHub チームにはメンバーが含まれています。
- すべての StaffHub チームメンバーは、Azure AD アカウントにリンクされています。

これらの前提条件が満たされない場合、移動要求は失敗します。

### <a name="assign-teams-licenses"></a>Teams のライセンスを割り当てる

各ユーザーは、ライセンス付与された有効な Microsoft 365 [](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)または Office 365 ライセンスを所有している必要があります。また、Teams ライセンスを割り当てる必要があります。 Teams ライセンスをユーザーに割り当てると、チームにアクセスできます。

Teams のライセンスは、Microsoft 365 管理センターで管理します。 詳細については、「[チームへのユーザーアクセスを管理](../../user-access.md)する」を参照してください。

> [!NOTE]
> 組織で Skype for Business を使用していて、すべてのユーザーをチームに移行する準備ができていない場合は、最初に Skype for Business を使用してチームを実行できるようにすることができます。 この共存モード (*孤島*) では、各クライアントアプリは個別のソリューションとして動作します。 詳細については、「[チームと Skype For business の共存と相互運用性につい](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)て」を参照してください。

### <a name="install-the-staffhub-powershell-module"></a>StaffHub PowerShell モジュールをインストールする

まだインストールしていない場合は、 [StaffHub PowerShell モジュールをインストール](install-the-staffhub-powershell-module.md)します。 

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a>StaffHub チームメンバーがない場合に、Azure AD アカウントをリンクさせる

各 StaffHub チームメンバーは、Azure Active Directory (Azure AD) アカウントにリンクされている必要があります。 次のシナリオのいずれかが適用されている場合、組織内のユーザーは Azure AD アカウントにリンクされません。

- チーム所有者が、Azure AD アカウントを持っていないユーザーを追加しました。
- チーム所有者が、ユーザーを StaffHub チームに招待し、そのユーザーが招待を承諾しなかった。

これらのユーザーに Azure AD アカウントをリンクさせることができます。  これを行うには、次の操作を実行します。

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-linked-to-an-azure-ad-account"></a>Azure AD アカウントにリンクされていないチームメンバーを持つ StaffHub teams 上のすべてのユーザーの一覧を取得する

次のコマンドを実行します。
```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="link-the-account"></a>アカウントをリンクする

次のいずれかの操作を行います。

- アカウントを変換してリンクします。

  StaffHub チーム所有者と管理者は、ユーザーのメールアドレスを StaffHub チームの設定ページで有効な UPN に変更することによって、非アクティブなアカウントを変換し、StaffHub の Azure AD アカウントにリンクすることができます。

- リンクされていないアカウントを削除し、UPN を使用してアカウントをもう一度追加します。
    1. StaffHub チームからプロビジョニングされていないアカウントを削除するには、 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps)コマンドレットを実行します。
    2. UPN を使用して StaffHub チームにアカウントを戻すには、 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps)コマンドレットを実行します。

- リンクされていないユーザーアカウントを削除します。 このオプションを使用すると、ユーザーアカウントは不要になります。

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>FirstlineWorker アプリのセットアップポリシーをユーザーに割り当てる

Teams には、組織内の最初の社員にとって最も重要なアプリを強調表示するために、チームをカスタマイズするために使用できる、標準の Lineworker アプリのセットアップポリシーが用意されています。 このポリシーをユーザーに割り当てると、ポリシーに含まれるアプリが、すばやく簡単にアクセスできるように Teams のアプリバーに固定されます。 他のチームに追加されたアプリは、[...] をクリックしてアプリバーに表示されます。 **** Teams のデスクトップと web クライアントでのアプリの増加、および teams のモバイルクライアントでの追加アプリ。 既定では、FirstlineWorker アプリのセットアップポリシーには、アクティビティ、シフト、チャット、通話アプリが含まれます。

FirstlineWorker アプリのセットアップポリシーをユーザーに割り当てる手順については、「 [firstlineworker アプリのセットアップポリシーを使用してチームへのシフトを固定](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)する」を参照してください。 ポリシーを割り当てた後は、最長24時間かかる場合があります。

StaffHub teams とユーザーを Teams に移行する前に、少なくとも1週間以上この手順を実行することをお勧めします。 ユーザーが Teams を使用している場合は、シフトアプリを表示してアクセスできることを確認します。

また、カスタムアプリセットアップポリシーを作成して、グローバルアプリセットアップポリシーの設定を編集することもできます。 詳細については、「[Teams でアプリの設定ポリシーを管理する](../../teams-app-setup-policies.md)」を確認してください。

### <a name="onboard-users-to-teams"></a>チームへのオンボードユーザー

オンボード戦略の一環として、チームに慣れてもらうためのトレーニングとガイダンスをユーザーに提供します。 次のリソースをユーザーと共有して、チームのクライアント、トレーニング、サポートを取得する場所を確認します。

- [Teams の Web クライアント](https://teams.microsoft.com)
- [デスクトップとモバイル クライアントのダウンロード リンク](https://teams.microsoft.com/downloads)
- [Teams のトレーニング用ビデオ](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Teams のヘルプ ドキュメント](https://support.office.com/teams)

チームを展開してチームを導入するためのガイダンスについては、「チームをロールアウトして[チームを採用](../../adopt-microsoft-teams-landing-page.md)[する方法](../../How-to-roll-out-teams.md)」を参照してください。

## <a name="conduct-a-pilot"></a>パイロットの実施

最初に、2つまたは3つの StaffHub teams を、最早採用者のグループごとに移動することをお勧めします。 パイロットを実行すると、移行計画を調整して、組織のすべての StaffHub チームをチームに移行できるようになります。 また、組織全体での導入を促進できるエキスパートも特定します。 段階的アプローチを必要としない小規模企業の場合は、このセクションの手順に従って、StaffHub から Teams に切り替える必要があります。

### <a name="identify-pilot-teams"></a>パイロットチームの特定

パイロットチームの2つまたは3つを確認してください。 すべてのチームメンバーは、チームでシフトを使用して、スケジュールを管理し、相互に通信して共同作業を行う必要があります。

### <a name="identify-team-champions"></a>チームのチャンピオンの特定

パイロットチーム全体のチャンピオンを特定し、啓蒙シフトを支援するために参加します。 チームの支持者は、チームメンバーのサポートとガイダンスを提供するために、独自の高い知識を共有しています。 チームチャンピオンはチームの所有者または管理者になることができます。

チームのメンバーがチームの[クライアントを取得](../../get-clients.md)し、teams にサインインして、スケジュールをシフトで確認し、互いにチャットを開始するためには、チームメンバーが設定されていることを確認する必要があります。 すでに StaffHub に慣れているユーザーは、シフトですぐに稼動することになります。 その他のヘルプについては、[[シフトヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)] をポイントすることもできます。

### <a name="move-a-staffhub-team"></a>StaffHub チームを移動する

次の手順を使用して、一度に1つの StaffHub チームを移動します。 パイロットチームでは、この方法をお勧めします。 後で、組織のすべての StaffHub チームを移行する準備ができたら、「複数のチームを一度に移動する」の手順については、「 [StaffHub teams を移行](#move-your-staffhub-teams)する」を参照してください。

StaffHub チームを移動するには、次を実行します。

```
Move-StaffHubTeam -TeamId <String>
```
次

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

次に示すのは、StaffHub チームを Teams に移動する要求を送信するときに表示される応答の例です。

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

移動要求の状態を確認するには、次を実行します。

```
Get-TeamMigrationJobStatus <String>
```
次

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

次に示すのは、移動が進行中の場合に表示される応答の例です。

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>StaffHub チームから Teams にファイルを移動する

この手順は、Teams に移動した StaffHub チームが、Teams にも移動するファイルを持っている場合にのみ適用されます。 SharePoint Online または PowerShell を使用して、ファイルを直接移動できます。

#### <a name="in-sharepoint-online"></a>SharePoint Online の場合

[SharePoint Online でファイルを移動する方法に](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)ついて説明します。

#### <a name="using-powershell"></a>PowerShell を使用する

[SharePoint Online 管理シェル](https://www.microsoft.com/download/details.aspx?id=35588)をダウンロードしてインストールします (まだインストールしていない場合)。 ファイルを移動するために必要なコマンドレットが含まれています。  

[Connect-admin.sharepoint.com](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps)コマンドレットを使用して、SharePoint Online チームサイトに接続します。

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

StaffHub から Teams に移動する各ファイルについて、 [PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile)コマンドレットを使用してファイルを移動します。

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

複数のファイルを移動するには、ファイルをループして、ループの2番目のコマンドを実行します。 セッションがアクティブな場合は、最初のコマンドを繰り返す必要はありません。

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>パイロット以外の場所に移動して、すべての StaffHub teams を移動する

### <a name="raise-awareness"></a>認識を高める

パイロットチームを超えて組織の StaffHub チームをチームに移行する準備ができたら、まず組織全体で変更を伝えることが重要です。 シフトについての単語を広げ、チームへの切り替えを行って、認知度を上げ、興奮を生み出し、導入を推進します。

### <a name="move-your-staffhub-teams"></a>StaffHub teams を移動する

次の手順を使用して、StaffHub teams をまとめて移動します。 組織のすべての StaffHub チームを移動するか、または特定の StaffHub teams を移動するかを選ぶことができます。 StaffHub teams を1つずつ移動する方法については、「 [StaffHub チームを移行](#move-a-staffhub-team)する」を参照してください。

#### <a name="move-all-staffhub-teams"></a>すべての StaffHub teams を移動する

組織内のすべての StaffHub teams の一覧を取得するには、次を実行します。

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq ‘StaffHub’ }
```

次に、次のことを実行してすべてのチームを移動します。

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

応答の例を次に示します。

既に Teams に移動されているか、Teams に既に存在しているチームの場合は、そのチームに移動するためにジョブを送信する必要がないため、jobId は "null" になります。

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>特定の StaffHub チームを移動する

組織内のすべての StaffHub チーム Id の一覧を取得するには、次を実行します。

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

前に実行した`Get-StaffHubteamsForTenant`コマンドレットによって返された結果で、移動するチーム id を選択し、コンマ区切り値 (CSV) ファイルに追加します。

CSV ファイルを書式設定する方法の例を次に示します。

|Id  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

CSV ファイルを作成したら、CSV ファイルで指定したチームを移動するには、次のように実行します。

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>StaffHub teams が Teams に移行されたことを確認する

組織内のすべてのチームの一覧を取得するには、次の操作を実行します。 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>StaffHub teams から Teams にファイルを移動する

移動した StaffHub teams に、Teams にも移動するファイルが含まれている場合は、「 [StaffHub チームからチームにファイルを移動](#move-files-from-a-staffhub-team-to-teams)する」を参照してください。

## <a name="monitor-teams-usage"></a>チームの利用状況を監視する

利用状況レポートは、使用パターンをより理解しやすくするのに役立ちます。また、組織全体でトレーニングとコミュニケーション作業の優先順位を決定する場所について理解を深めます。 チーム全体の利用状況、ユーザーが Teams で実行するアクティビティの種類、ユーザーが Teams に接続する方法などのレポートを実行できます。 詳細については、microsoft [teams 管理センターのチームレポート](../../teams-analytics-and-reports/teams-reporting-reference.md)と、 [microsoft 365 管理センターの teams アクティビティレポート](../../teams-activity-reports.md)を参照してください。

## <a name="troubleshooting"></a>トラブルシューティング

**StaffHub から Teams にファイルを移動しようとすると、"アクセス許可は拒否されました" というエラーメッセージが表示されます。**

この問題は、自分がメンバーでないプライベートの Office 365 グループでファイルを移動しようとしている場合に発生することがあります。 この場合は、 [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember)コマンドレットを使用して StaffHub チームに自分を追加してから、ファイルを移動します。 ファイルを移動した後、 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember)コマンドレットを使用してチームから自分自身を削除します。 

**StaffHub から Teams にファイルを移動しようとすると、[全般] フォルダーが存在しないというエラーが表示されます。**

次のコマンドを実行して、[全般] フォルダーを SharePoint に追加してから、もう一度試してください。

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>関連トピック
- [Microsoft Teams の展開方法](../../How-to-roll-out-teams.md)
- [Microsoft StaffHub はまもなく廃止予定です](microsoft-staffhub-to-be-retired.md)
- [Microsoft Teams で組織のシフト アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell リファレンス](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
