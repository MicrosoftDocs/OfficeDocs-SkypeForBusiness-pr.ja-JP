---
title: 医療関係組織向けテンプレートでTeamsを始めましょう
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 医療関係組織向けテンプレートでTeamsを始めましょう
ms.openlocfilehash: 38b2067bc91a79ff2efa8bc20726ad14d793aa24
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245883"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>医療関係組織向けテンプレートでTeamsを始めましょう

マイクロソフト チーム テンプレートでは、迅速にすることし、設定、チャネル、およびプリインストールされているアプリケーションの定義済みのテンプレートを提供することで簡単にチームを作成します。

医療機関は、テンプレートは、特に強力なユーザーが最適なチームを効果的に活用する方法を中心になる構造を提供するため。 テンプレートには、管理者は、組織全体で一貫性のあるチームを配置することもできます。 この資料は、計画、展開、および、医療機関での複数のチームの管理を担当する場合のです。

現在提供 2 最初製医療テンプレートのさまざまな状況を活用することができます。 チームの詳細についてテンプレート一般を参照してください[チーム テンプレートを使用して開始](../../get-started-with-teams-templates.md)します。

## <a name="ward-template"></a>ワード テンプレート

ワードのテンプレートは、ワード、ポッド、または部門のコミュニケーションやコラボレーションのものです。 テンプレートは、ワードの運用上のニーズと同様に、患者の管理を容易にするために使用できます。 などの*お知らせ*チャネルでのワードのお知らせを転記して、*スタッフ*のシフトを管理することができます。 区業務を合理化するのには、検索する場合は、このテンプレートは、するのです。

|基本テンプレートの種類 |baseTemplateId |ベースライン テンプレートのチャネル|
|:--- |:---|:---|
|医療・ ワード | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | お知らせ\* <br> Huddles\* <br> ラウンド\* <br> スタッフ\* <br> トレーニング\* |
|     | |         |

\*自動お気に入り

## <a name="hospital-template"></a>病院テンプレート

病院テンプレートは、通信および複数のそして、ポッド、および病院内の部門間のコラボレーションのものです。 含まれますが、このテンプレートに含まれている運用上のいくつかのチャンネル*のお知らせ*、 *Custodial*、および*薬剤*、その他の部門のさまざまなテンプレートを拡張するスクリプトも提供するか、追加、削除、または、自由に編集するためのチャネルを専門分野を中心としました。 などの*Endocrinology*部門がある*Ophthalmology*に、チャネルを必要としない場合は、し、スクリプトに適合できる、 *Endocrinology*チャネルを含めるし、 *Ophthalmology*チャネルを削除します。 これらの専門分野やチャネルのワードのモデル化できないという通知の飽和を避けるために、自動でお気に入りをお勧めします。 ユーザーがいずれかのチャンネルの関連を検索することが一般にお気に入りです。

|基本テンプレートの種類 |baseTemplateId |ベースライン テンプレートのチャネル|
|:--- |:---|:---|
|医療・病院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | お知らせ\* <br> コンプライアンス\* <br> 信託 <br> 人事管理 <br> 薬剤 |
| | |  |

\*自動お気に入り 

## <a name="how-to-use-first-party-templates"></a>パーティの最初のテンプレートを使用する方法

これらのテンプレートを使用するには、要求の本体を上記の TemplateIDs を '標準' からの 'template@odata.bind' プロパティを変更するだけです。  チーム テンプレートを配布する方法の詳細については、Microsoft Graph[でチームを作成する資料](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)を参照してください。

> [!NOTE]
> テンプレート内のチャンネルは、[全般] タブの下に自動的に作成されます。

### <a name="example-hospital-template-extension-script"></a>病院テンプレート拡張スクリプトの例:

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
              "displayName": "Women’s Health",
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

## <a name="related-topics"></a>関連トピック

[Teams のテンプレートの使用を開始する](../../get-started-with-teams-templates.md)

[医療関係組織のためのTeamsを始めましょう](teams-in-hc.md)
