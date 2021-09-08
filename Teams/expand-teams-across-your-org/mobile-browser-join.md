---
title: モバイル ブラウザーで仮想アクセスTeamsの参加エクスペリエンスを管理する
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: hafarmer
description: モバイル ブラウザーでの仮想アクセスTeamsの参加エクスペリエンスについて説明します。
ms.openlocfilehash: 4017947d53078b33ce2a4195a6ace9af92adc85c
ms.sourcegitcommit: 1c2364fbefd95151f0847a35e8bc7c4c1b3892f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2021
ms.locfileid: "58936147"
---
# <a name="manage-the-join-experience-for-teams-virtual-visits-on-mobile-browsers"></a>モバイル ブラウザーで仮想アクセスTeamsの参加エクスペリエンスを管理する

Microsoft Teamsをダウンロードすることなく、ユーザーがモバイル デバイスで簡単に予定に参加Teams。 よりシームレスなエクスペリエンスを実現するには、出席者はモバイル ブラウザーから医療訪問、財務相談、教育者のオフィス時間などの予定に参加できます。 出席者は、Android または iOS モバイル Teamsアプリをインストールする必要があります。

モバイル ブラウザー参加では、出席者がモバイル デバイスから予定に参加すると、モバイル デバイスから予定をダウンロードTeams。 代わりに、Teamsブラウザーで [今すぐ参加] を選択して参加できます。 この機能では、Teams が出席者のモバイル デバイスに既にインストールされている場合、Teams はアプリではなくモバイル ブラウザーで開きます。

現在、モバイル ブラウザーの参加は、次の予定を通じてスケジュールされている予定で使用できます。

- [Bookings アプリ](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-us&rs=en-us&ad=us#PickTab=Bookings)
- [Microsoft TeamsElectronic Health Records (EHR) コネクタ](healthcare/ehr-admin.md)

## <a name="set-up-mobile-browser-join"></a>モバイル ブラウザー参加を設定する

### <a name="appointments-scheduled-through-the-bookings-app"></a>Bookings アプリを通じてスケジュールされた予定

組織内のスケジューラは、特定の予定の種類と Bookings アプリの個々の予定に対してこの機能を有効にできます。

この機能を有効にすると、出席者に送信される確認メールまたは SMS テキストに、モバイル ブラウザーで Teams を開く会議参加リンクが含まれる。 Android モバイル デバイスでは、Chrome Teamsが開きます。 iOS モバイル デバイスでは、Safari Teamsが開きます。

#### <a name="turn-on-mobile-browser-join-for-an-appointment-type"></a>予定の種類に対してモバイル ブラウザー参加を有効にする

[Bookings] で、[予定の種類 **設定]** に移動し、予定の種類 を選択し、[モバイル ブラウザーから出席者の参加を許可する  >  ]**をオンにします**。 [](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887) これにより、この種類のすべての予定に対してモバイル ブラウザーに参加できます。

:::image type="content" source="../media/mobile-browser-join-bookings-appointment-type.png" alt-text="Bookings アプリの予定の種類の [モバイル ブラウザーから出席者の参加を許可する] 設定のスクリーンショット":::

#### <a name="turn-on-mobile-browser-join-for-an-individual-appointment"></a>個々の予定のモバイル ブラウザー参加を有効にする

[Bookings] で [ **新しい予約]** を選択し、[モバイル ブラウザーから出席者の参加 **を許可する] をオンにします**。

:::image type="content" source="../media/mobile-browser-join-bookings-form.png" alt-text="Bookings アプリの新しい予約フォームの [モバイル ブラウザーから出席者の参加を許可する] 設定のスクリーンショット":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>EHR コネクタでスケジュールTeams予定

セットアップは、ユーザーまたはスタッフが必要とします。

新Teams EHR コネクタは、MyChart Web とモバイルを介して仮想訪問に参加する患者をサポートします。 予約の時点で、患者は [仮想訪問の開始] ボタンを使用して、MyChart から仮想訪問 **を開始** できます。 患者が必要なブラウザーを選択し、そのTeams開きます。

## <a name="supported-mobile-browsers"></a>サポートされているモバイル ブラウザー

現在サポートされているモバイル ブラウザーを次に示します。 特に指定がない限り、最新バージョンと 2 つの以前のバージョンがサポートされます。

|プラットフォーム  |Chrome |Safari |Edge (Chromium)|
|---------|:---:|:---:|:---:|
|Android   |   &#x2714;      |         |         |
|iOS    |         |  &#x2714; &sup1;       |         |
|macOS     |         |  &#x2714; &sup2;    |         |

&sup1;Safari の iOS アプリでは、マイクとスピーカー デバイスを選択できません。 たとえば、デバイスBluetoothします。 これは、既定のデバイス選択を制御するオペレーティング システムの制限です。

&sup2;送信ビデオのサポートには、Safari 14+ と macOS 11+ が必要です。

> [!NOTE]
> Teams の今後のリリースでは、会議参加エクスペリエンスにさらに機能が追加されます。そのため、最新の情報を確認してください。 Teams 機能の最新情報を入手するには、「[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)」を参照してください。

## <a name="related-articles"></a>関連記事

- [Bookings アプリTeams仮想アクセス](../bookings-app-admin.md)
- [Bookings の予定の種類を作成する](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [Bookings の予定に出席者として参加する](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Teams での仮想アクセス - EHR への統合](healthcare/ehr-admin.md)
