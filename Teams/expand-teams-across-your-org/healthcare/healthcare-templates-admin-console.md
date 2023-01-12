---
title: Teamsの医療テンプレートを使用する
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
- tier2
- highpri
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: 医療組織のチームを迅速かつ簡単に作成するために、Teams 管理センターや Microsoft Graph で医療テンプレートを管理および使用する方法を説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 17f5ce2774dd163f5f244bea0e685623f64ed59f
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2023
ms.locfileid: "69778967"
---
# <a name="use-healthcare-team-templates"></a>Teamsの医療テンプレートを使用する

Microsoft Teams のチーム テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みチーム構造を使用することで、チームをすばやく簡単に作成できます。

医療組織の場合、チーム テンプレートは特に強力で、組織全体に一貫したチームを迅速に展開するのに役立ちます。 テンプレートは、スタッフが Teams を効果的に使用する方法を理解するのにも役立ちます。

Teams には、医療組織用に特化して設計されたテンプレートがあります。 これらの事前構築済みのテンプレートを使用して、患者の治療や運用上の必要に応じてスタッフがコミュニケーションや共同作業を行うチームを迅速に作成できます。 この記事では、これらの各テンプレートを紹介し、それらの使用方法を推奨します。

チーム テンプレートの管理方法と作業方法は、管理者か開発者かによって異なります。

|以下の場合: | 次に、以下の場合: |
| ---- | --------- |
| 管理者または IT 担当者 |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| 開発者 | [Microsoft Graph を使用](#use-team-templates-with-microsoft-graph)して、チーム テンプレートでチームを作成します。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理センターでチーム テンプレートを管理する

管理者として、Microsoft Teams 管理センターでチーム テンプレートを管理できます。 こちらで、各テンプレートに関する詳細を表示できます。 [テンプレート ポリシーを作成してスタッフに割り当て](../../templates-policies.md)、[チームの作成](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)のために Teams でスタッフが表示できるテンプレートを制御することもできます。

一般的なチーム テンプレートの詳細については、「[Teams 管理センターでチーム テンプレートの使用を開始する](../../get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。

現在、次の事前構築済みの医療チーム テンプレートを提供しています。 表示するには、Teams 管理センターの左側のナビゲーションで、**[Teams]**、 > **[チーム テンプレート]** の順に移動します。

### <a name="patient-care"></a>患者ケア

病棟、ポッド、部門内の医療コミュニケーションと共同作業を合理化できます。 このテンプレートを使用して、患者の管理と病棟の運用ニーズを容易にします。 たとえば、*[お知らせ]* チャネルで病棟のお知らせを投稿し、*[スタッフ]* チャネルでシフトを管理します。

>[!div class="mx-tdBreakAll"]
>| テンプレートの種類 |TemplateId| このテンプレートに含まれるプロパティ |
>| ------------------ |---|----------------------------------------------------- |
>| 患者ケア |`healthcareWard` | チャネル:<ul><li>全般</li><li>お知らせ</li><li>ハドル</li><li>ラウンド</li><li>人員配置</li><li>トレーニング</li></ul> アプリ: <ul><li>承認</li><li>情報</li><li>検査</li><li>リスト</li><li>Shifts</li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul>|

### <a name="hospital"></a>病院

病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を合理化します。 このテンプレートには、病院での活動のためのチャネルのセットが含まれており、拡張してさらにカスタマイズすることもできます。

>[!div class="mx-tdBreakAll"]
>| テンプレートの種類 |TemplateId | このテンプレートに含まれるプロパティ |
>| ------------------|-- |----------------------------------------------------- |
>|病院|`healthcareHospital`|チャネル <ul><li>全般</li><li>お知らせ</li><li>コンプライアンス</li></li><li>親権</li><li>人事</li><li>薬局</li></ul>  アプリ: <ul><li>承認</li><li>情報</li><li>従業員のアイデア</li><li>検査</li><li>リスト</li><li>Shifts</li><li>Planner と To Do によるタスク</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Microsoft Graph で Teams テンプレートを使用する

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](../../get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview), and [teamsTemplate resource type](/graph/api/resources/teamstemplate).

こちらに事前構築済みの医療チーム テンプレートを示します。

### <a name="patient-care"></a>患者ケア

このテンプレートは、病棟、ポッド、部門内でのコミュニケーションと共同作業を対象としています。 このテンプレートを使用して、患者の管理と病棟の運用ニーズを容易にします。 たとえば、病棟の連絡事項は、*お知らせ* チャネルに投稿され、シフトは、 *スタッフィング* で管理できます。 このテンプレートは、病棟業務の効率化を図っている場合に最適です。

>[!div class="mx-tdBreakAll"]
>|[テンプレートの種類] |TemplateId |テンプレート チャネル|
>|:--- |:---|:---|
>|医療 - 病棟 | `https://graph.microsoft.com/beta/teamsTemplates('healthcareWard')`   | 全般<br>お知らせ &sup2; <br> 打ち合わせ &sup2; <br> ラウンド &sup2; <br> 人員配置 &sup2; <br> トレーニング &sup2; |

&sup2; お気に入りに自動登録されたチャネル

### <a name="hospital"></a>病院

このテンプレートは、病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を対象としています。 これには、アナウンス、*カストディアル*、薬局などの複数 *の* 運用チャネルが含 *まれています*。 また、より多くの部門や専門チャネルでテンプレートを拡張するために使用できるスクリプトも用意されています。 ニーズに合わせてスクリプトを編集できます。

たとえば、 *内分泌学* 部門を持っていて、 *眼科* 用のチャネルが必要ない場合は、 *内分泌学* チャネルを含むようにスクリプトを適応させ、 *眼科学* チャネルを削除できます。 このような専門的なチャネルまたは病棟用に特化したチャネルは、過度の通知を回避するために、自動的にお気に入りに登録しないことをお勧めします。 ユーザーは通常、自分に関連するチャンネルをお気に入りにしています。

>[!div class="mx-tdBreakAll"]
>|テンプレートの種類 |TemplateId |テンプレート チャネル|
>|:--- |:---|:---|
>|医療 - 病院 | `https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')`   | 全般<br>お知らせ &sup2; <br> コンプライアンス &sup2; <br> カストディアル <br> 人事 <br> 薬局 |

&sup2; お気に入りに自動登録されたチャネル

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Microsoft Graph で Teams テンプレートを使用する方法

これらのテンプレートを使用するには、要求本文の「template@odata.bind」プロパティを「standard」から上記の TemplateID に変更します。 Teams テンプレートを展開する方法の詳細については、「[Teams の作成](/graph/api/team-post?view=graph-rest-beta)方法に関する Microsoft Graph の記事」をご参照ください。

> [!NOTE]
> テンプレートのチャネルは自動的に **[全般]** タブに作成されます。

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

### <a name="related-articles"></a>関連記事

- [テンプレートからチームを作成する](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Teams 管理センターで Teams テンプレートの使用を開始する](../../get-started-with-teams-templates-in-the-admin-console.md)
- [Microsoft Graph を使用して、チーム テンプレートの使用を開始する](../../get-started-with-teams-templates.md)
- [医療組織向けの Teams の使用を開始する](/microsoft-365/frontline/teams-in-hc?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)