---
title: Microsoft Teams のアプリ、ボット、およびコネクタ
ms.reviewer: ''
description: アプリ、ボット、コネクタについて、および組織のプロファイルとビジネスの要件に基づいてどれを Microsoft Teams に展開するかについて説明します。
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
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
ms.openlocfilehash: 10d17aedd0a653b6fc5bd24946ede5da09dc4647
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691333"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a>Microsoft Teams のアプリ、ボット、およびコネクタ

アプリを使用すると、お気に入りのサービスからコンテンツを見つけて、そのコンテンツをすぐに Teams で共有できるようになります。 チャネルの上部にサービスを固定したり、ボットとチャットしたり、タスクを共有および割り当てるときなどに役立ちます。 詳細については、「[Teams のアプリの概要](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)」を参照してください。

Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。 Teams 導入の進行に応じて、その他のアプリ、ボット、およびコネクタを追加してください。

また、独自のカスタム アプリを作成することもできます。 詳細については、「[開発者向けドキュメント](/microsoftteams/platform/overview)」を参照してください:

## <a name="apps-deployment-decisions"></a>アプリの展開に関する決定事項

Teams は、すぐに使用できる優れたコラボレーション エクスペリエンスを組織に提供します。既定の設定は、ほとんどの組織の業務に通用します。 この記事では、自分の組織のプロファイルとビジネスの要件に基づいて既定の設定に変更が必要かどうかを判断する際のガイダンスを示し、それぞれの変更の手順を説明します。 設定については 2 つのグループに分けて、まず、[変更する可能性が高いと考えられる](#core-deployment-decisions)中心的な部分について説明します。 2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。

## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

次に示すアプリの設定は、ほとんどの組織が変更を必要とするものです (Teams の既定の設定では適切に動作しない場合)。

### <a name="app-availability-settings"></a>アプリの可用性の設定 

Teams には、Microsoft とサード パーティが公開する複数のアプリがあり、ユーザー参加の促進、生産性のサポート、および一般に使用されるビジネス サービスの Teams への統合のために使用できます。 Teams Store からアプリを入手してください。 既定では、すべてのアプリ ([Teams Store 承認プロセス](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process)で提出したカスタム アプリを含む) が、すべてのユーザーに対してオンにされています。 たとえば、ユーザーは Planner アプリを使用して Teams のチーム タスクを作成および管理できます。

既定では、すべての Microsoft 提供のアプリとカスタム アプリが使用可能になっていて、個別のアプリをオンまたはオフにすることができます。 すべてのカスタム アプリを組織全体でオンまたはオフにできる組織全体の設定があります。

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
|組織でカスタムのボットを許可しますか?|ボットの追加の詳細については、「[Microsoft Teams でプライベートのチャットやチャネルのボットを追加する](add-bots.md)」を参照してください。 カスタムのボットをオンまたはオフにする方法の詳細については、「[Microsoft Teams でのアプリの管理設定](admin-settings.md)」を参照してください。|
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
| <br>誰がアクティビティ レポートの確認を必要としていて、レポートを表示するための適切なアクセス許可が割り当てられているか? |<ul><li>ユーザーに管理者の役割を割り当てたくない場合は、[レポート閲覧者の役割を割り当てる](teams-activity-reports.md#reports-reader-role)ことができます。</li><li>Azure Active Directory で管理者の役割を割り当てる方法の詳細については、「[役割とアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」および「[役割の表示と割り当て](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。</li></ul> |
|||

### <a name="app-templates"></a>アプリ テンプレート

アプリ テンプレートは、Microsoft Teams 用の実稼働可能なアプリです。コミュニティ主導型、オープン ソースで、GitHub で利用できます。 各アプリには、組織用に展開してインストールするための詳細な手順が記載されています。使用可能な状態でアプリが提供されているため、すぐにインストールして使用を開始できます。 完全なソース コードが提供されるので、詳細に調べたり、コードをフォークして特定のニーズに合わせて変更したりできます。

| 確認事項 | 操作 |
|--------------|--------|
| アイスブレーカーなどの Teams アプリ テンプレートをインストールしますか? |詳細については、「[Microsoft Teams 用のアプリ テンプレート](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)」を参照してください。|
|||


## <a name="next-steps"></a>次の手順
- おすすめのアプリ (Planner など) の[導入を推進](adopt-microsoft-teams-landing-page.md)する。
- [ミーティングと会議を展開する](deploy-meetings-microsoft-teams-landing-page.md)
- [クラウド ボイスを展開する](cloud-voice-landing-page.md)


