---
title: ブラウザーで仮想予定をTeamsするための参加エクスペリエンスを管理する
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
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: hafarmer
description: ブラウザーでのTeams仮想予定の参加エクスペリエンスについて説明します。
ms.openlocfilehash: 418186734befa66f145ca56f883605715d83aa30
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853308"
---
# <a name="manage-the-join-experience-for-teams-virtual-appointments-on-browsers"></a>ブラウザーで仮想予定をTeamsするための参加エクスペリエンスを管理する

Microsoft Teamsを使用すると、Teamsをダウンロードしなくても、仮想予定に簡単に参加できます。 よりシームレスなエクスペリエンスを実現するために、出席者は、デスクトップまたはモバイル ブラウザーから、医療訪問や財務コンサルテーションなどの予定に参加できます。 出席者は、デバイスにTeams アプリをインストールする必要はありません。

ブラウザーへの参加では、出席者が予定に参加するときに、Teamsのダウンロードを求めるメッセージは表示されません。 代わりに、ブラウザーでTeamsが開き、出席者は **[今すぐ参加**] を選択して参加できます。 この機能では、Teamsがデバイスに既にインストールされている場合、Teamsはアプリではなくブラウザーで開かれることに注意してください。

現在、ブラウザーの参加は、次を通じてスケジュールされた予定で使用できます。

- [Bookings アプリ](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)
- Microsoft Teams電子正常性レコード (EHR) コネクタ

  - [Cerner EHR](healthcare/ehr-admin-cerner.md) との統合
  - [エピック EHR](healthcare/ehr-admin.md) との統合

## <a name="set-up-browser-join"></a>ブラウザー結合を設定する

### <a name="appointments-scheduled-through-the-bookings-app"></a>Bookings アプリを通じてスケジュールされた予定

組織内のスケジューラは、特定の予定の種類と、Bookings アプリ内の個々の予定に対してこの機能を有効にすることができます。

この機能を有効にすると、出席者に送信される確認メールまたは SMS テキストに、デスクトップまたはモバイル ブラウザーでTeams開く会議参加リンクが含まれます。 サポートされているブラウザーの一覧については、「 [サポートされているブラウザー](#supported-browsers)」を参照してください。

#### <a name="turn-on-browser-join-for-an-appointment-type"></a>予定の種類に対してブラウザーの参加を有効にする

Bookingsで **、設定** > **Appointment の種類** に移動し、[予定の種類](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)を選択して、[**出席者にブラウザーからの参加を許可する**] をオンにします。 これを行うと、この種類のすべての予定に対するブラウザー参加が有効になります。

:::image type="content" source="../media/browser-join-bookings-appointment-type.png" alt-text="Bookings アプリの予定の種類のブラウザー設定から出席者の参加を許可するのスクリーンショット":::

#### <a name="turn-on-browser-join-for-an-individual-appointment"></a>個々の予定のブラウザー参加を有効にする

Bookingsで [**新しい予約**] を選択し、[**出席者がブラウザーから参加することを許可** する] をオンにします。

:::image type="content" source="../media/browser-join-bookings-form.png" alt-text="Bookings アプリの新しい予約フォームのブラウザー設定から出席者の参加を許可する設定のスクリーンショット":::

### <a name="appointments-scheduled-through-the-teams-ehr-connector"></a>Teams EHR コネクタを介してスケジュールされた予定

お客様またはスタッフによるセットアップは不要です。

**Cerner EHR との統合**: Teams EHR コネクタは、SMS テキスト メッセージのリンクを介して仮想予定に参加する患者をサポートします。 予定の時点で、患者は SMS テキスト メッセージのリンクをタップして参加でき、ブラウザーでTeams開きます。

**エピック EHR との統合**: Teams EHR コネクタは、MyChart Web とモバイルを介して仮想予定に参加する患者をサポートします。 予定の時点で、患者は **[仮想訪問の開始**] ボタンを使用して MyChart から予定を開始できます。ブラウザーでTeamsが開きます。

## <a name="supported-browsers"></a>サポートされているブラウザー

現在サポートされているブラウザーを次に示します。 特に明記されていない限り、最新バージョンと 2 つの以前のバージョンがサポートされています。

|プラットフォーム  |クロム |サファリ |Edge (Chromium)|
|---------|:---|:---|:---:|
|Android   | &#x2714; &sup1;      |         |         |
|iOS    |         | &#x2714; &sup1;&sup2; |         |
|macOS     | &#x2714; | &#x2714;|         |
|Windows    | &#x2714; |   | &#x2714; |
|Ubuntu/Linux     | &#x2714;         |     |         |

&sup1;発信画面の共有は、iOS または Android ではサポートされていません。

&sup2;Safari 上の iOS アプリでは、マイクデバイスとスピーカー デバイスを選択できません。 たとえば、デバイスをBluetoothします。 これは、既定のデバイス選択を制御するオペレーティング システムの制限です。

## <a name="things-to-consider"></a>考慮すべき点

予定を実施するスタッフメンバーは、デスクトップ、モバイル、または Web クライアントのTeams画面を、デスクトップまたはモバイル ブラウザーから参加する出席者と共有できます。 ただし、出席者はデスクトップまたはモバイル ブラウザーから画面を共有することはできません。

## <a name="related-articles"></a>関連記事

- [TeamsとBookings アプリを使用した仮想予定](bookings-virtual-visits.md)
- [Bookings予定の種類を作成する](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)
- [出席者としてBookings予定に参加する](https://support.microsoft.com/office/join-a-bookings-appointment-as-an-attendee-95cea12d-2220-421f-a663-6efb20913c7f)
- [Teamsを使用した仮想予定 - Cerner EHR への統合](healthcare/ehr-admin-cerner.md)
- [Teamsを使用した仮想予定 - エピック EHR への統合](healthcare/ehr-admin.md)
