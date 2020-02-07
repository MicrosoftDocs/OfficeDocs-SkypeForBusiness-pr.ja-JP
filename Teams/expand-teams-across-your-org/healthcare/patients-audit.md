---
title: 'Teams IT とコンプライアンス管理者のための患者アプリの監査 '
author: jambirk
ms.author: jambirk
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
description: Teams 管理者用の患者アプリ
ms.openlocfilehash: fd2aa97e9eb8fefdcaa4e9a4ccc432f42dbee5ce
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827615"
---
# <a name="audit-logs-for-patients-app"></a>患者アプリの監査ログ

患者のアプリアクティビティの監査ログでは、インシデント対応のチームが、患者の電子医療記録 (EMR) または患者の医療情報 (PHI) に対する変更を確認し、PHI access のポリシーまたはプロシージャの変更や改善を判断することができます。生産性ツールが必要です。 監査ログイベントは、患者のアプリのユーザーインターフェイスを通じて実行される操作をカバーします。

## <a name="meet-hipaa-requirements"></a>HIPAA の要件を満たす

HIPAA のガイドラインに従って、医療機関は PHI へのすべてのアクセス記録を保持する必要があります。そのため、変更内容を監査することができます。 Microsoft は、Microsoft Teams を使用して企業のお客様を対象としており、HIPAA の要件と制御に対応しています。 [患者] アプリから PHI へのアクセスは完全に追跡され、ログは M365 セキュリティ/コンプライアンスセンターで利用可能になります。詳細については、「[監査ログの検索機能](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)」の記事を参照してください。

> [!IMPORTANT]
> 患者のプライバシーを維持する負担は、法律によって医療機関に適用されます。 法律では、患者は患者のプライバシーを保護する必要があります。また、IT 管理者または HIPAA のコントローラーが、どの看護師、clinician、またはソーシャルワーカーのアクセスまたは変更されたかを簡単に判断する必要があります。 PHI アクセス違反の最も一般的な例の1つは、VIP 患者へのアクセスです。 監査ログ機能は、PHI アクセス違反の調査を実施し、HIPAA の要件を満たすために必要です。

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>患者アプリの監査ログを有効にする

監査は、いくつかの以前の構成に依存します。

1. 管理者は、自分の FHIR サービスプロバイダーと協力して、患者アプリで使用されている形式で EMR を利用できるようにする必要があります。 「[電子医療記録を Microsoft Teams に統合](patients-app.md)する」を参照してください。
2. 医療機関管理者は、Teams 管理センターで患者アプリを有効にする必要があります。 詳細については、「 [Microsoft Teams でアプリセットアップポリシーを管理](../../teams-app-setup-policies.md)する」を参照してください。
3. [Office 365 監査ログの検索を有効または無効](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search)にする前に説明し[た](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin)ように、管理者は 365 O365 でアクティビティの監査を有効にする必要があります。 監査ログがすでにオンになっている場合は、患者アプリに特別な情報は必要ありません。 医療機関がチーム内でアプリをインストールして実行するたびに、監査ログには PHI アクティビティが記録されます。
4. その後、管理者は、患者アプリの利用可能状況を知らせる必要があります。また、ヘルスケア担当者は、監査に含めるアクティビティの生成を開始する必要があります。

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>監査を実行する

アクティビティログの検索を実行する方法については、「[監査ログを検索](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)する」を参照してください。

## <a name="logged-activities-for-patients-app"></a>患者アプリのログに記録されたアクティビティ

患者のアプリには、次の表に示すように、独自のログに記録されたアクティビティが含まれています。

|フレンドリ名 |操作|説明|
|:---|:---|:---|
| 患者リストを表示 | PatientListView | ユーザーが患者リストを表示しました。|
| 削除された患者リスト | PatientListDelete | ユーザーが患者のリストを削除しました。|
| リストに患者が追加されました | PatientListAddPatient | 患者が患者のリストに追加されました。 |
| 患者のメモが追加されました | PatientNoteAdd | 患者レコードにメモが追加されました。 |
| 作成された患者のスキーマ | PatientSchemaCreate | 患者レコードで使用されている一連の列が作成されました。 |
| ユーザーがエクスポートを開始しました | エクスポートの開始 | 患者データは、患者アプリから Excel ファイルにエクスポートされました。 ファイルは、チームの sharepoint サイトに保存されます。 |
| 作成された患者リスト | PatientListCreate | ユーザーが患者のリストを作成しました。|
| 既定の患者リストを設定する| PatientListDefaultSet| ユーザーが既定のリストとして特定のリストを設定した場合。|
| リストから患者が削除されました| PatientListRemovePatient | 患者が患者のリストから削除されました。 |
| 患者の検索 | PatientSearch | EHR サービスの患者レコードを検索します。 |
| 更新された患者のスキーマ | PatientSchemaUpdate  | 患者レコードで使用されている既存の列セットを更新しました。 |<!-- | 患者が別のリストに移動されました| PatientMoved | 患者レコードが別のリストに移動されました。 |-->
| 患者リストの名前が変更されました | PatientListRename | 患者の一覧の名前が変更されました。 |
| 患者リストで編集した列 | PatientListEditColumns | 患者リストの列が編集された (追加または削除された)。 |
| 患者の詳細を表示 | PatientView | ユーザーが患者レコードを表示しました。|
| 編集される患者の詳細 | PatientDetailsEdit | 患者レコードの詳細が編集されました。 |
| EHR 接続を設定する | EHRConnectionSet | EHR FHIR サービス接続に接続するために使用する URL を設定します。 例: https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |
||||

必要に応じて監査をカスタマイズして、これらのログに記録されたアクティビティを検索またはフィルター処理することができます。

一般的な Microsoft Teams のログに記録されたアクティビティについては、「 [Microsoft teams のアクティビティ](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)」を参照してください。

## <a name="related-topics"></a>関連トピック

[Office 365 監査ログを検索する](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[電子医療記録を Microsoft Teams に統合する](patients-app.md)
