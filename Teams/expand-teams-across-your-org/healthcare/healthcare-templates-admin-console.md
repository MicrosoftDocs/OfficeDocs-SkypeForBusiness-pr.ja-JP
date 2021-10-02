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
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: 医療組織のチームを迅速かつ簡単に作成するために、Teams 管理センターや Microsoft Graph で医療テンプレートを管理および使用する方法を説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 78269b393c384af82e48284e3ffefe8785013975
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046003"
---
# <a name="use-healthcare-team-templates"></a>Teamsの医療テンプレートを使用する

Microsoft Teams のチーム テンプレートでは、設定、チャネル、事前にインストールされたアプリの定義済みチーム構造を使用することで、チームをすばやく簡単に作成できます。

医療組織の場合、チーム テンプレートは特に強力で、組織全体に一貫したチームを迅速に展開するのに役立ちます。 テンプレートは、スタッフが Teams を効果的に使用する方法を理解するのにも役立ちます。

Teams には、医療組織用に特化して設計されたテンプレートがあります。 これらの事前構築済みのテンプレートを使用して、患者の治療や運用上の必要に応じてスタッフがコミュニケーションや共同作業を行うチームを迅速に作成できます。 この記事では、これらの各テンプレートを紹介し、それらの使用方法を推奨します。

チーム テンプレートの管理方法と作業方法は、管理者か開発者かによって異なります。

|以下の場合: | 次に、以下の場合: |
| ---- | --------- |
| 管理者または IT 担当者 |[Teams 管理センターでチーム テンプレートを管理](#manage-team-templates-in-the-teams-admin-center)します。チーム テンプレートを表示し、テンプレート ポリシーを適用して、Teams でチームを作成するためにスタッフが使用できるテンプレートを制御します。 |
| 開発者 | [Microsoft Graph を使用](#use-team-templates-with-microsoft-graph)して、チーム テンプレートでチームを作成します。 |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Teams 管理センターでチーム テンプレートを管理する

管理者として、Microsoft Teams 管理センターでチーム テンプレートを管理できます。 こちらで、各テンプレートに関する詳細を表示できます。 [テンプレート ポリシーを作成してスタッフに割り当て](../../templates-policies.md)、[チームの作成](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)のために Teams でスタッフが表示できるテンプレートを制御することもできます。

一般的なチーム テンプレートの詳細については、「[Teams 管理センターでチーム テンプレートの使用を開始する](../../get-started-with-teams-templates-in-the-admin-console.md)」をご参照ください。

現在、次の事前構築済みの医療チーム テンプレートを提供しています。 表示するには、Teams 管理センターの左側のナビゲーションで、**[Teams]**、 > **[チーム テンプレート]** の順に移動します。
### <a name="patient-care"></a>患者のケア

 このテンプレートは、病棟、ポッド、部門内でのコミュニケーションと共同作業を対象としています。 このテンプレートを使用して、患者や病棟の業務上のニーズの管理に容易に対応できます。 たとえば、*[お知らせ]* チャネルで病棟のお知らせを投稿し、*[スタッフ]* チャネルでシフトを管理します。

| テンプレートの種類 |TemplateId| このテンプレートに含まれるプロパティ |
| ------------------ |---|----------------------------------------------------- |
| 患者のケア |`healthcareWard` | チャネル<ul><li>全般</li><li>お知らせ<ul><li>情報 &sup1;</li></ul></li><li>打ち合わせ<ul><li>リスト (患者リスト) &sup1;</li></ul></li><li>ラウンド<ul><li>検査 &sup1;</li></ul></li><li>人員配置</li><li>トレーニング</li></ul> アプリ: <ul><li>Wiki</li><li>リスト</li><li>タスク</li><li>承認</li><li>Shifts</li><li>情報</li><li>検査</li></ul>|
||||

&sup1; アプリがタブとしてチャネルに追加されました
### <a name="hospital"></a>病院

このテンプレートは、病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を対象としています。 このテンプレートには、病院での活動のためのチャネルのセットが含まれており、拡張してさらにカスタマイズすることもできます。

| テンプレートの種類 |TemplateId | このテンプレートに含まれるプロパティ |
| ------------------|-- |----------------------------------------------------- |
|病院|`healthcareHospital`|チャネル <ul><li>全般<ul><li>リスト &sup1;</li></ul></li><li>お知らせ<ul><li>情報 &sup1;</li></ul></li><li>コンプライアンス</li><ul><li>検査 &sup1;</li></ul></li><li>親権</li><li>人事管理<ul><li>アイデア&sup1;</li></ul></li><li>薬局</li></ul> アプリ: <ul><li>Wiki</li><li>タスク</li><li>リスト</li><li>承認</li><li>Shifts</li><li>情報</li><li>検査</li><li>アイデア</li></ul>|
||||

&sup1; アプリがタブとしてチャネルに追加されました
## <a name="use-team-templates-with-microsoft-graph"></a>Microsoft Graph で Teams テンプレートを使用する

開発者は、Microsoft Graph を使用して、事前構築済みのチーム テンプレートからチームを作成できます。Microsoft Graph でチーム テンプレートを使用する方法の詳細については、「[Microsoft Graph を使用して、チーム テンプレートの使用を開始する](../../get-started-with-teams-templates.md)」、「[Microsoft Teams API の概要](/graph/teams-concept-overview?view=graph-rest-1.0)」、および「[teamsTemplate リソースの種類](/graph/api/resources/teamstemplate?view=graph-rest-1.0)」を参照してください。

こちらに事前構築済みの医療チーム テンプレートを示します。
### <a name="ward"></a>病棟

この病棟用テンプレートは、病棟、ポッド、部門内でのコミュニケーションと共同作業を対象としています。 このテンプレートを使用すると、患者や病棟の業務上のニーズの管理に容易に対応できます。 たとえば、病棟の連絡事項は、*お知らせ* チャネルに投稿され、シフトは、 *スタッフィング* で管理できます。 このテンプレートは、病棟業務の効率化を図っている場合に最適です。

|[テンプレートの種類] |TemplateId |テンプレート チャネル|
|:--- |:---|:---|
|医療 - 病棟 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | 全般<br>お知らせ &sup2; <br> 打ち合わせ &sup2; <br> ラウンド &sup2; <br> 人員配置 &sup2; <br> トレーニング &sup2; |
|     | |         |

&sup2; お気に入りに自動登録されたチャネル

### <a name="hospital"></a>病院

病院のテンプレートは、病院内の複数の病棟、ポッド、部門間のコミュニケーションと共同作業を対象としています。 このテンプレートには、*お知らせ*、*管理*、*薬局* など、いくつかの運用チャネルがあります。 また、追加の部署や専門チャネルを使用してテンプレートを拡張するために使用できるスクリプトも用意されています。 ニーズに合わせてスクリプトを編集できます。

たとえば、*Endocrinology (内分泌学)* 部門はあるが、*Ophthalmology (眼科学)* のチャネルが必要ない場合、スクリプトで調整して、*Endocrinology (内分泌学)* チャネルを含め、 *Ophthalmology (眼科学)* のチャネルを削除することができます。 このような専門的なチャネルまたは病棟用に特化したチャネルは、過度の通知を回避するために、自動的にお気に入りに登録しないことをお勧めします。 ユーザーは通常、自分に関連するチャンネルをお気に入りにしています。

|テンプレートの種類 |TemplateId |テンプレート チャネル|
|:--- |:---|:---|
|医療 - 病院 | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | 全般<br>お知らせ &sup2; <br> コンプライアンス &sup2; <br> カストディアル <br> 人事 <br> 薬局 |
| | |  |

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
- [医療組織向けの Teams の使用を開始する](teams-in-hc.md)