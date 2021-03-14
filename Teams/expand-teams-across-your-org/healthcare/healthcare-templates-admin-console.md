---
title: Teams ヘルスケア テンプレートを使用してチームを作成する
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
description: 管理センターまたは Microsoft Graph で Microsoft Teams テンプレートを使用すると、設定、チャネル、およびアプリの定義済みのテンプレートを使用することで、チームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260309"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a>Teams ヘルスケア テンプレートを使用してチームを作成する

Microsoft Teams テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みテンプレートを使用することで、チームをすばやく簡単に作成できます。

医療組織の場合、テンプレートは特に有益です。テンプレートにより、ユーザーは Teams を効果的に使用する方法を自然に理解できます。 また、テンプレートを使用すると、管理者は組織全体で一貫したチームを展開できます。 この記事は、貴社の医療組織全体で複数のチームを計画、展開し、管理する責任があるユーザーに役立ちます。

Teams ヘルスケア テンプレートを使用してチームを作成する方法を選択します。

| 名前 | 使用する方法: |
| ---- | --------- |
| 管理者と IT プロフェッショナル | [Teams 管理センター を使用](#use-the-teams-templates-in-the-teams-admin-center)して、ヘルスケアの Teams のテンプレートに基づいてチームを作成できます。|
| 開発者およびシステム インテグレーター | [Microsoft Graph ツールを使用](#use-the-teams-templates-with-the-microsoft-graph)して、ヘルスケアの Teams のテンプレートに基づいてチームを作成します。 |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a>Teams 管理センターで Teams テンプレートを使用する

Microsoft Teams 管理者は、Teams 管理センターで、Teams テンプレートを使用してチームを作成できます。 現在、ファースト パーティの医療テンプレートが 2 つ提供されています。このテンプレートはさまざまな状況で使用できます。 一般的なチーム テンプレートの詳細については、「[管理センターで Teams テンプレートの使用を開始する](../../get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。

### <a name="collaborate-on-patient-care"></a>患者の治療で共同作業を行う

 病棟、ポッド、部門内の医療コミュニケーションと共同作業を合理化できます。 このテンプレートを使用すると、患者や病棟の業務上のニーズの管理に容易に対応できます。

| 基本テンプレートの種類 |baseTemplateId| この基本テンプレートに含まれるプロパティ |
| ------------------ |---|----------------------------------------------------- |
| 患者の治療で共同作業を行う |`healthcareWard` | チャネル<ul><li>全般</li><li>お知らせ</li><li>ハドル</li><li>ラウンド</li><li>人員配置</li><li>トレーニング</li></ul> アプリ: <ul><li>Wiki</li><li>リスト</li></ul>|
||||

### <a name="hospital"></a>病院

病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を合理化します。 このテンプレートには、病院での活動のための基本チャネルのセットが含まれています。自分で拡張して専門分野をその場で含めすることもできます。

| 基本テンプレートの種類 |baseTemplateId | この基本テンプレートに含まれるプロパティ |
| ------------------|-- |----------------------------------------------------- |
|病院|`healthcareHospital`|チャネル <ul><li>全般</li><li>お知らせ</li><li>コンプライアンス</li><li>親権</li><li>人事管理</li><li>薬局</li></ul> アプリ: <ul><li>Wiki</li><li>リスト </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a>Microsoft Graph で Teams テンプレートを使用する

開発者は、Microsoft Graph を使用して、Teams テンプレートでチームを作成できます。 現在、ファースト パーティの医療テンプレートが 2 つ提供されています。このテンプレートはさまざまな状況で使用できます。 一般的なチーム テンプレートの詳細については、「[Teams テンプレートの使用を開始する](../../get-started-with-teams-templates.md)」をご参照ください。 また、Teams テンプレートと Microsoft Graph については、「[Microsoft Teams API の概要 ](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0)」 および 「[Teams テンプレート リソース タイプ](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)」をご参照ください。

### <a name="ward-template"></a>病棟用テンプレート

この病棟用テンプレートは、病棟、ポッド、部門内でのコミュニケーションと共同作業を対象としています。 このテンプレートを使用すると、患者や、病棟の業務上のニーズの管理が容易にできます。 たとえば、病棟の連絡事項は、*お知らせ* チャネルに投稿され、シフトは、 *スタッフィング* で管理できます。 このテンプレートは、病棟業務の効率化を図っている場合に最適です。

|基本テンプレートの種類 |baseTemplateId |ベースライン テンプレート チャネル|
|:--- |:---|:---|
|ヘルスケア - 病棟 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | お知らせ\* <br> ハドル\* <br> ラウンド\* <br> 人員配置\* <br> トレーニング\* |
|     | |         |

\*自動的にお気に入りに登録する

### <a name="hospital-template"></a>病院のテンプレート

病院のテンプレートは、病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を対象としています。 このテンプレートには、*お知らせ*、*カストディアル* および *薬品* を含むいくつかの運用チャネルが含まれていますが、テンプレートの拡張が可能なスクリプトも用意されています。このスクリプトに、必要に応じて追加の部門、専門的な中枢チャネルを追加、削除、または編集できます。 たとえば、*Endocrinology (内分泌学)* 部門はあるが、*Ophthalmology (眼科学)* のチャネルが必要ない場合、スクリプトで調整して、*Endocrinology (内分泌学)* チャネルを含め、 *Ophthalmology (眼科学)* のチャネルを削除することができます。 このような専門的なチャネルまたは病棟用に特化したチャネルは、過度の通知を回避するために、自動的にお気に入りに登録しないことをお勧めします。 ユーザーは通常、自分に関連するチャンネルをお気に入りにしています。

|基本テンプレートの種類 |baseTemplateId |ベースライン テンプレート チャネル|
|:--- |:---|:---|
|医療 - 病院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | お知らせ\* <br> コンプライアンス\* <br> カストディアル <br> 人事 <br> 薬局 |
| | |  |

\*自動的にお気に入りに登録する 

### <a name="how-to-use-first-party-templates"></a>ファースト パーティ テンプレートの使い方

これらのテンプレートを使用するには、要求本文の 'template@odata.bind' プロパティを '標準' から TemplateIDs に変更します。  Teams テンプレートを展開する方法の詳細については、「[チームの作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)方法に関する Microsoft Graph の記事」をご参照ください。

> [!NOTE]
> テンプレートのチャネルは自動的に [全般] タブに作成されます。

#### <a name="example-hospital-template-extension-script"></a>例: 病院テンプレート拡張機能スクリプト

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

[医療組織向けの Teams の使用を開始する](teams-in-hc.md)
