---
title: Microsoft Teams のデバイス使用状況レポート
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/24/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: マイクロソフトのチームの管理センターでチームを組織内のユーザーの接続を確認するチームのデバイスの使用状況レポートを使用する方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: df5b912a9a4d76fd1be2947cea6dd2750ddbaa49
ms.sourcegitcommit: f29c0c41dc40f7e968a675d2cf10ef17d7e784da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/30/2019
ms.locfileid: "33495902"
---
# <a name="microsoft-teams-device-usage-report"></a>Microsoft Teams のデバイス使用状況レポート

マイクロソフト チームの管理センターでチーム デバイスの使用状況レポートは、ユーザーをチームに接続する方法に関する情報を提供します。 レポートを使用するに移動するときに自分のモバイル デバイスからのチームを使用して数を含む、組織全体で使用されているデバイスを参照してください。  

![マイクロソフトのチームの管理センターでチームのデバイスの使用状況レポートのスクリーン ショット](../media/teams-reports-device-usage.png "マイクロソフトのチームの管理センターでチームのデバイスの使用状況レポートのスクリーン ショット")

## <a name="view-the-report"></a>レポートを表示する

1. マイクロソフトのチーム管理センターの左側のナビゲーションでには、 **& レポートの分析**] をクリックし、[**レポート**] で [**デバイスの使用状況をチーム**を参照してください。 
2. [**日付の範囲**] の下で、範囲を選択して、[**レポートの実行**] をクリックします。 

## <a name="interpret-the-report"></a>レポートを解釈する

![マイクロソフトのチームの管理センターでチームのデバイスの使用状況レポートのスクリーン ショット](../media/teams-reports-device-usage-with-callouts.png "コールアウトの番号とマイクロソフトのチーム管理センターでチームのデバイスの使用状況レポートのスクリーン ショット")

|コールアウト |説明  |
|--------|-------------|
|**1**   |最後の 7 日間または 28 日間での傾向のチームのデバイスの使用状況レポートを表示できます。  |
|**2**   |各レポートには、レポートが生成されたときの日付があります。 通常、レポートはアクティビティの時刻から 24 ～ 48 時間の遅延を反映します。 |
|**3**   |<ul><li>グラフの X 軸は、チームへの接続に使用されるさまざまなデバイス (**Windows**、 **Mac**、 **iOS**、 **Android の電話**) を表します。 </li><li>Y 軸は、選択した期間にわたってデバイスを使用してユーザーの数です。</li> </ul>バーにポインターを置くチームに接続するデバイスを使用しているユーザーの数を表示するデバイスを表します。|
|**4**   |表では、ユーザーがデバイスの使用状況の内訳を示します。 <ul><li>**表示名**は、ユーザーの表示名です。 マイクロソフトのチームの管理センターでユーザーの設定] ページに移動するのには表示名をクリックすることができます。 </li><li>**Windows**は、ユーザーがチームのデスクトップ クライアントを Windows ベースのコンピューター上でアクティブな場合に選択されます。</li><li>**Mac**は、ユーザーが macOS コンピューター上のチームのデスクトップ クライアントでアクティブな場合に選択されます。 </li> <li>ユーザーは、iOS のチームのモバイル クライアント上でアクティブだった場合は、 **iOS**が選択されます。</li><li>**Android の電話**は、ユーザーが Android のチームのモバイル クライアント上でアクティブな場合に選択されます。 <li>**最後のアクティビティ**は、ユーザーがチームの活動に参加した最後の日付 (UTC) です。</li> </ul> 表に希望する情報を表示するには、表に列を追加する必要があります。 |
|**5**   |[**列の編集**] を選択して表で列を追加または削除します。 |
|**6**   |オフラインで分析できる CSV ファイルにレポートをエクスポートすることができます。 [ **Excel にエクスポート**する] をクリックし、[**ダウンロード**] タブの [**ダウンロード**の準備ができたときに、レポートをダウンロードする] をクリックします。<br>![ダウンロードするレポートをエクスポートするかを示す [ダウンロード] タブのスクリーン ショット](../media/teams-reports-export-to-csv.png)|

## <a name="related-topics"></a>関連トピック
- [Teams の分析とレポート](teams-reporting-reference.md)
- [Teams の使用状況レポート](teams-usage-report.md)
- [Teams ユーザー アクティビティ レポート](user-activity-report.md)