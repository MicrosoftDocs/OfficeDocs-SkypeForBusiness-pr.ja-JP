---
title: Microsoft Teams のアプリ、ボット、およびコネクタ
ms.reviewer: ''
description: アプリ、ボット、コネクタについて、および組織のプロファイルとビジネスの要件に基づいてどれを Microsoft Teams に展開するかについて説明します。
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 02/10/2021
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3022b1d1fbeff9713741955a0b40fd553028de0e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094393"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a>Microsoft Teams のアプリ、ボット、およびコネクタ

アプリを使用すると、お気に入りのサービスからコンテンツを見つけて、そのコンテンツを Teams で共有できるようになります。 チャネルの上部にサービスを固定したり、ボットとチャットしたり、タスクを共有および割り当てるときなどに役立ちます。 詳細については、「[Teams のアプリの概要](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)」を参照してください。 

Microsoft Teams で提供されるアプリを使用するか、認定されたサードパーティのアプリとテンプレートを使用するか、独自のカスタム アプリを作成することにより、Teams の展開にアプリを追加できます。

## <a name="use-microsoft-provided-apps"></a>Microsoft 提供のアプリを使用する

Teams には、リスト、Tasks、称賛、承認などを含む一連の組み込みアプリが付属しています。 Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。 Teams 導入の進行に応じて、その他のアプリ、ボット、およびコネクタを追加してください。

## <a name="use-third-party-apps"></a>サードパーティ製アプリを使用する

Microsoft 提供のアプリに加えて、Microsoft 認定のサードパーティ製アプリを使用できます。 Microsoft は、Microsoft 365 開発者パートナーと協力して、Teams アプリとアドインの使用に関する決定を迅速化するために必要な情報を提供します。詳細については、「[Microsoft Teams アプリのセキュリティとコンプライアンス](/microsoft-365-app-certification/teams/teams-apps)」を参照してください。

## <a name="use-teams-templates"></a>Teams テンプレートを使用する

また、Microsoft Teams 用の実稼働可能なアプリ、[Teams テンプレート](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)を使用することもできます。コミュニティ主導型、オープン ソースで、GitHub で利用できます。

## <a name="create-custom-apps"></a>カスタム アプリを作成する

Teams の [Microsoft Power Platform](teams-power-platfom-integration.md) との統合を使用すると、カスタムのローコード (わずかなコードを記述するだけで使用できる) ソリューションをすばやく構築できます。 ビジネス ニーズに合わせて独自のカスタム アプリを作成することもできます。 詳細については、「[Microsoft Teams 用アプリを構築する](/microsoftteams/platform/overview)」を参照してください。  


## <a name="apps-deployment-decisions"></a>アプリの展開に関する決定事項

Teams は、すぐに使用できる優れたコラボレーション エクスペリエンスを組織に提供します。ほとんどの組織は、既定の設定がよく機能することに気づいています。この記事は、組織のプロファイルとビジネス要件に基づいて、既定の設定のいずれかを変更するかどうかを決定する方法について、その後、各変更について説明します。設定を 2 つのグループに分割しました。まず、[変更を加える可能性が高い](#core-deployment-decisions)コアセットから始めます。2 番目のグループには、組織のニーズに基づいて構成する可能性のある[追加の設定](#additional-deployment-decisions)が含まれています。

## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

次に示すアプリの設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では適切に動作しない場合)。

### <a name="app-availability-settings"></a>アプリの可用性の設定 

Teams は、Microsoft とサード パーティによって発行された複数のアプリを提供します。それらのアプリは、ユーザー参加の促進、生産性のサポート、一般に使用されるビジネス サービスの Teams への統合に利用できます。 Teams Store からアプリを入手してください。 既定では、すべてのアプリ ([Teams Store 承認プロセス](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)で提出したカスタム アプリを含む) が、すべてのユーザーに対してオンにされています。 たとえば、ユーザーは Planner アプリを使用して Teams のチーム タスクを作成および管理できます。

既定では、すべての Microsoft 提供のアプリ、サード パーティ製、カスタム アプリが使用可能になっていて、個別のアプリをオンまたはオフにすることができます。 すべてのサード パーティ製および/またはカスタム アプリを組織全体でオンまたはオフにできる、組織全体の設定があります。

| 確認事項 | アクション |
|--------------|--------|
|既定の Teams アプリの設定を変更するか? | 組織内のアプリを管理するために使用できるポリシーと設定の詳細については、「[Microsoft Teams でのアプリの管理設定](admin-settings.md)」を参照してください。|
|||

### <a name="app-permissions-and-other-considerations"></a>アプリのアクセス許可とその他の考慮事項

アプリはユーザーが同意し、管理者または IT 担当者がポリシーによって管理します。 ただし、ほとんどの場合、アプリのアクセス許可とリスク プロファイルはアプリ自体で定義されています。 

| 確認事項 | アクション |
|--------------|--------|
|<br>どのアプリへのアクセスを許可するか? どのアプリへのアクセスを禁止するか?  | <ul><li>アプリ、ボット、タブ、またはコネクタへのアクセスを許可する際の考慮事項に関するリストについては、「[Microsoft Teams アプリのアクセス許可と考慮事項](app-permissions.md)」を参照してください。</li><li>組織内のユーザーがアプリを使用できるようにする方法の詳細については、「[Microsoft Teams 管理センターでアプリを管理する](manage-apps.md)」を参照してください。</li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a>プライベート チャットおよびチャネルのボット

ボットとは、クエリに応答したり、ユーザーが興味を持っている詳細や常に情報を得ていたい詳細について更新や通知を行う自動プログラムのことです。 ボットを使用すると、ユーザーは Teams チャットでのタスク管理、スケジュール設定、投票などのクラウド サービスと対話できるようになります。 Teams は、プライベートのチャットおよびチャネルでボットをサポートしています。 管理者は、Microsoft 365 組織または Office 365 組織でのボットの使用を許可するかどうかを制御できます。

| 確認事項 | アクション |
|--------------|--------|
|組織でカスタムのボットを許可しますか?|ボットの追加の詳細については、「[Microsoft Teams でプライベートのチャットやチャネルのボットを追加する](/microsoftteams/platform/bots/what-are-bots)」を参照してください。 カスタムのボットをオンまたはオフにする方法の詳細については、「[Microsoft Teams でのアプリの管理設定](admin-settings.md)」を参照してください。|
|||

### <a name="built-in-and-custom-tabs"></a>組み込みタブとカスタム タブ

所有者とチーム メンバーは、チャネル、プライベート チャット、およびグループ チャットにタブを追加して、クラウド サービスの統合に役立てることができます。 ユーザーが必要なデータや頻繁に使用するデータにアクセスしたり管理する際に役立つタブを追加します。 チャネルには、[会話] のタブと [ファイル] のタブが既定で作成されます。 すべてのプライベート チャットには、[会話]、[ファイル]、[組織]、および [アクティビティ] のタブが既定で作成されます。 これらの組み込みタブに加えて、カスタムのタブを設計して追加できます。 組織に対して Teams アプリをオンまたはオフにする方法の詳細については、「[Teams でのアプリの管理設定](admin-settings.md)」を参照してください。

| 確認事項 | アクション |
|--------------|--------|
|組織でカスタムのタブを許可しますか?|詳細については、「[Teams の組み込みタブとカスタム タブを使用する](built-in-custom-tabs.md)」を参照してください。|
|||

### <a name="custom-connectors"></a>カスタム コネクタ

コネクタにより、頻繁に使用するサービスからコンテンツと更新内容がチャネルに直接配信されるため、チームは最新の状態に保たれます。 コネクタを使用すると、Teams ユーザーはTwitter、Trello、Wunderlist、GitHub、Azure DevOps ServicesなどのポピュラーなサービスからTeams チャットで最新情報を受け取ることができます。

| 確認事項 | アクション |
|--------------|--------|
|ユーザーにカスタム コネクタの作成を許可するか?|詳細については、「[Teams でカスタム コネクタを使用する](office-365-custom-connectors.md)」を参照してください。|
|||

## <a name="additional-deployment-decisions"></a>その他の展開に関する決定事項

次の設定は、組織のニーズと構成に基づいて変更できます。

### <a name="activity-reports"></a>アクティビティ レポート

アクティビティ レポートを使用すると、組織内のユーザーがどのように Teams を使用しているかを確認できます。 たとえば、まだ Teams を使用していないユーザーがいる場合、そのユーザーは使用の開始方法を知らないか、Teams を使用して生産性と共同作業の効率を向上させる方法を理解していない可能性があります。 組織では、アクティビティ レポートを使用して、トレーニングとコミュニケーションに関する優先項目を判断できます。 アクティビティ レポートを表示するには、Microsoft 365 または Office 365 の全体管理者、Teams のサービス管理者、または Skype for Business の管理者である必要があります。

| 確認事項 | アクション |
|--------------|--------|
| <br>誰がアクティビティ レポートの確認を必要としていて、レポートを表示するための適切なアクセス許可が割り当てられているか? |<ul><li>ユーザーに管理者の役割を割り当てたくない場合は、[レポート閲覧者の役割を割り当てる](teams-activity-reports.md#reports-reader-role)ことができます。</li><li>Azure Active Directory で管理者の役割を割り当てる方法の詳細については、「[役割とアクセス許可](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」および「[役割の表示と割り当て](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。</li></ul> |
|||

### <a name="app-templates"></a>アプリ テンプレート

アプリ テンプレートは、Microsoft Teams 用の実稼働可能なアプリです。コミュニティ主導型、オープン ソースで、GitHub で利用できます。 各アプリには、組織用に展開してインストールするための詳細な手順が記載されています。使用可能な状態でアプリが提供されているため、すぐにインストールして使用を開始できます。 完全なソースコードも利用できるので、詳細を調べたり、コードをフォークして特定のニーズに合わせて変更したりできます。

| 確認事項 | 操作 |
|--------------|--------|
| アイスブレーカーなどの Teams アプリ テンプレートをインストールしますか? |詳細については、「[Microsoft Teams 用のアプリ テンプレート](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json)」を参照してください。|
|||