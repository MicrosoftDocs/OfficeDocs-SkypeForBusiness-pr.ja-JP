---
title: 通話品質ダッシュボード (CQD) のセットアップ
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
description: 通話品質ダッシュボードを有効にし、使用する方法と、通話の品質に関する概要レポートを取得する方法について学習します。
ms.openlocfilehash: cf4c6d56e4fa646495383b4998e80789d9cdaca67b9cc35d07f613cda4e70b85
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300453"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>通話品質ダッシュボードを設定する方法

[Microsoft 通話品質ダッシュボード] (CQD) を開 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) きます (管理者資格情報でサインインします)。 または、管理センターの Teamsに移動し、[品質ダッシュボードの呼び **出し] を選択します**。 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="管理センターの [通話品質ダッシュボード] Teamsスクリーンショット":::

開くページで、[サインイン]**をクリック** し、グローバル管理者アカウントまたは管理者アカウントMicrosoft Teams入力します。 初めてサインインすると、CQD はデータの収集と処理を開始します。 レポートに意味のある結果を表示するのに十分なデータを処理するのに 1 時間以上かかる場合があります。

CQD は、2019 年の Microsoft Teams、Skype for Business Online、および Skype for Business Serverの通話と会議の品質を組織全体で表示します。 

> [!IMPORTANT]
> CQD を 2019 Skype for Business Server使用するには、通話データ コネクタを[構成する必要があります](/skypeforbusiness/hybrid/configure-call-data-connector)。 開始する [前に、「通話データ コネクタを計画](/skypeforbusiness/hybrid/plan-call-data-connector) する」を参照してください。


## <a name="assign-admin-roles-for-access-to-cqd"></a>CQD へのアクセスに管理者の役割を割り当てる

[CQD](/microsoft-365/admin/add-users/about-admin-roles)にアクセスする役割を、それを使用する必要があるユーザーに割り当てます。

管理者以外のユーザー (サポート エンジニアやヘルプデスク エージェントなど) に通話品質ダッシュボードを使用する場合は、それらのユーザーに次のいずれかの役割を割り当て、CQD にアクセスできます。 


|&nbsp;  |レポートの表示  |EUII フィールドの表示  |レポートの作成  |アップロードデータの作成  |
|---------|:-------:|:-------:|:-------:|:-------:|
|グローバル管理者     |はい         |はい         |はい         |必要         |
|Teams管理者     |はい         |はい         |はい         |必要         |
|Teams 通信管理者     |はい         |はい         |はい         |必要         |
|Teams 通信サポート エンジニア     |はい         |はい         |必要         |いいえ         |
|Teams 通信サポート スペシャリスト     |必要         |いいえ         |はい         |いいえ         |
|Skype for Business 管理者     |はい         |はい         |はい         |必要         |
|グローバル閲覧者 |はい         |はい         |必要         |いいえ         |
|レポート リーダー<sup>1</sup>     |必要         |いいえ         |はい         |いいえ         |

<sup>1</sup>レポート リーダーは、CQD レポートの読み取り[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)に加えて、管理センター内のすべてのアクティビティ レポートと、Microsoft 365導入コンテンツ パック[のレポートを表示できます](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)。

> [!NOTE]
> [EUII (](CQD-data-and-reports.md#euii-data)エンドユーザー識別可能な情報) が表示されていない場合に、この情報を表示できる役割の 1 つがある場合は、CQD が EUII を 28 日間保持する必要があります。 28 日より前のデータは削除されます。

これらの役割の詳細については、「管理者ロールについて[」Office 365参照してください](/office365/admin/add-users/about-admin-roles)。


初めてサインインすると、CQD はデータの収集と処理を開始します。 2019 年 12 月現在でも、古いバージョンの CQD (cqd.lync.com) にアクセスすることができますが、従来のポータルでは最新の CQD (cqd.teams.microsoft.com) へのリンクが提供されています。 最終的に、古いバージョンの CQD は使用停止されます。 2020 年 7 月 1 日現在、古いバージョンの CQD は最新の CQD からデータにアクセスします。


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>以前のバージョンの CQD から建物データとレポートを移行する

> [!IMPORTANT]
> 2020 年 7 月 1 日より、古い CQD ( から建物データとレポートを移行できなくなりました https://CQD.lync.com) 。 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI を使用して CQD データを分析する

2020 年 1 月の新機能: [CQD Power BIクエリ テンプレートをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 カスタマイズ可能Power BI、CQD データの分析とレポートに使用できるテンプレートです。

詳[しくは、「CQD Power BIを分析する方法」](CQD-Power-BI-query-templates.md)を参照してください。


## <a name="related-topics"></a>関連項目

[通話の品質を向上し、監視Teams](monitor-call-quality-qos.md)

[CQD とは?](CQD-what-is-call-quality-dashboard.md)

[テナントとビルのデータをアップロードする](CQD-upload-tenant-building-data.md)

[CQD のデータとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で利用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD のストリーム分類](stream-classification-in-call-quality-dashboard.md)

[Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)
