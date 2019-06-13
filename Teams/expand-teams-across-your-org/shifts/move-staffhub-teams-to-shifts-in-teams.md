---
title: StaffHub チーム を Microsoft Teams のシフトに移動する
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub のチームとスケジュール データを Microsoft Teams のシフトに移動する方法を説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780810"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Microsoft StaffHub のチームを Microsoft Teams のシフトに移動する

> [!IMPORTANT]
> 2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。 Microsoft では、StaffHub の機能を Microsoft Teams に組み込む作業に取り組んでいます。 現在、Teams にはシフト アプリのスケジュール管理機能が含まれています。今後、他の機能もロールアウトされる予定です。 StaffHub は、2019 年 10 月 1 日以降すべてのユーザーがご利用できなくなります。 ユーザーが StaffHub を開くと、Teams をダウンロードするように求めるメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。

Teams 内のシフト アプリでは、スケジュール管理と日ごと常に発生し続けるシフトの入れ替えや取り消しのための簡単なアプローチが提供されます。 チーム メンバーはアプリを使用して複数のデバイスからスケジュールやシフトの情報に直接アクセスでき、基本設定、スケジュール管理、休暇の申請などの操作を行えます。

この記事では、組織の StaffHub のチームとスケジュール データを Teams 内のシフトに移動させる方法について説明します。 取り扱う内容:

- [Teams への移行について知っておくべき事項](#what-you-need-to-know-about-the-move-to-teams)
- [準備](#prepare)
- [パイロットの実施](#conduct-a-pilot) 
- [パイロットを終了しすべての StaffHub チームを移動する](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [Teams の使用状況の監視](#monitor-teams-usage)
- [トラブルシューティング](#troubleshooting)

この管理者向けガイダンスには Teams への移行を成功させるために必要な情報が含まれ、少数の StaffHub チームを運用する小規模な事業のお客様にも、StaffHub チームが何百もある大企業のお客様にもご利用いただけます。

この記事の手順を実行するには、全体管理者である必要があります。 「[StaffHub の廃止に関するよくあるご質問](microsoft-staffhub-to-be-retired.md)」をまだご覧になられていない場合はご覧いただき、不明点に関する答えをご確認ください。

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Teams への移行について知っておくべき事項

### <a name="when-to-move-to-teams"></a>Teams に移行する時期

2019 年 10 月 1 日より、StaffHub が廃止されます。 Teams の使用を今から開始し、組織のチームとユーザーの StaffHub からの移行を開始することをお勧めします。 StaffHub で最もよく使用される機能はスケジュール管理であるため、今後は Teams 内のシフト アプリを使用されることをお勧めします。

### <a name="what-is-moved-to-teams"></a>Teams に移動する内容

Teams に移動されるのは、ユーザーの詳細情報、スケジュール情報、チャットおよびファイルのデータです。 これには、チーム メンバーシップ、チーム スケジュール、および過去 90 日間のチャットとファイルが含まれます。

各 StaffHub チームには、対応する Office 365 グループが必要です。 StaffHub チームに Office 365 グループが関連付けられていない場合は、移行を支援するために自動的にグループが作成されます。 Teams と StaffHub ではチームとグループの名前の付け方に違いがあるため、Teams ではチーム名が異なる場合があります。

チームを StaffHub から Teams に移動すると、ユーザーは StaffHub のスケジュールにはアクセスできなくなり、Teams 内のシフトにリダイレクトされます。 中断を最小限に抑え、Teams の導入をユーザーに促すために、この変更について組織全体に伝達することをお勧めします。 Azure AD Premium を使用している場合は、[レポートを実行](run-report-to-show-staffhub-usage.md)して、組織の StaffHub ユーザーのうち、この変更について知っておく必要があるユーザーのリストを取得できます。  

StaffHub チームを Teams に移動した後は、それをロールバックするオプションはありません。

### <a name="user-experience-when-you-move-a-team"></a>チームを移動するときのユーザー エクスペリエンス

StaffHub から Teams 内のシフトにチームが切り替えられる際のユーザーのダウンタイムは、ほんのわずかです (あったとしても、1 秒未満です)。 ユーザーは、Teams への移行が完了するまで StaffHub を引き続き使用できます。 移行が完了すると、チームのスケジュールにアクセスするには Teams 内のシフトの使用を開始する必要があることを通知するメッセージがユーザーに表示されます。 StaffHub チームが Teams に移行した後に StaffHub でユーザーに表示されるメッセージの例です。

![ユーザーに表示されるメッセージの例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "StaffHub チームが Teams に移行した後に StaffHub でユーザーに表示されるメッセージの例")

## <a name="prepare"></a>準備

Teams に移動するための準備を行う方法について説明します。

### <a name="check-that-prerequisites-are-met"></a>前提条件を満たしていることを確認する

StaffHub チームを Teams に移動する前に、次のことを確認します。

- サインインしているユーザーが全体管理者であること。
- Teams がテナント内のすべてのユーザーに対して有効化されていること。
- Office 365 グループの作成がテナントで有効になっていること。
- StaffHub の teamId が有効であること。
- StaffHub チームにメンバーが含まれていること。 
- すべての StaffHub チーム メンバーが、Azure AD アカウントにリンクされていること。 

これらの前提条件を満たしていない場合、移動要求は失敗します。 

### <a name="assign-teams-licenses"></a>Teams のライセンスを割り当てる

各ユーザーは、[対象プラン](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)の有効な Microsoft 365 または Office 365 ライセンスを持っている必要があり、Teams ライセンスが割り当てられている必要があります。 Teams ライセンスを割り当てられたユーザーは Teams にアクセスできるようになります。

Teams ライセンスの管理は、Microsoft 365 管理センターで行います。 詳細については、「[Microsoft Teams へのユーザー アクセスを管理する](../../user-access.md)」をご覧ください。

> [!NOTE]
> Skype for Business を使用している組織ですべてのユーザーを Teams に移行する準備ができていない場合は、現場担当者に対して Teams を有効にし、これらのユーザーが Teams を Skype for Business と併用できるようにします。 「*アイランド*」と呼ばれるこの共存モードでは、各クライアント アプリが別個のソリューションとして動作します。 詳細については、「[Microsoft Teams と Skype for Business の共存と相互運用性について](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)」を参照してください。

### <a name="install-the-staffhub-powershell-module"></a>StaffHub PowerShell モジュールをインストールする

[StaffHub PowerShell モジュールのインストールがまだの場合は、インストールします](install-the-staffhub-powershell-module.md)。 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Azure AD の ID を持たない StaffHub ユーザーのアカウントをプロビジョニングする

各マネージャーとチームメンバーは、Azure Active Directory (Azure AD) で ID を持っている必要があります。 ユーザーが Azure AD で ID を持っていない場合は、アカウントをプロビジョニングします。 これを行うには、次の操作を実行します。 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a>Azure AD アカウントがプロビジョニングされていないチーム メンバーが所属する StaffHub チーム内のすべてのユーザーのリストを取得する

次のコマンドを実行します。
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a>アカウントをプロビジョニングする

次のいずれかの操作を行います。

- アカウントを、プロビジョニングされたアカウントに変換してリンクします。

  StaffHub チームの所有者と管理者は、StaffHub チーム設定ページでユーザーのメールアドレスを有効な UPN に変更することで、ダミーまたは非アクティブなアカウントを変換して、プロビジョニングされた StaffHub のアカウントにリンクできます。

- プロビジョニングされていないアカウントを削除し、UPN を使用してアカウントを追加し直します。
    1. [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) コマンドレットを実行して、StaffHub チームからプロビジョニングされていないアカウントを削除します。
    2. [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) コマンドレットを実行し、UPN を使用して StaffHub チームにアカウントを追加し直します。 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>FirstLineWorker アプリのセットアップ ポリシーをユーザーに割り当てる

Teams には、組織の現場担当者にとって最も重要なアプリをハイライトするために Teams をカスタマイズするのに使用できる、FirstlineWorker アプリ セットアップ ポリシーが組み込まれています。 このポリシーをユーザーに割り当てると、すばやく簡単にアクセスできるよう、ポリシー内のアプリがチームのアプリ バーに固定されます。 Teams に追加された他のアプリは、Teams のデスクトップと Web クライアントで [**その他のアプリ**] をクリックすると表示されます。Teams モバイル クライアントの場合は、上方向にスワイプします。 既定では、FirstlineWorker アプリのセットアップ ポリシーには、アクティビティ、シフト、チャット、および通話の各アプリが含まれています。

FirstlineWorker アプリのセットアップ ポリシーをユーザーに割り当てる手順については、「[FirstlineWorker アプリのセットアップ ポリシーを使用して Teams にシフトをピン留めする](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams)」を参照してください。 ポリシーの割り当て後、それが有効になるまで最大 24 時間かかる場合があります。

StaffHub のチームとユーザーを Teams に移動する少なくとも 1 週間前までにこの手順を完了しておくことをお勧めします。 ユーザーが Teams にサインインしたら、シフト アプリがユーザーに表示され、アクセスできることを確認します。

また、アプリのカスタム セットアップ ポリシーを作成し、アプリのグローバル セットアップ ポリシーでその設定を編集することもできます。 詳細については、「[Teams アプリのセットアップ ポリシーを管理する](../../teams-app-setup-policies.md)」を参照してください。

### <a name="onboard-users-to-teams"></a>Teams にユーザーをオンボードする

オンボードディング戦略の一環として、ユーザーが Teams を理解できるよう、トレーニングとガイダンスをユーザーに提供します。 Teams のクライアントの入手先やトレーニングおよびサポートを受けられる場所がわかるように、次のリソースをユーザーと共有します。

- [Teams の Web クライアント](https://teams.microsoft.com)
- [デスクトップとモバイル クライアントのダウンロード リンク](https://teams.microsoft.com/downloads)
- [Teams のトレーニング用ビデオ](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Teams のヘルプ ドキュメント](https://support.office.com/teams)

Teams の展開と Teams の導入推進に関するガイダンスは、「[Microsoft Teams の展開方法](../../How-to-roll-out-teams.md)」および「[Microsoft Teams を導入する](../../adopt-microsoft-teams-landing-page.md)」を参照してください。

## <a name="conduct-a-pilot"></a>パイロットの実施

早期導入者の限られたグループとして、手始めに 2 つか 3 つの StaffHub チームの移行を行うことをお勧めします。 パイロットの実施により、移行計画を微調整し、組織のすべての StaffHub チームをチームに移行する準備を整えられます。 また、先導役となるユーザーを特定して、組織全体での導入の促進につなげることもできます。 小規模なビジネスであるために段階的な手法を必要としない場合、StaffHub から Teams への切り替えに必要な手順は、すべてこのセクションで説明されている可能性があります。

### <a name="identify-pilot-teams"></a>パイロット チームの特定

パイロット チームを特定するためにユーザーに連絡をとります。 スケジュールの管理やチーム内での連絡と共同作業に Teams 内のシフトを使用することに、チーム メンバー全員がコミットする必要があります。

### <a name="identify-team-champions"></a>Teams の先導者の特定

パイロット チームの中で先導者を特定し、シフトを普及させるための協力を依頼します。 Teams の先導者は、業務に熱心に取り組み、自身の知見をチーム メンバーと共有してサポートやガイダンスを提供できるユーザーたちです。 Teams の先導者には、チームの所有者またはマネージャーがなれます。

すべてのユーザーが [Teams のクライアントを入手](../../get-clients.md)し、Teams にサインインして自分のスケジュールをシフトでチェックし、他のメンバーとチャットを開始できるよう、Teams の先導者はチーム メンバーの設定が行われていることをしっかり時間をかけて確認する必要があります。 StaffHub に慣れているユーザーは、シフトをすばやく稼働させられます。 追加のヘルプが必要なユーザーには、「[シフトのヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)」を参照するよう伝えることもできます。

### <a name="move-a-staffhub-team"></a>特定のStaffHub チームを移動する

これらの手順を使用して、一度に 1 チームずつ StaffHub チームを移動します。 このアプローチをパイロット チームについて使用することをお勧めします。 後に、組織のすべての StaffHub チームを移動する準備ができた場合は、一度に複数のチームを移動させる手順ついて、「[StaffHub チームを移動する](#move-your-staffhub-teams)」を参照してください。

StaffHub チームを移動するには、次を実行します。

```
Move-StaffHubTeam -TeamId <String>
```
例:

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

StaffHub チームを Teams に移動する要求を送信した際に返される応答の例です。

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

移動要求の状態を確認するには、次を実行します。

```
Get-TeamMigrationJobStatus <String>
```
例:

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

移動の進行中に返される応答の例です。

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>StaffHub チームから Teams にファイルを移動する

この手順は、Teams に移動する StaffHub チームが、やはり Teams に移動させたいファイルを持っている場合にのみ適用されます。 ファイルは SharePoint Online 内で直接移動する方法でも、PowerShell を使用する方法でも移動できます。 

#### <a name="in-sharepoint-online"></a>SharePoint Online 内で行う場合

「[SharePoint Online でファイルを移動する方法](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30)」を参照してください。

#### <a name="using-powershell"></a>PowerShell を使用する場合

まだの場合、[SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588) をダウンロードしてインストールしてください。 ファイルを移動するために必要なコマンドレットが含まれています。  

[Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) コマンドレットを使用して、SharePoint Online チームサイトに接続します。

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

StaffHub から Teams に移動する各ファイルに対して [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) コマンドレットを使用してファイルを移動します。

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

複数のファイルを移動するには、ファイルをループして、ループに対して 2 つ目のコマンドを実行します。 セッションがアクティブなままの場合は、最初のコマンドを繰り返す必要はありません。

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>パイロットを終了しすべての StaffHub チームを移動する

### <a name="raise-awareness"></a>認知度を上げる

パイロット チームの移動を終了し組織の StaffHub チームをチームに移行する準備ができた場合は、変更について組織全体に通知することが重要です。 シフトと Teams への移行に関する情報を広めて認知度を上げ、期待感を高めることによって導入の促進を図ります。

### <a name="move-your-staffhub-teams"></a>StaffHub チームを移動する

これらの手順を使用して、StaffHub チームを一括移動します。 組織のすべての StaffHub チームを移動する方法も、特定の StaffHub チームを移動する方法も選べます。 StaffHub チームを1つずつ移動する場合は、「[StaffHub チームを移動する](#move-a-staffhub-team)」を参照してください。

#### <a name="move-all-staffhub-teams"></a>すべての StaffHub チームを移動する

次を実行して、組織内のすべての StaffHub チームのリストを取得します。

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

次を実行してすべてのチームを移動します。

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

応答の例を下に示します。

既に Teams に移動されたか既に Teams に存在するチームの場合、そうしたチームを移動するためのジョブを送信する必要がないため、jobId は "null" になります。

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>特定の StaffHub チームを移動する

次を実行して、組織内のすべての StaffHub チームの ID のリストを取得します。

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

先ほど実行した `Get-StaffHubteamsForTenant` コマンドレットによって返された結果で移動するチーム ID を選択し、コンマ区切り値 (CSV) ファイルに追加します。

CSV ファイルで必要な書式設定の例を次に示します。

|ID  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

CSV ファイルを作成したら、次のコマンドを実行して CSV ファイルで指定したチームを移動します。

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>StaffHub チームが Teams に移動したことを確認する

次を実行して、組織内のすべてのシフトのチームのリストを取得します。 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>StaffHub チームから Teams にファイルを移動する

移動した StaffHub チームに Teams に移動するファイルが含まれている場合は、「[StaffHub チームから Teams にファイルを移動する](#move-files-from-a-staffhub-team-to-teams)」を参照してください。

## <a name="monitor-teams-usage"></a>Teams の使用状況の監視

使用状況レポートは、使用パターンを正しく理解するために役立ち、組織全体でのトレーニングとコミュニケーションの取り組みに関する優先順位を決定するのに活用できる見識を提供します。 シフトは Teams 内のアプリであるため、その使用状況は Teams のレポート上で確認できます。 詳細については、「[Microsoft Teams 管理センターでの Teams のレポート](../../teams-analytics-and-reports/teams-reporting-reference.md) 」および「[Microsoft 365 管理センターでの Teams のアクティビティ レポート](../../teams-activity-reports.md)」を参照してください。

## <a name="troubleshooting"></a>トラブルシューティング 

**StaffHub から Teams にファイルを移動しようとすると、"アクセスは拒否されました" というエラー メッセージが表示されます。**

これは、自分がメンバーでないプライベートの Office 365 グループ内のファイルを移動しようとした場合に発生することがあります。 該当する場合は、[AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) コマンドレットを使用して自分自身を StaffHub チームに追加してからファイルを移動します。 ファイルの移動後は、[Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) コマンドレットを使用して、チームから自分自身を削除します。 

**StaffHub から Teams にファイルを移動しようとすると、[全般] フォルダーが存在しないというエラーが表示されます。**

次のコマンドを実行して [全般] フォルダーを SharePoint に追加してから、もう一度お試しください。

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>関連項目
- [Microsoft Teams の展開方法](../../How-to-roll-out-teams.md)
- [Microsoft StaffHub はまもなく廃止予定です](microsoft-staffhub-to-be-retired.md)
- [Microsoft Teams で組織のシフト アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
