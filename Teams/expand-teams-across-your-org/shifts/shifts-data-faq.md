---
title: Shifts データに関する FAQ
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
description: Shifts データの格納場所、データの保持、取得、暗号化など、Shifts データに関してよく寄せられる質問への回答を取得します。
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
ms.openlocfilehash: d4fc6e36c0c78bdf86e1384fe6269f292f20deb7
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922828"
---
# <a name="shifts-data-faq"></a>Shifts データに関する FAQ

この記事では、Shifts データの格納場所、データの保持、取得、暗号化など、Shifts データに関してよく寄せられる質問について説明します。

## <a name="where-is-shifts-data-stored"></a>Shifts データはどこに保存されますか?

Shifts データは、アジア太平洋 (APAC)、欧州連合 (EU)、または米国の 3 つの地域のいずれかに格納されます。 各 geo では、高可用性 (HA) とディザスター リカバリー (DR) 用の少なくとも 2 つの Azure データ センター リージョンにデータが格納されます。 現在、米国/北米 geo では、中北部と中南部の米国のデータ センターが使用されています。 詳細については、「[顧客データの保存場所Microsoft 365](/microsoft-365/enterprise/o365-data-locations)」を参照してください。

現在、Shifts はオーストラリア、カナダ、フランス、日本、英国にデータ常駐を提供しています。 より多くの場所へのサポートの拡大に積極的に取り組んでいます。

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Shifts データを格納する場所を選択できますか?

Teamsを初めて設定するときは、サブスクリプション レベルで設定されている国または地域を選択します。 Shifts は、この選択を受け入れ、そのリージョンをサポートしている場合は、Teamsで設定されているロケールとリージョンを使用します。 そのリージョンにまだ存在しない場合は、サポートされている近くのリージョンにデータが格納されます。 今後、近くのリージョンに格納されている場合は、既存のデータを、Teamsでプロビジョニングされたリージョンに移行する予定です。

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Shifts でユーザーの個人データにアクセスしたり、エクスポートしたり、削除したりできますか?

シフトは、一般的なデータ保護規則 (GDPR) に準拠しています。個人データに対してアクションを実行するための人物 (データ主体と呼ばれる) による正式な要求は、データ 主体要求 (DSR) と呼ばれます。 DSR に応答して、Shifts で個人データを検索して操作できます。

Microsoft Purview コンプライアンス ポータルの Content Search 電子情報開示ツールを使用して、スケジュールと時刻のデータを検索してExcelにエクスポートできます。 他のすべての Shifts データの場合は、データのスクリーンショットを撮ることができます。

詳細については、「[OFFICE 365 GDPR と CCPA のデータ主体要求](/microsoft-365/compliance/gdpr-dsr-office365)」を参照してください。

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>組織の Shifts をオフにした場合、Shifts データはどうなりますか?

組織内の Shift をオフにしても、データ *は削除されません* 。 Shifts をオフにした後で Shift を有効にした場合でも、Shifts データは引き続き使用できます。

テナントを削除すると、保持期間が終了すると、すべての Shifts データが削除されます。

Shifts データのみを削除するオプションはありません。 Teamsでチームを削除すると、保持期間が終了すると、そのチームに関連付けられているデータが削除されます。 詳細については、「[Microsoft 365でのデータの保持、削除、破棄](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)」を参照してください。

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>削除された Shifts スケジュールを回復できますか?

削除されたスケジュールを復元できるのは、それをバックアップするMicrosoft 365 グループ (またはTeamsのチーム) が復元された場合です。

既定では、削除された Office 365 グループは 30 日間保持されます。 この 30 日間は、グループを復元できるため、"論理的な削除" と呼ばれます。 詳細については、「[削除されたMicrosoft 365 グループを復元する](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center)」を参照してください。

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Shifts データにカスタムアイテム保持ポリシーを使用できますか?

現時点では、Shifts ではカスタムアイテム保持ポリシーはサポートされていません。

Teamsのアイテム保持ポリシーの詳細については、「Teams[のリテンション期間の詳細とTeams](/microsoft-365/compliance/retention-policies-teams)[のアイテム保持ポリシーの管理」を](../../retention-policies.md)参照してください。

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>ライセンスが取り消されたユーザーの Shifts データを取得できますか?

現在、ライセンスが取り消されたユーザーのデータを取得する機能は提供されていません。 この機能は、私たちが取り組んでいるものです。

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>保存時および転送中のデータに対して、Shifts はどのような種類の暗号化を使用しますか?

Shifts データは、Azure Cosmos DB と Azure Storageによって保存時に暗号化されます。 詳細については、「[保存時の Azure データ暗号化](/azure/security/fundamentals/encryption-atrest)」と「[Azure Cosmos DB のデータ暗号化](/azure/cosmos-db/database-encryption-at-rest)」を参照してください。

シフトは、転送中のデータの暗号化に関するMicrosoft 365ガイドラインに従います。 詳細については、「 [転送中データの暗号化](/compliance/assurance/assurance-encryption-in-transit)」を参照してください。

保存時および転送中のデータのシフト暗号化は、SOC2 コンプライアンス監査によって毎年検証されます。

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Shifts データの変更できないコピーにアクセスできますか?

Shifts データの不変コピーは格納しません。 たとえば、マネージャーは、メモの追加、シフト時間の変更、タスクの割り当てなど、スケジュールに変更を加えることができます。

## <a name="can-shifts-data-be-edited"></a>Shifts データを編集できますか?

Shift には、変更できない特定の側面と、変更できる特定の側面があります。 たとえば、ノートや色などのシフトの詳細は、Shifts アプリで変更する方法と同様に編集できます。 シフト要求は、要求が取り消されない限り編集できません。

変更されたフィールドを確認するには、Microsoft 365監査ログで Shifts イベントを検索します。 Microsoft 365監査ログの Shifts アクティビティに対してログに記録されるイベントの詳細については、「[Teams アクティビティのシフト](../../audit-log-events.md#shifts-in-teams-activities)」を参照してください。

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>組織では、スケジュール設定に従業員管理システムを使用しています。 Shifts データと統合してアクセスできますか?

Shifts Graph API を使用すると、Shifts データと外部従業員管理 (WFM) システムを統合できます。 詳細については、「[Shifts Graph API」を参照](/graph/api/resources/shift)してください。

また、マネージド Shifts コネクタとオープンソースの Shifts コネクタも提供しています。 これらのコネクタを使用すると、WFM システムを Shifts と直接統合できます。 Shifts コネクタとサポートされている WFM システムの詳細については、「 [Shifts コネクタ](shifts-connectors.md)」を参照してください。

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>指定した期間後に Shifts データを完全に削除できますか?

現在、Shifts データはまったく削除されません。 [Shifts Graph API を](/graph/api/resources/shift)使用すると、[Power Appsを使用してアプリを作成](/powerapps/maker/)し、指定した期間データを保持できます。 ただし、これはネイティブではサポートされていません。

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>テナント間移行で Shifts データを移動できますか?

シフト データは、特定の要求に応じて、あるテナントから別のテナントに移行できます。 テナント間の移行は既定ではサポートされていませんが、顧客の要求として発生する可能性があることに注意してください。

## <a name="related-articles"></a>関連記事

- [Shifts for Teams](../shifts-for-teams-landing-page.md)
- [Shifts アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
