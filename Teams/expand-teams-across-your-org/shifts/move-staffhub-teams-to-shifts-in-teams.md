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
description: Microsoft StaffHub チームを移動し、マイクロソフトのチームの変化へのデータのスケジュールを設定する方法について説明します。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa224306f3d42d4746f8e8f2276b44208fc568bd
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "31520217"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>マイクロソフト チームの変化に、マイクロソフトの StaffHub チームを移動します。

> [!IMPORTANT]
> 2019 年 10 月 1 日より、Microsoft StaffHub が廃止されます。 マイクロソフトのチームに StaffHub 機能が進められています。 今日では、チームには、スケジュール管理のためのシフトのアプリケーションが含まれていて、その他の機能が時間の経過と共に展開されます。 StaffHub は、2019 年 10 月 1 日ですべてのユーザーの作業を停止します。 StaffHub を開こうとするとすべての人がチームをダウンロードすることを指示するメッセージ表示されます。 詳細については、「[Microsoft StaffHub の廃止](microsoft-staffhub-to-be-retired.md)」を参照してください。

> この資料で説明した機能は、まだリリースされていません。 発表されてはまもなく、2019 の 4 月の最後の方です。 管理者にする場合を調べることができますこのが使用できます ( [Microsoft 365 管理センター](https://portal.office.com/adminportal/home)) のメッセージ センターにするとします。

チームでシフトのアプリケーションでは、スケジュール、および shift キーを交換し、日常的に発生するキャンセルの一定のフローを管理するための単純なアプローチを提供します。 チーム メンバーは、スケジュールにアクセスできるし、shift キーを押しの情報直接アプリケーションでは、プレファレンスを設定するようにデバイスの間で彼らのスケジュールを管理オフ時間を要求します。

この資料では、組織の StaffHub チームを移動し、チームの変化へのデータのスケジュールを設定する方法について説明します。 1 つまたは 2 つの StaffHub チームと共同で小規模なビジネスや StaffHub チームの何百もの大規模な企業であれ、ここにある管理者ガイドを成功に導くための移行チームを支援する必要があります。

この資料の手順を実行するのにはグローバル管理者でなければなりません。 実行していない場合必要がある[StaffHub 退職に関する FAQ](microsoft-staffhub-to-be-retired.md)を参照する必要があります質問に対する回答を得ます。 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>チームの移動について理解する必要があります。

### <a name="when-to-move-to-teams"></a>チームに移行する時期

効果的な 2019 年 10 月 1日 StaffHub は廃止されます。 今日のチームの使用を開始し、組織のチームと StaffHub からのユーザーの移行を開始することをお勧めします。 スケジュール管理を使用する最も一般的に使用される機能は、StaffHub をされていることをお勧めシフト アプリケーションを使用して、チームで前方に移動します。

### <a name="what-is-moved-to-teams"></a>チームにどのような移動します。

チームには、ユーザーの詳細情報、スケジュール情報、およびチャットとファイルのデータが移行します。 これには、チームのメンバーシップ、チームのスケジュール、およびチャットおよび過去 90 日間のファイルが含まれます。

StaffHub のすべてのチームには、対応する Office 365 のグループが必要があります。 StaffHub チームには、それに関連付けられている Office 365 グループが割り当てられていない、1 つの移行をサポートする自動的に作成されます。 チームとチームと StaffHub の間でグループの名前付けの違いを指定するには、チーム内の別のチーム名を確認できます。

チームに StaffHub からのチームを移行してユーザーは、彼らのスケジュールへのアクセスを StaffHub でチームの変化にリダイレクトされます。 システム停止を最小限に抑えるとするを採用し、チームを促進する組織全体でこの変更を通信することをお勧めします。

## <a name="prepare"></a>準備

チームへの移行を準備するには。

### <a name="assign-teams-licenses"></a>Teams のライセンスを割り当てる

各ユーザーは[、対象となる計画](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in)からアクティブな Microsoft 365 または Office 365 のライセンスが必要し、チームのライセンスを割り当てる必要があります。 チームのライセンスをユーザーに割り当て、それらにアクセス チーム。

Microsoft 365 の管理センターでのチームのライセンスを管理します。 詳細については、[チームへのユーザー アクセスの管理](../../user-access.md)を参照してください。

> [!NOTE]
> 組織は、ビジネスの Skype を使用しているすべてのユーザーをチームに移動する準備がわからない場合は、ビジネスの Skype と共にチームを実行できるよう、先頭行者のチームを有効にできます。 *島*と呼ばれるこの共存モードでは、各クライアント アプリケーションは、別のソリューションとして動作します。 詳細については、[チームの理解とビジネスの共存と相互運用性の Skype](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md)を参照してください。

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Azure AD 内の id を持たない StaffHub ユーザーのアカウントをプロビジョニング

各マネージャーとチーム メンバーに、Azure Active directory (AD の Azure) の id が必要です。 ユーザー Azure AD で id を持っていない場合、は、それらのアカウントを準備します。 これを行うには、次の操作を実行します。

- StaffHub チーム所有者およびマネージャーはダミーか、アクティブでないアカウントを変換し、StaffHub チームの設定] ページで有効な upn のユーザーの電子メール アドレスを変更することによって StaffHub でプロビジョニングされているアカウントにリンクします。

- StaffHub チームの準備ではないアカウントを削除し、アカウントを追加、[削除 StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps)コマンドレットは、UPN を使用してバックアップし、管理者は、[追加 StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps)を実行できます。

### <a name="install-the-staffhub-powershell-module"></a>StaffHub PowerShell モジュールをインストールします。

いない場合は、 [StaffHub の PowerShell モジュールをインストール](install-the-staffhub-powershell-module.md)します。

StaffHub チームを移動すると、移動要求は、常に前提条件をチェックします。 移動要求が失敗する理由の理由を以下に示します。

- サインインしているユーザーは、グローバル管理者ではありません。
- チームはテナント内のすべてのユーザーに対して無効になります。
- テナントで office 365 のグループの作成が無効になっています。
- StaffHub 別子ですが正しくないか、メンバーが存在しません。
- StaffHub チームには、Azure AD のアカウントにリンクされていないメンバーが含まれています。  

## <a name="run-a-pilot"></a>パイロットを実行します。

早期採用者のグループの 2 つまたは 3 つの StaffHub チームを移動することによって開始することをお勧めします。 パイロットを実行すると、移行計画を調整し、チーム、組織内のすべての StaffHub のチームに移動する準備ができていることを確認することができます。 組織全体での採用を推進を支援できるエキスパートを識別します。 段階的なアプローチを必要としている中小企業の場合、このセクションの手順は、StaffHub からのチームに、スイッチを確認する必要がありますすべてで可能性があります。

### <a name="identify-pilot-teams"></a>パイロット チームを特定します。

パイロット チームの 2 つまたは 3 つの識別にアクセスします。 すべてのチーム メンバーは、スケジュールの管理し通信を行い、お互いの共同作業をチームでシフトを使用してにコミットする必要があります。

### <a name="identify-team-champions"></a>エキスパートのチームを識別します。

パイロット チーム間でのエキスパートを特定し、シフトを浸透させるために参加します。 チームのエキスパートが, それらの動作に関するサポートとガイダンスをチーム メンバーに提供する独自のな学習項目を共有します。 エキスパートのチームは、チームの所有者または管理者にあります。

チーム チャンピオンには、チーム メンバー[チームのクライアントを取得](../../get-clients.md)するすべてのユーザーの専用の時間を設定、チームにサインインするのには、シフトでスケジュールを確認し、お互いにチャットを開始する必要がありますを確認します。 StaffHub に慣れているユーザーになります起動してすぐにシフトで。 指定することもに[シフトのため](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)に追加のヘルプを表示します。

### <a name="move-a-staffhub-team-coming-soon"></a>(準備中) StaffHub チームを移動します。

一度に 1 つの StaffHub チームを移動するのには次の手順を使用します。 パイロット チームが、この方法をお勧めします。 後で、組織内のすべての StaffHub のチームに移動する準備ができたら、 [StaffHub チームを移動する](#move-your-staffhub-teams-coming-soon)手順について、一度に複数のチームを移動参照してください。

StaffHub チームを移動するのには、次を実行します。

```
Move-StaffHubTeam -Identity <String>
```

ここでは、StaffHub チームをチームに移動する要求を送信するときのような応答の例です。

```
    jobId   teamId                                      teamAlreadyInMicrosofteams  
    -----   ------                                      ------------          
        1   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   True
```

移動要求のステータスを確認するには、次の手順を実行します。

```
Get-TeamMigrationJobStatus <Int32>
```

ここでは、移動の実行中のときのような応答の例です。

```
    jobId   status       teamId                                     isO365GroupCreated  Error
    -----   ------       ------                                     ------------------  -----    
        1   InProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  True                None
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>チームに StaffHub からの移行を行う

### <a name="raise-awareness"></a>意識を向上させる

パイロット チームより先に進む準備ができたらし、チーム、組織の StaffHub のチームに移動することが重要、組織全体で変更を最初に通信します。 意識を向上させる、刺激を生成し、プロジェクトに適用するには、シフトとチームへの移行に関する単語を拡散します。

### <a name="move-your-staffhub-teams-coming-soon"></a>(近日公開予定)、StaffHub チームを移動します。

StaffHub チームを一括で移動するのには次の手順を使用します。 組織内のすべての StaffHub のチームを移動したり、特定の StaffHub チームを移動することができます。 StaffHub チームが 1 つずつ移動する場合は、 [StaffHub チームの移動](#move-a-staffhub-team-coming-soon)を参照してください。

#### <a name="move-all-staffhub-teams-coming-soon"></a>(準備中) すべての StaffHub チームを移動します。

組織のすべての StaffHub チームの一覧を取得するのには、次を実行します。

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
```

次に、すべてのチームを移動するのには、次を実行します。

```
$StaffHubTeams | foreach {Move-StaffHubTeam -Identity {$_.Id}}
```

ここでは、応答の例です。

```
    jobId   teamId                                      teamAlreadyInMicrosofteams  
    -----   ------                                      ------------          
        1   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   True
        2   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   False
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>(準備中) 特定の StaffHub チームを移動します。

組織のすべての StaffHub チームの一覧を取得するのには、次を実行します。

```
$StaffHubTeams = Get-StaffHubTeamsForTenant
```

コンマ区切り値 (CSV) ファイルを作成し、移動しチームの Id を追加します。
ここで例を示します。

|Id  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0 fc 9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0 fc 9-408b-85ff-c14a26700000|

CSV ファイルで指定したチームを移動するのには、次を実行します。

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -Identity {$_.Id}}
```

## <a name="monitor-teams-usage"></a>チームの使用率を監視します。

利用状況レポートの使用パターンを理解し、組織全体でのトレーニングとコミュニケーションの取り組みに優先順位をどこに情報を提供することができます。 シフトはチームのアプリケーションであるため、チームのレポートでの使用状況を表示できます。 詳細については、[チームは、マイクロソフト チームの管理センターに報告](../../teams-analytics-and-reports/teams-reporting-reference.md)し、 [Microsoft 365 の管理センターでチームの活動レポート](../../teams-activity-reports.md)を参照してください。

## <a name="related-topics"></a>関連トピック
- [Microsoft StaffHub はまもなく廃止予定です](microsoft-staffhub-to-be-retired.md)
- [Microsoft Teams で組織のShifts アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell 参照](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
