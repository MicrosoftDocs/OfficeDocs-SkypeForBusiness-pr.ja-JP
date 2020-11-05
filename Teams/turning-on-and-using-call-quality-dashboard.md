---
title: 通話品質ダッシュボード (CQD) を設定する
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 通話品質ダッシュボードをオンにして使用し、通話の品質に関する概要レポートを取得する方法について説明します。
ms.openlocfilehash: 9a864b0ad0f48e3a0bd8665b8dfeb917e67f4062
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918648"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) を設定する

で Microsoft 通話品質ダッシュボード (CQD) を開き [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) ます (管理者の資格情報でサインインします)。 または、Teams 管理センターに移動して、[ **通話品質ダッシュボード** ] を選びます。 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 管理センターの [通話品質ダッシュボード] ボタンのスクリーンショット":::

表示されたページで、[ **サインイン** ] をクリックして、グローバル管理者アカウントまたは Microsoft Teams サービス管理者アカウント情報を入力します。 初めてサインインすると、CQD でデータの収集と処理が開始されます。 レポートに意味のある結果を表示するために十分なデータの処理には、1時間以上かかる場合があることに注意してください。

CQD は、組織全体のレベルで、Microsoft Teams、Skype for Business Online、Skype for Business Server 2019 に、通話と会議の品質を示します。 

> [!IMPORTANT]
> Skype for Business Server 2019 で CQD を使用するには、 [通話データコネクタを構成](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)する必要があります。 始める前に「 [通話データコネクタを計画](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) する」を参照してください。


## <a name="assign-admin-roles-for-access-to-cqd"></a>CQD へのアクセスに管理者ロールを割り当てる

CQD にアクセスするための [役割](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) を、使用する必要があるユーザーに割り当てます。

管理者以外のユーザー (サポートエンジニアやヘルプデスクエージェントなど) が通話品質ダッシュボードを使用できるようにするには、次のロールのいずれかをユーザーに割り当てることができます。これにより、CQD へのアクセスが提供されます。 


|  |レポートを表示する  |EUII フィールドを表示する  |レポートを作成する  |建物のデータをアップロードする  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Office 365 のグローバル管理者     |はい         |はい         |はい         |はい         |
|Teams サービス管理者     |はい         |はい         |はい         |はい         |
|Teams 通信管理者     |はい         |はい         |はい         |はい         |
|Teams 通信サポート エンジニア     |はい         |はい         |はい         |いいえ         |
|Teams 通信サポート スペシャリスト     |はい         |いいえ         |はい         |いいえ         |
|Skype for Business 管理者     |はい         |はい         |はい         |はい         |
|Azure AD グローバルリーダー |はい         |はい         |はい         |いいえ         |
|Office 365 レポートリーダー<sup>1</sup>     |はい         |いいえ         |はい         |いいえ         |

<sup>1</sup> CQD レポートの読み取りに加えて、Office 365 レポート閲覧者は、管理センターのすべての [アクティビティレポート](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) と、 [Microsoft 365 導入コンテンツパック](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)のすべてのレポートを表示できます。

> [!NOTE]
> [Euii (エンドユーザーを特定できる情報)](CQD-data-and-reports.md#euii-data)が表示されず、この情報を表示することを許可されているロールの1つがある場合は、CQD によって、28日間のみ EUII が保持されることに注意してください。 28日より前のものは削除されます。

これらの役割の詳細については、「 [Office 365 管理者ロールについ](/office365/admin/add-users/about-admin-roles)て」を参照してください。


初めてサインインすると、CQD でデータの収集と処理が開始されます。 2019年12月以降、古いバージョンの CQD (cqd.lync.com) にアクセスできます。ただし、従来のポータルでは、最新の CQD (cqd.teams.microsoft.com) へのリンクが提供されています。 最終的には、古いバージョンの CQD が廃止されます。 2020年7月1日以降、古いバージョンの CQD は最新の CQD のデータにアクセスします。


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>以前のバージョンの CQD から作成したデータとレポートを移行する

> [!IMPORTANT]
> 2020年7月1日以降、古い CQD () からの建物データとレポートの移行はできなくなりました https://CQD.lync.com) 。 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI を使用して CQD データを分析する

2020年1月の新 [機能: POWER BI クエリテンプレートをダウンロードして CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)します。 CQD データの分析と報告に使用できる、カスタマイズ可能な Power BI テンプレート。

詳細については、「 [POWER BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md) 」を参照してください。


## <a name="related-topics"></a>関連項目

[Teams の通話品質を向上させて監視する](monitor-call-quality-qos.md)

[CQD とは何ですか?](CQD-what-is-call-quality-dashboard.md)

[テナントのアップロードとデータの構築](CQD-upload-tenant-building-data.md)

[CQD データとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で使用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD でのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)
