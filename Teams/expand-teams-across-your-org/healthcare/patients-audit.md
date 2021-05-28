---
title: 'IT 管理者とコンプライアンス管理者Teams患者の監査アプリ '
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
description: 管理者向け Patients アプリの監査についてTeamsする
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a2c5b006384d113dde82f702dee68a82b99685f6
ms.sourcegitcommit: e6e6a2a85ff376f97a3af3548e13d1273fa84a52
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697834"
---
# <a name="audit-logs-for-patients-app"></a>患者アプリの監査ログ

> [!NOTE]
> 2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。 患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。 患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。 ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。
>
>リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。 開始するには、リストの患者テンプレートを確認してください。 組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。

患者の監査ログ アプリ アクティビティを使用すると、インシデント後の対応チームは、患者の電子医療記録 (EMR) または患者医療情報 (PHI) の変更を確認し、生産性ツールでの PHI アクセスに関するポリシーまたは手順の変更または改善が必要かどうかを判断できます。 監査ログ イベントには、Patients アプリのユーザー インターフェイスを介して実行されるアクションが含まれます。

## <a name="meet-hipaa-requirements"></a>HIPAA の要件を満たす

HIPAA ガイドラインに従って、医療プロバイダーは、変更を監査するために、PHI へのすべてのアクセスの記録を保持する必要があります。 Microsoft は、エンタープライズのお客様が MICROSOFT TEAMS を使用し、HIPAA の要件と制御を満たすのを支援します。 Patients アプリを使用した PHI へのアクセスは完全に追跡され、監査ログ検索機能に関する記事の説明に従って、Microsoft 365 コンプライアンス センターでログ[を利用](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)できます。

> [!IMPORTANT]
> 患者のプライバシーを維持する負担は、法律により医療提供者に適用されます。 この法律では、患者にプライバシーの権利が与え、IT 管理者または HIPAA コントローラーが患者記録にアクセスまたは変更された看護師、医師、ソーシャル ワーカーを簡単に特定できる必要があります。 PHI アクセス違反の最も一般的な例の 1 つは、VIP 患者へのアクセスです。 監査ログ機能は、PHI アクセス違反の調査を実施し、HIPAA 要件を満たすために必要です。

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Patients アプリの監査ログを有効にする

監査は、いくつかの以前の構成に依存します。

1. 管理者は、Patients アプリで使用される形式で EMR を使用するには、FHIR サービス プロバイダーと作業する必要があります。 
2. 医療プロバイダーの管理者は、管理センターで患者アプリを有効Teams必要があります。 詳細[については、「アプリセットアップ ポリシーの管理」Microsoft Teams](../../teams-app-setup-policies.md)関連記事を参照してください。
3. 管理者は、「開始する前に」および「監査ログ検索を有効または無効にする」で説明したように、[](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin)アクティビティ ログ監査を有効にするのと同じ方法で、アクティビティ監査を有効[にする必要があります](/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search)。 監査ログが既に有効な場合は、Patients アプリに特別な情報は必要とされません。 医療プロバイダーがチーム内でアプリをインストールして実行すると、監査ログに PHI アクティビティが記録されます。
4. その後、管理者は Patients アプリの可用性を発表する必要があります。また、医療従事者は監査に含めるアクティビティの生成を開始する必要があります。

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>監査を実行する

アクティビティ ログの検索を実行する手順については、「監査ログを検索 [する」を参照してください](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)。

## <a name="logged-activities-for-patients-app"></a>Patients アプリのログに記録されたアクティビティ

Patients アプリには、次の表に示すログに記録された独自のアクティビティがあります。

|フレンドリ名 | 操作​​ | 説明|
|:---|:---|:---|
| 患者リストの表示 | PatientListView | ユーザーが患者リストを表示しました。|
| 削除された患者リスト | PatientListDelete | ユーザーが患者のリストを削除しました。|
| 一覧に患者を追加しました | PatientListAddPatient | 患者が患者のリストに追加されました。 |
| 患者のメモを追加しました | PatientNoteAdd | 患者レコードにメモが追加されました。 |
| 患者スキーマを作成しました | PatientSchemaCreate | 患者レコードで使用される列のセットが作成されました。 |
| ユーザーがエクスポートを開始しました | ExportInitiation | 患者データは、患者アプリから患者ファイルにExcelしました。 ファイルはチームの SharePoint サイトに保存されます。 |
| 作成された患者リスト | PatientListCreate | ユーザーが患者のリストを作成しました。|
| 既定の患者リストを設定する| PatientListDefaultSet| ユーザーは、特定のリストを既定のリストとして設定します。|
| リストから患者を削除しました| PatientListRemovePatient | 患者が患者のリストから削除されました。 |
| 検索された患者 | PatientSearch | EHR サービスで患者レコードを検索しました。 |
| 更新された患者スキーマ | PatientSchemaUpdate  | 患者レコードで使用されている列の既存のセットを更新しました。 |<!-- | 患者を別のリストに移動しました| PatientMoved | 患者レコードが一覧から別のリストに移動されました。 |-->
| 名前が変更された患者リスト | PatientListRename | 患者のリストの名前が変更されました。 |
| 患者リストで編集された列 | PatientListEditColumns | 患者の一覧の列が編集 (追加または削除) されました。 |
| 患者の詳細を表示しました | PatientView | ユーザーが患者レコードを表示しました。|
| 患者の詳細を編集しました | PatientDetailsEdit | 患者レコードの詳細が編集されました。 |
| EHR 接続を設定する | EHRConnectionSet | EHR FHIR サービス接続への接続に使用する URL を設定します。 例:<span>https:// api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |

必要に応じて監査をカスタマイズして、ログに記録されたアクティビティを検索またはフィルター処理できます。

ログに記録されるアクティビティについてはMicrosoft Teamsアクティビティに関するページ[Microsoft Teamsされています](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)。

## <a name="related-topics"></a>関連項目

[監査ログを検索する](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
