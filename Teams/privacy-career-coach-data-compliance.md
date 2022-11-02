---
title: キャリア コーチのデータとコンプライアンス情報
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ''
search.appverid: MET150
f1keywords: ''
description: 教育機関または EDU のキャリア コーチに関して Microsoft が取ったプライバシー、コンプライアンス、および Purview 対策について説明します。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 0f28381aad61cbe7fecf21e189bc5ab278ce3008
ms.sourcegitcommit: 9ea1ed450ba89e9cbc094018a832bd25c08e92e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2022
ms.locfileid: "68825685"
---
# <a name="career-coach-data-and-compliance"></a>キャリア コーチのデータとコンプライアンス

この記事では、アプリ内機能やその他のツールを使用して、個人データまたは個人情報を見つけて行動し、GDPR 義務に準拠したデータ主体要求 (DSR) に対応する方法について説明します。 キャリア コーチは、データを顧客コンテンツとシステム生成ログの 2 つのカテゴリに大まかに分類します。 Career Coach では、顧客コンテンツにはユーザー データ、テナント構成データ、学生アクティビティ データが含まれますが、システム生成ログには、Microsoft がエンタープライズ サービスをユーザーに提供するのに役立つ Microsoft によって生成されたログと関連データが含まれます。

## <a name="customer-content"></a>顧客コンテンツ

### <a name="user-data"></a>ユーザー データ

キャリアコーチによって収集されたユーザーデータには、目標や活動の進捗状況、研究分野、学年、保存されたスキル、保存されたキャリア、アップロードされた履歴書、トランスクリプトなどのプロファイル情報が含まれます。

#### <a name="deleting-user-data"></a>ユーザー データの削除

キャリア コーチからユーザー データを削除するには、次の手順に従います。

1. グローバル管理者は、GDPR 削除 DSR (データ主体要求) 操作の要求を明確に示す [サポート チケット](https://edusupport.microsoft.com/support?product_id=career_coach) を開く必要があります。 **削除のデータ セットまたは時間枠を制限する機能はありません**。
2. 要求では、削除する必要があるデータの種類を明確に示す必要があります。
    1. テナントのすべてのユーザー データ。
    2. 特定のユーザーのユーザー データ。 削除要求の一部として、ユーザーの OID (オブジェクト識別子) を含めてください。
3. 提出後、コンプライアンスの最小限の保持ポリシーを満たすために、サポート チケットは 1 週間後に対処されます。 この期間中に操作を取り消すことができます。
4. 1 週間後、キャリア コーチ チームはテナントに関連するすべてのデータを削除します。 Microsoft サポートはチケットを監視し、削除プロセスが完了すると  **30 日以内に** 通知されます。

#### <a name="exporting-user-data"></a>ユーザー データのエクスポート

キャリア コーチからユーザー データをエクスポートするには、次の手順に従います。

1. [オープンキャリアコーチ](https://aka.ms/Career_Coach_App) プロファイルを表示します。
1. [プライバシーとセキュリティ] セクションまでスクロールします。
1. [ダウンロード] を選択して、アカウントのすべての顧客データをエクスポートします。

### <a name="tenant-configuration-data"></a>テナント構成データ

テナント データには、Career Coach アプリケーション構成の一部としてアップロードまたは生成された情報が含まれます。 このデータには、テナントのブランド情報、ロゴと学習アイコン、コース カタログ、LinkedIn 学校の URL、学習リストのフィールド、および Teams 管理センターのキャリア コーチ テナント構成中に追加されたすべてのデータが含まれます。

#### <a name="deleting-tenant-configuration-data"></a>テナント構成データの削除

キャリア コーチからテナント構成データを削除するには、次の手順に従います。

1. グローバル管理者は、テナントの構成データを削除する要求を明確に示す [サポート チケットを開く](https://edusupport.microsoft.com/support?product_id=career_coach) 必要があります。 **削除のデータ セットまたは時間枠を制限する機能はありません**。
1. 提出後、コンプライアンスの最小限の保持ポリシーを満たすために、サポート チケットは 1 週間後に対処されます。 この期間中に操作を取り消すことができます。
1. 1 週間後、キャリア コーチ チームはテナントに関連するすべてのデータを削除します。 Microsoft サポートはチケットを監視し、削除プロセスが完了すると  **30 日以内に** 通知されます。

### <a name="student-activity-data"></a>学生のアクティビティ データ

キャリア コーチは、学生のアクティビティ データを [Education Insights](class-insights.md)と同じ場所に格納します。 集計されたデータは、キャリア コーチの学生アクティビティ分析情報エクスペリエンス内に表示されます。 この機能を強化するためにキャプチャされた学生の使用状況データは、保存され、1 年間保持されます。

#### <a name="deleting-student-activity-data"></a>学生アクティビティ データの削除

個人またはテナントの学生アクティビティ データを削除するには、「 [Education Insights からユーザー データを削除する方法](class-insights.md#how-to-delete-user-data-from-education-insights)」の手順に従います。

## <a name="system-generated-logs"></a>システムによって生成されたログ

システム生成ログには、Microsoft がエンタープライズ サービスをユーザーに提供するのに役立つ、Microsoft によって生成されたログと関連データが含まれます。 システム生成ログには、個人を識別することはできませんが、エンタープライズ サービスをユーザーに提供するために使用される一意識別子 (通常はシステムによって生成される数値) などの、主に仮名化されたデータが含まれます。 このデータの例を次に示します。

- ユーザー アクティビティ ログなどの製品およびサービスの使用状況データ。
- ユーザー検索要求とクエリ データ。
- ユーザーまたは他のシステムによるシステム機能と対話の製品として製品やサービスによって生成されたデータ。

> [!NOTE]
> システム生成ログのデータを制限または修正する機能はサポートされていません。 システム生成ログ内のデータは、Microsoft クラウドと診断データ内で行われる事実に基づくアクションを構成し、そのようなデータを変更すると、アクションの履歴記録が損なわれ、詐欺やセキュリティリスクが高まります。 キャリア コーチは、システム生成ログを 30 日間保持します。

### <a name="exporting-and-deleting-system-generated-logs"></a>システム生成ログのエクスポートと削除

テナント グローバル管理者は、特定のユーザーによる Office 365 サービスとアプリケーションの使用に関連するシステム生成ログにアクセスできる組織内の唯一のユーザーです。 キャリア コーチは、 [Office 365によって提供されるシステム生成ログにアクセスしてエクスポートするプロセスと](https://learn.microsoft.com/compliance/regulatory/gdpr-dsr-Office365#accessing-and-exporting-system-generated-logs)一致します。

## <a name="more-information"></a>詳細情報

- [Microsoft Teams のキャリア コーチの概要](career-coach.md)
- [プライバシーに関するよく寄せられる質問](https://privacy.microsoft.com/faq)
- [Microsoft 製品とデータ - Microsoft プライバシー](https://privacy.microsoft.com/privacy-in-our-products)
- [Microsoft アカウントのプライバシー設定](https://account.microsoft.com/account/privacy?refd=privacy.microsoft.com&ru=https%3A%2F%2Faccount.microsoft.com%2Fprivacy%2F%3Frefd%3Dprivacy.microsoft.com&destrt=privacy-dashboard)
