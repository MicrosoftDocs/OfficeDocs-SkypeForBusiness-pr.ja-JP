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
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: 医療関係組織向けテンプレートでTeamsを始めましょう
ms.openlocfilehash: e19c0403f259f400e784faf928738d36df66d618
ms.sourcegitcommit: ced9b584eeceff7ca0109cba5823c7c3ddbd092e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "37886440"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>医療関係組織向けテンプレートでTeamsを始めましょう

Microsoft Teams のテンプレートを使用すると、設定、チャネル、プリインストールされているアプリに定義済みのテンプレートを提供して、チームをすばやく簡単に作成できます。

医療機関の場合、テンプレートは、ユーザーが効率的にチームを効果的に活用できるようにするための構造を提供するため、特に強力です。 テンプレートを使用すると、管理者は組織全体で一貫したチームを展開することができます。 この記事は、医療組織全体で複数のチームの計画、展開、管理を担当している場合に使います。

現時点では、さまざまな状況で利用できる、2つのサードパーティの医療機関向けテンプレートが提供されています。 チームテンプレートの詳細については、「[チームテンプレートの概要](../../get-started-with-teams-templates.md)」を参照してください。

## <a name="ward-template"></a>ワードテンプレート

このテンプレートは、ワード、ポッド、または部門でのコミュニケーションとコラボレーションを目的としています。 このテンプレートを使用すると、患者の管理や、補助の運用ニーズを簡単に行うことができます。 たとえば、"いいね!" を*お知らせ*チャネルに投稿して、*スタッフ*でシフトを管理することができます。 ワード操作の合理化を検討している場合は、このテンプレートが適しています。

|ベーステンプレートの種類 |baseTemplateId |ベースラインテンプレートのチャネル|
|:--- |:---|:---|
|医療 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | お知らせ\* <br> Huddles\* <br> 切り下げ\* <br> 割り当てる\* <br> トレーニング\* |
|     | |         |

\*自動お気に入り

## <a name="hospital-template"></a>病院のテンプレート

病院のテンプレートは、病院内の複数の wards、ポッド、部門間のコミュニケーションとコラボレーションを目的としています。 このテンプレートには、*お知らせ*、 *Custodial*、*薬剤*など、いくつかの運用チャネルが含まれていますが、次のスクリプトを用意して、さまざまな部門でテンプレートを拡張することもできます。好みに合わせて追加、削除、または編集できる特殊な中心のチャネル。 たとえば、 *Endocrinology* department を持っているが、 *Ophthalmology*のチャネルが必要ない場合、スクリプトは*Endocrinology*チャネルを含めて*Ophthalmology*チャネルを削除するように調整できます。 通知の飽和を回避するために、これらの専門分野または補助のチャネルは自動お気に入りにならないようにすることをお勧めします。 通常、ユーザーは関連するチャネルをお気に入りにお気に入りに表示します。

|ベーステンプレートの種類 |baseTemplateId |ベースラインテンプレートのチャネル|
|:--- |:---|:---|
|医療-病院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | お知らせ\* <br> コン\* <br> Custodial <br> 人事 <br> 薬 |
| | |  |

\*自動お気に入り 

## <a name="care-coordination-template"></a>治療の調整テンプレート

治療の調整テンプレートは、治療チーム内でのコミュニケーションを容易にすることを目的としており、multidisciplinary teams などの例があります。 このテンプレートには、skype 専有の患者アプリケーションが事前にロードされています。 患者アプリケーションを使用すると、患者とその関連する価値と vitals の一覧を作成して、丸めや患者管理のシナリオに役立てることができます。 

|ベーステンプレートの種類 |baseTemplateId |ベースラインテンプレートのチャネル|
|:--- |:---|:---|
|ヘルスケアの調整 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareCareCoordination')`   | 治療後のレビュー\* <br> 管理\* <br> トレーニング\* |
| | |  |

\*自動お気に入り 

## <a name="how-to-use-first-party-templates"></a>ファーストパーティテンプレートの使用方法

これらのテンプレートを使用するには、要求本文の ' template@odata.bind ' プロパティを "standard" から "TemplateIDs" に変更します。  Teams テンプレートの展開方法の詳細については、Microsoft Graph の記事「[チームを作成](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)する方法」を参照してください。

> [!NOTE]
> テンプレートのチャネルは、[全般] タブに自動的に作成されます。

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

## <a name="related-topics"></a>関連項目

[Teams のテンプレートの使用を開始する](../../get-started-with-teams-templates.md)

[医療関係組織のためのTeamsを始めましょう](teams-in-hc.md)
