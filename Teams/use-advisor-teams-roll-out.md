---
title: Teams のアドバイザー (パブリック プレビュー) を使用して、Microsoft Teams の展開を支援する
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ''
description: Teams のアドバイザー (パブリック プレビュー) を使用して、Microsoft Teams の展開を計画および完了します。
ms.openlocfilehash: 79273c0c0d96bf5f7c52399310bffce433928e2b
ms.sourcegitcommit: c3f44fccdbd9178d30b52bb0db6f6d31a6dd174b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139200"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Teams のアドバイザーを使用して、Microsoft Teams の展開を支援する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Teams のアドバイザー (パブリック プレビュー) を使用して、Microsoft Teams の展開について説明します。 Office 365 組織の環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。 次に、Teams のアドバイザーは、展開する各ワークロードのチャネルを備えた展開チーム (チーム内) を作成します。展開チームの各ワークロードには、各ワークロードのすべての展開タスクを含む包括的な Planner の計画が付属しています。  この Planner プランを使用して、プロジェクト マネージャー、Teams および Office 365 の管理者、サポート担当者、導入およびユーザー準備チームなど、展開の各フェーズの責任者にタスクを割り当てます。 各展開タスクには、タスクを正常に完了するために必要なすべてのガイダンスとリソースが含まれています。

Teams のアドバイザーは、[Teams 管理センター](https://admin.teams.microsoft.com)の一部です。 Teams を Forms および Planner と統合させるためのアドバイザーを活用するには、少なくとも Microsoft 365 Business Basic ライセンスが必要です。 Teams のアドバイザーの使用を開始するには、ダッシュボードの [**チームのワークロードの展開**] ウィジェットの [**開始**] ボタンをクリックします。 または、[**計画**] > [**Teams アドバイザー**] の順に移動します。

> [!IMPORTANT]
> Teams のアドバイザーは、Microsoft 365 Government - GCC High または DoD 展開では使用できません。

Teams のアドバイザー エクスペリエンスのガイド付きの概要については、Microsoft Mechanics のビデオ「[Deploy & Configure Microsoft Teams (Microsoft Teams の展開と構成)](https://youtu.be/o2mlsUubIO4?t=50)」をご覧ください。

## <a name="using-advisor-for-teams-public-preview"></a>Teams のアドバイザーを使用する (パブリック プレビュー)

**Teams アドバイザーを使用するには、Teams、Forms、および Planner のライセンスが必要です。** ただし、Teams アドバイザーを使用するために Teams 管理者である必要はありません。組織内の誰でも使用できます。 Teams 管理センターにあるにもかかわらず、管理者以外のユーザーが Teams のアドバイザーにアクセスできるように、特別なアクセス許可を設定しました。 テナント準備状況アセスメントを開くには、Teams 管理者、Teams サービス管理者、またはグローバル管理者である必要があります (これは、特別な非管理者ロールが評価の基となる Microsoft Graph API にアクセスできないためです)。

> [!IMPORTANT]
> **Teams アドバイザー**が Teams 管理センターの [**計画**] の下に表示されていない場合、ユーザーは Teams のライセンスを取得していません。 この動作は、今後変更されます。

Teams のアドバイザーを初めて使用する場合、Teams で展開チームが作成されます。 選択したワークロードごとにチャネルが追加されます。

> [!IMPORTANT]
> 展開チームが既に作成されていて、別のユーザーが作成しようとすると、サポート チームに連絡するように指示するエラーが表示されます。 これにより、Teams が既存のチームとそのメンバーに関する情報を意図せずに開示することを防ぎます。 展開チームの所有者に追加を依頼するか、サポート担当者に連絡してください。

## <a name="available-advisor-for-teams-plans"></a>Teams のアドバイザーの利用可能なプラン

Teams のアドバイザーはパブリック プレビュー中ですが、以下 2 つのプランを提供しています。

1. チャット、チーム、チャネルおよびアプリ
    - テナントの評価
    - 導入タスクを含む Planner プラン
    - Forms のユーザー アンケート
    - Teams のアドバイザー ボット
1. ミーティングと会議
    - テナントの評価
    - 導入タスクを含む Planner プラン
    - Forms のユーザー アンケート
    - Teams のアドバイザー ボット
1. Skype for Business のアップグレード
    - テナントの評価
    - 導入タスクを含む Planner プラン
    - Forms のユーザー アンケート
    - Teams のアドバイザー ボット
    - Skype for Business のアップグレード プランは、現在 Skype for Business Online またはオンプレミス環境で Skype for Business をご利用のお客様向けに設計されており、アップグレードの行程を正確に把握できるようになっています。 このプランでは、Teams を使い始めたばかりのお客様、Skype for Business と併せて既に Teams を使用しているお客様、あるいはアップグレードの準備ができているお客様のすべてに、変更の実装に実績のあるフレームワークを利用してステップ バイ ステップでアップグレードのプロセスを案内します。 このプランではさらに、[オンライン ガイダンスとベスト プラクティス](https://aka.ms/SkypeToTeams)、[ダウンロード可能なリソース ファイル](https://aka.ms/UpgradeSuccessKit)、[ライブでの 1 対多のアップグレード計画ワークショップ](https://aka.ms/UpgradeWorkshops)の他、成功を支援するさまざまなリソースにアクセスできます。

チャット、チーム、チャネル、アプリ プランから始めることをお勧めします。 そのワークロードの展開が完了したら Teams のアドバイザーに戻り、[**チャネルの追加**] をクリックして次のワークロードを開始します。

## <a name="tenant-assessment"></a>テナントの評価
各プランには、Teams を展開する前に修復が必要な環境についての状況を迅速に特定するために使用できるテナント準備状況アセスメントが含まれています。 アセスメントには、前提条件とベスト プラクティスが含まれています。 各アセスメント テストには、緑色のチェック マークまたはオレンジ色の警告三角形が付いています。 

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>緑色のチェックマークは、テナントが特定のテストに合格したことを意味しています。 
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>オレンジ色の警告の三角形は、何らかのアクションが必要かどうかを判断するためのフォロー アップを推奨していることを意味します (たとえば、Office 365 グループの有効期限ポリシーが推奨されますが、必須ではありません)。

> [!IMPORTANT]
> 管理者ロールを持つユーザーが Teams のアドバイザーを開始すると、すべてのアセスメントがバックグラウンドで実行されます。 何かを更新または修復した場合、最大 24 時間はアセスメントに反映されないことがあります。 これは一時的なものです。Teams のアドバイザーがパブリック プレビューを終了して一般公開されるとすぐに、アセスメントはほぼリアルタイムで更新されます。

以下のセクションでは、何らかの前提条件が存在するか、またはベスト プラクティスであるか、各アセスメント チェックの実行内容および理由、必要に応じた修復のガイダンスなど、各アセスメントについて説明します。

### <a name="assessment-tests-for-all-workloads"></a>すべてのワークロードのアセスメント テスト

|アセスメント テスト  |確認できること  |
|---------|---------|
|構成済みのバニティ ドメイン     |テナント用に構成された @onmicrosoft.com 以外のドメイン (たとえば、@contoso.onmicrosoft.com) があるかどうか。 もちろん、@onmicrosoft.com ドメインを使用することも、バニティ ドメインを構成することもできます (任意)。 詳細については、「[Office 365 にドメインを追加する](https://docs.microsoft.com/office365/admin/setup/add-domain)」をご覧ください。 |
|Teams のライセンス     |これは前提条件です。Teams を展開するには、Teams ライセンスが**必須です**。 Microsoft Graph 内を検索して、(割り当て可能なライセンスが少なくとも 1 つはある) Teams ライセンスがあるかどうかを確認します。 詳細については、「[Microsoft Teams サービスのサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)」を参照してください。    |
|Exchange Online ライセンス     |使用可能な Exchange Online のライセンスで有効なサブスクリプションを所有しているかどうか 基本的な Teams 機能には Exchange は必要ありませんが、Exchange との統合により、最適な Teams エクスペリエンスが可能になります。 Microsoft Graph 内を検索して、テナントに関連付けられているサブスクリプションを分析し、対象の (割り当て可能なライセンスが少なくとも 1 つはある) Exchange Online ライセンスのサブスクリプションがあるかどうかを検証します。 詳細については、「[Exchange と Teams の連携](exchange-teams-interact.md)」をご覧ください。    |
|SharePoint Online のライセンス     |使用可能な SharePoint Online のライセンスで有効なサブスクリプションを所有しているかどうか チャットのファイル ストレージに OneDrive for Business を提供する場合、ユーザーごとに SharePoint Online ライセンスを所有することをお勧めします。 Microsoft Graph 内を検索して、(割り当て可能なライセンスが少なくとも 1 つはある) SharePoint Online ライセンスがあるかどうかを確認します。 詳細については、[Teams との SharePoint Online と OneDrive for Business の連携](https://docs.microsoft.com/microsoftteams/sharepoint-onedrive-interact)をご覧ください。    |
|ゲスト アクセスの有効化     |[ゲスト アクセス](guest-access.md)が有効になっているかどうか。 ゲスト アクセスを使用すると、外部ユーザーをチームに招待できます。 [Teams のゲスト アクセスのチェックリスト](guest-access-checklist.md)を使用して、Teams でゲスト アクセスを有効にします。チェックリストには、必要な Azure AD 構成が含まれています。 |
|構成済み外部アクセス     |[外部アクセス](manage-external-access.md)が有効になっているかどうか。 規定では、オープン フェデレーションで有効になっています。 |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>チャット、チーム、チャンネル、アプリのアセスメント

[すべてのワークロードのアセスメント テスト](#assessment-tests-for-all-workloads)に加えて、チャット、チーム、チャネル、アプリのワークロードに対して以下の追加アセスメントが実行されます。

|アセスメント テスト  |確認できること  |
|---------|---------|
|構成済みの Office 365 グループの名前付けポリシー     |名前付け基準が Microsoft 365 グループ用に構成されているかどうか。 Microsoft 365 グループの名前付けポリシーにより、組織はユーザーが作成したチームに対して一貫した名前付け戦略を適用でき、他のグループ ワークロード (Outlook、SharePoint、Planner、Yammer を含む) にも適用できます。 このテストでは、Microsoft Graph を介して Azure AD にクエリを実行し、Microsoft 365 グループに適用される名前付けポリシーの存在を確認します。 詳細については、「[Office 365 Group naming policy (Office 365 グループの名前付けポリシー)](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)」を参照してください。    |
|構成済みの Office 365 グループ有効期限ポリシー     |Microsoft 365 グループに対してグループ有効期限ポリシーが定義されているかどうか。 これにより、組織は非アクティブなチームを自動的に削除できます。 規定ではオフになっています。 このテストでは、Microsoft Graph を介して Azure AD にクエリを実行し、値が規定から変更されたかどうかを報告します。 詳細については、「[Office 365 グループの有効期限ポリシー](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy)」を参照してください。    |

### <a name="assessments-for-meetings-and-conferencing"></a>ミーティングと会議のアセスメント

[すべてのワークロードのアセスメント テスト](#assessment-tests-for-all-workloads)に加えて、ミーティングおよび会議のワークロードに対して以下の追加アセスメントが実行されます。

|アセスメント テスト  |確認できること  |
|---------|---------|
|電話会議のライセンス    |電話会議のライセンスの有効なサブスクリプションを所有しているかどうか。 これは、電話会議ブリッジを展開する場合の前提条件です。 Microsoft Graph を照会して、(割り当て可能なライセンスが少なくとも 1 つはある) 音声会議ライセンスがあるかどうかを確認します。詳細については、「[Teams アドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。    |
|Stream のライセンス     |使用可能な Microsoft Stream のライセンスで有効なサブスクリプションを所有しているかどうか。 これは、会議の記録を有効にする場合の前提条件です。 Microsoft Graph 内を検索して、(割り当て可能なライセンスが少なくとも 1 つはある) Microsoft Stream ライセンスがあるかどうかを確認します。 Stream の詳細および有効化の方法については、「[Teams のクラウド会議の記録](cloud-recording.md)」をご覧ください。

### <a name="assessments-for-skype-for-business-upgrade"></a>Skype for Business のアップグレードのアセスメント
[すべてのワークロードのアセスメント テスト](#assessment-tests-for-all-workloads)に加え、Skype for Business のアップグレードには会議や会議プランで使用するアセスメントも含まれています。

### <a name="advisor-for-teams-bot"></a>Teams のアドバイザー ボット

Teams のアドバイザーが展開チームを作成すると、アドバイザー ボットは全般チャネルで以下のメッセージを配信します。

>**Microsoft Teams の展開チームへようこそ!**
>  
>このチームの目的は、必要なすべてのリソースとプロジェクト チームに共同作業スペースを提供することにより、組織の Teams の展開について説明することです。 Teams のアドバイザーを使用して作成された各チャネルには、段階的な Planner プランと、展開全体で使用できる Forms のユーザー アンケートなどの他のリソースが含まれています。 いつでも戻って、テナントの準備状況の評価を確認したり、Teams 管理センターを使用してワークロード計画を追加したりできます。
> 
>**実施すべき内容** 
>- Teams または Planner を初めて使用する場合は、「[Teams のチュートリアル](https://teamsdemo.office.com/)」を確認し、「[Planner クイックスタート ビデオ](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)」をご覧ください。 
>- Teams の展開チームを見てみます。 ワークロード チャネル (チャット、チーム、チャネル、アプリなど) を選択し、[**Planner**] タブを選択して開始します。
> 
>Teams のアドバイザーの詳細については、「[Teams のアドバイザーを使用して Microsoft Teams を展開する](use-advisor-teams-roll-out.md)」を参照してください。
>

> [!IMPORTANT]
> Teams のアドバイザー ボットは、展開チームにウェルカム メッセージを送信するためにのみ使用されます。 追加のデータは収集されません。

> [!IMPORTANT]
> Teams のアドバイザー ボットは既定でオンになっています。 Teams のアドバイザーを使用または使用する予定の場合は、オフにしないでください。

## <a name="frequently-asked-questions"></a>よく寄せられる質問
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Teams のアドバイザーのライセンス要件は何ですか?
Teams を Forms および Planner と統合させるためのアドバイザーを活用するには、少なくとも Microsoft 365 Business Basic が必要です。

### <a name="can-i-delete-the-deployment-team"></a>展開チームを削除できますか?
Teams のアドバイザーが展開チームを作成した後、他のチームと同様にチームを管理できます。これには削除機能も含まれます。 Teams 管理センターを使用しチームを削除しない場合、Teams 管理センターはチームがまだ存在していることを表示することに注意してください。 これは一時的なものです。Teams のアドバイザーがパブリック プレビュー期間を終了し、一般公開されると修正されます。

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>展開チームでチャネルを追加または削除できますか?
はい。展開チームが作成されたら、他のチームと同じ方法でチャネルを管理できます。

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>展開チームでプロジェクト チームのメンバーを追加または削除できますか?
はい。展開チームが作成されたら、他のチームと同じ方法で管理できます。

### <a name="can-i-modify-the-planner-plans"></a>Planner プランを変更できますか?
はい。Teams のアドバイザーが展開チームを作成した後、Teams の展開を最適にサポートするために Planner プランを更新する必要があります。 他の Planner プランと同様に、バケット、タスク、タスク詳細など、何でも変更できます。

### <a name="can-i-modify-the-forms-survey"></a>Forms アンケートを変更できますか?
はい。Teams のアドバイザーが展開チームを作成した後、必要に応じて Forms アンケートを変更できます。

### <a name="are-there-any-differences-between-advisor-for-teams-in-gcc"></a>GCC での Teams のアドバイザーとの間の違いはありますか?
はい。GCC では現在 Teams Forms アプリを使用できないため、Forms のユーザー アンケートは作成されますがプランのチャネルにはピン留めされません。

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Teams のアドバイザーは自分の組織についてどのような情報を収集しますか?
Teams のアドバイザーは、非 EUII (エンド ユーザー識別情報) の収集に関する同意を要求します。 収集される情報はテレメトリーの形式であり、Teams のアドバイザーがどの程度成果を上げているのか、改善すべきところはどこなのか​​について、Microsoft にフィードバックを提供します。 このデータは、Microsoft が展開を支援するために組織と積極的に連携する機会を特定するために使用されます。

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>FastTrack で Teams のアドバイザーを使用できますか?
はい。FastTrack では、Teams の展開を検討しているすべての顧客に対して Teams のアドバイザーを活用しています。 FastTrack は、Teams のアドバイザー (必要な場合) を使用して展開チームの初期セットアップを支援し、Teams の展開中に特定のトピックに関する必要に応じたサポートも提供します。

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>パートナーで Teams のアドバイザーを使用できますか?
はい。Teams の展開に展開パートナーを使用しながら、Teams のアドバイザーを使用できます。 パートナーが CSP であり、顧客の代わりにテナントを管理している場合、Teams のアドバイザーを使用して展開チームを作成し、プロジェクト全体の実行を支援できます。 さらに、展開チームにゲストとしてそれらの個人を追加して、プロジェクト チーム全体のメンバーとして参加できるようにすることで、パートナーと連携できます。

### <a name="how-do-i-use-planner"></a>Planner を使用するにはどうすればよいですか?
「[Microsoft Planner のヘルプ](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)」と「[Planner のクイック スタート ビデオ](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)」をご覧ください。 

### <a name="how-do-i-use-forms"></a>Forms を使用するにはどうすればよいですか?
「[Forms ヘルプ センター](https://support.office.com/forms)」に移動します。

## <a name="related-topics"></a>関連トピック

[Teams の展開方法](How-to-roll-out-teams.md)

[Teams でチームを編成するためのベスト プラクティス](best-practices-organizing.md)

[ライセンスのための製品名とサービス プラン識別子](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference
)
