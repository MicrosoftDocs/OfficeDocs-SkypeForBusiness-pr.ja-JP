---
title: 'Teams IT およびコンプライアンス管理者向け Auditing Patients アプリ '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: Teams 管理者向け患者アプリの監査について
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3cf850b8ae7312fa6c43f879baefb617f48d30b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096191"
---
# <a name="audit-logs-for-patients-app"></a>患者アプリの監査ログ

> [!NOTE]
> 2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。 患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。 患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。 ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。
>
>リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。 開始するには、リストの患者テンプレートを確認してください。 組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。

患者アプリアクティビティの監査ログを使用すると、インシデント後の対応チームは、患者の電子医療記録 (EMR) または患者医療情報 (PHI) の変更を確認し、生産性向上ツールでの PHI アクセスに関するポリシーや手順の変更や改善が必要かどうかを判断できます。 監査ログ イベントには、患者アプリのユーザー インターフェイスを介して実行されるアクションが含まれます。

## <a name="meet-hipaa-requirements"></a>HIPAA の要件を満たす

HIPAA ガイドラインによると、医療プロバイダーは PHI へのすべてのアクセスの記録を保持し、変更を監査できる必要があります。 Microsoft は、Microsoft Teams を使用して企業のお客様に取り組み、HIPAA の要件と制御を満たして支援します。 患者アプリを介した PHI へのアクセスは完全に追跡され、監査ログ検索機能の記事に記載されている Microsoft 365 コンプライアンス センターでログ [を利用](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) できます。

> [!IMPORTANT]
> 患者のプライバシーを維持する負担は、法律で医療プロバイダーに適用されます。 この法律では、患者のプライバシーに関する権利が付与され、IT 管理者または HIPAA コントローラーは、患者記録にアクセスまたは変更された看護師、診療所、ソーシャル ワーカーを簡単に特定できる必要があります。 PHI アクセス違反の最も一般的な例の 1 つは、VIP 患者へのアクセスです。 PHI アクセス違反の調査を行い、HIPAA の要件を満たすには、監査ログ機能が必要です。

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>患者アプリの監査ログを有効にする

監査は、いくつかの以前の構成に依存します。

1. 管理者は FHIR サービス プロバイダーと共に、患者アプリで使用される形式で EMR を使用する必要があります。 「 [電子医療記録を Microsoft Teams に統合する」を参照してください](patients-app.md)。
2. 医療プロバイダーの管理者は、Teams 管理センターで患者アプリを有効にする必要があります。 詳細 [については、「Microsoft Teams のアプリ セットアップ ポリシーの](../../teams-app-setup-policies.md) 管理」および関連記事を参照してください。
3. 管理者は、アクティビティ ログの監査を有効にするのと同じ方法で、アクティビティ 監査を有効[](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin)にする必要があります。これは、「開始する前に」および「監査ログの検索を有効または無効にする」で[説明](/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search)されています。 監査ログが既に有効な場合は、患者アプリに特別な情報は必要とされません。 医療プロバイダーがチーム内でアプリをインストールして実行すると、監査ログに PHI アクティビティが記録されます。
4. その後、管理者は患者アプリの可用性をアナウンスする必要があります。また、医療従事者は監査に含めるアクティビティの生成を開始する必要があります。

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>監査を実行する

アクティビティ ログの検索を実行する手順については、「監査ログを検索 [する」を参照してください](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)。

## <a name="logged-activities-for-patients-app"></a>患者アプリのログに記録されたアクティビティ

患者アプリには、次の表に示す独自のログ記録されたアクティビティがあります。

|フレンドリ名 |操作​​|説明|
|:---|:---|:---|
| 患者リストが表示されました | PatientListView | ユーザーが患者リストを表示しました。|
| 患者リストが削除されました | PatientListDelete | ユーザーが患者のリストを削除しました。|
| 患者をリストに追加しました | PatientListAddPatient | 患者が患者のリストに追加されました。 |
| 患者用のメモを追加しました | PatientNoteAdd | 患者記録にメモが追加されました。 |
| 患者スキーマが作成されました | PatientSchemaCreate | 患者記録で使用される一連の列が作成されました。 |
| ユーザーがエクスポートを開始しました | ExportInitiation | 患者データが患者アプリから Excel ファイルにエクスポートされた。 ファイルはチームの SharePoint サイトに保存されます。 |
| 患者リストが作成されました | PatientListCreate | ユーザーが患者のリストを作成しました。|
| 既定の患者リストを設定する| PatientListDefaultSet| ユーザーが特定のリストを既定のリストとして設定します。|
| 一覧から患者を削除しました| PatientListRemovePatient | 患者が患者のリストから削除されました。 |
| 検索された患者 | PatientSearch | EHR サービスで患者レコードを検索しました。 |
| 更新された患者スキーマ | PatientSchemaUpdate  | 患者記録で使用されている列の既存のセットを更新しました。 |<!-- | 患者を別のリストに移動しました| PatientMoved | 患者記録があるリストから別のリストに移動されました。 |-->
| 名前が変更された患者リスト | PatientListRename | 患者のリストの名前が変更されました。 |
| 患者リストの編集された列 | PatientListEditColumns | 患者のリストの列が編集されました (追加または削除されました)。 |
| 患者の詳細が表示されました | PatientView | ユーザーが患者の記録を表示しました。|
| 患者の詳細を編集しました | PatientDetailsEdit | 患者記録の詳細が編集されました。 |
| EHR 接続を設定する | EHRConnectionSet | EHR FHIR サービス接続への接続に使用する URL を設定します。 例:<span>https:// api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |
||||

必要に応じて監査をカスタマイズして、これらのログに記録されたアクティビティを検索またはフィルター処理できます。

Microsoft Teams のログに記録されたアクティビティの一般的な内容は [、Microsoft Teams のアクティビティに記載されています](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)。

## <a name="related-topics"></a>関連項目

[監査ログを検索する](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[電子医療記録を Microsoft Teams に統合する](patients-app.md)