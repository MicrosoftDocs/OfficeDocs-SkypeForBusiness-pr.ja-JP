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
description: 通話品質ダッシュボードを有効にし、使用する方法と、通話の品質に関する概要レポートを取得する方法について学習します。
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112838"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>通話品質ダッシュボード (CQD) を設定する

Microsoft 通話品質ダッシュボード (CQD) を開 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) きます (管理者の資格情報でサインインします)。 または、Teams 管理センターに移動し、[通話品質 **ダッシュボード] を選択します**。 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 管理センターの [通話品質ダッシュボード] ボタンのスクリーンショット":::

表示されたページで、[ **サインイン]** をクリックし、グローバル管理者アカウントまたは Microsoft Teams サービス管理者アカウント情報を入力します。 初めてサインインすると、CQD はデータの収集と処理を開始します。 レポートに意味のある結果を表示するのに十分なデータを処理するのに 1 時間以上かかる場合があります。

CQD では、Microsoft Teams、Skype for Business Online、Skype for Business Server 2019 の通話と会議の品質が組織全体レベルで表示されます。 

> [!IMPORTANT]
> Skype for Business Server 2019 で CQD を使用するには、通話データ コネクタを [構成する必要があります](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)。 開始 [する前に、「通話データ コネクタを](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) 計画する」を参照してください。


## <a name="assign-admin-roles-for-access-to-cqd"></a>CQD へのアクセスに管理者ロールを割り当てる

[CQD](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)にアクセスするロールを、CQD を使用する必要があるユーザーに割り当てます。

管理者以外のユーザー (サポート エンジニアやヘルプデスク エージェントなど) に通話品質ダッシュボードを使用する場合は、これらのユーザーに次のいずれかの役割を割り当て、CQD にアクセスできます。 


|  |レポートを表示する  |[EUII] フィールドを表示する  |レポートを作成する  |建物データをアップロードする  |
|---------|:-------:|:-------:|:-------:|:-------:|
|グローバル管理者     |はい         |はい         |はい         |はい         |
|Teams サービス管理者     |はい         |はい         |はい         |はい         |
|Teams 通信管理者     |はい         |はい         |はい         |はい         |
|Teams 通信サポート エンジニア     |はい         |はい         |はい         |いいえ         |
|Teams 通信サポート スペシャリスト     |はい         |いいえ         |はい         |いいえ         |
|Skype for Business 管理者     |はい         |はい         |はい         |はい         |
|グローバル リーダー |はい         |はい         |はい         |いいえ         |
|レポート リーダー<sup>1</sup>     |はい         |いいえ         |はい         |いいえ         |

<sup>1</sup>レポート リーダーは、CQD レポートの閲覧に加えて[](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)、管理センターのすべてのアクティビティ レポートと[、Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)導入コンテンツ パックのレポートを表示できます。

> [!NOTE]
> [EUII (](CQD-data-and-reports.md#euii-data)エンド ユーザーを特定できる情報) が表示されない場合、この情報の表示が許可されているロールの 1 つがある場合は、CQD では 28 日間のみ EUII が保持されます。 28 日より前のデータは削除されます。

これらの役割の詳細については [、「365 管理者ロールの概要Officeを参照してください](/office365/admin/add-users/about-admin-roles)。


初めてサインインすると、CQD はデータの収集と処理を開始します。 2019 年 12 月の現在、古いバージョンの CQD (cqd.lync.com) には引き続きアクセスできます。ただし、従来のポータルでは最新の CQD (cqd.teams.microsoft.com) へのリンクが提供されています。 最終的には、古いバージョンの CQD は使用停止されます。 2020 年 7 月 1 日の現在、古いバージョンの CQD は最新の CQD のデータにアクセスします。


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>以前のバージョンの CQD から建物データとレポートを移行する

> [!IMPORTANT]
> 2020 年 7 月 1 日の現在、以前の CQD https://CQD.lync.com) (. 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Power BI を使用して CQD データを分析する

2020 年 1 月の新機能: [CQD 用の Power BI クエリ テンプレートをダウンロードします](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。 カスタマイズ可能な Power BI テンプレートを使用して、CQD データを分析およびレポートできます。

詳細 [については、「Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md) 」を参照してください。


## <a name="related-topics"></a>関連項目

[Teams の通話品質の向上と監視](monitor-call-quality-qos.md)

[CQD とは](CQD-what-is-call-quality-dashboard.md)

[テナントと建物のデータをアップロードする](CQD-upload-tenant-building-data.md)

[CQD データとレポート](CQD-data-and-reports.md)

[CQD を使用して通話と会議の品質を管理する](quality-of-experience-review-guide.md)

[CQD で使用できるディメンションとメジャー](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD でのストリームの分類](stream-classification-in-call-quality-dashboard.md)

[Power BI を使用して CQD データを分析する](CQD-Power-BI-query-templates.md)
