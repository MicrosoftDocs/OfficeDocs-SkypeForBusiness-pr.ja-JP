---
title: 医療組織向けテンプレート
author: serdarsoysal
ms.author: serdars
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
description: Microsoft Graph で Microsoft Teams テンプレートを使用すると、設定、チャネル、アプリの定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX
ms.openlocfilehash: e288bc68c8160fb80d4e56a6477437e0a79fea0a
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260339"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>医療組織向け Teams テンプレートの使用を開始する

Microsoft Teams テンプレートを使用すると、設定、チャネル、およびプレインストールされているアプリの定義済みのテンプレートを提供することで、チームをすばやく簡単に作成できます。

医療組織の場合、テンプレートは特に強力です。テンプレートは、ユーザーが Teams を効果的に使用する方法を指向するための構造を提供します。 また、テンプレートを使用すると、管理者は組織全体に一貫したチームを展開できます。 この記事は、医療組織全体で複数のチームを計画、展開、管理する責任がある場合に役立ちます。

現在、さまざまな状況で使用できる 2 つのファースト パーティの医療テンプレートを提供しています。 チーム テンプレート全般の詳細については、「Teams テンプレートの使用を開始 [する」を参照してください](../../get-started-with-teams-templates.md)。

## <a name="ward-template"></a>ワードテンプレート

ワード テンプレートは、ワード、ポッド、部署内でのコミュニケーションと共同作業を行う場合に使用します。 テンプレートを使用すると、患者の管理と、ワードの業務上のニーズを容易に行えます。 たとえば、ワードのお知らせは [お知らせ] チャネルに投稿し、シフトはスタッフ管理で *管理できます*。 ワード操作を合理化する場合は、このテンプレートが最適です。

|基本テンプレートの種類 |baseTemplateId |ベースライン テンプレート チャネル|
|:--- |:---|:---|
|医療 - ワード | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | お知らせ\* <br> ハドル\* <br> 丸め\* <br> スタッフ\* <br> トレーニング\* |
|     | |         |

\* 自動お気に入り

## <a name="hospital-template"></a>病院のテンプレート

病院テンプレートは、病院内の複数のワード、ポッド、部署間のコミュニケーションと共同作業を行う場合に使用します。 このテンプレートには、お知らせ、カストディアル、役員用など、いくつかの運用チャネルが含まれていますが、以下のスクリプトも用意されています。このスクリプトでは、お好みで追加、削除、または編集できる、さまざまな部門または専門中心のチャネルを含むテンプレートを拡張します。  たとえば、内科学部門を持っているが *、Ophophmology* のチャネルが必要ない場合、スクリプトは内科学チャネルを含め *、Ophophmology* チャネルを削除するために適応できます。  通知の飽和を避けるために、これらの専門チャネルまたはワードモデルのチャネルは自動お気に入りに追加しないようにすることをお勧めします。 ユーザーは通常、関連するチャネルをお気に入りに追加します。

|基本テンプレートの種類 |baseTemplateId |ベースライン テンプレート チャネル|
|:--- |:---|:---|
|医療 - 病院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | お知らせ\* <br> コンプライアンス\* <br> Custodial <br> 人事 <br> [分数] |
| | |  |

\* 自動お気に入り 

## <a name="how-to-use-first-party-templates"></a>ファースト パーティテンプレートの使い方

これらのテンプレートを使用するには、要求本文の "template@odata.bind" プロパティを "標準" から上記の TemplateID に変更します。  Teams テンプレートを展開する方法の詳細については、チームを作成する方法に関する Microsoft Graph の [記事を参照してください](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)。

> [!NOTE]
> テンプレートのチャネルは、[全般] タブの下に自動的に作成されます。

### <a name="example-hospital-template-extension-script"></a>例: 病院テンプレート拡張スクリプト

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

## <a name="related-topics"></a>関連項目

[Teams のテンプレートの使用を開始する](../../get-started-with-teams-templates.md)

[医療関係組織のためのTeamsを始めましょう](teams-in-hc.md)

[管理コンソールで Teams テンプレートの使用を開始する](../../get-started-with-teams-templates-in-the-admin-console.md)
