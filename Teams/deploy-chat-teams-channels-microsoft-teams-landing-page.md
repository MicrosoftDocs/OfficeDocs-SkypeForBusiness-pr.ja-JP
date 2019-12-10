---
title: Microsoft Teams のチャット、チーム、チャネル、およびアプリ
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Microsoft Teams のチャット、チーム、チャネル、およびアプリを展開する際の段階的なガイダンス
localization_priority: Priority
ms.collection:
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.dashboard.helparticle.quickstartteamsadmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c76a50c330a6f67a61edcb29861eecb76312f05a
ms.sourcegitcommit: 2fd1fcb0e5944f36261e551df04819713d868a11
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2019
ms.locfileid: "39886251"
---
# <a name="chat-teams-channels--apps-in-microsoft-teams"></a>Microsoft Teams のチャット、チーム、チャネル、およびアプリ

Teams は、すぐに使用できる優れたコラボレーション エクスペリエンスを組織に提供します。既定の設定は、ほとんどの組織の業務に通用します。 この記事では、自分の組織のプロファイルとビジネスの要件に基づいて既定の設定に変更が必要かどうかを判断する際のガイダンスを示し、それぞれの変更の手順を説明します。 設定については 2 つのグループに分けて、まず、[変更する可能性が高いと考えられる](#core-deployment-decisions)中心的な部分について説明します。 2 番目のグループには、組織のニーズ応じた構成が求められる可能性がある[追加の設定](#additional-deployment-decisions)が含まれています。 

開始するには、短い Teams チャット、チーム、およびチャネルのビデオをご覧ください (4:30 分): 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE476Yj]

*2019 年 11 月の新機能*
 - [Teams のアドバイザー (プレビュー) を使用して、Microsoft Teams を展開できる](use-advisor-teams-roll-out.md)ようになりました。 Teams のアドバイザー (プレビュー) を使用して、Teams の展開について説明します。 Office 365 環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。
 - [IT 担当者向けの Microsoft Teams の基礎の YouTube チャネル](https://aka.ms/MicrosoftTeamsforIT)には、Teams の展開、構成、および管理の方法を示す短い (8 〜 10 分) ビデオが含まれています。

> [!TIP]
> Teams の初期展開時に、おすすめのアプリ (Planner など) を含めることをお勧めします。 Teams 導入の進行に応じて、その他の[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)を追加してください。

## <a name="chat-deployment-prerequisites"></a>チャットの展開に関する前提条件

組織全体に Teams を展開する前に、環境が Teams に対応しているかどうかを確認するために時間を割いてください。 次の情報を確認して、環境に対して必要な変更を実行してください。

- Teams の完全なエクスペリエンスを実現する場合、組織は [Exchange Online および SharePoint Online](#exchange-and-sharepoint-interoperability) を展開している必要があり、ユーザーには Office 365 の確認済みドメイン (たとえば、contoso.com) が必要になります。

- チャット、チーム、およびチャネルを組織全体に展開する場合は、すべての場所で Office 365 に接続するためのインターネット アクセスが可能であることを確認します。 少なくとも、次に示す共通のポートが、すべての場所からインターネットに対して開かれていることを確認してください。

    - Teams を使用するクライアントからの送信トラフィック用に **TCP** ポート 80 および 443 を開きます。
    - Teams を使用するクライアントからの送信トラフィック用に **UDP** ポート 3478 から 3481 を開きます。

|確認事項|アクション |
|------------|-------|
|Teams を展開するために組織の準備が整っているか?|この質問に回答するには、次を参照してください。 <ul><li> [Teams の導入に向けた環境の準備を確認する](environment-readiness.md)</li><li>[Teams 用に組織のネットワークを準備する](prepare-network.md)</li><li>[Office 365 の URL と IP アドレスの範囲](office-365-urls-ip-address-ranges.md)</li><li>[チームを作成するときの Office 365 グループの計画](plan-office-365-groups.md)</li></ul>|
|||

## <a name="core-deployment-decisions"></a>展開に関する重要な決定事項

次に示すチャット、チーム、およびチャネルの設定は、ほとんどの組織が変更を必要とするものです (既定の設定では適切に機能しない場合)。

### <a name="teams-administrators"></a>Teams の管理者

Teams には、組織に適した Teams の管理に使用できる、カスタムの管理者の役割のセットが用意されています。 この役割によって、さまざまな機能が管理者に提供されます。

| 確認事項 | アクション |
|--------------|--------|
|Teams 通信管理者の役割を誰に割り当てるか?|Teams 管理者の役割の詳細については、「[Microsoft Teams の管理者ロールを使用して Teams を管理する](using-admin-roles.md)」を参照してください。|
|Teams 通信サポート エンジニアの役割を誰に割り当てるか?|管理者の役割を割り当てるには、「[Active Directory で管理者の役割と管理者以外の役割をユーザーに割り当てる](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)」を参照してください。|
|Teams 通信サポート スペシャリストの役割を誰に割り当てるか?||
|||

### <a name="teams-owners-and-members"></a>Teams の所有者とメンバー

管理者の役割に加えて、Teams には所有者とメンバーのユーザーの役割を割り当てる機能があります。また、それらのユーザーに選択的にモデレーターの役割を与えて (モデレートを設定している場合)、チャネル内で特定の操作を実行できるユーザーを制御できます。 モデレート機能を使用すると、チャネルで新しい投稿を開始できるユーザーを制御したり、チーム メンバーをモデレーターとして追加、削除したり、既存のチャネル メッセージに返信可能かどうかを制御したりできます。

|確認事項|アクション |
|------------|-------|
|各役割に誰を割り当てるか? | 各役割の機能を比較するには「[Microsoft Teams でチームの所有者、モデレーター、メンバーを割り当てる](assign-roles-permissions.md)」を参照してください。
|ユーザー役割を割り当てるにはどうすればよいか? | 役割を割り当てたり変更したりするには、「[ユーザー役割の割り当て](assign-roles-permissions.md#assign-a-user-role)」を参照してください。
|チャネルで投稿したり、返信したりできるユーザーを制御する必要があるか? | モデレートを構成するには、「[Microsoft Teams でチャネル モデレートをセットアップして管理する](manage-channel-moderation-in-teams.md)」を参照してください。

### <a name="messaging-policies"></a>メッセージング ポリシー

メッセージング ポリシーでは、Teams のユーザーが、チャットおよびチャネルのどのメッセージング機能を使用できるかを制御します。 たとえば、どのユーザーが送信メッセージの編集および削除が可能か、どのユーザーがチャットを使用できるか、どのユーザーが会話でミームを使用できるかなどです。 既定では、ユーザーにグローバル メッセージング ポリシーが割り当てられていて、すべての機能が**オン**になっています。 既定のグローバル ポリシーを使用することも、組織内のユーザーに応じた 1 つ以上のポリシーを作成することもできます。 

|確認事項|アクション |
|------------|-------|
|グローバル メッセージング ポリシーをカスタマイズするか?|Microsoft Teams 管理センターを使用したグローバル メッセージング ポリシーの変更や新しいポリシーの追加に関する詳細については、「[Teams でのメッセージング ポリシーを管理する](messaging-policies-in-teams.md)」を参照してください。|
|複数のメッセージング ポリシーが必要か?|メッセージング ポリシーを PowerShell で作成して割り当てる場合は、「[PowerShell スクリプトのサンプル: メッセージング ポリシーの作成と割り当て](scripts/powershell-script-teams-messaging-policy-edu.md)」を参照してください。|
|どのユーザーのグループにどのメッセージング ポリシーを割り当てるかについて判断する方法は?|CsTeamsMessagingPolicy コマンドレットの詳細については、「[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps)」を参照してください。|
||| 

### <a name="external-access"></a>外部アクセス

外部アクセス (旧称: フェデレーション) を使用すると、Teams と Skype for Business のユーザーが、組織外部のユーザーと通信できるようになります。 これをオンにして許可リストにドメインを追加すると、ユーザーは別のドメインおよび別の組織のユーザーと通信できます。外部アクセスは、ゲスト アクセスとは異なり、個人ではなくドメイン全体にアクセス許可を与えます。 外部アクセスは、既定でオフになっています。

|確認事項|アクション |
|------------|-------|
|<ul><li>自分の組織の外部アクセスをオンにするか?</li><li>有効にする場合は、自分の組織との通信を許可するドメインを制限するか?</li></ul> |<br>外部アクセスを有効にするには、「[外部アクセスを計画する](manage-external-access.md#plan-for-external-access)」を参照してください。|
|||

### <a name="guest-access"></a>ゲスト アクセス

Teams のゲスト アクセスを使用すると、組織の外部にいる個人がチームおよびチャネルにアクセスできるようになります。 ゲスト アクセスの設定を使用すると、ゲスト ユーザーが使用できる (または使用できない) 機能を制御できます。 ゲスト アクセスは、既定でオフになっています。 詳細については、「[Teams でのゲスト アクセス](https://docs.microsoft.com/microsoftteams/guest-access)」を参照してください。

|確認事項|アクション |
|------------|-------|
|自分の組織のゲスト アクセスをオンにするか?|ゲスト アクセスをオンにするに場合は、「[Teams のゲスト アクセスをオンまたはオフにする](set-up-guests.md)」を参照してください。|
|有効にする場合、自分の組織でゲストが使用できる機能をカスタマイズするか?|ゲスト アクセス機能の有効/無効をカスタマイズする場合は、「[Teams のゲスト アクセスを許可する](teams-dependencies.md)」を参照してください。|
|||

### <a name="teams-settings"></a>Teams の設定

Teams の設定を使用すると、チームに対する電子メール統合、クラウド ストレージのオプション、組織タブ、会議室デバイスのセットアップ、検索範囲などの機能を設定できます。 このような設定を変更すると、その変更は組織内のすべてのチームに適用されます。詳細については、「[Teams の設定](enable-features-office-365.md#teams-settings)」を参照してください。

|確認事項|アクション |
|------------|-------|
|自分の組織に合わせて Teams の設定をカスタマイズするか? | Teams の設定とカスタマイズ方法の詳細は、「[Teams の設定](enable-features-office-365.md#teams-settings)」を参照してください。|
|||

### <a name="teams-clients"></a>Teams のクライアント

Teams は、Web からデスクトップ、モバイルまで複数のクライアントをサポートしています。ユーザーは既定の構成で好みのクライアントを選択できます。詳細については、「[Teams のクライアントを取得する](get-clients.md)」を参照してください。

|確認事項|アクション |
|------------|-------|
|自分の組織に合わせて Teams クライアントの利用可能性をカスタマイズするか?|「[Teams アプリのハードウェア要件](hardware-requirements-for-the-teams-app.md)」を確認してください。 |
|自分の組織に合わせて Teams クライアントの設定をカスタマイズするか?|詳細については、「[MSI を使用した Teams のインストール](msi-deployment.md)」を参照してください。|
|||


### <a name="teams-usage-reporting"></a>Teams の使用状況レポート

Office 365 の全体管理者、Teams のサービス管理者、およびレポート閲覧者の役割は、Teams の使用状況レポートを表示できます。 詳細については、「[Microsoft 365 利用状況分析](https://docs.microsoft.com/office365/admin/usage-analytics/usage-analytics?redirectSourcePath=%252farticle%252fMicrosoft-365-usage-analytics-77ff780d-ab19-4553-adea-09cb65ad0f1f&view=o365-worldwide)」の記事を参照してください。

|確認事項|アクション |
|------------|-------|
|<br> 誰が Teams の使用状況レポートの確認を必要としていて、レポートを表示するための適切な役割が割り当てられているか? |<ul><li>そのユーザーが管理者でない場合は、[レポート閲覧者の役割を割り当てます](teams-activity-reports.md#reports-reader-role)。</li><li>Azure Active Directory で管理者の役割を割り当てる方法については、「[役割とアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」および「[役割の表示と割り当て](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)」を参照してください。 |
|||

### <a name="teams-default-apps"></a>Teams の既定のアプリ 

Teams には、複数のファースト パーティ (Microsoft 提供) のアプリとサード パーティ製アプリがあり、ユーザー参加の促進、生産性のサポート、および一般に使用されるビジネス サービスの Teams への統合のために使用できます。 Teams Store からアプリを入手してください。 Teams ではアプリが既定でオンになっています。 

Teams のアプリを展開および管理する方法の詳細については、[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)のガイダンスを参照してください。


## <a name="additional-deployment-decisions"></a>その他の展開に関する決定事項

次の設定は、組織のニーズと構成に基づいて変更できます。

### <a name="teams-licensing"></a>Teams のライセンス

Teams は多くの Office 365 ライセンスの一部として提供されています。 Teams のライセンスの詳細については、「[Teams の Office 365 ライセンス](office-365-licensing.md)」を参照してください。

|確認事項|アクション |
|------------|-------|
|展開しようとしている Teams のすべての機能を使用するために必要なライセンスをユーザーが所持しているか? | ライセンス要件の詳細については、「[Teams の Office 365 ライセンス](office-365-licensing.md)」を参照してください。|
|||

### <a name="exchange-and-sharepoint-interoperability"></a>Exchange と SharePoint の相互運用性 

Teams のすべての機能を活用するために、すべてのユーザーは Exchange Online、SharePoint Online、および Office 365 グループの作成が可能になっている必要があります。 次の記事では、さまざまな環境でホストされている Exchange メールボックス、Exchange と Teams の相互作用のしくみ、および SharePoint と OneDrive for Business に関する同様の考慮事項について概要を示します。 

|確認事項|アクション |
|------------|-------|
| 現在の Exchange および SharePoint の展開で Teams の必要な機能を展開できるか? |Teams での Exchange と SharePoint の詳細については、次を参照してください。<ul><li> [Exchange と Teams の連携](exchange-teams-interact.md)</li><li>[Teams との SharePoint Online と OneDrive for Business の連携](sharepoint-onedrive-interact.md)|
|||

### <a name="teams-limits-and-specifications"></a>Teams の制限と仕様 

Teams のエンタープライズ展開を計画している場合は、1 つのチームの最大メンバー数やユーザーが作成可能なチーム数の上限など、関連する制限と仕様について考慮する必要があります。

|確認事項|アクション |
|------------|-------|
| Teams の展開でどのような制限が問題になる可能性があるか? | 詳細については、「[Teams の制限と仕様](limits-specifications-teams.md)」を参照してください。 |
|||

### <a name="office-365-urls-and-ports"></a>Office 365 の URL とポート

インターネット トラフィックの詳細な制御を維持している組織は、Teams の適切な構成が必要になる URL、IP アドレス、ポート、およびプロトコルに関する最新のリストについて、「[Office 365 の URL と IP アドレス範囲](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)」を確認してください。 マイクロソフトは、必要なポート、URL、IP アドレスが時間の経過とともに変更する可能性があることを踏まえて、継続して Office 365 サービスを改善し、新機能を追加します。 この情報が更新または変更されたときに通知を受け取れるように、RSS で購読することをお勧めします。 少なくとも、前述の「[チャットの展開に関する前提条件](#chat-deployment-prerequisites)」に示したポートが開かれているを確認してください。

|確認事項|アクション |
|------------|-------|
| ユーザーが Teams を使用できるようにするためにインターネット アクセスのルールが必要か、それとも最低限必要なポートを開くだけで十分か? | 詳細については、「[Office 365 の URL と IP アドレス範囲](office-365-urls-ip-address-ranges.md)」を参照してください。|
|||


### <a name="governance-naming-conventions-who-can-create-teams"></a>ガバナンス (命名規則、チームの作成が可能なユーザー)

組織はチームの命名方法と分類方法、チームの作成が許可されるユーザー、チームの有効期限、保持、およびアーカイブに関する制御を実施するように要求することがあります。 これは、ガバナンスと呼ばれます。 Azure Active Directory (Azure AD) を使用すると、こうした分野のそれぞれを構成できます。


| 確認事項 | アクション |
|--------------|--------|
|チームの作成が可能なユーザーに関する制御の実施が必要になるか?| 「[Teams でのガバナンスを計画する](plan-teams-governance.md)」を参照してください。|
|チームの命名に関する制御の実施が必要になるか?|「[Azure Active Directory での Office 365 グループの名前付けポリシーの強制](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)」を参照してください。|
|||

### <a name="teams-application-policy-side-rail-control"></a>Teams のアプリケーション ポリシー (サイドレール制御)

固定アプリは Teams のサイドレールに表示されます。 Teams のアプリケーション ポリシーを作成すると、選択したユーザー グループ用にカスタマイズした固定の Teams アプリのセットを事前に構成できます。 既定では、**[Microsoft Teams で外部ありを利用できるようになります]** 設定がオンになっています。

| 確認事項 | アクション |
|--------------|--------|
|事前に構成した固定の Teams アプリケーションのセットを作成する必要があるか? | 「[Teams でのアプリの管理設定](admin-settings.md)」を参照してください。|
|該当するアプリのグループ化を受け取るグループの決定方法は?|「[Teams アプリのアクセス許可と考慮事項](app-permissions.md)」を参照してください。|
|||

### <a name="archiving-and-compliance"></a>アーカイブとコンプライアンス 

組織は、チームのアーカイブ方法と、特定の種類のチームで保持されるデータの種類に関する制御を実施するように要求することがあります。 既定でオンになっている設定の詳細については、「[Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」を参照してください。

| 確認事項 | アクション |
|--------------|--------|
|チームの保持期間を構成する必要があるか?|保持ポリシーを設定する場合は、「[Teams の保持ポリシーを設定する](retention-policies.md)」を参照してください。|
|チームのアーカイブを構成する必要があるか?|チームをアーカイブまたは復元する場合は、「[チームのアーカイブまたは復元](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)」を参照してください。|
|追加のコンプライアンス設定を構成する必要があるか?|セキュリティとコンプライアンスの詳細については、「[Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」を参照してください。|
|||

### <a name="conditional-access"></a>条件付きアクセス 

Teams は、主要な生産性シナリオ (会議、予定表、相互運用チャット、ファイル共有など) に関して Exchange Online、SharePoint Online、および Skype for Business Online に大きく依存しています。 これらのクラウド アプリ向けに設定された条件付きアクセス ポリシーは、ユーザーが任意のクライアントで Teams に直接サインインするときに Teams に適用されます。 Teams のクラウド アプリ向けに設定された条件付きアクセス ポリシーでは、ユーザーが特定のネットワークから Teams のサービスにアクセスできるかどうかなどの側面を制御します。

| 確認事項 | アクション |
|--------------|--------|
|<br>Teams に対する条件付きアクセスを構成する必要があるか?|<ul><li>アクセス ポリシーのしくみについては、「[Teams で条件付きアクセス ポリシーはどのように機能しますか?](security-compliance-overview.md#how-do-conditional-access-policies-work-for-teams)」を参照してください。</li><li>Teams の多要素認証を設定する場合は、次を参照してください。<ul><li>[クイック スタート: Azure Active Directory の条件付きアクセスを使用して特定のアプリケーションに対して MFA を必要にする](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-mfa)</li><li>[Azure Active Directory の条件付きアクセス設定に関するリファレンス](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference)</li></ul></ul>|
|||


### <a name="education-edu"></a>教育機関 (EDU) 

教育機関の業務に従事する IT 担当者は、教育機関向け Teams を利用できます。この Teams には、学生、教職員、および広範な業務に応じた教育機関に固有のシナリオに適合する多数の機能が備わっています。

| 確認事項 | アクション |
|--------------|--------|
|教育機関固有の Teams テンプレートを使用するか? |教育機関向け Teams の詳細については、「[Microsoft Education ガバナンスに関するよく寄せられる質問 (管理者向け)](plan-teams-governance-edu.md)」を参照してください。|
|範囲設定された検索を展開するか?|教育機関向け Teams をセットアップする場合は、「[クイックスタート: 教育機関向け Teams の管理](teams-quick-start-edu.yml)」を参照してください。|
|ユーザー アカウントのプロビジョニングのために Teams と学校データ同期サービスを統合するか?|[教育機関管理者向けの Teams のリソース](resources-teams-edu.md)|
|||

### <a name="government---gcc-considerations"></a>政府機関: GCC に関する考慮事項

政府機関向け Microsoft 365 (GCC: Government Certificate of Competency) の使用は、米国連邦、州、地方、民族、または領土の政府機関など、政府の規制と要件の対象になるデータを扱う機関で Office 365 の展開を推進している IT 担当者の要件を満たすために適しています。

| 確認事項 | アクション |
|--------------|--------|
| Microsoft 365 Government: GCC 環境に Teams を展開する必要があるか? | 展開に関する考慮事項については、「[Microsoft 365 Government: GCC 展開の計画](plan-for-government-gcc.md)」を参照してください。|
|||

## <a name="next-steps"></a>次のステップ
- チャット、チーム、チャネル、およびアプリの[導入を推進する](adopt-microsoft-teams-landing-page.md)。
- お勧めのアプリ (Planner など) を Teams の初期ロールアウトに組み込む。 Teams 導入の進行に応じて、その他の[アプリ、ボット、およびコネクタ](deploy-apps-microsoft-teams-landing-page.md)を追加してください。
- [ミーティングと会議を展開する](deploy-meetings-microsoft-teams-landing-page.md)
- [クラウド ボイスを展開する](cloud-voice-landing-page.md)

