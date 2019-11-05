---
title: Teams のアドバイザー (プレビュー) を使用して、Microsoft Teams の展開を支援する
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: Teams のアドバイザー (プレビュー) を使用して、Microsoft Teams の展開を計画および完了します。
ms.openlocfilehash: 13c76c61a99869459c0dabcffedc45e06f6fd42e
ms.sourcegitcommit: 2e005b335b1566c99b93fc311498702838466324
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "37931815"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Teams のアドバイザーを使用して、Microsoft Teams の展開を支援する

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Teams のアドバイザー (プレビュー) を使用して、Microsoft Teams の展開について説明します。 Office 365 テナント環境を評価し、Teams を正常に展開する前に更新または変更する必要がある最も一般的な構成を特定します。 次に、Teams のアドバイザーは、展開する各ワークロードのチャネルを備えたサービス管理チーム (チーム内) を作成します。サービス管理チームの各ワークロードには、各ワークロードのすべての展開タスクを含む包括的な Planner の計画が付属しています。  この Planner プランを使用して、プロジェクト マネージャー、Teams および Office 365 の管理者、サポート担当者、導入およびユーザー準備チームなど、展開の各フェーズの責任者にタスクを割り当てます。 各展開タスクには、タスクを正常に完了するために必要なすべてのガイダンスとリソースが含まれています。

Teams のアドバイザーは、[Teams 管理センター](https://admin.teams.microsoft.com)の一部です。 Teams のアドバイザーを初めて使用するには、ダッシュボードの [**チームのワークロードの展開**] ウィジェットの [**開始**] ボタンをクリックします。 または、[**計画**] > [**アドバイザー**] の順に移動します。

> [!IMPORTANT]
> Teams のアドバイザーは、Microsoft 365 Government - GCC High または DoD 展開では使用できません。

## <a name="using-advisor-for-teams-preview"></a>Teams のアドバイザーを使用する (プレビュー)

Teams のアドバイザーを使用するために Teams 管理者である必要はありません。組織内の誰でも使用できます。 Teams 管理センターにあるにもかかわらず、管理者以外のユーザーが Teams のアドバイザーにアクセスできるように、特別なアクセス許可を設定しました。 テナントの準備状況の評価を開くには、Teams 管理者、Teams サービス管理者、またはグローバル管理者である必要があります。

Teams のアドバイザーを初めて使用する場合、Teams でサービス管理チームが作成されます。 展開するワークロードごとにチャネルを追加します。 


## <a name="available-advisor-for-teams-plans"></a>Teams プランの利用可能なアドバイザー

Teams のアドバイザーはプレビュー段階ですが、次の 2 つの計画を提供しています。

1. チャット、チーム、チャネルおよびアプリ
    - テナントの評価
    - 導入タスクを含む Planner プラン
    - Forms のユーザー アンケート
1. ミーティングと会議
    - テナントの評価
    - 導入タスクを含む Planner プラン
    - Forms のユーザー アンケート

チャット、チーム、チャネル、アプリ プランから始めることをお勧めします。 そのワークロードの展開が完了したら、アドバイザーに戻り、[**チャネルの追加**] をクリックして次のワークロードを開始します。 

## <a name="tenant-assessment"></a>テナントの評価
各プランには、Teams を展開する前に環境内の欠陥を特定して修復するために使用できるテナント準備状況の評価が含まれています。 各評価では次のことを確認します。

### <a name="chat-teams-channels-and-apps"></a>チャット、チーム、チャネルおよびアプリ


|評価  |確認できること  |
|---------|---------|
|Teams のライセンス     |使用可能な Teams のライセンスで有効なサブスクリプションを所有しているかどうか |
|Exchange のライセンス     |使用可能な Exchange Online のライセンスで有効なサブスクリプションを所有しているかどうか 基本的な Teams 機能には Exchange は必要ありませんが、Exchange との統合により、最適な Teams エクスペリエンスが可能になります。         |
|SharePoint Online のライセンス     | 使用可能な SharePoint Online のライセンスで有効なサブスクリプションを所有しているかどうか ファイル記憶域、チャネル共同作業、チャット用に、ユーザーごとに 1 つの SharePoint Online のライセンスが必要です。 
|ゲスト アクセスの有効化     |Teams でゲスト アクセスが有効になっている場合。 ゲスト アクセスの Azure Active Directory 設定は確認されません。   |
|構成済みのバニティ ドメイン     |テナント用に @onmicrosoft.com 以外のドメインが構成されているかどうか  |
|構成済みの Office 365 グループの名前付け基準     | 名前付け基準が Office 365 グループ用に構成されているかどうか        |
|構成済みの Office 365 グループの有効期限     |  グループの有効期限ポリシーが Office 365 グループに対して定義されているかどうか そうでない場合、値は [なし] に設定されます。        |
|構成済み外部アクセス     |外部アクセスがオンになっていて、Teams の外部組織と通信できる場合。          |

### <a name="meetings-and-conferencing"></a>ミーティングと会議


|評価  |確認できること  |
|---------|---------|
|Teams のライセンス     |使用可能な Teams のライセンスで有効なサブスクリプションを所有しているかどうか |
|Exchange のライセンス     |使用可能な Exchange Online のライセンスで有効なサブスクリプションを所有しているかどうか 基本的な Teams 機能には Exchange は必要ありませんが、Exchange との統合により、最適な Teams エクスペリエンスが可能になります。 |
|電話会議のライセンス    |電話会議のライセンスの有効なサブスクリプションを所有しているかどうか |
|ストリームのライセンス     |会議の記録が必要な場合に使用できる、ストリームのライセンスの有効なサブスクリプションがあるかどうか |
|ゲスト アクセス     |Teams でゲスト アクセスが有効になっている場合。 ゲスト アクセスの Azure Active Directory 設定は確認されません。|
|バニティ ドメイン     |テナント用に @onmicrosoft.com 以外のドメインが構成されているかどうか  |
|外部アクセス     |外部アクセスがオンになっていて、Teams の外部組織と通信できる場合。 |


### <a name="advisor-bot"></a>アドバイザー ボット
アドバイザーがサービス管理チームを作成すると、アドバイザー ボットは次のメッセージを配信します。

>**Microsoft Teams のサービス管理チームへようこそ!**
>  
>このチームの目的は、必要なすべてのリソースとプロジェクト チームに共同作業スペースを提供することにより、組織の Teams の展開について説明することです。 Teams のアドバイザーを使用して作成された各チャネルには、段階的な Planner プランと、展開全体で使用できる Forms のユーザー アンケートなどの他のリソースが含まれています。 いつでも戻って、テナントの準備状況の評価を確認したり、Teams 管理センターを使用してワークロード計画を追加したりできます。 
> 
>**実施すべき内容** 
>- Teams または Planner を初めて使用する場合は、「[Teams のチュートリアル](https://teamsdemo.office.com/)」を確認し、「[Planner クイックスタート ビデオ](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)」をご覧ください。 
>- Teams のサービス管理チームを見てみます。 ワークロード チャネル (チャット、チーム、チャネル、アプリなど) を選択し、[**Planner**] タブを選択して開始します。
> 
>Teams のアドバイザーの詳細については、「[Teams のアドバイザーを使用して Microsoft Teams を展開する](use-advisor-teams-roll-out.md)」を参照してください。
>
> [!IMPORTANT]
> Teams のアドバイザー ボットは、サービス管理チームにウェルカム メッセージを送信するためにのみ使用されます。 追加のデータは収集されません。

> [!IMPORTANT]
> Teams のアドバイザー ボットは既定で有効になっています。 Teams のアドバイザーを使用または使用する予定の場合は、無効にしないでください。


## <a name="frequently-asked-questions"></a>よく寄せられる質問
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Teams のアドバイザーのライセンス要件は何ですか?
Teams 用のライセンスにされる以外に、追加のライセンス要件はありません。

### <a name="can-i-delete-the-service-management-team"></a>サービス管理チームを削除できますか?
Teams のアドバイザーがサービス管理チームを作成した後、他のチームと同様にチームを管理できます。これには削除機能も含まれます。 Teams 管理センターを使用してチームを削除しない場合、チームの存在が報告されることに注意してください。

### <a name="can-i-add-or-remove-channels-in-the-service-management-team"></a>サービス管理チームでチャネルを追加または削除できますか?
はい。サービス管理チームが作成されたら、他のチームと同じ方法でチャネルを管理できます。

### <a name="can-i-add-or-remove-project-team-members-in-the-service-management-team"></a>サービス管理チームでプロジェクト チームのメンバーを追加または削除できますか?
はい。サービス管理チームが作成されたら、他のチームと同じ方法で管理できます。

### <a name="can-i-modify-the-planner-plans"></a>Planner プランを変更できますか?
はい。Teams のアドバイザーがサービス管理チームを作成した後、Teams の展開を最適にサポートするために Planner プランを更新する必要があります。 他の Planner プランと同様に、バケット、タスク、タスク詳細など、何でも変更できます。


### <a name="can-i-modify-the-forms-survey"></a>Forms アンケートを変更できますか?
はい。Teams のアドバイザーがサービス管理チームを作成した後、必要に応じて Forms アンケートを変更できます。

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Teams のアドバイザーは自分の組織についてどのような情報を収集しますか?
Teams のアドバイザーは、非 EUII (エンド ユーザー識別情報) の収集に関する同意を要求します。 収集される情報はテレメトリーの形式であり、Teams のアドバイザーがどの程度成果を上げているのか、改善すべきところはどこなのか​​について、Microsoft にフィードバックを提供します。 このデータは、Microsoft が展開を支援するために組織と積極的に連携する機会を特定するために使用されます。

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>FastTrack で Teams のアドバイザーを使用できますか?
はい。FastTrack では、Teams の展開を検討しているすべての顧客に対して Teams のアドバイザーを活用しています。 FastTrack は、Teams のアドバイザー (必要な場合) を使用してサービス管理チームの初期セットアップを支援し、Teams の展開中に特定のトピックに関する必要に応じたサポートも提供します。

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>パートナーで Teams のアドバイザーを使用できますか?
はい。Teams の展開に展開パートナーを使用しながら、Teams のアドバイザーを使用できます。 パートナーが CSP であり、顧客の代わりにテナントを管理している場合、Teams のアドバイザーを使用してサービス管理チームを作成し、プロジェクト全体の実行を支援できます。 さらに、サービス管理チームにゲストとしてそれらの個人を追加して、プロジェクト チーム全体のメンバーとして参加できるようにすることで、パートナーと連携できます。

### <a name="how-do-i-use-planner"></a>Planner を使用するにはどうすればよいですか?
「[Microsoft Planner のヘルプ](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)」と「[Planner のクイック スタート ビデオ](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)」をご覧ください。 

### <a name="how-do-i-use-forms"></a>Forms を使用するにはどうすればよいですか?
「[Forms ヘルプ センター](https://support.office.com/forms)」に移動します。

## <a name="related-topics"></a>関連トピック

[Teams の展開方法](How-to-roll-out-teams.md)
