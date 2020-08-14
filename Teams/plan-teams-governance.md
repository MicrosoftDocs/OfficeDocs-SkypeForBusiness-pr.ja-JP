---
title: Teams でのガバナンスを計画する - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: この記事では、チームでのガバナンス機能の実装を計画する方法について説明します。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7037594158dd64cb69f07a3d7efb38ca963c6a63
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662117"
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
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  |判断ポイント|<ul><li>自分の組織において、チームについての特定の名前付け規則はありますか?</li><li>チーム作成者は組織固有の分類をチームに割り当てる機能を必要としていますか?</li><li>チームにゲストを追加する機能を、チーム単位で制限する必要はありますか?</li><li>自分の組織において、チームを作成可能なユーザーを制限する必要はありますか?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>|次の手順|<ul><li>チームの作成、名前付け、分類、およびゲスト アクセスについて、自分の組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

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
> グループとチームの作成を制限すると、Microsoft 365 および Office 365 サービスの多くでは、サービスを機能させるためにグループを作成する必要があるため、ユーザーの生産性が低下する可能性があります。 詳細については、「 [Microsoft 365 グループを作成するユーザーを制御](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618#why)する」を参照してください。


#### <a name="additional-information"></a>追加情報

要件の決定後、Azure AD のコントロールを使用してその要件を実装できます。これらの設定を実装する方法に関する技術面のガイダンスは、次をご覧ください。

- [グループ設定を構成するための Azure Active Directory コマンドレット](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)。

- [Azure Active Directory で Microsoft 365 グループの名前付けポリシーを適用](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-naming-policy)します。

- [Microsoft 365 グループの名前付けポリシー](https://support.office.com/article/office-365-groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552)。


## <a name="group-and-team-expiration-retention-and-archiving"></a>グループとチームの有効期限、保持、およびアーカイブ化

組織には、有効期限、保持、チームとチームデータ (チャネル メッセージとチャネル ファイル) のアーカイブに関するポリシーの設定に追加の要件がある場合があります。グループの有効期限ポリシーを設定すると、自動でグループポリシーと保持ポリシーを管理して、必要に応じて情報を保存または削除できます。チーム (読み取り専用モードに設定) をアーカイブし、アクティブでなくなったチームのその時のビューを保存します。

|           |            |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>組織はチームに有効期限日を指定することを必要としていますか?</li><li>自分の組織でチームに特定のデータ保持ポリシーを適用する必要はありますか?</li><li>自分の組織で、コンテンツを読み取り専用の状態で保存するために、非アクティブなチームをアーカイブ化する機能が必要となる見込みはありますか?</li></ul>|
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>有効期限、データ保持、アーカイブ化についての組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、これらの要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

> [!TIP]
> 次の表を使用して、組織の要件を把握します。

|機能 |詳細 |Azure AD Premium ライセンスが必要 |Decision |
|---------|---------|---------|---------|
|有効期限ポリシー |有効期限ポリシーを設定して、Microsoft 365 グループのライフサイクルを管理します。 |P1 |TBD|
|アイテム保持ポリシー |セキュリティ/コンプライアンス センター内で Teams の保持ポリシーを設定することによって特定の期間におけるデータを保持または削除します。 **注**: この機能を使用するには、Microsoft 365 または Office 365 Enterprise E3 以上のライセンスが必要です。 |いいえ |TBD |
|アーカイブと復元 |チームがアクティブでなくなったときにチームをアーカイブして、参照用または将来再アクティブ化するために保持します。 |いいえ |TBD |

> [!Note]
> グループの有効期限は、Azure AD Premium の機能です。この機能を使えるようにするには、お使いのテナントに、設定と影響を受けるグループのメンバーを構成する管理者の Azure AD Premium とライセンスへのサブスクリプションが必要です。

#### <a name="additional-information"></a>追加情報

これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。

- [Microsoft 365 グループの有効期限を設定](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)します。

- [Teams の保持ポリシーをセットアップする](retention-policies.md).

- [チームをアーカイブする、または復元する](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)

## <a name="group-and-team-membership-management"></a>グループとチームメンバーシップの管理

Project ベースのメンバーを一貫して管理する、またはグループ化を行う必要があるチームでは、迅速なオンボードとオフボード、またはユーザーとゲストに対応する必要があります。 組織では、現在のすべてのメンバーがチーム内でビジネスの正当性を確認する必要がある場合もあります。 メンバーの管理は困難なのは、プロジェクトが終了したときやロールを変更したときに、ユーザーが自分の accord でグループを脱退できないためです。 必要に応じてユーザーがアクセスできるようにするグループメンバーシップを管理するのが最適な方法ですが、グループにアクセス権管理とアクセスレビューという2つのディストリクトプロセスが含まれていないことを確認します。

利用[資格管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)では、プロジェクトマネージャーなどのユーザーに委任して、チームのメンバーシップなど、必要なすべてのリソースを1つのパッケージにまとめることができます。 また、テナント内のユーザーまたは他の接続されている組織から要求を行うことができるユーザーを定義することもできます。 プロジェクトマネージャーは、アクセス要求をメールで受け取り、MyAccess ポータルで要求を承認または拒否します。 管理者は、アクセスを更新しない限り、ユーザーまたはゲストがチームから削除されるまでの有効期限の日付または期間を含めるように、access の条件を構成できます。 管理者は、access レビューに参加するためにチームに関連付けられているグループを設定することもできます。 [Access レビュー](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)の場合、グループの所有者は、チームのメンバーを確認するための定期的なアラームを受け取ります。 Access レビューには推奨事項が含まれているため、グループの所有者は通常の構成証明プロセスを簡単に行うことができます。

||||
|:-|:-|:-|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting decision points"/>  | 判断ポイント | 組織では、1つ以上のチームのメンバーシップを管理するための一貫したプロセスが必要ですか? <br> 組織には、1人または複数のチームの継続的なメンバーシップを定期的に正当化するための所有者またはメンバーが必要ですか? <br> 組織では、チーム、グループ、SharePoint サイト、アプリなどのリソースへのアクセス権を要求するユーザーとゲストの承認が必要ですか? |
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next steps"/>| 次のステップ | 各チームまたは特定のチームに対して、メンバーシップの有効期限に関する組織要件を文書化します。<br>組織で、チーム、グループ、SharePoint サイト、アプリを access パッケージでまとめる方法を計画します。<br>要求者のマネージャー、プロジェクトマネージャー、接続された組織のスポンサー、または組織内のセキュリティ担当者のスポンサーなど、アクセス要求を承認または拒否する必要があるユーザーを計画します。 |

> [!TIP]
> 次の表を使用して、組織の要件を把握します。

| 機能 | 詳細 | Azure AD Premium ライセンスが必要 | Decision |
|:-|:-|:-|:-|
| Access レビュー | 特定のチームのメンバーシップを定期的に recertify するためのアクセスレビューを設定する | P2 | TBD |
| 権利管理 | ユーザーおよびゲストがチームへのアクセスを要求できるように access パッケージをセットアップする | P2 | TBD |

> [!NOTE]
> 事前の計画を立てるために、 [必要なライセンスの詳細についてご](https://azure.microsoft.com/pricing/details/active-directory/)確認ください。

### <a name="additional-information"></a>追加情報

これらの設定を実装する方法についての技術面のガイダンスは、次をご覧ください。

- [権利管理](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)
- [Access レビュー](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

## <a name="teams-feature-management"></a>Teams 機能の管理

Teams でのガバナンスおよびライフサイクル管理のもう 1 つの重要な側面として、自分たちのユーザーがどの機能にアクセスするかを制御する機能があります。 Microsoft 365 または Office 365 組織レベルまたはユーザーごとのいずれかで、メッセージング、会議、通話の機能を管理できます。


|         |         |
|---------|---------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>自分の組織で、テナント全体に対して Teams 機能を制限することが必要ですか?</li><li>自分の組織で、特定のユーザーに対して Teams 機能を制限することが必要ですか?</li></ul>|
| ![次の手順を示すアイコン](media/audio_conferencing_image9.png)<br/>次の手順|<ul><li>テナントおよびユーザー レベルで Teams の機能を制限するための組織の要件を文書化します。</li><li>Teams のロールアウトの一部として、特定の要件を実施する計画を立てます。</li><li>ポリシーの伝達と公開を行い、Teams ユーザーに求められる動作について通知します。</li></ul>|

### <a name="teams-feature-management-focus-areas"></a>Teams の機能管理での重点領域

Teams にはポリシーを介して、メッセージング、会議、通話、ライブ イベントの機能などを制御するための詳細な機能が用意されています。既定ではすべてのユーザー、または組織で必要となるユーザーそれぞれに異なるポリシーを適用できます。 

自分の組織での各設定の実行についての技術的なガイダンスを含む、すべての設定の詳細なリストについては、次の記事を参照してください。

- [組織のMicrosoft Teams の設定を管理する](enable-features-office-365.md)
- [新しい Microsoft Teams 管理センターへの移行中に Teams を管理する](manage-teams-skypeforbusiness-admin-center.md)
- [Teams での会議ポリシーを管理する](meeting-policies-in-teams.md)
- [Teams のメッセージング ポリシーを管理する](messaging-policies-in-teams.md)

さらに、チャネルのモデレーションを設定し、特定のユーザーに対してモデレーター機能を提供して、チャネルの投稿を作成したり、それらに返信したりできるユーザーを制御できるようにすることができます。 詳細については [、「Microsoft Teams でチャネルのモデレーションを設定および管理](manage-channel-moderation-in-teams.md) する」を参照してください。

## <a name="security-and-compliance"></a>セキュリティとコンプライアンス

Teams は、Microsoft 365 および Office 365 の高度なセキュリティ機能とコンプライアンス機能に基づいて構築されており、監査とレポート、コンプライアンスコンテンツの検索、電子情報開示、法的保持、アイテム保持ポリシーをサポートしています。

> [!Important]
> 自分の組織でコンプライアンスおよびセキュリティに関する要件がある場合は、「[Microsoft Teams のセキュリティとコンプライアンスの概要](security-compliance-overview.md)」の記事で、このトピックについての掘り下げた内容を確認してください。

## <a name="related-topics"></a>関連トピック

[Teams のガバナンスのクイック スタート](teams-adoption-governance-quick-start.md)

<!--
## Teams lifecycle management

In addition to planning for governance, your organization might also be interested in planning for Teams lifecycle management. For practical guidance on planning for teams lifecycle management, see [Plan for lifecycle management in Teams](plan-teams-lifecycle.md).
-->
