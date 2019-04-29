---
title: Teams でのガバナンスを計画する - Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 08/10/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
description: Teams でガバナンスを実施するための計画を立てる方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b4e6d7c647c619baf5a890b74b2e807dbc111ca0
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401714"
---
# <a name="plan-for-governance-in-teams"></a>Teams でのガバナンスを計画する

Teams には組織が必要とする可能性のあるガバナンス機能を実装するための豊富なツールセットが用意されています。この記事では、IT プロフェッショナルが、ガバナンスに関する組織の要件と、その要件を満たす方法を判断する際に適切な質問をするためのガイドを示します。 

> [!Tip] 
> Microsoft Teams でのガバナンスの詳細については、次のセッションをご覧ください。[Microsoft Teams でのガバナンス、管理、およびライフサイクル](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>グループおよびチームの作成、名前付け、分類、およびゲスト アクセス

自分の組織において、チームの命名や分類について、ゲストがチーム メンバーとして追加することができるかどうかについて、チームを作成できるユーザーが誰であるかについて、厳密な制御の実施が必要な場合があります。この各領域は Azure Active Directory (Azure AD) を使って設定できます。 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断ポイント|<ul><li>自分の組織において、チームについての特定の名前付け規則はありますか?</li><li>チーム作成者は組織固有の分類をチームに割り当てる機能を必要としていますか?</li><li>チームにゲストを追加する機能を、チーム単位で制限する必要はありますか?</li><li>自分の組織において、チームを作成可能なユーザーを制限する必要はありますか?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次の手順|<ul><li>チームの作成、名前付け、分類、およびゲスト アクセスについて、自分の組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

> [!TIP]
> 次の表を使用して、組織の要件を把握します。

|機能 |詳細 |Azure AD プレミアム <br> ライセンス必要 |Decision |
|---------|---------|---------|---------|
|Team の名前付けポリシー | プレフィックス サフィックスに基づくカスタム ブロックの単語を使用します。 |P1 |TBD |
|チーム分類 |チームに分類を割り当てます。 |P1 |TBD |
|チームのゲスト アクセス |ゲストがチームに追加されるのを許可または禁止します。 |いいえ |TBD |
|チームの作成 |チームの作成を管理者に限定します。 |いいえ |TBD|
|チームの作成 |チームの作成をセキュリティ グループのメンバーに限定します。 |P1 |TBD|

> [!NOTE]
> 事前に計画を立てやすくなるために、[これらのポリシーの設定について、およびどのライセンスが必要とされるかについて確認してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。
> 
> [!NOTE]
> グループおよびチームの作成を制限すると、多くの Office 365 サービスは、そのサービスが機能するためのグループの作成が必要になり、ユーザーの生産性が低下することがあります。詳細については、「[Office 365 グループの作成ユーザーを制御する理由](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)」に移動して参考にしてください。


#### <a name="additional-information"></a>追加情報

要件の決定後、Azure AD のコントロールを使用してその要件を実装できます。これらの設定を実装する方法に関する技術面のガイダンスは、次をご覧ください。

-   [グループ設定を構成するための Azure Active Directory コマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。

-   [Azure Active Directory での Office 365 グループの名前付けポリシーの強制](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。

-   [Office 365 グループの名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。


## <a name="group-and-team-expiration-retention-and-archiving"></a>グループとチームの有効期限、保持、およびアーカイブ化

組織には、有効期限、保持、チームとチームデータ (チャネル メッセージとチャネル ファイル) のアーカイブに関するポリシーの設定に追加の要件がある場合があります。グループの有効期限ポリシーを設定すると、自動でグループポリシーと保持ポリシーを管理して、必要に応じて情報を保存または削除できます。チーム (読み取り専用モードに設定) をアーカイブし、アクティブでなくなったチームのその時のビューを保存します。

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>組織はチームに有効期限日を指定することを必要としていますか?</li><li>自分の組織でチームに特定のデータ保持ポリシーを適用する必要はありますか?</li><li>自分の組織で、コンテンツを読み取り専用の状態で保存するために、非アクティブなチームをアーカイブ化する機能が必要となる見込みはありますか?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>有効期限、データ保持、アーカイブ化についての組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

> [!TIP]
> 次の表を使用して、組織の要件を把握します。

|機能 |詳細 |Azure AD Premium ライセンスが必要 |Decision |
|---------|---------|---------|---------|
|有効期限ポリシー |有効期限ポリシーを設定することにより、Office 365 グループのライフ サイクルを管理します。 |P1 |TBD|
|アイテム保持ポリシー |セキュリティ/コンプライアンス センターで Teams の保持ポリシーを設定して、特定の期間内のデータを保持または削除します。**注:** この機能を使用するには、Office 365 Enterprise E3 以上のライセンスが必要です。 |いいえ |TBD |
|アーカイブと復元 |チームがアクティブでなくなったときにチームをアーカイブして、参照用または将来再アクティブ化するために保持します。 |いいえ |TBD |

> [!Note]
> グループの有効期限は、Azure AD Premium の機能です。この機能を使えるようにするには、お使いのテナントに、設定と影響を受けるグループのメンバーを構成する管理者の Azure AD Premium とライセンスへのサブスクリプションが必要です。

#### <a name="additional-information"></a>追加情報

これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。

-   [Office 365 グループの有効期限をセットアップする](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

-   [Teams の保持ポリシーをセットアップする](retention-policies.md).

-   [チームをアーカイブする、または復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)


## <a name="teams-feature-management"></a>Teams 機能の管理

Teams のガバナンスとライフ サイクル管理における別の重要な側面は、ユーザーがアクセスできる機能の制御が可能なことです。メッセージング、会議、通話の機能、Office 365 のテナント レベルまたはユーザーごとのいずれかの機能を管理できます。 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>自分の組織で、テナント全体に対して Teams 機能を制限することが必要ですか?</li><li>自分の組織で、特定のユーザーに対して Teams 機能を制限することが必要ですか?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>テナントおよびユーザー レベルで Teams の機能を制限するための組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、特定の要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams の機能管理での重点領域

Teams にはポリシーを介して、メッセージング、会議、通話、ライブ イベントの機能などを制御するための詳細な機能が用意されています。既定ではすべてのユーザー、または組織で必要となるユーザーそれぞれに異なるポリシーを適用できます。 

自分の組織での各設定の実行についての技術的なガイダンスを含む、すべての設定の詳細なリストについては、次の記事を参照してください。

-   [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)
-   [新しい Microsoft Teams 管理センターへの移行中に Teams を管理する](manage-teams-skypeforbusiness-admin-center.md)
-   [Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a>セキュリティとコンプライアンス

Teams は Office 365 の高度なセキュリティおよびコンプライアンス機能に基づいて構築されており、監査および報告、コンプライアンスのコンテンツ検索、電子情報開示、訴訟ホールド、および保持ポリシーをサポートします。 

> [!Important]
> 自分の組織でコンプライアンスおよびセキュリティに関する要件がある場合は、「[Microsoft Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」の記事で、このトピックについての掘り下げた内容を確認してください。

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
