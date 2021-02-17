---
title: Teams の医療テンプレートを使用してチームを作成する
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 管理センターまたは Microsoft Graph で Microsoft Teams テンプレートを使用すると、設定、チャネル、アプリの定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260309"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>Teams の医療テンプレートを使用してチームを作成する

Microsoft Teams テンプレートを使用すると、設定、チャネル、およびプレインストールされているアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。

医療組織の場合、テンプレートは特に強力です。テンプレートは、ユーザーが Teams を効果的に使用する方法を指向するための構造を提供します。 また、テンプレートを使用すると、管理者は組織全体に一貫したチームを展開できます。 この記事は、医療組織全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。

Teams の医療テンプレートを使用してチームを作成する方法を選択します。

| 誰が | 使用する方法: |
| ---- | --------- |
| 管理者と IT プロフェッショナル | [Teams 管理センターを使用して、](#use-the-teams-templates-in-the-teams-admin-center) 医療 Teams テンプレートに基づいてチームを作成します。|
| 開発者とシステム インテグレーター | [Microsoft Graph を使用して](#use-the-teams-templates-with-the-microsoft-graph) 、医療チームのテンプレートに基づいてチームを作成します。 |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Teams 管理センターで Teams テンプレートを使用する

Microsoft Teams 管理者は、Teams 管理センターを使用して、Teams テンプレートを使用してチームを作成できます。 現在、さまざまな状況で使用できる 2 つのファースト パーティの医療テンプレートを提供しています。 チーム テンプレート全般の詳細については、管理センターの「Teams テンプレートの使用を開始する」 [を参照してください](../../get-started-with-teams-templates-in-the-admin-console.md)。

### <a name="collaborate-on-patient-care"></a>患者の治療で共同作業する

 ワード、ポッド、部署内の医療コミュニケーションとコラボレーションを合理化します。 テンプレートを使用すると、患者管理とワードの業務上のニーズを容易に行えます。

| 基本テンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------ |---|----------------------------------------------------- |
| 患者の治療で共同作業する |`healthcareWard` | チャネル:<ul><li>General</li><li>お知らせ</li><li>ハドル</li><li>丸め</li><li>スタッフ</li><li>トレーニング</li></ul> アプリ: <ul><li>Wiki</li><li>リスト</li></ul>|
||||

### <a name="hospital"></a>病院

病院内の複数のワード、ポッド、部署間のコミュニケーションとコラボレーションを合理化します。 このテンプレートには、病院の運営のための基本チャネルのセットが含まれています。自己拡張して専門分野を臨時に含めすることができます。

| 基本テンプレートの種類 |baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------|-- |----------------------------------------------------- |
|病院|`healthcareHospital`|チャネル: <ul><li>General</li><li>お知らせ</li><li>コンプライアンス</li><li>Custodial</li><li>人事</li><li>[分数]</li></ul> アプリ: <ul><li>Wiki</li><li>リスト </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Microsoft Graph で Teams テンプレートを使用する

開発者は Microsoft Graph を使用して、Teams テンプレートを使用してチームを作成できます。 現在、さまざまな状況で使用できる 2 つのファースト パーティの医療テンプレートを提供しています。 チーム テンプレート全般の詳細については、「Teams テンプレートの使用を開始 [する」を参照してください](../../get-started-with-teams-templates.md)。 Teams テンプレートと Microsoft Graph の詳細については [、Microsoft Teams API](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) の概要と [teamsTemplate リソースの種類を参照してください](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)。

### <a name="ward-template"></a>ワードテンプレート

ワード テンプレートは、ワード、ポッド、部署内でのコミュニケーションと共同作業を行う場合に使用します。 テンプレートを使用すると、患者の管理と、ワードの業務上のニーズを容易に行えます。 たとえば、ワードのお知らせは [お知らせ] チャネルに投稿し、シフトはスタッフ管理で *管理できます*。 ワード操作を合理化する場合は、このテンプレートが最適です。

|基本テンプレートの種類 |baseTemplateId |ベースライン テンプレート チャネル|
|:--- |:---|:---|
|医療 - ワード | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | お知らせ\* <br> ハドル\* <br> 丸め\* <br> スタッフ\* <br> トレーニング\* |
|     | |         |

\* 自動お気に入り

### <a name="hospital-template"></a>病院のテンプレート

病院テンプレートは、病院内の複数のワード、ポッド、部署間のコミュニケーションと共同作業を行う場合に使用します。 このテンプレートには、お知らせ、カストディアル、役員用など、いくつかの運用チャネルが含まれていますが、以下のスクリプトも用意されています。このスクリプトでは、お好みで追加、削除、または編集できる、さまざまな部門または専門中心のチャネルを含むテンプレートを拡張します。  たとえば、内科学部門を持っているが *、Ophophmology* のチャネルが必要ない場合、スクリプトは内科学チャネルを含め *、Ophophmology* チャネルを削除するために適応できます。  通知の飽和を避けるために、これらの専門チャネルまたはワードモデルのチャネルは自動お気に入りに追加しないようにすることをお勧めします。 ユーザーは通常、関連するチャネルをお気に入りに追加します。

|基本テンプレートの種類 |baseTemplateId |ベースライン テンプレート チャネル|
|:--- |:---|:---|
|医療 - 病院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | お知らせ\* <br> コンプライアンス\* <br> Custodial <br> 人事 <br> [分数] |
| | |  |

\* 自動お気に入り 

### <a name="how-to-use-first-party-templates"></a>ファースト パーティテンプレートの使い方

これらのテンプレートを使用するには、要求本文の "template@odata.bind" プロパティを "標準" から上記の TemplateID に変更します。  Teams テンプレートを展開する方法の詳細については、チームを作成する方法に関する Microsoft Graph の [記事を参照してください](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> テンプレートのチャネルは、[全般] タブの下に自動的に作成されます。

#### <a name="example-hospital-template-extension-script"></a>例: 病院テンプレート拡張スクリプト

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-topics"></a>関連項目

[Teams のテンプレートの使用を開始する](../../get-started-with-teams-templates.md)

[医療関係組織のためのTeamsを始めましょう](teams-in-hc.md)
