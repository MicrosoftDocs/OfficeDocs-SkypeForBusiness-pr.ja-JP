---
title: Microsoft Teams と Bookings アプリを使用した仮想訪問
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
ms.reviewer: ''
description: 仮想アクセスをスケジュール、管理、実施するために、Teams Bookings アプリを使用する方法について説明します。
ms.openlocfilehash: a37a024e31c75bbedbdb36d9aa0d6acfd2af614c
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432459"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Microsoft Teams と Bookings アプリを使用した仮想訪問

## <a name="overview"></a>概要

Bookings[アプリをMicrosoft Teams、](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)スタッフと出席者の仮想予定を簡単にスケジュールおよび管理できます。 医療訪問、財務相談、面接、カスタマー サポート、仮想ショッピング エクスペリエンス、教育オフィス時間などの仮想予定をスケジュールするために使用します。

Bookings アプリを使用すると、組織の複雑なスケジュール要求を簡単に管理できます。 スケジュール担当者は、1 つの操作環境から、複数の部門とスタッフの予定表、および組織内外の出席者との通信を管理できます。

仮想アクセスは、堅牢なビデオ会議Microsoft Teams会議を通じて開催されます。 たとえば、医師は画面を共有し、患者とテスト結果を確認できます。 または、銀行アドバイザーはドキュメントに電子署名を要求して、リモートでトランザクションを閉じできます。

各仮想予定にはTeams会議リンクが含まれています。このリンクは、Web ブラウザーまたは任意のデバイスの Teams から簡単に参加できるメールで出席者に送信されます。 自動メール アラームは、表示を減らし、顧客とクライアントのエンゲージメントを強化するのに役立ちます。

Bookings を使用すると、業界に合わせてカスタマイズされたエクスペリエンスを利用できます。 組織で使用する方法の例を次に示します。

|業界 | 例 |
|---------|---------|
|金融サービス    |  リモート販売とサービスの仮想訪問<br/>銀行関係マネージャー、財務アドバイザー、クレーム調整担当者の仮想予定をスケジュールおよび管理して、効率と利便性を高める顧客にサービスを提供します。  |
|医療   |  患者のケアのための仮想訪問 <br/>患者や他の医療プロバイダーと会って医療について話し合う、ケア チーム メンバーの仮想訪問をスケジュールおよび管理します。   |
|リテール   | 仮想ショッピング エクスペリエンス <br/>顧客との仮想ショッピング エクスペリエンスを実施するために、営業担当者、製品エキスパート、および設計コンサルタントの予定をスケジュールおよび管理します。   |

この記事では、Teams で Bookings アプリを使用して仮想アクセスをスケジュール、管理、実施する方法の概要について説明します。

## <a name="before-you-get-started"></a>使用を開始する前に

管理者の場合は、「Teams で Bookings アプリを管理する」を参照して、Teams で Bookings アプリを使用するための前提条件、組織内の[Bookings](../bookings-app-admin.md)へのアクセスを制御する方法、推奨されるポリシーと管理者設定について説明します。

Bookings アプリをインストールする必要があるのは、組織内のスケジューラTeams。 仮想予定を実施または参加するスタッフは、アプリを必要とします。 自分の予定表または予定表Teams Outlook予約確認メールの会議リンクを使用して、予定に参加します。

## <a name="set-up-a-new-booking-calendar"></a>新しい予約予定表を設定する

### <a name="create-the-booking-calendar"></a>予約予定表を作成する

**[Teams、[Bookings** の開始]  >  **に移動** し、[新しい予約カレンダー **] を選択します**。 フォームに入力し、組織に関連するビジネスの種類を選択してください。

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="ビジネスの種類を示す新しい予約予定表画面のスクリーンショット":::

大規模な組織の場合は、出席者が組織全体ではなく特定の部署から予約メールを受け取る場合は、複数の予約予定表を作成します。
詳細については、「Bookings カレンダー [を作成する」を参照してください](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)。

> [!NOTE]
> これが Bookings アプリで初めてではない場合、または既存の予約予定表で作業する場合は、[Bookings] で組織名の横にあるドロップダウン矢印を選択し、[既存の予約予定表] を選択 **します。** ここから、必要な情報を検索できます。

### <a name="add-staff"></a>スタッフを追加する

予約予定表で、[その他のオプション (...)] に移動 **>設定、[スタッフ**] を **選択します**。 スタッフ メンバーを追加し、追加する各ユーザーにロールを割り当てる。

Bookings アプリは、Bookings アプリと Outlook。 スタッフを追加すると、そのユーザーの予定表の空き時間情報を表示し、そのユーザーの予約をスケジュールできます。 詳細については、「スタッフを追加 [する」と「Bookings カレンダーを表示する」を参照してください](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0)。  

### <a name="create-appointment-types"></a>予定の種類を作成する

組織が提供するサービスを表し、予約エクスペリエンスを調整するために、特定の予定の種類を作成します。

予約予定表で、[予定の種類] の **[その** 他のオプション (...>] に **移動** し、[新しい予定の種類] **を選択します**。 名前を入力します。たとえば、アカウントの開始、支払い方法の更新、ローンコンサルテーション、税金の準備、その他の情報と &mdash; &mdash; 設定を入力します。

追加した情報とリンクは、この種類の予定が予約されるごとに出席者に送信されるメールの確認に含まれます。 メール アラームなどのオプション (出席者がモバイル ブラウザーから参加できるかどうかなど)[](mobile-browser-join.md)を設定Teams。 詳細については、「予定の種類を [作成する」を参照してください](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)。

## <a name="schedule-a-virtual-visit"></a>仮想アクセスのスケジュールを設定する

予約予定表で、[新しい予約] **を選択します**。 予定の種類を選択し、関連する情報を入力します。

これには、出席者の連絡先情報、サービスを提供するスタッフ メンバー、スタッフだけが表示できる内部メモ、メール アラーム、および出席者がモバイル ブラウザーから参加できるかどうかが含まれます。 詳細については、「Bookings アプリ[で予約をスケジュールする」Teams参照してください](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f)。

出席者に送信されたメールの確認には、会議のリンクと添付ファイルが含まれるので、予定表に仮想予定を追加できます。 スタッフには、メールによる確認と会議への招待も送信されます。

## <a name="conduct-a-virtual-visit"></a>仮想訪問を実施する

予定表TeamsまたはOutlookで、予約に移動し、[参加] または [会議への参加] Teams選択します。 オーディオとビデオの設定を確認し、[今すぐ参加] **を選択します**。 詳細については、「Bookings の予定 [を実施する」を参照してください](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd)。

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Bookings Web アプリを使用した追加機能

Bookings Web アプリでは、追加の機能が提供されます。 たとえば、セルフサービスのオンライン予約ページを公開して、スタッフとの予定をスケジュールできます。 Bookings Web アプリにアクセスするには、「Bookings Web アプリを開く」> オプション (...)**に移動します**。

詳細については [、「Microsoft Bookings」を参照してください](/microsoft-365/bookings/bookings-overview)。

## <a name="related-articles"></a>関連記事

[モバイル ブラウザーで仮想アクセスTeamsの参加エクスペリエンスを管理する](mobile-browser-join.md)

[医療機関向け Microsoft Teams の使用を開始する](healthcare/teams-in-hc.md)

[Bookings アプリのヘルプ Teamsドキュメント](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
