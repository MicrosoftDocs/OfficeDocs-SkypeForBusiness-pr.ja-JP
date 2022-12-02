---
title: 通話品質ダッシュボード (CQD) のセットアップ
author: CarolynRowe
ms.author: crowe
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
description: 通話品質ダッシュボードを有効にして使用し、通話の品質の概要レポートを取得する方法について説明します。
ms.openlocfilehash: 5f3b9fbb42199892136569ac179907b18da4e460
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245651"
---
# <a name="set-up-the-call-quality-dashboard"></a>通話品質ダッシュボードを設定する

Microsoft通話品質ダッシュボード (CQD) を[https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)開きます (管理者の資格情報を使用してサインインします)。 または、Teams 管理センターに移動し、[ **分析&レポート** > **通話品質ダッシュボード**] を選択します。

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Teams 管理センターの [通話品質ダッシュボード] ボタンのスクリーンショット。":::

開いたページ **で、[サインイン**] をクリックし、グローバル管理者アカウントを入力するか、Teams 管理者アカウント情報をMicrosoftします。 初めてサインインすると、CQD はデータの収集と処理を開始します。 レポートに意味のある結果を表示するのに十分なデータを処理するには、1 時間以上かかる場合があることに注意してください。

CQD には、Microsoft Teams、Skype for Business Online、Skype for Business Server 2019 の通話と会議の品質が組織全体で表示されます。 

> [!IMPORTANT]
> Skype for Business Server 2019 で CQD を使用するには、[呼び出しデータ コネクタを構成](/skypeforbusiness/hybrid/configure-call-data-connector)する必要があります。 開始する前に、「 [通話データ コネクタを計画](/skypeforbusiness/hybrid/plan-call-data-connector) する」を参照してください。


## <a name="assign-admin-roles-for-access-to-cqd"></a>CQD へのアクセスに管理者ロールを割り当てる

CQD にアクセスするための [ロール](/microsoft-365/admin/add-users/about-admin-roles) を、使用する必要があるユーザーに割り当てます。

管理者以外のユーザー (サポート エンジニアやヘルプデスク エージェントなど) に通話品質ダッシュボードを使用させる場合は、CQD へのアクセスを許可する次のいずれかのロールをそれらのユーザーに割り当てることができます。 


|&nbsp;  |レポートを表示する  |EUII フィールドを表示する  |レポートを作成する  |建物データのアップロード  |
|---------|:-------:|:-------:|:-------:|:-------:|
|グローバル管理者     |Yes         |Yes         |Yes         |Yes         |
|Teams 管理者     |Yes         |Yes         |Yes         |Yes         |
|Teams 通信管理者     |Yes         |Yes         |Yes         |Yes         |
|Teams 通信サポート エンジニア     |Yes         |Yes         |Yes         |いいえ         |
|Teams 通信サポート スペシャリスト     |Yes         |いいえ         |Yes         |いいえ         |
|Skype for Business管理者     |Yes         |Yes         |Yes         |Yes         |
|グローバル リーダー |Yes         |Yes         |Yes         |いいえ         |
|レポート 閲覧者<sup>1</sup>     |Yes         |いいえ         |Yes         |いいえ         |

<sup>1</sup> CQD レポートの読み取りに加えて、レポート閲覧者は管理センターのすべての[アクティビティ レポート](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263)と[、Microsoft 365 導入コンテンツ パック](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)からのレポートを表示できます。

> [!NOTE]
> [EUII (エンド ユーザーを特定できる情報)](CQD-data-and-reports.md#euii-data) が表示されず、この情報の表示が許可されているロールの 1 つがある場合は、CQD が EUII を 28 日間のみ保持していることに注意してください。 28 日より前のものは削除されます。

これらのロールの詳細については、「[Office 365管理者ロールについて](/office365/admin/add-users/about-admin-roles)」を参照してください。


初めてサインインすると、CQD はデータの収集と処理を開始します。

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
