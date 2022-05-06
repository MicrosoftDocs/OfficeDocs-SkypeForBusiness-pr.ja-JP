---
title: Teams でのガバナンスを計画する - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: この記事では、Teamsでのガバナンス機能の実装を計画する方法について説明します。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 00a4fa6f2b0532ca0ff9837be4f3ee00f57662b0
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711301"
---
# <a name="plan-for-governance-in-teams"></a>Teams でのガバナンスを計画する

Teams には組織が必要とする可能性のあるガバナンス機能を実装するための豊富なツールセットが用意されています。この記事では、IT プロフェッショナルが、ガバナンスに関する組織の要件と、その要件を満たす方法を判断する際に適切な質問をするためのガイドを示します。 

> [!Tip] 
> Microsoft Teams でのガバナンスの詳細については、次のセッションをご覧ください。[Microsoft Teams でのガバナンス、管理、およびライフサイクル](https://aka.ms/teams-governance)

## <a name="group-and-team-creation-naming-classification-and-guest-access"></a>グループおよびチームの作成、名前付け、分類、およびゲスト アクセス

自分の組織において、チームの命名や分類について、ゲストがチーム メンバーとして追加することができるかどうかについて、およびチームを作成することができるユーザーが誰であるかについて、厳密な制御を実施する必要がある可能性があります。 これらの領域は、Azure Active Directory (Azure AD) ラベルと秘密度ラベルを使用して構成できます。 

<br>

|-        |-        |-        |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |判断ポイント|<ul><li>自分の組織において、チームについての特定の名前付け規則はありますか?</li><li>チーム作成者は組織固有の分類をチームに割り当てる機能を必要としていますか?</li><li>チームにゲストを追加する機能を、チーム単位で制限する必要はありますか?</li><li>自分の組織において、チームを作成可能なユーザーを制限する必要はありますか?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|次のステップ|<ul><li>チームの作成、名前付け、分類、およびゲスト アクセスについて、自分の組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

> [!NOTE]
> 事前に計画を立てやすくなるために、[これらのポリシーの設定について、およびどのライセンスが必要とされるかについて確認してください](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#template-settings)。
> 
> [!NOTE]
> 多くのMicrosoft 365およびOffice 365 サービスでは、サービスが機能するためにグループを作成する必要があるため、グループとチームの作成を制限すると、ユーザーの生産性が低下する可能性があります。 詳細については、[Teamsのガバナンスの計画に関するページを](/microsoft-365/solutions/manage-creation-of-groups)参照してください。


#### <a name="additional-information"></a>その他の情報

要件の決定後、Azure AD のコントロールを使用してその要件を実装できます。これらの設定を実装する方法に関する技術面のガイダンスは、次をご覧ください。

- [グループ設定を構成するためのAzure Active Directoryコマンドレット](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)

- [Azure Active DirectoryのMicrosoft 365 グループに名前付けポリシーを適用する](/azure/active-directory/users-groups-roles/groups-naming-policy)

- [Microsoft 365 グループ名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)

- [秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

- [グループ、チーム、Yammerのライフサイクル終了オプション](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)

## <a name="group-and-team-expiration-retention-and-archiving"></a>グループとチームの有効期限、保持、およびアーカイブ化

自分の組織で、有効期限、保持、チームおよびチームのデータ (チャネルのメッセージとチャネルのファイル) をアーカイブ化することについてのポリシーを設定するための追加の要件がある可能性があります。 グループの有効期限ポリシーを構成して、グループのライフサイクルや、必要に応じて情報の保存や削除を行うための保持ポリシーを自動的に管理することができます。また、チームをアーカイブ化して (読み取り専用モードに設定して)、アクティブでなくなったチームについて特定の時点の表示を保存することができます。 アーカイブされたチームは引き続き有効期限ポリシーが適用され、除外または更新されない限り削除される可能性があることに注意してください。

|-          |-           |
|-----------|------------|
| ![判断ポイントを表すアイコン。](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>組織はチームに有効期限日を指定することを必要としていますか?</li><li>自分の組織でチームに特定のデータ保持ポリシーを適用する必要はありますか?</li><li>自分の組織で、コンテンツを読み取り専用の状態で保存するために、非アクティブなチームをアーカイブ化する機能が必要となる見込みはありますか?</li></ul>|
| ![次の手順を示すアイコン。](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>有効期限、データ保持、アーカイブ化についての組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

> [!TIP]
> 次の表を使用して、組織の要件を把握します。

|機能 |詳細 |Azure AD Premium ライセンスが必要 |Decision |
|---------|---------|---------|---------|
|有効期限ポリシー |有効期限ポリシーを設定して、Microsoft 365 グループのライフサイクルを管理します。 |P1 |TBD|
|アイテム保持ポリシー |セキュリティ/コンプライアンス センター内で Teams の保持ポリシーを設定することによって特定の期間におけるデータを保持または削除します。 **注**: この機能を使用するには、Microsoft 365または Office 365 Enterprise E3 以降のライセンスが必要です。 |いいえ |TBD |
|アーカイブと復元 |チームがアクティブでなくなったときにチームをアーカイブして、参照用または将来再アクティブ化するために保持します。 |いいえ |TBD |

> [!Note]
> グループの有効期限は、Azure AD Premium の機能です。この機能を使えるようにするには、お使いのテナントに、設定と影響を受けるグループのメンバーを構成する管理者の Azure AD Premium とライセンスへのサブスクリプションが必要です。

#### <a name="additional-information"></a>追加情報

これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。

- [Microsoft 365 グループの有効期限を設定します](/azure/active-directory/users-groups-roles/groups-lifecycle)。

- [Teams の保持ポリシーをセットアップする](retention-policies.md).

- [チームをアーカイブする、または復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

## <a name="group-and-team-membership-management"></a>グループとチームのメンバーシップ管理

迅速なオンボードとオフボーディング、またはユーザーとゲストを必要とするチームでは、プロジェクト ベースまたは制限付きグループのメンバーを一貫して管理する必要があります。 組織では、現在のすべてのメンバーがチーム内に存在するビジネス上の正当な理由を持っていることを確認する必要がある場合もあります。 チームの所有者は退出でき、ユーザーは通常、プロジェクトの終了時やロールの変更時にグループを単独で離れることがないため、メンバーの管理は困難になる可能性があります。 ユーザーが必要なときにアクセスできるが、グループに不適切なアクセスのリスクがないようにするグループ メンバーシップを管理する最善の方法は、エンタイトルメント管理とアクセス レビューの 2 つの地区プロセスを通じて行います。

[エンタイトルメント管理](/azure/active-directory/governance/entitlement-management-overview) を使用すると、プロジェクト マネージャーなどの他のユーザーに委任して、チーム メンバーシップを含め、必要なすべてのリソースを 1 つのパッケージに収集できます。 また、テナント内のユーザー、または他の接続された組織から要求を行うことができるユーザーを定義することもできます。 プロジェクト マネージャーは、メールでアクセス要求を受信し、MyAccess ポータルで要求を承認または拒否します。 管理者は、アクセスが更新されない限り、ユーザーまたはゲストがチームから削除される期限または期間を含めるために、アクセスの条件を構成できます。 管理者は、アクセス レビューに参加するようにチームに関連付けられているグループを設定することもできます。 [アクセス レビュー](/azure/active-directory/governance/access-reviews-overview)の場合、グループの所有者は、チームのメンバーを確認するための定期的なリマインダーを受け取ります。 アクセス レビューには推奨事項が含まれています。これにより、グループ所有者は通常の構成証明プロセスを簡単に実行できます。

|-|-|-|
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 判断ポイント | 組織では、1 つ以上のチームのメンバーシップを管理するための一貫したプロセスが必要ですか? <br> 組織では、1 つ以上のチームの継続的なメンバーシップを定期的に正当化するために、所有者またはメンバー自身が必要ですか? <br> 組織では、チーム、グループ、SharePoint サイト、アプリなどのリソースへのアクセスを要求するために、ユーザーとゲストに対する承認が必要ですか? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 次の手順は? | メンバーシップの有効期限の各チームまたは特定のチームに対する組織の要件を文書化します。<br>組織でチーム、グループ、SharePoint サイト、アプリをアクセス パッケージにまとめる方法を計画します。<br>要求者のマネージャー、プロジェクト マネージャー、接続された組織のスポンサー、組織内のセキュリティ担当者など、アクセス要求を承認または拒否する必要があるユーザーを計画します。 |

> [!TIP]
> 次の表を使用して、組織の要件を把握します。

| 機能 | 詳細 | Azure AD Premium ライセンスが必要 | Decision |
|:-|:-|:-|:-|
| アクセス レビュー | 一定の間隔で特定のチームのメンバーシップを再認定するようにアクセス レビューを設定する | P2 | TBD |
| エンタイトルメント管理 | ユーザーとゲストがチームへのアクセスを要求できるようにアクセス パッケージを設定する | P2 | TBD |

> [!NOTE]
> 事前の計画を立てるために、必要な [ライセンスの詳細を確認](https://azure.microsoft.com/pricing/details/active-directory/)してください。

### <a name="additional-information"></a>その他の情報

これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。

- [エンタイトルメント管理](/azure/active-directory/governance/entitlement-management-overview)
- [アクセス レビュー](/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams 機能の管理

Teams でのガバナンスおよびライフサイクル管理のもう 1 つの重要な側面として、自分たちのユーザーがどの機能にアクセスするかを制御する機能があります。 メッセージング、会議、通話機能は、Microsoft 365レベルまたはOffice 365組織レベルまたはユーザー単位で管理できます。


|-        |-        |
|---------|---------|
| ![判断ポイントを表すアイコン。](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>自分の組織で、テナント全体に対して Teams 機能を制限することが必要ですか?</li><li>自分の組織で、特定のユーザーに対して Teams 機能を制限することが必要ですか?</li></ul>|
| ![次の手順を示すアイコン。](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>テナントおよびユーザー レベルで Teams の機能を制限するための組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、特定の要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams の機能管理での重点領域

Teams にはポリシーを介して、メッセージング、会議、通話、ライブ イベントの機能などを制御するための詳細な機能が用意されています。既定ではすべてのユーザー、または組織で必要となるユーザーそれぞれに異なるポリシーを適用できます。 

自分の組織での各設定の実行についての技術的なガイダンスを含む、すべての設定の詳細なリストについては、次の記事を参照してください。

- [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)
- [新しい Microsoft Teams 管理センターへの移行中に Teams を管理する](manage-teams-skypeforbusiness-admin-center.md)
- [Microsoft Teams のプライベート チャネル](private-channels.md)
- [Microsoft Teams の共有チャネル](shared-channels.md)
- [Teams での会議ポリシーを管理する](meeting-policies-overview.md)
- [Teams のメッセージング ポリシーを管理する](messaging-policies-in-teams.md)
- [Microsoft Teams 管理センターで、Teams アプリの組織向けアプリを管理します。](manage-apps.md)

さらに、チャネルのモデレーションを設定し、特定のユーザーにモデレーター機能を提供して、チャネル投稿を作成して返信できるユーザーを制御できます。 詳細については、「[Microsoft Teamsでのチャネル モデレーションの設定と管理](manage-channel-moderation-in-teams.md)」を参照してください。

## <a name="security-and-compliance"></a>セキュリティとコンプライアンス

Teamsは、Microsoft 365とOffice 365の高度なセキュリティとコンプライアンス機能に基づいて構築されており、監査とレポート、コンプライアンス コンテンツ検索、電子検出、訴訟ホールド、保持ポリシーをサポートします。

> [!Important]
> 自分の組織でコンプライアンスおよびセキュリティに関する要件がある場合は、「[Microsoft Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」の記事で、このトピックについての掘り下げた内容を確認してください。

## <a name="related-topics"></a>関連トピック

[Teams のガバナンスのクイック スタート](teams-adoption-governance-quick-start.md)

[セキュリティ&コンプライアンスに関するMicrosoft 365ライセンスガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->