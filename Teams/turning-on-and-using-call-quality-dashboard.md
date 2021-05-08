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
description: 通話品質ダッシュボードを有効にし、使用する方法と、通話品質の概要レポートを取得する方法について学習します。
ms.openlocfilehash: c71cb25732a99f207467a988ad0db54c959d15f4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52254465"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) を設定する

で Microsoft 通話品質ダッシュボード (CQD) を開 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) きます (管理者の資格情報でサインインします)。 または、管理センターの [Teamsに移動し、[通話品質ダッシュボード **] を選択します**。 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="管理センターの [通話品質] ダッシュボード ボタンTeamsスクリーンショット":::

表示されたページで、[サインイン]**をクリック** し、グローバル管理者アカウントまたは管理者アカウントMicrosoft Teams入力します。 初めてサインインすると、CQD はデータの収集と処理を開始します。 レポートに意味のある結果を表示するのに十分なデータを処理するのに 1 時間以上かかる場合があります。

CQD では、Microsoft Teams、Skype for Business Online、および 2019 年の組織全体の通話と会議の品質がSkype for Business Serverされます。 

> [!IMPORTANT]
> Skype for Business Server 2019 で CQD を使用するには、通話データ コネクタ を[構成する必要があります](/skypeforbusiness/hybrid/configure-call-data-connector)。 開始する [前に、「通話データ コネクタを計画](/skypeforbusiness/hybrid/plan-call-data-connector) する」を参照してください。


## <a name="assign-admin-roles-for-access-to-cqd"></a>CQD にアクセスするために管理者ロールを割り当てる

[CQD](/microsoft-365/admin/add-users/about-admin-roles)にアクセスするロールを、それを使用する必要があるユーザーに割り当てます。

管理者以外のユーザー (サポート エンジニアやヘルプデスク エージェントなど) に通話品質ダッシュボードを使用する場合は、これらのユーザーに次のいずれかのロールを割り当てることができます。これにより、CQD にアクセスできます。 


|  |レポートを表示する  |EUII フィールドを表示する  |レポートを作成する  |アップロードの作成  |
|---------|:-------:|:-------:|:-------:|:-------:|
|グローバル管理者     |はい         |はい         |はい         |はい         |
|Teams 管理者     |はい         |はい         |はい         |はい         |
|Teams 通信管理者     |はい         |はい         |はい         |はい         |
|Teams 通信サポート エンジニア     |はい         |はい         |はい         |いいえ         |
|Teams 通信サポート スペシャリスト     |はい         |いいえ         |はい         |いいえ         |
|Skype for Business管理者     |はい         |はい         |はい         |はい         |
|グローバル リーダー |はい         |はい         |はい         |いいえ         |
|レポート閲覧<sup>者 1</sup>     |はい         |いいえ         |はい         |いいえ         |

<sup>1</sup>レポート 閲覧者は、CQD レポートを読み取[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)るだけでなく、管理センター内のすべてのアクティビティ レポートと、Microsoft 365 導入コンテンツ パック[からのすべてのレポートを表示できます](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)。

> [!NOTE]
> [EUII (](CQD-data-and-reports.md#euii-data)エンドユーザーを特定できる情報) が表示されない場合、この情報の表示が許可されているロールの 1 つがある場合、CQD は EUII を 28 日間のみ保持します。 28 日より前のデータは削除されます。

これらのロールの詳細については、「管理者ロールについて[」Office 365参照してください](/office365/admin/add-users/about-admin-roles)。


初めてサインインすると、CQD はデータの収集と処理を開始します。 2019 年 12 月の現在でも、古いバージョンの CQD (cqd.lync.com) にアクセスできます。ただし、レガシ ポータルには最新の CQD (cqd.teams.microsoft.com) へのリンクが表示されます。 最終的に、以前のバージョンの CQD は使用停止されます。 2020 年 7 月 1 日の現在、古いバージョンの CQD は最新の CQD からデータにアクセスします。


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>以前のバージョンの CQD から建物のデータとレポートを移行する

> [!IMPORTANT]
> 2020 年 7 月 1 日の現在、以前の CQD () から建物のデータとレポートを移行できなくなりました https://CQD.lync.com) 。 



## <a name="use-power-bi-to-analyze-cqd-data"></a>CQD Power BI分析するには、次のコマンドを使用します。

2020 年 1 月の新機能: [CQD Power BIテンプレートをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 カスタマイズ可能Power BI、CQD データの分析とレポートに使用できるテンプレートです。

詳細[については、「Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)」を参照してください。


## <a name="related-topics"></a>関連トピック

[Teams の通話品質の向上と監視](monitor-call-quality-qos.md)

[CQD とは](CQD-what-is-call-quality-dashboard.md)

[アップロードとデータの構築](CQD-upload-tenant-building-data.md)

[CQD データとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で使用可能なディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD のストリーム分類](stream-classification-in-call-quality-dashboard.md)

[CQD Power BI分析するには、次のコマンドを使用します。](CQD-Power-BI-query-templates.md)