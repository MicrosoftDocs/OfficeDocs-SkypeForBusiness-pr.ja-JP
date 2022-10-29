---
title: シフト データに関する FAQ
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Shifts データの保存場所、データ保持、取得、暗号化など、Shifts データに関してよく寄せられる質問に対する回答を取得します。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a8b6620b86154ba3903024d3b48c53e717b204a5
ms.sourcegitcommit: e6182aa3b15346dc955333a2bc571565ef463a57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2022
ms.locfileid: "68784452"
---
# <a name="shifts-data-faq"></a>シフト データに関する FAQ

この記事では、Shifts データの保存場所、データ保持、取得、暗号化など、Shifts データに関してよく寄せられる質問について説明します。

## <a name="where-is-shifts-data-stored"></a>Shifts データはどこに格納されますか?

シフト データは、アジア太平洋 (APAC)、欧州連合 (EU)、または米国の 3 つの地域のいずれかに格納されます。 各 geo には、高可用性 (HA) とディザスター リカバリー (DR) 用の少なくとも 2 つの Azure データ センター リージョンにデータが格納されます。 現在、米国/北米 geo では、北中部と中南部の米国のデータ センターが使用されています。 詳細については、「 [Microsoft 365 顧客データが格納されている場所](/microsoft-365/enterprise/o365-data-locations)」を参照してください。

現在、Shifts はオーストラリア、カナダ、フランス、日本、英国にデータ所在地を提供しています。 より多くの場所へのサポートの拡大に積極的に取り組んでいます。

## <a name="can-i-choose-where-shifts-data-is-stored"></a>Shifts データを保存する場所を選択できますか?

Teams を初めて設定するときは、サブスクリプション レベルで設定されている国または地域を選択します。 Shifts はこの選択を受け入れ、そのリージョンをサポートしている場合は Teams で設定されているロケールとリージョンを使用します。 まだそのリージョンにいない場合は、サポートされている近くのリージョンにデータを格納します。 今後、近くのリージョンに保存されている既存のデータを Teams でプロビジョニングされているリージョンに移行する予定です。

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>Shifts でユーザーの個人データにアクセスしてエクスポートまたは削除できますか?

シフトは、一般的なデータ保護規則 (GDPR) に準拠しています。 個人データに対してアクションを実行する個人 (データ主体と呼ばれる) による正式な要求は、データ主体要求 (DSR) と呼ばれます。 DSR に応答して、Shifts で個人データを見つけて操作できます。

Microsoft Purview コンプライアンス ポータルのコンテンツ検索電子情報開示ツールを使用して、スケジュールと時刻クロック データを検索して Excel にエクスポートできます。 その他のすべての Shifts データについては、データのスクリーンショットを撮ることができます。

詳細については、「[GDPR と CCPA のデータ主体要求をOffice 365する](/microsoft-365/compliance/gdpr-dsr-office365)」を参照してください。

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>組織のシフトをオフにすると、Shifts データはどうなりますか?

組織で Shifts をオフに *しても* 、データは削除されません。 Shifts をオフにした後で Shifts をオンにすると、Shifts データは引き続き使用できます。

テナントを削除すると、保持期間が終了すると、すべての Shifts データが削除されます。

Shifts データのみを削除するオプションはありません。 Teams でチームを削除すると、そのチームに関連付けられている Shifts スケジュール データは、保持期間が終了した後に削除されます。 詳細については、「 [Microsoft 365 でのデータの保持、削除、破棄](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)」を参照してください。

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>削除された Shifts スケジュールを回復できますか?

削除されたスケジュールは、バックアップする Microsoft 365 グループ (または Teams のチーム) が復元された場合に回復できます。

既定では、削除された Office 365 グループは 30 日間保持されます。 この 30 日間は、引き続きグループを復元できるため、"論理的な削除" と呼ばれます。 詳細については、「 [削除された Microsoft 365 グループを復元](/microsoft-365/admin/create-groups/restore-deleted-group?tabs=admin-center)する」を参照してください。

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>Shifts データにカスタム保持ポリシーを使用できますか?

現在、Shifts ではカスタムアイテム保持ポリシーはサポートされていません。

Teams のアイテム保持ポリシーの詳細については、「Teams の[リテンション期間について」および「Teams の](/microsoft-365/compliance/retention-policies-teams)[アイテム保持ポリシーを管理する」を](../../retention-policies.md)参照してください。

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>ライセンスが取り消されたユーザーの Shifts データを取得できますか?

現在、ライセンスが取り消されたユーザーのデータを取得する機能は提供されていません。 この機能は、私たちが取り組んでいるものです。

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>保存データと転送中のデータに Shifts はどのような種類の暗号化を使用しますか?

シフト データは、Azure Cosmos DB と Azure Storage によって保存時に暗号化されます。 詳細については、「 [保存時の Azure データ暗号化](/azure/security/fundamentals/encryption-atrest) 」と「 [Azure Cosmos DB でのデータ暗号化](/azure/cosmos-db/database-encryption-at-rest)」を参照してください。

シフトは、転送中のデータの暗号化に関する Microsoft 365 ガイドラインに従います。 詳細については、「 [転送中のデータの暗号化](/compliance/assurance/assurance-encryption-in-transit)」を参照してください。

保存データと転送中のデータの暗号化は、SOC2 コンプライアンス監査によって毎年検証されます。

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>Shifts データの変更できないコピーにアクセスできますか?

Shifts データの変更できないコピーは格納されません。 たとえば、マネージャーは、メモの追加、シフト時間の変更、タスクの割り当てなど、スケジュールを変更できます。

## <a name="can-shifts-data-be-edited"></a>Shifts データを編集できますか?

変更できないシフトの特定の側面と、変更できる特定の側面があります。 たとえば、ノートや色などのシフトの詳細は、Shifts アプリで変更する方法と同様に編集できます。 Shift 要求は、要求が取り消されない限り編集できません。

変更されたフィールドを確認するには、Microsoft 365 監査ログで Shifts イベントを検索できます。 Microsoft 365 監査ログで Shifts アクティビティに記録されるイベントの詳細については、「 [Teams アクティビティのシフト](../../audit-log-events.md#shifts-in-teams-activities)」を参照してください。

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>私の組織では、スケジュールに従業員管理システムを使用しています。 Shifts データと統合してアクセスできますか?

Shifts Graph API を使用すると、Shifts データを外部の従業員管理 (WFM) システムと統合できます。 詳細については、「 [Shifts Graph API」を](/graph/api/resources/shift)参照してください。

また、管理された Shifts コネクタも提供しています。 これらのコネクタを使用すると、WFM システムを Shifts と直接統合できます。 Shifts コネクタとサポートされているWFM システムの詳細については、「[Shifts コネクタ](/microsoft-365/frontline/shifts-connectors)」を参照してください。

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>Shifts データは、指定した期間を過ぎると完全に削除できますか?

現在、Shifts データはまったく削除されません。 [Shifts Graph API を](/graph/api/resources/shift)使用すると、[Power Apps を使用してアプリを作成](/powerapps/maker/)して、指定した期間データを保持できます。 ただし、これはネイティブではサポートされていません。

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>テナント間の移行で Shifts データを移動できますか?

既存の Shifts データを別のテナントに移行するには、日付範囲の Shifts スケジュールをエクスポートし、ユーザー名 (必要に応じて) を変更してから、スケジュールを移行先テナントにインポートする必要があります。 一度に最大 100 日のシフト データをエクスポートできます。 日付範囲は、過去または将来にすることができます。 100 日より長い期間データをエクスポートする必要がある場合は、このプロセスを繰り返します。

Shifts データを移行する前に、次の要件が満たされていることを確認してください。

- 移行先のテナント ドメイン、チーム、チーム メンバーが既に存在している必要があります。 移行では、チームが作成されたり、チームのメンバーシップや所有権が変更されたりすることはありません。
- Shifts アプリは、移行先テナントのチームで設定し、空のスケジュールにする必要があります。 移行によって既存のデータが置き換えられたり削除されたりすることはありません。 つまり、チームに既存のスケジュールがある場合、ユーザーに重複または競合するシフトが表示される可能性があり、手動で解決する必要があります。
- 承認待ちのオープン要求 (スワップ要求や休暇要求など) は移行されません。 データの移行を開始する前に、開いている要求をすべて閉じることをお勧めします。

Shifts データを別のテナントに移行する手順の概要を次に示します。

1. ソース テナントで、チームごとに Shifts スケジュールをエクスポートします。
    1. Shifts の **[スケジュール**] ページで、**その他のオプション (...)** >  に移動します。**エクスポート スケジュール**。
    1. 日付範囲を選択します。
    1. **インポートできる形式でエクスポート** を有効にし、[エクスポート] を選択 **します**。 Shifts スケジュール データは Excel ファイルにエクスポートされます。
1. 移行の一環として、チーム メンバーがメール ドメインを切り替えている場合は、Excel ファイルを手動で更新して、それらのユーザーのユーザー プリンシパル名 (UPN) を移行先テナント ドメインに変更します。
1. 移行先テナントで、スケジュールを各チームにインポートします。
    1. Shifts の **[スケジュール**] ページで、**その他のオプション (...)** >  に移動します。**インポート スケジュール**。
    1. [ **ファイルのアップロード]** を選択し、そのチームの Excel ファイルに移動し、[ **開く**] を選択します。

詳細については、「 [Shifts 用 Excel テンプレート」を](https://support.microsoft.com/office/the-excel-template-for-shifts-6fc6a206-e7cc-4907-87b8-a296bae84ce3)参照してください。

## <a name="related-articles"></a>関連記事

- [Shifts for Teams](../shifts-for-teams-landing-page.md)
- [Shifts アプリを管理する](manage-the-shifts-app-for-your-organization-in-teams.md)
