---
title: 正常性レポートと使用状況レポート
author: altsou
ms.author: altsou
manager: serdars
ms.date: 04/07/2022
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: レポートの正常性と使用状況に関するレポート ノード データ
f1keywords: ''
ms.openlocfilehash: 9b1f3e1960cbe0089f498045922125b121679646
ms.sourcegitcommit: 64c01699022b47fdfec8dc6e2ca279e57eae3baa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2022
ms.locfileid: "68243798"
---
# <a name="health-and-usage-reports"></a>正常性レポートと使用状況レポート

レポート ノードには、Pro Management ポータルのMicrosoft Teams Roomsの正常性と使用状況に関するデータが含まれています。 **[概要]** では、ルームのテナント全体の正常性の傾向が表示されます。 [ **正常性** ] タブには、対応する正常性データを含む会議室の一覧が表示されます。 予定表情報と通話品質データに基づく会議室の使用状況は、[ **使用状況** ] タブに表示されます。

## <a name="navigating-reports"></a>レポートの移動

<!--![A screenshot of active tickets bar graph](../media/health-and-usage-002new.png)-->

概要セクションでは、会議室管理の重要な側面をグラフィカルに表現します。 グラフは、選択した期間または選択したグループによって変わります。 期間を変更するには、ドロップダウン メニューをクリックします。

<!--!![A screenshot of a menu to choose a day](../media/health-and-usage-004.png)-->

グループを変更するには、バナーのグループ選択ドロップダウン メニューをクリックします。

<!--!![A screenshot of the banner menu auto-generated](../media/health-and-usage-005.png)-->
### <a name="tickets-by-category"></a>カテゴリ別のチケット

ドーナツには、選択した期間とグループに対して発生したチケットの合計が表示されます (既定値は 7 日間、すべてのグループ)。 チケットは、オーディオ、ディスプレイ、周辺機器、接続、バージョン管理、記録済みの問題という主要なカテゴリで表されます。

<!--!![A screenshot of pie chart tickets by category](../media/health-and-usage-006.png)-->

選択すると、そのカテゴリのチケットの詳細ビューのポップアップが表示されます。

<!--!![A screenshot of tickets and versioning side by side](../media/health-and-usage-007.png)-->

ポップアップでは、ドーナツのそれぞれの部分を選択することで、サブカテゴリでチケットの一覧をフィルター処理できます。 

<!--!![A screenshot tickets by subcategory automatically generated](../media/health-and-usage-008.png)-->

戻るには、ドーナツをクリックするか、左上の階層リンクをクリックします。

このリスト ビューで特定のチケットに移動するには、[ **サポート チケット] 列** の下にあるリンクをクリックします。

<!--### Ticket history

The ticket history graph shows a comparison of incidents assigned to you or Microsoft over the specified time period.

> [!NOTE]
> If a ticket changes owner in a day, whoever owns the assignment for the majority of that day will have the ticket counted towards them. For example, if you assign the ticket to Microsoft early in the day, the ticket counts towards **Assigned to Microsoft** for the day.

<!--![A screen shot of Tickets history by different periods](../media/health-and-usage-009.png)-->

### <a name="health-history"></a>正常性履歴

このグラフは、テナント内のすべての部屋の平均正常性 (正常性セクションの定義) と、すべての MRT Pro 顧客の平均正常性を日常的に示しています。 平均正常性は最大 90 日間表示できます。

<!--!![A screenshot of rooms health and average health](../media/health-and-usage-010.png)-->

### <a name="most-reliableleast-reliable-rooms"></a>最も信頼性の高い/最も信頼性の低い部屋

2 つのテーブルには、正常性に基づいて最も信頼性が高く、信頼性の低い部屋が表示されます。 完全なリスト ビューで [正常性] を選択し、[正常性] 列で一覧を並べ替えます。

### <a name="rooms-history"></a>ルームの履歴

サービスに登録されている部屋の履歴ビューを提供し、同じ期間に正常または監視されていない部屋の比較ビューを提供します。

## <a name="health"></a>動作状態

すべての会議室の正常性レポートに移動するには、[レポート] を選択し、[  **正常性**] を選択します。

<!--!![A screenshot of a Reports health percentage](../media/health-and-usage-001.png)-->

正常性スコアは、エンド ユーザーの不満を引き起こす可能性が最も高い部屋を表示するように設計されたメトリックです。 特定の日は、部屋が正常であるか異常である可能性があります。 チケットまたは多くのチケットがメンテナンス以外の時間 (午前 5 時から午後 9 時のマシンローカル時間) に合計 20 分を超えて部屋に影響を与えた場合、異常と見なされます。 たとえば、チケットが午前 5 時 00 分に開かれているが、午前 5 時 15 分に終了した場合、部屋は正常と見なされます。 ただし、午前 9 時 00 分から午前 9 時 10 分に 2 番目のチケットが発生した場合、部屋はその日の異常と見なされます。 同様に、チケットが午前 5 時 00 分から午前 5 時 21 分に発生した場合、その日は異常と見なされます。

> [!NOTE]
> 1 日の正常性は、1 日 12:00 AM UTC 時刻に集計されます。 国際日付行に近い顧客の場合、稼働日の真ん中近くに正常性集計が発生する可能性があります。

> [!NOTE]
> オンボーディング中の会議室は、[正常性] タブの会議室の一覧には表示されず、テナントの平均正常性にはカウントされません。

このビューに表示されている部屋をクリックすると、詳細が表示されます。

棒グラフには、毎日のチケットの数が表示されます。 その日に開かれたチケットは青色で表示されます。 それぞれの日より前に開かれたチケットはオレンジ色で表示されます。 グラフで 1 日をクリックすると、円グラフとテーブルが関連するチケットにフィルター処理されます。 フィルターを反転するには、階層リンクを使用して移動するか、グラフをクリックします。

チケットの分類はドーナツ グラフで表されます。 これを操作すると、タイムライン グラフとテーブルがフィルター処理されます。 フィルターを反転するには、階層リンクを使用して移動するか、グラフをクリックします。

<!--!![A screenshot of a Reports health bar graph](../media/health-and-usage-014.png)-->

会議の影響ビューには、重大度が "重要" または "重大" のチケットが開かれたスケジュールされた会議が表示されます。 このビューの目的は、参加者が問題が発生する可能性がある会議の近似値を提供することです。

会議の影響ビューには、重大度が "重要" または "重大" のチケットが開かれたスケジュールされた会議が表示されます。 このビューの目的は、参加者が問題が発生する可能性がある会議の近似値を提供することです。

<!--![A screenshot of a Reports meeting impact](../media/health-and-usage-015.png)-->

[設定] タブには、ハードウェア情報、デバイス設定、BIOS 情報、アプリの設定、場所などのルームのメタデータが表示されます。

## <a name="usage"></a>使用方法

すべてのルームの利用状況レポートを表示するには、[ **レポート] >[使用状況**] を選択します。

<!--!![A screenshot of all rooms' usage by health](../media/health-and-usage-011.png)-->

見出しには、次のような分析情報が表示されます。

- テナント内の合計ルーム数
- オフラインまたはオンラインの予約済みの会議がないユーザーの数
- テナント全体の会議室の使用率の割合
- 交換を通じて予約された会議の合計数
- Skype または Teams のリンクを含む予約済み会議の割合
- ルーム参加による通話の合計数
- "良い" 品質で分類されたすべての呼び出しからすべての呼び出しに対する呼び出しのパフォーマンス スコアを集計します。 

見出しメトリックの下には、対応するメトリックを含む会議室のテーブルがあります。 部屋を選択すると、その他の使用状況の詳細が表示されます。 次の表では、表のメトリックについて説明します。

|列|説明|
|---|---|
|利用|選択した期間の営業時間中に会議室が予約された時間の割合。 元。 期間は 7 日間に設定されます。 部屋が 32/40 時間予約されたことを意味する 80% 使用率|
|オンラインで予約済み|予約された会議のうち、Teams で有効にされた割合。 元。 10 件の会議が予約されました。 そのうち、8 には Teams のリンクがありました。 オンライン予約 = 80%|
|予約された会議|会議室でスケジュールされた会議の絶対数|
|呼び出しの合計数|ルームを参加者として使用する呼び出しの絶対数。|
呼び出しのパフォーマンス|"Good" 評価の呼び出しの割合。 各呼び出しが評価され、Good、Poor、Unknown の評価を受け取ります。 このメトリックは、良好な呼び出し/合計呼び出しから計算されます|

使用量は、会議室デバイスの現地時間の午前 0 時 (00:00) に毎日の終わりに計算されます。 使用率は、その日に予約された会議の合計時間を 8 時間で割った値に基づいて計算されます。

## <a name="usage-details-of-a-room"></a>ルームの使用状況の詳細

リスト ビューで会議室をクリックすると、より詳細な情報を含むポップアップが表示されます。 ポップアップの [使用率] タブの下には、過去 5 営業日の使用時間を示すグラフが表示されます。 毎日、2 つのバーがあります。青は、予約された会議時間を表します。紫色は、Teams/Skype 対応会議のスケジュールされた時刻を表します。 下部には、過去 5 営業日の平均会議の予約と期間が計算されます。

<!--![A screenshot of utilization by hours per day](../media/health-and-usage-012.png)-->

**[通話]** テーブルには、会議室が Teams 通話に参加した会議が表示されます。 ルームのオーディオ品質は、すべての参加者ではなく、ルームのみに対して評価されます。 特定の通話のすべての参加者の通話品質を表示するには、[開始時刻] をクリックして通話を選択します。

<!--!![A screenshot of room audio quality](../media/health-and-usage-016.png)-->

ルームのストリームの詳細を表示するには、セッションの開始時刻をクリックします。
