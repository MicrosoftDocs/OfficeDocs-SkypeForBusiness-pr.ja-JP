---
title: シフト データに関する FAQ
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Shifts データの保存場所、データのリテンション期間、取得、暗号化など、Shifts データに関してよく寄せられる質問への回答を得る。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2df5c465c9115dce47ee9e80ea649768606c338f
ms.sourcegitcommit: 10bee789272e648ea1e93d7d7c27ec645d0a8bdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2022
ms.locfileid: "62918955"
---
# <a name="shifts-data-faq"></a>シフト データに関する FAQ

この記事では、Shifts データの保存場所、データのリテンション期間、取得、暗号化など、Shifts データについてよく寄せられる質問について説明します。

## <a name="where-is-shifts-data-stored"></a>Shifts データはどこに格納されますか?

シフト データは、アジア太平洋 (APAC)、欧州連合 (EU)、または米国の 3 つの地域 (geo) の 1 つに格納されます。 各 geo は、高可用性 (HA) とディザスター リカバリー (DR) のために、少なくとも 2 つの Azure データ センター リージョンにデータを格納します。 現在、米国/北米地域では、米国中北部と中南部のデータ センターが使用されています。 詳細については、「顧客データを格納[する場所Microsoft 365」を参照してください](/microsoft-365/enterprise/o365-data-locations)。

現在、Shifts は、オーストラリア、カナダ、フランス、日本、英国にデータの保存場所を提供しています。 サポートを他の場所に拡大するために積極的に取り組み中です。

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Shifts データの格納場所を選択できますか?

サブスクリプションを初めてTeams、サブスクリプション レベルで設定されている国または地域を選択します。 Shift は、この選択を受け入れ、そのリージョンをサポートする場合は、Teamsに設定されているロケールとリージョンを使用します。 まだそのリージョンにいない場合は、サポートされている近くのリージョンにデータを格納します。 今後、近くのリージョンに保存されている場合は、既存のデータを、Teams でプロビジョニングされているリージョンに移行する予定です。

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Shifts でユーザーの個人データにアクセスしたり、エクスポートまたは削除したりできますか?

シフトは一般データ保護規則 (GDPR) に準拠しています。個人データに対してアクションを実行する人 (データ主体と呼ばれる) による正式な要求は、データ主体要求 (DSR) と呼ばれています。 DSR に応じて、Shifts で個人データを検索して処理できます。

Microsoft 365 コンプライアンス センター のコンテンツ検索電子情報開示ツールを使用して、スケジュールと時刻のデータを検索およびエクスポートExcel。 その他のすべての Shifts データについては、データのスクリーンショットを取得できます。

詳細については、「[GDPR と CCPA Office 365データサブジェクト要求の詳細」を参照してください](/microsoft-365/compliance/gdpr-dsr-office365)。

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>組織で Shifts をオフにした場合、Shifts データは何が起こりますか?

組織内の Shifts をオフに *しても、データは* 削除されない。 Shifts をオフにした後で Shifts を有効にした場合、Shifts データは引き続き使用できます。

テナントを削除すると、保持期間が終了すると、すべての Shifts データが削除されます。

Shifts データのみを削除するオプションはありません。 Teams でチームを削除すると、保持期間の終了後に、そのチームに関連付けられているデータが削除されます。 詳細については、「[データの保持](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)、削除、および削除」を参照Microsoft 365。

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>削除されたシフト スケジュールを回復できますか?

削除されたスケジュールは、そのスケジュールをMicrosoft 365グループ (またはグループ内のチーム) が復元Teams回復できます。

既定では、削除されたMicrosoft 365は 30 日間保持されます。 この 30 日間の期間は"ソフト削除" と呼ばれるため、グループを復元できます。 詳細については、「削除されたグループ[を復元する」Microsoft 365してください](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center)。

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Shifts データにカスタム保持ポリシーを使用できますか?

現時点では、Shifts はカスタム保持ポリシーをサポートされていません。

Teams のアイテム保持ポリシーの詳細については、「Teams のアイテム保持ポリシー[](/microsoft-365/compliance/retention-policies-teams)の管理」を参照[Teams。](../../retention-policies.md)

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>ライセンスが取り消されたユーザーの Shifts データを取得できますか?

現在、ライセンスが取り消されたユーザーのデータを取得する機能は提供されません。 この機能は、現在取り組み中の機能です。

## <a name="is-shifts-supported-in-government-cloud-community-gcc-environments"></a>Government Cloud Community (GCC) 環境ではシフトはサポートされていますか?

シフトは、GCC環境では使用できますが、High 環境GCC DoD 環境では使用できません。

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>保存データと転送中のデータには、Shifts でどのような種類の暗号化が使用されますか。

シフト データは、Azure Cosmos DB と Azure Storage によって暗号化されます。 詳細については、「保存時[の Azure データ暗号化」と](/azure/security/fundamentals/encryption-atrest)「[Azure Cosmos DB でのデータ暗号化」を参照してください](/azure/cosmos-db/database-encryption-at-rest)。

シフトは、転送中Microsoft 365暗号化に関するガイドラインに従います。 詳細については、「転送中データ [の暗号化」を参照してください](/compliance/assurance/assurance-encryption-in-transit)。

保存データと転送中のデータの暗号化は、SOC2 コンプライアンス監査によって毎年検証されます。

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Shifts データの不変コピーにアクセスできますか?

Shifts データの不変コピーは保存されません。 たとえば、マネージャーは、メモの追加、シフト時間の変更、タスクの割り当てなど、スケジュールを変更できます。

## <a name="can-shifts-data-be-edited"></a>Shifts データを編集できますか?

シフトには、変更できない特定の側面と、変更できる特定の側面があります。 たとえば、ノートや色などのシフトの詳細は、Shifts アプリでの変更方法と同様に編集できます。 シフト要求は、要求が取り下げ解除されていない限り編集することはできません。

変更されたフィールドを確認するには、Shifts イベントMicrosoft 365監査ログを検索します。 監査ログの Shifts アクティビティに対してログに記録されるイベントの詳細については、「Microsoft 365 アクティビティのシフト」[をTeamsしてください](../../audit-log-events.md#shifts-in-teams-activities)。

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>組織では、スケジュール設定に従業員管理システムを使用しています。 Shifts データと統合してアクセスできますか?

Shifts Graph API を使用すると、Shifts データを外部の従業員管理 (WFM) システムと統合できます。 詳細については、「[Shifts Graph API」を参照してください](/graph/api/resources/shift)。

また、管理された Shifts コネクタとオープン ソースの Shifts コネクタも提供しています。 これらのコネクタを使用すると、WFM システムを Shifts と直接統合できます。 Shifts コネクタとサポートされている WFM システムの詳細については、「 [Shifts コネクタ」を参照してください](shifts-connectors.md)。

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Shifts データは、指定した期間後に完全に削除できますか。

現在、Shifts データは削除されるのでは一度も行われず、 [Shifts Graph API を](/graph/api/resources/shift)使用して、Power Apps を使用して、指定[](/powerapps/maker/)した期間データを保持するアプリを作成できます。 ただし、ネイティブではサポートされていません。

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>テナント間の移行でシフト データを移動できますか。

シフト データは、特定の要求に応じて、あるテナントから別のテナントに移行できます。 テナント間の移行は、常にサポートされていませんが、顧客の要求として発生する可能性があります。

## <a name="related-articles"></a>関連記事

- [Shifts for Teams](../shifts-for-teams-landing-page.md)
- [Shifts アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
