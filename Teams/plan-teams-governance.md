---
title: Teams でのガバナンスを計画する - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: この記事では、ガバナンス機能の実装を計画する方法について説明Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ab70daffa91b534f15b032cd0c137efe89abb438
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117815"
---
# <a name="plan-for-governance-in-teams"></a>Teams でのガバナンスを計画する

Teams には組織が必要とする可能性のあるガバナンス機能を実装するための豊富なツールセットが用意されています。この記事では、IT プロフェッショナルが、ガバナンスに関する組織の要件と、その要件を満たす方法を判断する際に適切な質問をするためのガイドを示します。 

> [!Tip] 
> Microsoft Teams でのガバナンスの詳細については、次のセッションをご覧ください。[Microsoft Teams でのガバナンス、管理、およびライフサイクル](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>グループおよびチームの作成、名前付け、分類、およびゲスト アクセス

自分の組織において、チームの命名や分類について、ゲストがチーム メンバーとして追加することができるかどうかについて、およびチームを作成することができるユーザーが誰であるかについて、厳密な制御を実施する必要がある可能性があります。 これらの領域を構成するには、Azure Active Directory (Azure AD) と感度ラベルを使用します。 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |判断ポイント|<ul><li>自分の組織において、チームについての特定の名前付け規則はありますか?</li><li>チーム作成者は組織固有の分類をチームに割り当てる機能を必要としていますか?</li><li>チームにゲストを追加する機能を、チーム単位で制限する必要はありますか?</li><li>自分の組織において、チームを作成可能なユーザーを制限する必要はありますか?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|次の手順|<ul><li>チームの作成、名前付け、分類、およびゲスト アクセスについて、自分の組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

> [!NOTE]
> 事前に計画を立てやすくなるために、[これらのポリシーの設定について、およびどのライセンスが必要とされるかについて確認してください](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。
> 
> [!NOTE]
> グループとチームの作成を制限すると、ユーザーの生産性が低下する可能性があります。多くの Microsoft 365 サービスと Office 365 サービスを機能するには、グループを作成する必要があります。 詳細については、グループを作成するユーザーを制御する[理由に](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)移動して展開Microsoft 365します。


#### <a name="additional-information"></a>追加情報

要件の決定後、Azure AD のコントロールを使用してその要件を実装できます。これらの設定を実装する方法に関する技術面のガイダンスは、次をご覧ください。

- [Azure Active Directory設定を構成するための新しいコマンドレット](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [グループに名前付けポリシーを適用Microsoft 365グループAzure Active Directory](/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365グループの名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [感度ラベルを使用して、Microsoft Teams、Microsoft 365、サイトのコンテンツをSharePointする](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [グループ、チーム、およびグループのライフサイクルのYammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>グループとチームの有効期限、保持、およびアーカイブ化

自分の組織で、有効期限、保持、チームおよびチームのデータ (チャネルのメッセージとチャネルのファイル) をアーカイブ化することについてのポリシーを設定するための追加の要件がある可能性があります。 グループの有効期限ポリシーを構成して、グループのライフサイクルや、必要に応じて情報の保存や削除を行うための保持ポリシーを自動的に管理することができます。また、チームをアーカイブ化して (読み取り専用モードに設定して)、アクティブでなくなったチームについて特定の時点の表示を保存することができます。 アーカイブされたチームには引き続き有効期限ポリシーが適用され、除外または更新されていない限り削除される可能性があります。

|-          |-           |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>組織はチームに有効期限日を指定することを必要としていますか?</li><li>自分の組織でチームに特定のデータ保持ポリシーを適用する必要はありますか?</li><li>自分の組織で、コンテンツを読み取り専用の状態で保存するために、非アクティブなチームをアーカイブ化する機能が必要となる見込みはありますか?</li></ul>|
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>有効期限、データ保持、アーカイブ化についての組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

> [!TIP]
> 次の表を使用して、組織の要件を把握します。

|機能 |詳細 |Azure AD Premium ライセンスが必要 |Decision |
|---------|---------|---------|---------|
|有効期限ポリシー |有効期限ポリシーを設定Microsoft 365グループのライフサイクルを管理します。 |P1 |TBD|
|アイテム保持ポリシー |セキュリティ/コンプライアンス センター内で Teams の保持ポリシーを設定することによって特定の期間におけるデータを保持または削除します。 **注**: この機能を使用するには、E3 以上Microsoft 365またはOffice 365 Enterpriseライセンスが必要です。 |いいえ |TBD |
|アーカイブと復元 |チームがアクティブでなくなったときにチームをアーカイブして、参照用または将来再アクティブ化するために保持します。 |いいえ |TBD |

> [!Note]
> グループの有効期限は、Azure AD Premium の機能です。この機能を使えるようにするには、お使いのテナントに、設定と影響を受けるグループのメンバーを構成する管理者の Azure AD Premium とライセンスへのサブスクリプションが必要です。

#### <a name="additional-information"></a>追加情報

これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。

- [グループの有効期限Microsoft 365設定します](/azure/active-directory/users-groups-roles/groups-lifecycle)。

- [Teams の保持ポリシーをセットアップする](retention-policies.md).

- [チームをアーカイブする、または復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

## <a name="group-and-team-membership-management"></a>グループとチームのメンバーシップ管理

迅速なオンボーディングとオフボード、またはユーザーとゲストを必要とするチームでは、プロジェクト ベースまたは制限付きグループのメンバーを一貫して管理する必要があります。 また、組織は、現在のすべてのメンバーがチーム内に入るビジネス上の正当な理由を持っている必要がある場合があります。 メンバーの管理は、チーム所有者が離れる可能性が高く、通常、プロジェクトが終了したりロールを変更したりするときに、ユーザーが自分でグループを離れないので、難しい場合があります。 必要に応じてユーザーがアクセスできるが、グループが不適切なアクセスのリスクを持たなかったグループ メンバーシップを管理する最善の方法は、資格管理とアクセス レビューの 2 つの地区プロセスを通じて行う方法です。

[資格管理](/azure/active-directory/governance/entitlement-management-overview) を使用すると、プロジェクト マネージャーなどのユーザーに委任して、チーム メンバーシップを含む必要なすべてのリソースを 1 つのパッケージに収集できます。 また、要求を行えるユーザー (テナント内のユーザー、または他の接続された組織からのユーザー) を定義できます。 プロジェクト マネージャーは、メールでアクセス要求を受信し、MyAccess ポータルで要求を承認または拒否します。 管理者は、アクセスが更新されていない限り、ユーザーまたはゲストがチームから削除される有効期限または期間を含めるアクセス条件を構成できます。 管理者は、アクセス レビューに参加するチームに関連付けられているグループを設定することもできます。 アクセス [レビューの場合、](/azure/active-directory/governance/access-reviews-overview)グループ所有者は定期的にアラームを受け取り、チームのメンバーを確認します。 アクセス レビューには推奨事項が含まれるので、グループ所有者は通常の構成証明プロセスを簡単に実行できます。

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 判断ポイント | 組織では、1 つ以上のチームのメンバーシップを管理するための一貫したプロセスが必要ですか? <br> 組織では、定期的に 1 つ以上のチームの継続的なメンバーシップを正当化するために、所有者またはメンバー自身が必要ですか。 <br> 組織では、チーム、グループ、サイト、アプリなどのリソースへのアクセスを要求するために、ユーザーとゲストSharePoint必要ですか。 |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 次の手順 | メンバーシップの有効期限について、各チームまたは特定のチームの組織の要件を文書化します。<br>アクセス パッケージにチーム、グループ、SharePointアプリをまとめてバンドルする方法を計画します。<br>要求者のマネージャー、プロジェクト マネージャー、接続されている組織のスポンサー、組織内のセキュリティ責任者などのユーザーがアクセス要求を承認または拒否する必要があるユーザーを計画します。 |

> [!TIP]
> 次の表を使用して、組織の要件を把握します。

| 機能 | 詳細 | Azure AD Premium ライセンスが必要 | Decision |
|:-|:-|:-|:-|
| アクセス レビュー | アクセス レビューを設定して、一定の間隔で特定のチームのメンバーシップを再認定する | P2 | TBD |
| 権利管理 | ユーザーとゲストがチームへのアクセスを要求できるアクセス パッケージを設定する | P2 | TBD |

> [!NOTE]
> 前もって計画を立てるには、必要 [なライセンスの詳細を確認してください](https://azure.microsoft.com/pricing/details/active-directory/)。

### <a name="additional-information"></a>追加情報

これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。

- [権利管理](/azure/active-directory/governance/entitlement-management-overview)
- [アクセス レビュー](/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams 機能の管理

Teams でのガバナンスおよびライフサイクル管理のもう 1 つの重要な側面として、自分たちのユーザーがどの機能にアクセスするかを制御する機能があります。 メッセージング、会議、通話機能は、組織レベルまたはMicrosoft 365レベルOffice 365ユーザーごとに管理できます。


|-        |-        |
|---------|---------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>自分の組織で、テナント全体に対して Teams 機能を制限することが必要ですか?</li><li>自分の組織で、特定のユーザーに対して Teams 機能を制限することが必要ですか?</li></ul>|
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>テナントおよびユーザー レベルで Teams の機能を制限するための組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、特定の要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams の機能管理での重点領域

Teams にはポリシーを介して、メッセージング、会議、通話、ライブ イベントの機能などを制御するための詳細な機能が用意されています。既定ではすべてのユーザー、または組織で必要となるユーザーそれぞれに異なるポリシーを適用できます。 

自分の組織での各設定の実行についての技術的なガイダンスを含む、すべての設定の詳細なリストについては、次の記事を参照してください。

- [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)
- [新しい Microsoft Teams 管理センターへの移行中に Teams を管理する](manage-teams-skypeforbusiness-admin-center.md)
- [Microsoft Teams のプライベート チャネル](private-channels.md)
- [Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)
- [Teams でメッセージング ポリシーを管理する](messaging-policies-in-teams.md)
- [管理センターでアプリMicrosoft Teams管理する](manage-apps.md)

さらに、チャネルのモデレーションを設定し、特定のユーザーにモデレーター機能を提供して、チャネル投稿を作成してそれに応答できるユーザーを制御できます。 詳細[については、「Microsoft Teams でのチャネル モデレーションの設定](manage-channel-moderation-in-teams.md)と管理」を参照してください。

## <a name="security-and-compliance"></a>セキュリティとコンプライアンス

Teamsは、Microsoft 365 と Office 365 の高度なセキュリティとコンプライアンスの機能を基に構築され、監査とレポート、コンプライアンス コンテンツ検索、電子検出、法的保持、保持ポリシーをサポートします。

> [!Important]
> 自分の組織でコンプライアンスおよびセキュリティに関する要件がある場合は、「[Microsoft Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」の記事で、このトピックについての掘り下げた内容を確認してください。

## <a name="related-topics"></a>関連トピック

[Teams のガバナンスのクイック スタート](teams-adoption-governance-quick-start.md)

[Microsoft 365コンプライアンスに関する&ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->