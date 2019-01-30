---
title: Teams でのガバナンスを計画する - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 08/10/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Teams でガバナンスを実施するための計画を立てる方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: db98b9b5ab460207b2dd9f9a793a486402ec29fd
ms.sourcegitcommit: 788e3526ff973454f3904c33d867691a2fae814f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "28326867"
---
# <a name="plan-for-governance-in-teams"></a>Teams でのガバナンスを計画する

Teams には、自分の組織で必要となるあらゆるガバナンス機能を実施するための豊富なツールのセットが用意されています。 この記事では、正しい質問を通して、IT 専門家が自分たちのガバナンスの要件を判断したり、それらを満たすための方法を決めたりすることができるようになるガイドを提供します。 

> [!Tip] 
> Microsoft Teams でのガバナンスの詳細については、次のセッションをご覧ください。[Governance, management and lifecycle in Microsoft Teams (Microsoft Teams でのガバナンス、管理、およびライフサイクル)](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>グループおよびチームの作成、名前付け、分類、およびゲスト アクセス

自分の組織において、チームの命名や分類について、ゲストがチーム メンバーとして追加することができるかどうかについて、およびチームを作成することができるユーザーが誰であるかについて、厳密な制御を実施する必要がある可能性があります。 これらの各領域について、Azure Active Directory (Azure AD) を使用して構成することができます。 

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|判断ポイント|<ul><li>自分の組織において、チームについての特定の名前付け規則はありますか?</li><li>チーム作成者は組織固有の分類をチームに割り当てる機能を必要としていますか?</li><li>チームにゲストを追加する機能を、チーム単位で制限する必要はありますか?</li><li>自分の組織において、チームを作成可能なユーザーを制限する必要はありますか?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|次のステップ|<ul><li>チームの作成、名前付け、分類、およびゲスト アクセスについて、自分の組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

> [!TIP]
> 次の表を使用して、組織の要件を把握します。

|機能 |詳細 |Azure AD プレミアム <br> ライセンス必要 |判断 |
|---------|---------|---------|---------|
|Team の名前付けポリシー | プレフィックス/サフィックスの形式の、カスタムの禁止語句を使用します。 |P1 |TBD |
|チーム分類 |チームに分類を割り当てます。 |P1 |TBD |
|チームのゲスト アクセス |ゲストがチームに追加されるのを許可または禁止します。 |なし |TBD |
|チームの作成 |チームの作成を管理者に制限します。 |なし |TBD|
|チームの作成 |チームの作成をセキュリティ グループ メンバーに制限します。 |P1 |TBD|

> [!NOTE]
> 事前に計画を立てやすくなるために、[これらのポリシーの設定について、およびどのライセンスが必要とされるかについて確認してください](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。
> 
> [!NOTE]
> グループおよびチームの作成を制限することにより、自分たちのユーザーの生産性が下がる可能性があります。これは、多くの Office 365 サービスで、サービスが機能するためにグループが作成されることが必要となるためです。 詳細については、「[Office 365 グループを作成するユーザーを制御する理由](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)」に移動して展開してください。


#### <a name="additional-information"></a>追加情報

自分の要件を判別した後、Azure AD の制御を使用してそれらを実施することができます。 これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。

-   [グループ設定を構成するための Azure Active Directory コマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。

-   [Azure Active Directory での Office 365 グループの名前付けポリシーの強制](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)。

-   [Office 365 グループの名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。


## <a name="group-and-team-expiration-retention-and-archiving"></a>グループとチームの有効期限、保持、およびアーカイブ化

自分の組織で、有効期限、保持、チームおよびチームのデータ (チャネルのメッセージとチャネルのファイル) をアーカイブ化することについてのポリシーを設定するための追加の要件がある可能性があります。 グループの有効期限ポリシーを構成して、グループのライフサイクルや、必要に応じて情報の保存や削除を行うための保持ポリシーを自動的に管理することができます。また、チームをアーカイブ化して (読み取り専用モードに設定して)、アクティブでなくなったチームについて特定の時点の表示を保存することができます。

|           |            |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>自分の組織でチームについて有効期限日を指定する必要はありますか?</li><li>自分の組織でチームに特定のデータ保持ポリシーを適用する必要はありますか?</li><li>自分の組織で、コンテンツを読み取り専用の状態で保存するために、非アクティブなチームをアーカイブ化する機能が必要となる見込みはありますか?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>有効期限、データ保持、アーカイブ化についての組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

> [!TIP]
> 次の表を使用して、組織の要件を把握します。

|機能 |詳細 |Azure AD Premium ライセンスが必要 |判断 |
|---------|---------|---------|---------|
|有効期限ポリシー |有効期限ポリシーを設定して、Office 365 グループのライフサイクルを管理します。 |P1 |TBD|
|保持ポリシー |セキュリティ/コンプライアンス センター内で Teams の保持ポリシーを設定することによって特定の期間におけるデータを保持または削除します。 **注**: この機能の使用には Office 365 Enterprise E3 またはそれ以降のライセンスが必要です。 |なし |TBD |
|アーカイブ化と復元 |アクティブでなくなったチームを、参照用として保持する目的で、または将来的に再びアクティブ化する可能性がある場合に備えて、アーカイブ化します。 |なし |TBD |

> [!Note]
> グループの有効期限は、Azure AD Premium の機能です。 この機能を利用できるようにするためには、Azure AD Premium に対するサブスクリプションと、影響を受けるグループの設定およびメンバーを構成する管理者のためのライセンスが存在している必要があります。

#### <a name="additional-information"></a>追加情報

これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。

-   [Office 365 グループの有効期限をセットアップする](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

-   [Teams の保持ポリシーをセットアップする](retention-policies.md).

-   [チームをアーカイブする、または復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)


## <a name="teams-feature-management"></a>Teams 機能の管理

Teams でのガバナンスおよびライフサイクル管理のもう 1 つの重要な側面として、自分たちのユーザーがどの機能にアクセスするかを制御する機能があります。 メッセージング、会議、通話機能を Office 365 のテナントレベル、またはユーザー単位のいずれかで管理することができます。 


|         |         |
|---------|---------|
| ![](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>自分の組織で、テナント全体に対して Teams 機能を制限することが必要ですか?</li><li>自分の組織で、特定のユーザーに対して Teams 機能を制限することが必要ですか?</li></ul>|
| ![](media/audio_conferencing_image9.png)<br/>次のステップ|<ul><li>テナントおよびユーザー レベルで Teams の機能を制限するための組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、特定の要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams の機能管理での重点領域

Teams は、ポリシーに応じて、メッセージング、会議、通話、およびライブ イベント機能などの細かい機能を提供します。 既定では、組織での要件に応じてユーザーごとに異なるポリシーがすべてのユーザーに対して適用されます。 

自分の組織での各設定の実行についての技術的なガイダンスを含む、すべての設定の詳細なリストについては、次の記事を参照してください。

-   [Office 365 を使用する組織で Microsoft Teams の機能を管理する](enable-features-office-365.md)
-   [新しい Microsoft Teams および Skype for Business の管理センターへの移行中に Teams を管理する](manage-teams-skypeforbusiness-admin-center.md)
-   [Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)


## <a name="security-and-compliance"></a>セキュリティとコンプライアンス

Teams は Office 365 の高度なセキュリティおよびコンプライアンス機能に基づいて構築されており、監査および報告、コンプライアンスのコンテンツ検索、電子情報開示、訴訟ホールド、および保持ポリシーをサポートします。 

> [!Important]
> 自分の組織でコンプライアンスおよびセキュリティに関する要件がある場合は、「[Microsoft Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」の記事で、このトピックについての掘り下げた内容を確認してください。

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
