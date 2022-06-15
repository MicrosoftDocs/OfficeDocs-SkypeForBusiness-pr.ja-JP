---
title: Microsoft Teams と Bookings アプリを使用した仮想予定
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
ms.reviewer: ''
description: Teamsの Bookings アプリを使用して仮想予定をスケジュール、管理、実行する方法について説明します。
ms.openlocfilehash: a89eaa242cd62238d4e5c6c9d7a88f3a2e9ac62c
ms.sourcegitcommit: 39fc58109da6b4628ffb658f2c6b94099e0ab604
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2022
ms.locfileid: "66103384"
---
# <a name="virtual-appointments-with-microsoft-teams-and-the-bookings-app"></a>Microsoft Teams と Bookings アプリを使用した仮想予定

## <a name="overview"></a>概要

Microsoft Teamsの [Bookings アプリ](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5)を使用すると、組織はスタッフと出席者の仮想予定を簡単にスケジュールして管理できます。 これを使用して、医療訪問、財務コンサルテーション、面接、顧客サポート、仮想設備とコンサルテーション、教育オフィスの時間などの予定をスケジュールします。

Bookings アプリを使用すると、組織の複雑なスケジュール要求を簡単に管理できます。 スケジュール担当者は、1 つの操作環境から、複数の部門とスタッフの予定表、および組織内外の出席者との通信を管理できます。

仮想予定は、堅牢なビデオ会議機能を提供するMicrosoft Teams会議を通じて開催されます。 たとえば、医師は画面を共有し、患者とテスト結果を確認できます。 または、銀行アドバイザーは、ドキュメントに対して電子署名を要求して、トランザクションをリモートで閉じることができるようにすることができます。

各仮想予定には、電子メールで出席者に送信されるTeams会議リンクが含まれています。このリンクは、Web ブラウザーから、または任意のデバイスのTeamsで簡単に参加できます。 自動メール リマインダーは、ノーショーを減らし、顧客とクライアントのエンゲージメントを強化するのに役立ちます。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4TQop]

Bookings を使用すると、業界に合わせてカスタマイズされたエクスペリエンスが得られます。 組織内で使用する方法の例をいくつか次に示します。

|業界 | 例 |
|---------|---------|
|金融サービス    |  リモート販売とサービスの仮想予定<br/>銀行関係マネージャー、財務アドバイザー、クレーム調整者の予定をスケジュールし、管理します。たとえば、数名を指定するだけで、効率と利便性を高めて顧客にサービスを提供できます。  |
|小売   | 仮想試着と相談 <br/>営業アソシエイト、製品エキスパート、および設計コンサルタントの予定をスケジュールおよび管理して、顧客との仮想的な備品やコンサルテーションを行います。   |
|医療   |  患者ケアの仮想予定 <br/>医療について話し合うために、患者や他の医療提供者と会うために、ケア チームのメンバーの予定をスケジュールして管理します。   |

この記事では、Teamsの Bookings アプリを使用して仮想予定をスケジュール、管理、および実行する方法の概要について説明します。

## <a name="before-you-get-started"></a>使用を開始する前に

管理者の場合は、「[Teamsで Bookings アプリを管理](../bookings-app-admin.md)する」を参照して、Teamsで Bookings アプリを使用するための前提条件、組織内の Bookings へのアクセスを制御する方法、および推奨されるポリシーと管理者の設定について説明します。

組織内のスケジューラのみが、Teamsに Bookings アプリをインストールする必要があることを忘れないでください。 仮想予定を実施または参加するスタッフは、アプリを必要としません。 TeamsまたはOutlook予定表から、または予約確認メールの会議リンクを使用して、予定に参加します。

## <a name="set-up-a-new-booking-calendar"></a>新しい予約カレンダーを設定する

### <a name="create-the-booking-calendar"></a>予約予定表を作成する

Teamsで、**Bookings** > **概要** に移動し、[**新しい予約予定表**] を選択します。 フォームに入力し、組織に関連するビジネスタイプを選択してください。

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="ビジネスタイプを示す新しい予約カレンダー画面のスクリーンショット":::

大規模な組織の場合は、組織全体ではなく特定の部署から予約メールを出席者に受信させる場合は、複数の予約予定表を作成することを検討してください。
詳細については、「 [Bookings 予定表を作成する」を](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)参照してください。

> [!NOTE]
> Bookings アプリで初めてではない場合、または既存の予約予定表で作業する場合は、Bookings で組織名の横にあるドロップダウン矢印を選択し、 **既存の予約カレンダー** を選択します。 ここから、目的のものを検索できます。

### <a name="add-staff"></a>スタッフを追加する

予約カレンダーで、[**その他のオプション** (...)] >**設定** に移動し、[**スタッフ**] を選択します。 スタッフ メンバーを追加し、追加する各ユーザーにロールを割り当てます。 予約カレンダーには、最大 100 人のスタッフ メンバーを追加できます。

Bookings アプリはOutlookと統合されます。 スタッフを追加すると、そのユーザーの予定表の空き状況を表示し、そのユーザーの予約をスケジュールできます。 詳細については、「スタッフの [追加と Bookings カレンダーの表示」を](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0)参照してください。  

### <a name="create-appointment-types"></a>予定の種類を作成する

組織が提供するサービスを表す特定の予定の種類を作成し、予約エクスペリエンスを調整します。 その後、スケジューラは予定の種類を使用して予定をスケジュールできます。

予約予定表で、**その他のオプション** (...) >**設定** に移動し、[**予定の種類**] を選択し、[**予定の種類の追加**] を選択します。 アカウントの開設、契約更新、ローン相談、税金の準備&mdash;、その他必要な情報や設定などの名前&mdash;を入力します。

追加する情報は、この種類の予定が予約されるたびに出席者に送信される電子メールの確認に含まれます。 出席者が[デスクトップブラウザーまたはモバイル ブラウザーから参加](browser-join.md)できるかどうかなど、電子メールのリマインダーやその他のオプションをTeamsダウンロードせずに設定できます。

Bookings 管理者の場合は、この予定の種類が予約されるたびに出席者に最大 4 つのフォームをリンクして入力できます。 たとえば、出席者が予定に参加する前に、登録フォームに入力を求める場合があります。 フォームをリンクするには、[フォーム **のリンク**] を選択します。 フォームの URL を入力し、[ **リンク**] を選択します。 (フォームを初めてリンクする場合は、フォームを格納するMicrosoft 365 グループを作成するように求められます。 [ **グループの作成]** を選択してグループを作成します。 この操作は、予約予定表に対して 1 回だけ行う必要があります)。

フォームを操作する場合は、次の点に注意してください。

- 既に予定の種類にリンクされているフォームに変更を加えるには、予定の種類またはMicrosoft 365 グループ内で[https://forms.office.com](https://forms.office.com)フォームを選択します。
- ファイルアップロードの質問を含むフォームへの [ファイルのアップロード](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) は、すべての出席者が同じ組織の場合にサポートされます。

スケジューラは、予定の種類を使用して予定をスケジュールするときに、フォームの追加、削除、または予定の種類にリンクしたその他のフォームの追加を選択できます。 出席者は、予定に参加する前にフォームに入力する必要があります。

> [!NOTE]
> 医療記録の継続性または保有目的に必要な予約サービスまたは仮想予約サービスの一部としてフォーム内の患者によって提供されるすべての情報は、ダウンロード、コピー、またはそのようなレコードに直接記載する必要があります。 このサービスは、法的な医療記録または指定されたレコード セットを構成しません。

詳細については、「 [予定の種類の作成」を](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)参照してください。

## <a name="schedule-an-appointment"></a>予定をスケジュールする

予約カレンダーで、[ **新しい予約**] を選択します。 予定の種類を選択し、関連情報を入力します。

これには、出席者の連絡先情報、サービスを提供するスタッフメンバー、スタッフだけが表示できる内部ノート、電子メールのリマインダー、出席者がモバイル ブラウザーから参加できるかどうかが含まれます。 フォームが予定の種類にリンクされている場合は、フォームを含めるか、削除するか、他のリンクされたフォームを追加するかを選択できます。

出席者に送信される電子メールの確認には、会議のリンクと添付ファイルが含まれており、仮想予定を予定表に追加できます。 スタッフには、メールの確認と会議出席依頼も届きます。 フォームが予定に含まれていた場合、Bookings 管理者とスケジューラは、予定の前に出席者がフォームを完了したかどうかを確認し、出席者の応答を表示できます。

詳細については、「[Teams Bookings アプリで予約をスケジュールする」を](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f)参照してください。

## <a name="conduct-an-appointment"></a>予定を実施する

TeamsまたはOutlook予定表で、予約に移動し、[**参加**] または [Teams会議のリンク] を選択します。 オーディオとビデオの設定を確認し、[ **今すぐ参加**] を選択します。 詳細については、「 [Bookings の予定を実施する](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd)」を参照してください。

## <a name="monitor-appointments-and-get-real-time-status-updates"></a>予定を監視し、リアルタイムの状態の更新を取得する

Bookings の [キュー ビュー](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) には、その日のすべての仮想予定をリアルタイムで更新して監視するためのダッシュボードがスタッフに提供されます。 キューを表示するには、Bookings の [ **キュー** ] タブに移動します。

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Teamsの Bookings アプリのキュー ビューのスクリーンショット" lightbox="../media/bookings-virtual-visits-queue.png":::

キューから、スケジューラは新しい予約を追加し、関連する予定の詳細を表示し、1 日を通して予定の状態を確認できます。 患者が待機室に参加すると、状態が変化し、待機時間が表示および追跡されます。 変更を簡単に識別できるように、ビューは自動的に色分けされた更新で更新されます。

スタッフは、キューから直接予定に参加して管理することもできます。

> [!NOTE]
> 現在、Bookings アプリでは、予約カレンダーあたり最大 100 人のスタッフを追加できます。 Graph API を使用して予約カレンダーにスタッフを設定および追加した場合、この制限は適用されない可能性があります。 このシナリオでは、[ **キュー]** タブでは、スタッフが 100 人を超える予定表のコンテンツをレンダリングできません。 最適なエクスペリエンスを得るには、予約カレンダーに 100 人以下のスタッフを追加することをお勧めします。 今後のリリースでは、この制限の解決に取り組んでいます。

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Bookings Web アプリを使用したその他の機能

Bookings Web アプリには、追加機能が用意されています。 たとえば、セルフサービスのオンライン予約ページを公開すると、スタッフと一緒に予定をスケジュールできます。 Bookings Web アプリにアクセスするには、[ **その他のオプション** (...)] > **[Bookings Web アプリを開く]** に移動します。

詳細については、「[Microsoft Bookings](/microsoft-365/bookings/bookings-overview)」を参照してください。

## <a name="get-insight-into-virtual-appointments-usage"></a>仮想予定の使用状況に関する分析情報を取得する

Microsoft Teams管理センターの [Virtual Visits 使用状況レポート](../teams-analytics-and-reports/virtual-visits-usage-report.md)では、組織内の仮想予定アクティビティTeamsの概要を管理者に提供します。 このレポートには、Bookings の予定を含む仮想予定の詳細な分析が表示されます。

ロビーの待機時間や予定の期間などの主要なメトリックを表示できます。 この情報を使用して使用状況の傾向を把握し、仮想予定を最適化してビジネス成果を向上させるために役立ちます。

## <a name="related-articles"></a>関連記事

- [モバイル ブラウザーでTeams仮想予定の参加エクスペリエンスを管理する](browser-join.md)

- [Teams Virtual Visits の使用状況レポート](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [医療機関向けのTeamsとの概要](healthcare/teams-in-hc.md)

- [Teamsヘルプ ドキュメントの Bookings アプリ](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
