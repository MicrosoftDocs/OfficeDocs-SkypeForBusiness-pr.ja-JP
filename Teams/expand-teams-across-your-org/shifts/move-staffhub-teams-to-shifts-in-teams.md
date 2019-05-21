---
title: 'StaffHub teams を Microsoft Teams の Shifts に移動する '
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Microsoft StaffHub teams を移動して、Microsoft Teams のシフトにデータをスケジュールする方法について説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74a9b23479f5357c0014ef5ef88b3f5da03ace7f
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865053"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Microsoft Teams で Microsoft StaffHub teams をシフトに移行する

> [!IMPORTANT]
> 2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。 Microsoft Teams で StaffHub 機能を構築しています。 現在、チームには、スケジュール管理のためのシフトアプリが含まれており、その他の機能も時間の経過と共にロールアウトされます。 2019年10月1日の StaffHub はすべてのユーザーに対して機能しなくなります。 StaffHub を開こうとしたユーザーには、チームをダウンロードするように指示するメッセージが表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。

> この記事で説明されている機能は、まだリリースされていません。 これは発表されました。まもなく、2019年5月の中央に表示されます。 管理者の場合は、この機能がメッセージセンター ( [Microsoft 365 管理センター](https://portal.office.com/adminportal/home)) で利用可能になるタイミングを確認できます。

Teams のシフトアプリは、スケジュールを管理するための簡単なアプローチを提供します。また、1日のうちに発生するシフト交換とキャンセルの流れを定期的に行うことができます。 チームメンバーは、アプリやデバイス間で直接、スケジュールとシフト情報にアクセスして、ユーザー設定の設定、スケジュールの管理、休暇のリクエストを行うことができます。

この記事では、組織の StaffHub teams を移動して、チーム内のシフトにデータをスケジュールする方法について説明します。 1人または2人の StaffHub チームを持つ小規模企業でも、数百人の StaffHub teams を持つ大企業でも、チームへの移行を成功させるために必要な管理ガイダンスが記載されています。

この記事の手順を実行するには、グローバル管理者である必要があります。 まだインストールしていない場合は、 [StaffHub 定年](microsoft-staffhub-to-be-retired.md)に関する faq を参照して、お客様からの質問に回答してください。 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Teams への移行について知っておくべきこと

### <a name="when-to-move-to-teams"></a>Teams に移動する場合

2019年10月1日、StaffHub は廃止されます。 今すぐ Teams の使用を開始して、組織のチームとユーザーを StaffHub から移行することをお勧めします。 StaffHub でスケジュール管理が最も一般的に使用される機能である場合は、チームでのシフトアプリの使用を進めることをお勧めします。

### <a name="what-is-moved-to-teams"></a>Teams に移動されるもの

ユーザの詳細、スケジュール情報、チャットとファイルデータは Teams に移行されます。 これには、チームメンバーシップ、チームのスケジュール、および過去90日間のチャットとファイルが含まれます。

すべての StaffHub チームには、対応する Office 365 グループが必要です。 StaffHub チームに Office 365 グループが関連付けられていない場合は、移行をサポートするために、1つが自動的に作成されます。 Teams と StaffHub の間でのチームとグループの名前の違いにより、Teams に異なるチーム名が表示されることがあります。

チームを StaffHub から Teams に移行すると、ユーザーは StaffHub のスケジュールにアクセスできなくなり、Teams のシフトにリダイレクトされます。 この変更を組織全体で伝達することをお勧めします。中断を最小限に抑え、ユーザーにチームの採用と検討を促します。 Azure AD Premium を使用している場合は、[レポートを実行](run-report-to-show-staffhub-usage.md)して、この変更について知っておく必要がある、組織内の StaffHub ユーザーの一覧を取得できます。  

StaffHub チームを Teams に移動しても、ロールバックオプションはありません。

### <a name="user-experience-when-you-move-a-team"></a>チームを移動するときのユーザーエクスペリエンス

チームの StaffHub からシフトへの切り替えが発生した場合、ユーザーに対してダウンタイム (1 秒未満) が最小限に抑えられます。 チームへの移動が完了するまで、ユーザーは StaffHub を引き続き使用することができます。 移動が完了すると、チームメンバーにメッセージが表示され、チームのスケジュールにアクセスするためにチームのシフトの使用を開始する必要があることがわかります。 次に、ユーザーに表示されるメッセージの例を示します。

![StaffHub チームが Teams に移動した後に StaffHub に表示されるメッセージの例。](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "StaffHub チームが Teams に移動した後に StaffHub に表示されるメッセージの例")

## <a name="prepare"></a>備える

ここでは、Teams への移行を準備する方法について説明します。

### <a name="assign-teams-licenses"></a>Teams のライセンスを割り当てる

各ユーザーは、ライセンス付与された有効な Microsoft 365 [](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)または Office 365 ライセンスを所有している必要があります。また、Teams ライセンスを割り当てる必要があります。 Teams ライセンスをユーザーに割り当てると、チームにアクセスできます。

Teams のライセンスは、Microsoft 365 管理センターで管理します。 詳細については、「[チームへのユーザーアクセスを管理](../../user-access.md)する」を参照してください。

> [!NOTE]
> 組織で Skype for Business を使用していて、すべてのユーザーをチームに移行する準備ができていない場合は、最初に Skype for Business を使用してチームを実行できるようにすることができます。 この共存モード (*孤島*) では、各クライアントアプリは個別のソリューションとして動作します。 詳細については、「[チームと Skype For business の共存と相互運用性につい](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)て」を参照してください。

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Azure AD で id を持っていない StaffHub ユーザーのアカウントをプロビジョニングする

各マネージャーとチームメンバーは、Azure Active Directory (Azure AD) で id を持っている必要があります。 ユーザーがまだ Azure AD で id を持っていない場合は、アカウントをプロビジョニングします。 これを行うには、次の操作を実行します。

- StaffHub チーム所有者と管理者は、ダミーまたは非アクティブなアカウントを変換して、StaffHub のプロビジョニングされたアカウントにユーザーのメールアドレスを変更することで、StaffHub チーム設定] ページの有効な UPN に変更することができます。

- 管理者は、 [StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps)と[StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps)のコマンドレットを実行して、StaffHub チームからプロビジョニングされていないアカウントを削除し、UPN を使用してアカウントを追加し直すことができます。

### <a name="install-the-staffhub-powershell-module"></a>StaffHub PowerShell モジュールをインストールする

まだインストールしていない場合は、 [StaffHub PowerShell モジュールをインストール](install-the-staffhub-powershell-module.md)します。

StaffHub チームを移動すると、移動要求によって前提条件が確認されます。 次に、移動要求が失敗する理由について説明します。

- サインインしたユーザーはグローバル管理者ではない
- テナントのすべてのユーザーに対してチームが無効になっている
- テナントで Office 365 グループの作成が無効になっている
- StaffHub teamId が有効ではないか、メンバーがいません
- StaffHub チームには、Azure AD アカウントにリンクされていないメンバーが含まれています  

## <a name="run-a-pilot"></a>パイロットを実行する

最初に、2つまたは3つの StaffHub teams を、最早採用者のグループごとに移動することをお勧めします。 パイロットを実行すると、移行計画を調整して、組織のすべての StaffHub チームをチームに移行できるようになります。 また、組織全体での導入を促進できるエキスパートも特定します。 段階的アプローチを必要としない小規模企業の場合は、このセクションの手順に従って、StaffHub から Teams に切り替える必要があります。

### <a name="identify-pilot-teams"></a>パイロットチームの特定

パイロットチームの2つまたは3つを確認してください。 すべてのチームメンバーは、チームでシフトを使用して、スケジュールを管理し、相互に通信して共同作業を行う必要があります。

### <a name="identify-team-champions"></a>チームのチャンピオンの特定

パイロットチーム全体のチャンピオンを特定し、啓蒙シフトを支援するために参加します。 チームの支持者は、チームメンバーのサポートとガイダンスを提供するために、独自の高い知識を共有しています。 チームチャンピオンはチームの所有者または管理者になることができます。

チームのメンバーがチームの[クライアントを取得](../../get-clients.md)し、teams にサインインして、スケジュールをシフトで確認し、互いにチャットを開始するためには、チームメンバーが設定されていることを確認する必要があります。 すでに StaffHub に慣れているユーザーは、シフトですぐに稼動することになります。 その他のヘルプについては、[[シフトヘルプ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)] をポイントすることもできます。

### <a name="move-a-staffhub-team-coming-soon"></a>StaffHub チームを移動する (近日公開)

次の手順を使用して、一度に1つの StaffHub チームを移動します。 パイロットチームでは、この方法をお勧めします。 後で、組織のすべての StaffHub チームを移行する準備ができたら、「複数のチームを一度に移動する」の手順については、「 [StaffHub teams を移行](#move-your-staffhub-teams-coming-soon)する」を参照してください。

StaffHub チームを移動するには、次を実行します。

```
Move-StaffHubTeam -TeamId <String>

Sample:

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

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

次に示すのは、移動が進行中の場合に表示される応答の例です。

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>StaffHub から Teams への切り替えを行う

### <a name="raise-awareness"></a>認識を高める

パイロットチームを超えて組織の StaffHub チームをチームに移行する準備ができたら、まず組織全体で変更を伝えることが重要です。 シフトについての単語を広げ、チームへの切り替えを行って、認知度を上げ、興奮を生み出し、導入を推進します。

### <a name="move-your-staffhub-teams-coming-soon"></a>StaffHub teams を移動する (近日公開)

次の手順を使用して、StaffHub teams をまとめて移動します。 組織のすべての StaffHub チームを移動するか、または特定の StaffHub teams を移動するかを選ぶことができます。 StaffHub teams を1つずつ移動する方法については、「 [StaffHub チームを移行](#move-a-staffhub-team-coming-soon)する」を参照してください。

#### <a name="move-all-staffhub-teams-coming-soon"></a>すべての StaffHub teams を移動する (近日公開)

組織内のすべての StaffHub teams の一覧を取得するには、次を実行します。

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

次に、次のことを実行してすべてのチームを移動します。

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

応答の例を次に示します。

既に Teams に移動されているか、Teams に既に存在しているチームの場合は、そのチームに移動するためにジョブを送信する必要がないため、jobId は "null" になります。

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>特定の StaffHub チームを移動する (近日公開)

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
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a>StaffHub teams が Teams に移行されたことを確認する (近日公開)

組織内のすべてのチームの一覧を取得するには、次の操作を実行します。 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a>チームの利用状況を監視する

利用状況レポートは、使用パターンをより理解しやすくするのに役立ちます。また、組織全体でトレーニングとコミュニケーション作業の優先順位を決定する場所について理解を深めます。 シフトは Teams のアプリであるため、チームレポートで利用状況を表示できます。 詳細については、microsoft [teams 管理センターのチームレポート](../../teams-analytics-and-reports/teams-reporting-reference.md)と、 [microsoft 365 管理センターの teams アクティビティレポート](../../teams-activity-reports.md)を参照してください。

## <a name="related-topics"></a>関連トピック
- [Microsoft StaffHub はまもなく廃止予定です](microsoft-staffhub-to-be-retired.md)
- [Microsoft Teams で組織のシフト アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell リファレンス](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
