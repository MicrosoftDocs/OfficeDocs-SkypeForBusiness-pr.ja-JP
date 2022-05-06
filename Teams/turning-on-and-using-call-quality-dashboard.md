---
title: 通話品質ダッシュボード (CQD) をセットアップする
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 通話品質ダッシュボードを有効にして使用し、通話品質の概要レポートを取得する方法について説明します。
ms.openlocfilehash: 5a220ac01965623417354df35a9052648652f607
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "60081619"
---
# <a name="set-up-call-quality-dashboard"></a>通話品質ダッシュボードをセットアップする

Microsoft 通話品質ダッシュボード (CQD) を [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) 開きます (管理者資格情報を使用してサインインします)。 または、Teams管理センターに移動し、**Analytics & reportsCall** >  **品質ダッシュボード** を選択します。

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="管理センターの [通話品質ダッシュボード] ボタンTeamsスクリーンショット。":::

開いたページで、[**サインイン**] をクリックし、グローバル管理者アカウントを入力するか、管理者アカウント情報をMicrosoft Teamsします。 初めてサインインすると、CQD によってデータの収集と処理が開始されます。 レポートに意味のある結果を表示するのに十分なデータを処理するには、1 時間以上かかる場合があることに注意してください。

CQD では、Microsoft Teams、Skype for Business Online、Skype for Business Server 2019 の通話と会議の品質が組織全体で表示されます。 

> [!IMPORTANT]
> Skype for Business Server 2019 で CQD を使用するには、[通話データ コネクタを構成](/skypeforbusiness/hybrid/configure-call-data-connector)する必要があります。 開始する前に、「 [通話データ コネクタを計画](/skypeforbusiness/hybrid/plan-call-data-connector) する」を参照してください。


## <a name="assign-admin-roles-for-access-to-cqd"></a>CQD にアクセスするための管理者ロールの割り当て

CQD にアクセスするための [ロール](/microsoft-365/admin/add-users/about-admin-roles) を、それを使用する必要があるユーザーに割り当てます。

管理者以外のユーザー (サポート エンジニアやヘルプデスク エージェントなど) に通話品質ダッシュボードを使用させる場合は、これらのユーザーに次のいずれかのロールを割り当てて、CQD にアクセスできます。 


|&nbsp;  |レポートを表示する  |EUII フィールドを表示する  |レポートを作成する  |データの構築アップロード  |
|---------|:-------:|:-------:|:-------:|:-------:|
|グローバル管理者     |Yes         |Yes         |Yes         |Yes         |
|Teams 管理者     |Yes         |Yes         |Yes         |Yes         |
|Teams 通信管理者     |Yes         |Yes         |Yes         |Yes         |
|Teams 通信サポート エンジニア     |Yes         |Yes         |Yes         |いいえ         |
|Teams 通信サポート スペシャリスト     |Yes         |いいえ         |Yes         |いいえ         |
|Skype for Business管理者     |Yes         |Yes         |Yes         |Yes         |
|グローバル リーダー |Yes         |Yes         |Yes         |いいえ         |
|レポート リーダー <sup>1</sup>     |Yes         |いいえ         |Yes         |いいえ         |

<sup>1</sup> CQD レポートの読み取りに加えて、レポート リーダーは管理センター内のすべての[アクティビティ レポート](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)と[、Microsoft 365導入コンテンツ パック](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)からのすべてのレポートを表示できます。

> [!NOTE]
> [EUII (エンド ユーザー識別可能な情報)](CQD-data-and-reports.md#euii-data) が表示されず、この情報の表示が許可されているロールの 1 つがある場合は、CQD が EUII を 28 日間だけ保持することに注意してください。 28 日を超えたものは削除されます。

これらのロールの詳細については、「管理者ロール[Office 365について](/office365/admin/add-users/about-admin-roles)」を参照してください。


初めてサインインすると、CQD によってデータの収集と処理が開始されます。

## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI を使用して CQD データを分析する

2020 年 1 月の新機能: [CQD 用の Power BI クエリ テンプレートのダウンロード](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 CQD データの分析やレポートに使えるカスタマイズ可能な Power BI テンプレートです。

「[Power BI を使って CQD データを分析する](CQD-Power-BI-query-templates.md)」をご覧ください。

## <a name="related-topics"></a>関連項目

[Teams の通話品質の向上と監視](monitor-call-quality-qos.md)

[CQD とは](CQD-what-is-call-quality-dashboard.md)

[テナントと建物のデータをアップロードする](CQD-upload-tenant-building-data.md)

[CQD のデータとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD のストリーム分類](stream-classification-in-call-quality-dashboard.md)

[Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)
