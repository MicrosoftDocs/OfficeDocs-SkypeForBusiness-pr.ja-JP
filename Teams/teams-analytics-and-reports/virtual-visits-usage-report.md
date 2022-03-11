---
title: Microsoft Teams Virtual Visits 利用状況レポート
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Microsoft Teams 管理センターで Virtual Visits 利用状況レポートを使用して、組織内の Virtual Visits アクティビティの概要を取得する方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b3432ea92ad89c5304d81b266fce61fb9b95d5b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435851"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams Virtual Visits 利用状況レポート

Microsoft Teams 管理センターの [仮想アクセスの使用状況] レポートには、組織内の仮想Teamsアクティビティの概要が表示されます。 [Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md) アプリと電子正常性レコード (EHR) コネクタを使用してスケジュールされた[仮想Microsoft Teamsアクティビティを表示できます](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-visits-and-electronic-healthcare-record-ehr-integration)。

レポートを表示するには、グローバル管理者または管理者であるTeamsがあります。

レポートには、次のタブが含まれています。 レポートに表示される情報は、Bookings アプリのライセンス、EHR コネクタ、または両方のライセンスTeamsによって異なります。

|Tab |説明  |
|---------|---------|
|**[Virtual Visits](#virtual-visits)**     |仮想アクセスの総数が表示され、Bookings アプリを使用してスケジュールされた訪問数と、EHR システムから実施された Teams EHR 統合会議の内訳が表示されます。         |
|**[[時間]](#duration)**     |参加者の平均訪問時間とロビーの平均待機時間を示します。         |
|**[Bookings](#bookings)**     |Bookings アプリを通じてスケジュールされたアクセス数を示します。         |
|**[EHR](#ehr)**     |EHR システムからTeamsされた EHR 統合訪問の数を示します。         |  

このレポートを使用して、組織の Virtual Visits アクティビティと傾向に関する分析情報を取得します。 この情報は、より良いビジネス成果を実現するために仮想訪問を最適化するのに役立ちます。

## <a name="view-the-virtual-visits-usage-report"></a>Virtual Visits 使用状況レポートを表示する

1. 管理センターの左側のナビゲーションで、[Microsoft Teamsレポートの管理] &**を** > **選択します**。 [レポートの **表示] タブの** [レポート **] で、[****仮想アクセスの使用状況] を選択します**。
2. [ **日付範囲]** で、7 日、30 日、または 90 日の日付範囲を選択します。 次に、[レポートの **実行] を選択します**。

> [!NOTE]
> 既定では、Virtual Visits 分析はオンであり、レポートを使用できます。 このレポートを使用すると、組織内の Virtual Visits に関するデータを収集するアクセス許可を Microsoft に付与します。 データ保持ポリシーの詳細については、「データの保持、削除、および削除」を参照[Microsoft 365。](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview)
>
>組織のレポートをオフにする場合は、ページの右上隅の [**設定] で** オフにできます。 この設定は、変更後に有効になるのに 0 ~2 時間かかる場合があります。

## <a name="interpret-the-report"></a>レポートを解釈する

### <a name="virtual-visits"></a>Virtual Visits

ここに表示されるグラフは、Bookings アプリのライセンス、EHR コネクタ、または両方のライセンスTeamsによって異なっています。 詳細については、「 [Bookings](../bookings-app-admin.md) アプリの管理」と「 [Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) への統合」または「 [Integration into Epic EHR(EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md) への統合)」を参照してください。

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="番号付きコールアウトを示す Virtual Visits 利用状況レポートの [Virtual Visits] タブのスクリーンショット。" lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|Callout |説明  |
|--------|-------------|
|**1**   |各レポートには、レポートが生成された日付があります。 通常、レポートには、アクティビティの時刻から 24 ~ 48 時間の待機時間が反映されます。 |
|**2**   |X 軸は、レポートで選択した日付範囲です。 Y 軸は訪問数です。<br>特定の日付のドットにマウス ポインターを合わせると、その日付の訪問数が表示されます。|
|**3**   |凡例内の項目を選択すると、グラフに表示される項目をフィルター処理できます。 たとえば、[Total **Bookings Virtual Visits]** または **[Total EHR Virtual Visits** ]を選択すると、それぞれに関連する情報だけが表示されます。 この選択を変更しても、表内の情報は変わりません。 |
|**4**   |表には、選択した日付範囲で行った各訪問に関する詳細情報が表示されます。 <ul><li>**開始時刻 (UTC)** は、スタッフ メンバーと参加者の両方が会議に参加している日付と時刻、または会議で最初のアクティビティが発生した日時です。  </li> <li>**[会議 ID** ] は、会議の一意の ID です。</li> <li>**ロビーの待機時間** とは、参加者がロビーに最初に参加して、その同じ参加者または別の参加者がスタッフ メンバーによって会議に参加を認めるまでの間の時間です。</li><li>**[** 期間] は、開始時刻と最後のユーザーが会議から離れる時間の差です。 スタッフ メンバーと参加者の両方が会議に参加しなかった場合、期間は 0 (ゼロ) と表示されます。</li> <li>**[状態** ] には会議の状態が表示されます。 <ul><li>**完了:** 1 人または複数のスタッフ メンバーと参加者が会議に参加し、会議が終了した場合。 または、1 人または複数の参加者が会議に参加し、会議が終了した場合。</li> <li> **表示なし**: 1 人のスタッフ メンバーが会議に参加するが、他のユーザーが参加し、会議が終了した場合。 </li></ul> </li> <li>**[会議の** 種類] は、仮想予定が Bookings アプリまたは EHR コネクタを介してスケジュールTeamsを示します。</li> <li>**[出席者** ] は、会議のスタッフ メンバーと参加者の総数です。</li> <li>**SMS 送信は** 、SMS 通知が出席者に送信されたかどうかを示します。 </li> </li> </ul> |
|**5**   |[**仮想設定** を選択して、[**Virtual Visits Analytics] ウィンドウを開** きます。 ここから、組織の Virtual Visits レポートをオフまたはオンにしたり、テーブルの列を追加または削除することができます。 表に希望する情報を表示するには、表に列を追加する必要があります。|
|**6**   |レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。 [**エクスポート] Excel** 選択し、[ダウンロード] タブで [ダウンロード] を選択して、レポートの準備ができたらレポートをダウンロードします。|

### <a name="duration"></a>[時間]

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="番号付き吹き出しを示す Virtual Visits 利用状況レポートの [期間] タブのスクリーンショット。" lightbox="../media/virtual-visits-usage-report-duration.png":::

|Callout |説明  |
|--------|-------------|
|**1**   |各レポートには、レポートが生成された日付があります。 通常、レポートには、アクティビティの時刻から 24 ~ 48 時間の待機時間が反映されます。 |
|**2**   |X 軸は、レポートで選択した日付範囲です。 Y 軸は分数です。<br>特定の日付のドットにマウス ポインターを合わせると、特定の日付の平均訪問時間または平均ロビー待機時間が表示されます。  |
|**3**   |凡例内の項目を選択すると、グラフに表示される項目をフィルター処理できます。 たとえば、[平均仮想アクセス **時間] または** [ **ロビー** の平均待機時間] を選択して、それぞれに関連する情報のみを表示します。 この選択を変更しても、表内の情報は変わりません。 |
|**4**   |表には、選択した日付範囲で行った各訪問に関する詳細情報が表示されます。 <ul><li>**開始時刻 (UTC)** は、スタッフ メンバーと参加者の両方が会議に参加している日付と時刻、または会議で最初のアクティビティが発生した日時です。  </li> <li>**[会議 ID** ] は、会議の一意の ID です。</li> <li>**ロビーの待機時間** とは、参加者がロビーに最初に参加して、その同じ参加者または別の参加者がスタッフ メンバーによって会議に参加を認めるまでの間の時間です。</li><li>**[** 期間] は、開始時刻と最後のユーザーが会議から離れる時間の差です。 スタッフ メンバーと参加者の両方が会議に参加しなかった場合、期間は 0 (ゼロ) と表示されます。</li> <li>**[状態** ] には会議の状態が表示されます。 <ul><li>**完了:** 1 人または複数のスタッフ メンバーと参加者が会議に参加し、会議が終了した場合。 または、1 人または複数の参加者が会議に参加し、会議が終了した場合。</li> <li> **表示なし**: 1 人のスタッフ メンバーが会議に参加するが、他のユーザーが参加し、会議が終了した場合。 </li></ul> </li> <li>**[会議の** 種類] は、仮想予定が Bookings アプリまたは EHR コネクタを介してスケジュールTeamsを示します。</li> <li>**[出席者** ] は、会議のスタッフ メンバーと参加者の総数です。</li> <li>**SMS 送信は** 、SMS 通知が出席者に送信されたかどうかを示します。 </li> </li> </ul>|
|**5**   |[**仮想設定** を選択して、[**Virtual Visits Analytics] ウィンドウを開** きます。 ここから、組織の Virtual Visits レポートをオフまたはオンにしたり、テーブルの列を追加または削除することができます。 表に希望する情報を表示するには、表に列を追加する必要があります。|
|**6**   |レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。 [**エクスポート] Excel** 選択し、[ダウンロード] タブで [ダウンロード] を選択して、レポートの準備ができたらレポートをダウンロードします。|
### <a name="bookings"></a>Bookings

Bookings アプリを含むライセンスがある場合は、このタブが表示されます。 詳細については、「 [Bookings アプリの管理」を参照してください](../bookings-app-admin.md)。

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="番号付きコールアウトを示す Virtual Visits 利用状況レポートの [Bookings] タブのスクリーンショット。" lightbox="../media/virtual-visits-usage-report-bookings.png":::

|Callout |説明  |
|--------|-------------|
|**1**   |各レポートには、レポートが生成された日付があります。 通常、レポートには、アクティビティの時刻から 24 ~ 48 時間の待機時間が反映されます。 |
|**2**   |X 軸は、レポートで選択した日付範囲です。 Y 軸は、Bookings の訪問数です。<br>特定の日付のドットにマウス ポインターを合わせると、その日付に発生した Bookings のアクセス数が表示されます。|
|**3**   |表には、選択した日付範囲で行った各訪問に関する詳細情報が表示されます。 <ul><li>**開始時刻 (UTC)** は、スタッフ メンバーと参加者の両方が会議に参加している日付と時刻、または会議で最初のアクティビティが発生した日時です。  </li> <li>**[会議 ID** ] は、会議の一意の ID です。</li> <li>**ロビーの待機時間** とは、参加者がロビーに最初に参加して、その同じ参加者または別の参加者がスタッフ メンバーによって会議に参加を認めるまでの間の時間です。</li><li>**[** 期間] は、開始時刻と最後のユーザーが会議から離れる時間の差です。 スタッフ メンバーと参加者の両方が会議に参加しなかった場合、期間は 0 (ゼロ) と表示されます。</li> <li>**[状態** ] には会議の状態が表示されます。 <ul><li>**完了:** 1 人または複数のスタッフ メンバーと参加者が会議に参加し、会議が終了した場合。 または、1 人または複数の参加者が会議に参加し、会議が終了した場合。</li> <li> **表示なし**: 1 人のスタッフ メンバーが会議に参加するが、他のユーザーが参加し、会議が終了した場合。 </li></ul> </li> <li>**[会議の** 種類] は、仮想予定が Bookings アプリまたは EHR コネクタを介してスケジュールTeamsを示します。</li> <li>**[出席者** ] は、会議のスタッフ メンバーと参加者の総数です。</li> <li>**SMS 送信は** 、SMS 通知が出席者に送信されたかどうかを示します。 </li> </li> </ul>|
|**4**   |[**仮想設定** を選択して、[**Virtual Visits Analytics] ウィンドウを開** きます。 ここから、組織の Virtual Visits レポートをオフまたはオンにしたり、テーブルの列を追加または削除することができます。 表に希望する情報を表示するには、表に列を追加する必要があります。|
|**5**   |レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。 [**エクスポート] Excel** 選択し、[ダウンロード] タブで [ダウンロード] を選択して、レポートの準備ができたらレポートをダウンロードします。|
### <a name="ehr"></a>EHR

EHR コネクタを含むライセンスがある場合は、このTeams表示されます。 詳細については、「 [Cerner EHR への統合」](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) または「 [エピック EHR への統合」を参照してください](../expand-teams-across-your-org/healthcare/ehr-admin.md)。

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="番号付きコールアウトを示す Virtual Visits 利用状況レポートの [EHR] タブのスクリーンショット。" lightbox="../media/virtual-visits-usage-report-ehr.png":::

|Callout |説明  |
|--------|-------------|
|**1**   |各レポートには、レポートが生成された日付があります。 通常、レポートには、アクティビティの時刻から 24 ~ 48 時間の待機時間が反映されます。 |
|**2**   |X 軸は、レポートで選択した日付範囲です。 Y 軸は、EHR 訪問の数です。<br>特定の日付のドットにマウス ポインターを合わせると、その日付の EHR 訪問数が表示されます。|
|**3**   |表には、選択した日付範囲で行った各訪問に関する詳細情報が表示されます。 <ul><li>**開始時刻 (UTC)** は、スタッフ メンバーと参加者の両方が会議に参加している日付と時刻、または会議で最初のアクティビティが発生した日時です。  </li> <li>**[会議 ID** ] は、会議の一意の ID です。</li> <li>**ロビーの待機時間** とは、参加者がロビーに最初に参加して、その同じ参加者または別の参加者がスタッフ メンバーによって会議に参加を認めるまでの間の時間です。</li><li>**[** 期間] は、開始時刻と最後のユーザーが会議から離れる時間の差です。 スタッフ メンバーと参加者の両方が会議に参加しなかった場合、期間は 0 (ゼロ) と表示されます。</li> <li>**[状態** ] には会議の状態が表示されます。 <ul><li>**完了:** 1 人または複数のスタッフ メンバーと参加者が会議に参加し、会議が終了した場合。 または、1 人または複数の参加者が会議に参加し、会議が終了した場合。</li> <li> **表示なし**: 1 人のスタッフ メンバーが会議に参加するが、他のユーザーが参加し、会議が終了した場合。 </li></ul> </li> <li>**[会議の** 種類] は、仮想予定が Bookings アプリまたは EHR コネクタを介してスケジュールTeamsを示します。</li> <li>**[出席者** ] は、会議のスタッフ メンバーと参加者の総数です。</li> <li>**SMS 送信は** 、SMS 通知が出席者に送信されたかどうかを示します。 </li> </li> </ul>|
|**4**   |[**仮想設定** を選択して、[**Virtual Visits Analytics] ウィンドウを開** きます。 ここから、組織の Virtual Visits レポートをオフまたはオンにしたり、テーブルの列を追加または削除することができます。 表に希望する情報を表示するには、表に列を追加する必要があります。|
|**5**   |レポートを CSV ファイルにエクスポートすると、オフラインで分析できます。 [**エクスポート] Excel** 選択し、[ダウンロード] タブで [ダウンロード] を選択して、レポートの準備ができたらレポートをダウンロードします。|

> [!NOTE]
> 組織が、ビジネス上の意思決定者などの管理者以外のユーザーが、このレポートにアクセスして表示するプライベート プレビューに参加する場合は、お問い [合わせください](mailto:tapmwtanalytics@microsoft.com)。

## <a name="related-articles"></a>関連記事

- [Teams の分析とレポート](teams-reporting-reference.md)
- [Bookings アプリTeams仮想アクセス](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [仮想アクセスと Teams - エピック EHR への統合](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [仮想アクセスと Teams - Cerner EHR への統合](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
