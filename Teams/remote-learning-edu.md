---
title: 遠隔学習向けに Microsoft Teams の使用を開始する。
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith, lakuan
description: Microsoft Teams for Education 向けの遠隔学習スタートアップ ガイダンス。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 231007549102b8cddc02a0d2a5d29266662b4b2f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466025"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>遠隔学習向けに Microsoft Teams の使用を開始する。

この記事では、Microsoft Teams を使用して教育機関をリモート ラーニング用に設定するための IT 管理手順について説明します。

Teams 内では、 **教育者は次の** ことができます。

- 学生とすぐに会話します。
- ファイルと Web サイトを共有します。
- OneNote クラス ノートブックを作成します。
  - 対話型のレッスンを整理します。
  - 効果的でタイムリーなフィードバックを提供します。
- 課題を配布して採点する。
- Professional Learning Communityes で教材を共有する。

**教育機関の管理者とスタッフは、** 次のことができます。

- イベントを最新の状態に保つ。
- スタッフ チームを使用して、お知らせや話題の会話を共同作業します。

# <a name="accounts--licenses"></a>[アカウント & ライセンス](#tab/accounts)

## <a name="user-accounts-licenses-and-identity-security"></a>ユーザー アカウント、ライセンス、ID のセキュリティ

Teams では、Microsoft 365 を使用してユーザーを認証し、サービスを提供します。 すべてのユーザーは、共同作業を容易にするために、Microsoft 365 ID を確立する必要があります。

ユーザー ID がまだ存在しない場合は、次の手順に従ってユーザー ID を確立します。

1. [School Data Sync を使用してユーザーを作成します](/microsoft-365/education/deploy/school-data-sync)。
2. [ユーザーにライセンスを割り当てます](teams-edu-licensing.md)。
3. [Microsoft 365 グループを作成します](Office-365-groups.md)。
4. [Exchange を設定します](Exchange-Teams-interact.md)。
5. [SharePoint と OneDrive を設定します](SharePoint-OneDrive-interact.md)。
6. [Google メールを持つユーザーを設定します](/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users)。

Microsoft Teams は、無料の A1 教育プランを含むすべての Microsoft 365 プランに含まれています。

Microsoft 365 の展開と Teams のセットアップに関するガイダンスについては、「 [Microsoft 365 テナントの作成」を参照してください](/microsoft-365/education/deploy/create-your-office-365-tenant)。

# <a name="set-up-teams"></a>[Teams を設定する](#tab/setup)

## <a name="easily-set-up-teams"></a>Teams をすばやく設定する

Teams を使用して起動して実行するには、次の 2 つの操作を行う必要があります。

### <a name="1-allow-users-to-create-teams"></a>1. ユーザーがチームを作成できるようにする

**既定では、すべてのユーザーが Microsoft 365 グループと Teams を作成できますが**、この機能が適切であるとは限りません。

たとえば、一部の学校では、学生が監督なしで Teams を作成できないように制限したい場合があります。 Microsoft 365 グループとチームの作成は、 [特定のセキュリティ グループに制限](/microsoft-365/admin/create-groups/manage-creation-of-groups)できます。

教育機関では、学生を含むすべてのユーザーが、クラス、研究、グループ プロジェクト、および学習グループ用のチームを作成できるようにすることをお勧めします。

Teams を作成する方法の詳細については、「 [Microsoft Teams でクラス チームを作成する](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)」を参照してください。

### <a name="2-configure-user-experiences-using-policies"></a>2. ポリシーを使用してユーザー エクスペリエンスを構成する

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> [Teams で学生を安全に保ち、遠隔学習を行](https://support.office.com/article/f00fa399-0473-4d31-ab72-644c137e11c8)う方法を確認してください。
>
> EDU ポリシーの推奨事項を表示する場合は、 [教育機関向けの Teams ポリシーとポリシー パッケージに関するページを](policy-packages-edu.md)参照してください。

Teams ポリシーは、特定のユーザーまたはグループで使用できる機能を制御します。 ポリシーでは、プライベート チャット、プライベート通話、会議のスケジュール設定、共有できるコンテンツ タイプなどを使用できるユーザーを定義できます。

**教育機関のスタッフ、教育者、学生は、** 既定の (グローバル) ポリシーを使用できます。 ポリシーを調整して、 [翻訳機能](messaging-policies-in-teams.md#messaging-policy-settings) や [会議の自動文字起こし](meetings-policies-recording-and-transcription.md#transcription)など、Teams にさらに機能を追加できます。

**初等中等学校の学生は** 、制限付きの機能が必要な場合があります。 学生ポリシーの変更は、"グローバル (組織全体の既定値)" ポリシーに行うことをお勧めします。

**初等中等学校のスタッフと教育者** には、プライベート チャットの許可や会議のスケジュール設定など、主要な機能を付与するポリシーを割り当てる必要があります。 [これらのポリシーを教職員に一括して割り当てます](batch-group-policy-assignment-edu.md)。

> [!IMPORTANT]
> 会議ポリシーを任意のユーザーに割り当てるには、[ユーザーを **自動的に許可** する] 設定を **組織内のすべてのユーザー** に設定することをお勧めします。 これにより、認証されていないユーザーが Teams 会議に参加する前にロビーから承認される必要があります。
>
> 詳細については、「[Teams での会議ポリシーを管理する](meeting-policies-participants-and-guests.md#automatically-admit-people)」を参照してください。

# <a name="class-teams"></a>[クラス チーム](#tab/class-teams)

## <a name="create-class-teams-for-secure-classroom-use"></a>授業で安全に使用できる、クラス チームを作成する

Microsoft Teams for Education では、教育機関向けの [特別なチーム タイプ](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) が提供されています。 [クラスチームタイプ](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)は教室での使用を目的として設計されており、教室のニーズを次の特定の機能でサポートします。

- 割り当て。
- 成績。
- OneNote クラスルーム ノートブック。
- 学生の読み取り専用コンテンツをセキュリティで保護するための [Class Materials フォルダー](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)。
- 各教室の学生の関与、課題、幸福に関するリアルタイム データを提供するための [Insights](./class-insights.md)。
- 学生が追加される前にクラスを設定するための[早期教育者アクセス](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)。
- 破壊的な学生やその他の特別なアクセス許可をミュートする機能。

クラス チームは、次の方法で作成できます。

- [School Data Sync (SDS)](#automatic-team-creation-using-sds)。
- [Microsoft 365 クラス グループを使用した教育者主導の作成](#educator-led-team-creation-from-microsoft-365-class-groups)。
- [Graph API を使用した PowerShell スクリプト](#powershell-script-using-graph-apis)。
- [チームの手動作成](#manual-team-creation)。

ニーズに合わせて、最適に且つ適切に導入できるように、さまざまなオプションについて説明していきます。

### <a name="automatic-team-creation-using-sds"></a>SDS を使用したチームの自動作成

[School Data Sync (SDS) は](/SchoolDataSync) 、教育機関のレコード システム (学生情報システム (SIS) や Learning Management System (LMS) など) からデータを読み取ります。

SDS では、任意のレコード システムからデータをインポートでき、多くの [SIS ベンダー](/schooldatasync/frequently-asked-questions#what-sismis-vendors-does-school-data-sync-support)に組み込みのコネクタが用意されています。  

#### <a name="benefits-of-sds"></a>SDS の利点

- ユーザーを自動的に作成し、ライセンスを適用します。
- クラス チームを自動的に作成して管理します。
- SIS/LMS と同期して、学生メンバーシップの変更を維持します。
- [教師は、学生を追加する前にクラスを準備できます](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)。
- セキュリティ グループを自動的に作成できます。
- スコープ付き管理委任の管理単位を作成します。
- [教育者のパスワード リセットを許可します](/schooldatasync/how-to-enable-teacher-password-reset)。
- グループとチームの名前を変更してアーカイブするためのクリーンアップ機能が組み込まれています。
- [Teams の成績を SIS に同期します](/schooldatasync/grade-sync)。
- [学生の個人データを保護します](/schooldatasync/protecting-student-personal-data)。
- 保護者の同意を追跡および管理します。
- より優れたEducation Insightsデータを提供します。

#### <a name="considerations-for-sds"></a>SDS に関する考慮事項

SDS では、次の 2 つの手順でチームが作成されます。

1. SDS は、Azure Active Directory (Azure AD) に Microsoft 365 グループを作成します。
2. SDS は、そのグループをチームに自動的に変換します。

チームを作成する2番目のステップは、SDS ではオプションです。 管理者は、導入時間と結果として生じる可能性のある未使用のチームの数によっては、チームを自動作成したがらない可能性があります。 代わりに、 [教育者主導のチーム作成方法](#educator-led-team-creation-from-microsoft-365-class-groups)を参照してください。  

#### <a name="get-started-with-sds"></a>SDS の使用を開始する

作業を開始するには、 [School Data Sync (SDS)](/SchoolDataSync) に移動し、無料の展開のサポートを受けるためにお問い合わせください [https://aka.ms/sdssupport](https://aka.ms/sdssupport) 。  

### <a name="educator-led-team-creation-from-microsoft-365-class-groups"></a>Microsoft 365 クラス グループからの教育者主導のチーム作成

教育者主導のチーム作成により、教師は必要なクラスを簡単に作成できます。  

この方法では、SDS を使用して各クラスのグループを作成するか (推奨)、[Graph API](/graph/api/educationroot-post-classes)を使用して独自に作成できます。

クラス グループが準備されたら、教育者はグループをチームに変換できます。

1. Teams の [Teams] タブを選択します。
2. クライアントの上部にある [ **推奨クラス** ] アイコンを選択します。

#### <a name="benefits-of-educator-led-team-creation"></a>教育者主導のチーム作成の利点

- クラスは準備され、提案されますが、教育者が使用する予定がない限り作成されません。
- 500,000 チームを超える教育機関の場合、この方法により不要なチームの数が減ります。
- [SDS の利点](#benefits-of-sds)。
- Graph API特典。
  - 教師は、作成するクラスを制御できます。
  - SDS と統合する必要ありません。

#### <a name="considerations-for-educator-led-team-creation"></a>教育者主導のチーム作成に関する考慮事項

- 完全に自動化されておらず、教職員のアクションを必要とします。
- チームを作成する権限を持たない教育者は、引き続き [既存のグループからチームを作成](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b)できます。
- Graph APIには、高度な技術的専門知識、スクリプトを作成して実行する時間、問題を解決する時間が必要です。

#### <a name="get-started-with-educator-led-team-creation"></a>教育者主導のチーム作成を開始する

SDS メソッドの使用を開始するには、 [School Data Sync (SDS)](/SchoolDataSync) に移動し、無料の展開サポートを受けられるようにお問い合わせください [https://aka.ms/sdssupport](https://aka.ms/sdssupport) 。

- SDS プロファイルでチームの自動作成の切り替えをオフにする必要があります。
- 2 つの SDS プロファイルを使用して、クラス チームの自動チームと教育者主導のチーム作成の組み合わせを使用できます。

Graph API メソッドの利用方法は、「[Graph API](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-1.0&preserve-view=true)」および「[クラスチームを作成する](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true)」を参照してください。  

### <a name="powershell-script-using-graph-apis"></a>Graph API を使用した PowerShell スクリプト

PowerShell を使用すると、チームとチャネルを作成し、設定を自動的に構成するスクリプトを作成できます。

この方法では、管理者が [最初にグループを作成し、教育者と学生を追加してからチームを作成する](/graph/teams-create-group-and-team)必要があります。

[Microsoft Graph APIを使用して、チームを作成、構成、複製、アーカイブ](/graph/api/resources/teams-api-overview)することもできます。

#### <a name="benefits-of-powershell-scripts"></a>PowerShell スクリプトの利点

- IT 管理者がクラスの作成を制御できるようにします。
- 教職員への早期アクセスチームを作成するか、生徒へのチームへの即時アクセスを作成するオプション。
- [学生メンバーシップの変更を Azure AD グループに同期します](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true)。

#### <a name="considerations-for-powershell-scripts"></a>PowerShell スクリプトに関する考慮事項

- スクリプトの作成や実行、クラスグループの作成時に発生した問題の修正など高度な技術的専門知識と時間を必要とします。
- 組み込みのエラー処理や再試行ロジックはありません。
- メンバーシップの変更は SIS と同期されません。

> [!NOTE]
> クラスチームには非表示のグループメンバーシップが必要ですので、クラス内の教職員と生徒だけがそのクラスのメンバーを見ることができます。 Microsoft 365 クラス グループを作成するには、「プライバシー要件を満たす [クラス チームを作成](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true) する」を参照してください。

### <a name="manual-team-creation"></a>チームの手動作成

ユーザーは、独自のチームを作成する機能を持つことで、Teams エクスペリエンスを調整できます。

ユーザーのアクセス許可に応じて、次のことができます。

- [独自のチームを設定し、学生を含むユーザーを招待](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch)します。
- [チームにユーザーを手動で追加します](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954)。
- [結合コードを共有します](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)。
- [チームへのリンクを共有します](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)。

教師にチームに学生を追加して、学生がアクセスできるようにし、追加されたことを通知することをお勧めします。

#### <a name="benefits-of-manual-team-creation"></a>手動チーム作成の利点

- 教育者にクラス作成の完全な制御を提供します。
- クラス チームはすぐに作成されます。

#### <a name="considerations-for-manual-team-creation"></a>チームの手動作成に関する考慮事項

- 教職員によるアクションおよび時間を必要とします。
- 学生メンバーシップは SIS と同期されないため、手動で管理する必要があります。
- 学生は、クラス チームにすぐにアクセスできます。

### <a name="recommended-best-practices"></a>推奨されるベストプラクティス

- 早期に導入して、すべてが確実に機能し、初日の準備ができるようにします。

- SDS 自動チーム作成に関する問題については、教育者 [が主導するチーム作成方法](#educator-led-team-creation-from-microsoft-365-class-groups) を使用して再試行できます。 [手動チーム作成](#manual-team-creation) は別のソリューションですが、クラスは SIS と同期されません。

- テナントチームの上限は500,000チームです。 そのため、管理者は、これらの制限に達しないように、未使用のチームの数を減らす必要があります。 詳細については、「 [Microsoft Teams の制限と仕様」を参照してください](limits-specifications-teams.md)。  

# <a name="educator-early-access"></a>[教育者の早期アクセス](#tab/early-access)

## <a name="early-access-to-class-teams"></a>クラスチームに早期アクセスする

早期アクセス クラス Teams を使用すると、学生がクラス チームを表示する前に、教師はクラス チームにアクセスできます。 教育者は、学生へのアクセスを許可する前に、セットアップ、ファイルの追加、整理を行う時間があります。

学生がチームにアクセスする準備ができたら、 [クラスをアクティブ化](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78)できます。

### <a name="how-do-i-create-class-teams-that-allow-educators-early-access-to-set-up-a-team-before-admitting-students"></a>学生にアクセス許可を付与する前に、教職員が早期アクセスしてクラス チームを作成するにはどうすればいいですか?

グループから作成されるチーム (SDS、教職員主導、または Graph API) では、既定で自動的に早期アクセス チームを作成します。

Graph API を使用して自身の早期アクセス チームを作成するには、[クラスを作成](/graph/api/educationroot-post-classes?tabs=http&view=graph-rest-beta&preserve-view=true)して、[グループからチームを作成](/graph/api/team-post?tabs=http&view=graph-rest-beta#example-4-create-a-team-from-group&preserve-view=true)する必要があります。

### <a name="how-do-i-check-if-a-class-is-activated"></a>クラスがアクティブ化されているか確認するにはどうすればいいですか?

[チーム リソースの種類](/graph/api/resources/team?view=graph-rest-beta&preserve-view=true)で、プロパティ [isMembershipLimitedToOwners](/graph/api/resources/team?view=graph-rest-beta#properties&preserve-view=true) を表示して、クラスがアクティブ化されているかどうかを確認します。

[Team API を取得](/graph/api/team-get?tabs=http&view=graph-rest-beta&preserve-view=true) を使用して、特定のクラス用の```isMembershipLimitedToOwners```プロパティをクエリします。 チームがアクティブ化されると、False の値が返されます。 チームがアクティブ化されていない場合は、true の値が返されます。

### <a name="how-do-i-activate-a-class-for-an-educator"></a>教職員用のクラスをアクティブ化するにはどうすればいいですか?

[チームの更新 API](/graph/api/team-update?tabs=http&view=graph-rest-beta&preserve-view=true) を使用し、プロパティを ```isMembershipLimitedToOwners``` false に設定して、教育者に代わってチームをアクティブ化します。 チームがアクティブ化された後は、元に戻すことはできません。

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>職員の通信と共同作業用にスタッフ チームを作成する

[スタッフタイプ チーム](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) は、教育機関の管理者とスタッフが情報を共有し、教育機関全体のイニシアチブに協力するためのチームです。

教育機関の管理者は、チーム作成ウィザードを使用してチームにスタッフを追加したり、 [チームの作成後にメンバーを追加](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9)したり、 [参加コードを共有したり、チームにリンクしたりできます](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)。

# <a name="meeting-scenarios"></a>[会議のシナリオ](#tab/scenarios)

## <a name="teams-meeting-scenarios"></a>Teams の会議シナリオ

### <a name="collaborative-meetings-for-virtual-classes"></a>仮想クラスの共同作業会議

[Microsoft Teams 会議](./tutorial-meetings-in-teams.yml)では、同時に 250 人までの参加者がサポートされており、音声、ビデオ、[コンテンツ共有](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7)、ホワイトボード、および共有メモを使用できます。

会議は次のことができます。

- [Teams クライアント内でスケジュールされます](./tutorial-meetings-in-teams.yml)。
- 出席者が後で確認できるように記録および保存されます。
- [コンテンツを簡単に見つけるために書き起こされます](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308)。
- ノート PC または携帯電話の Web カメラ、マイク、およびスピーカーを使用してアクセスします。
- [特定のデバイス用に最適化されています](https://products.office.com/microsoft-teams/across-devices/devices)。
- 学生が教師なしの会議に参加していないことを確認するために、すべての参加者が終了しました。

### <a name="districtuniversity-events-or-updates"></a>学区全体または大学全体のイベントや近況報告

一部の会議には、多くの対象ユーザーと追加の運用ニーズがあります。 これらの会議では多くの場合、発表者や制作者があらかじめ設定されており、調整役付きの質疑応答が行われます。

Teams では、[Microsoft Teams ライブ イベント](teams-live-events/what-are-teams-live-events.md)を使用してこれらのセッションをサポートしています。

ライブ イベントは、次のようなシナリオに使用できます。

- 地区または大学全体の更新プログラム。
- リーダーシップのアドレス。
- 大規模なクラスまたは学生グループの手順。
- コミュニティへの拡張。

ライブ セッションの実施については、次のページを参照してください。

- [ライブ イベントの計画とスケジュールを設定します](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)。
- [ライブ イベントを生成](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb)します。
- [ライブ イベントに参加します](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac)。
- [Q&A のモデレーション](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76)。

# <a name="resources"></a>[リソース](#tab/resources)

## <a name="support-resources"></a>リソースをサポートする

リモート ラーニングへの移行の一般的な概要については、 [ここから](https://www.microsoft.com/education/remote-learning)

IT 管理者、教育者、学生、保護者の場合、これらのリソースは Teams の使用に役立つ場合があります。

- **IT 管理者**
  - [プラットフォーム別の Teams 機能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。
  - [Teams クライアントをダウンロードして配布します](get-clients.md)。
  - [Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)。
  - [仮想化デスクトップ インフラストラクチャの Teams](./teams-for-vdi.md)。
  - [通話品質を監視および管理します](monitor-call-quality-qos.md)。
  - [Teams のサービス正常性を確認します](service-health.md)。
  - [リモート スタッフ用に Microsoft 365 トラフィックを最適化](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)します。
  - [Teams のサポート連絡先](/microsoft-365/admin/contact-support-for-business-products)。
  - [ウェビナー Microsoft Teams for Education](https://aka.ms/TeamsEDUWebinars)。

- **教職員**
  - [教育者向けのヘルプ センター](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114)。
  - [リモート ラーニングのヘルプ](https://aka.ms/RemoteLearningHelp)。
  - [Teams をダウンロードします](get-clients.md)。
  - [ウェビナー Microsoft Teams for Education](https://aka.ms/TeamsEDUWebinars)。
  - [Teams を使用する教育者向けのオンライン コース](https://education.microsoft.com/course/9c9f5c11/overview)。
  - [Teams を使用してコラボレーションラーニング環境を作成するオンライン コース](https://education.microsoft.com/course/b1e15cfc/overview)。
  - [サポート チケットを提出します](https://www.microsoft.com/microsoft-teams/download-app)。

- **学生**
  - [学生向けのヘルプ センター](https://support.office.com/article/student-help-center-395ab230-55bf-44c6-b265-e832d729b694)。
  - [リモート ラーニングのヘルプ](https://aka.ms/RemoteLearningHelp)。
  - [Teams をダウンロードします](https://www.microsoft.com/microsoft-teams/download-app)。

- **保護者**
  - [リモート ラーニングのヘルプ](https://aka.ms/RemoteLearningHelp)。
  - [Teams をダウンロードします](https://www.microsoft.com/microsoft-teams/download-app)。

---
