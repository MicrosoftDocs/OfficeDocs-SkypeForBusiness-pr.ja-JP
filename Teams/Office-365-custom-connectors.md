---
title: "Microsoft のチームで Office 365 ユーザー設定コネクタを使用します。"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "コネクタでは、チャンネルに直接頻繁に使用するサービスからのコンテンツと更新プログラムを提供することで現在、チームを保持します。"
ms.openlocfilehash: 2e852f88cffefdc259b1a0dbf20349bbaf5e3686
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="e96d6-103">Microsoft のチームで Office 365 ユーザー設定コネクタを使用します。</span><span class="sxs-lookup"><span data-stu-id="e96d6-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="e96d6-p101">コネクタでは、チャンネルに直接頻繁に使用するサービスからのコンテンツと更新プログラムを提供することで現在、チームを保持します。コネクタを使用 Microsoft チーム ユーザーは、Twitter、Trello、Wunderlist、GitHub、VSTS など、チームでチャット ストリーム内の一般的なサービスから更新を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="e96d6-p101">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and VSTS within the chat stream in their team.</span></span>

<span data-ttu-id="e96d6-p102">チームのメンバーが、コネクタでの一般的なクラウド サービスに自分のチームを接続できるし、そのサービスからのアクティビティのすべてのチーム メンバーは通知します。チームからユーザーを削除する場合は、削除したユーザーによって、チームに追加されたすべてのコネクタは動作を停止します。スケジュールされた会議では、グループの予定表をオンになっているために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e96d6-p102">Any member of a team can connect their team to popular cloud services with the connectors, and all team members are notified of activities from that service. If a user is removed from a team, any connectors added to the team by the removed user do stop working. Scheduled meetings continue to work because they're on the group calendar.</span></span>

<span data-ttu-id="e96d6-p103">Office 365 のコネクタは、両方の Microsoft チームで使用できると Office 365 グループを簡単にすべてのメンバーのでもと関連する情報をすばやく表示します。Microsoft チームと Exchange の両方、両方のプラットフォームで同じコネクタを使用することができますが、同じコネクタ モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e96d6-p103">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly. Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span>

<span data-ttu-id="e96d6-p104">現時点では、Microsoft チーム デスクトップと web クライアントを使用してコネクタを追加することができます。ただし、これらのコネクタが投稿された情報は、モバイルを含む**すべてのクライアント**を使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="e96d6-p104">Currently, connectors can be added by using Microsoft Teams desktop and web clients. However, information posted by these connectors can be viewed using **all clients** including mobile.</span></span>

1.  <span data-ttu-id="e96d6-113">チャンネルにコネクタを追加するには、チャンネル名の右側の**省略記号 (…)]**をクリックし] をクリックして**コネクタ**。</span><span class="sxs-lookup"><span data-stu-id="e96d6-113">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors.**</span></span>

    ![選択されているチャンネル名とコネクタ] オプションが選択されているチーム インターフェイスのスクリーン ショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  <span data-ttu-id="e96d6-115">ユーザーは、使用可能なコネクタは、さまざまなからを選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e96d6-115">Users can select from a variety of available connectors, then click **Add**.</span></span>

    ![[コネクタ] ダイアログのコネクタを追加するためのスクリーン ショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  <span data-ttu-id="e96d6-p105">選択したコネクタの必要な情報を入力し、[**保存**] をクリックします。各コネクタには、さまざまな一連の情報が正常に機能が必要です。 とコネクタの構成] ページに表示されているリンクを使用して、サービスにサインインするのにはいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="e96d6-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![RSS コネクタの構成] ページのスクリーン ショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  <span data-ttu-id="e96d6-120">チャネルをコネクタによって提供されるデータが自動的に転記します。</span><span class="sxs-lookup"><span data-stu-id="e96d6-120">Data provided by the connector is automatically posted to the channel.</span></span>

    ![チャンネルの会話が表示されているチーム インターフェイスのスクリーン ショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="e96d6-122">ユーザー設定コネクタを作成します。</span><span class="sxs-lookup"><span data-stu-id="e96d6-122">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="e96d6-p106">基幹業務 (LOB) アプリケーションに統合可能なユーザー設定コネクタを開発する非常に簡単できます。組み込みの**着信 Webhook**コネクタを使用するには、HTTP post メソッドを使用しているアプリケーションからのデータを抽出するチャネルの両端のシートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e96d6-p106">It is very easy to develop custom connectors that can integrate into your Line-of-Business (LOB) applications. You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel, that pulls data from any application using HTTP post methods.</span></span>

1.  <span data-ttu-id="e96d6-125">その他のすべてのコネクタのような**着信 Webhook**を追加します。</span><span class="sxs-lookup"><span data-stu-id="e96d6-125">Add the **Incoming Webhook** like any other connector.</span></span>

    ![受信した Webhook コネクタを追加するオプションのスクリーン ショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="e96d6-127">Webhook を作成するには、**名**を指定して、必要に応じて、Webhook イメージを更新および**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e96d6-127">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![<span data-ttu-id="e96d6-128">受信した Webhook コネクタの構成] ページのスクリーン ショット。</span><span class="sxs-lookup"><span data-stu-id="e96d6-128">Screenshot of the configuration page for the Incoming Webhook connector.</span></span> ](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="e96d6-p107">このチャネルにデータをプッシュするアプリケーションでは、Webhook コネクタの URL が必要です。**Webhook**の作成時に、**一意の URL**が作成されます。必要に応じて、データをプッシュするアプリケーションを構成することができるように、開発者は、この URL を共有します。</span><span class="sxs-lookup"><span data-stu-id="e96d6-p107">Applications that push data to this channel, require the Webhook connector URL. A **unique URL** is created when you created the **Webhook**. Share this URL with your developers, so that they can configure their applications to push data, as needed.</span></span>

    ![[Webhook の一意の URL のスクリーン ショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  <span data-ttu-id="e96d6-133">外部アプリケーションでは、データをプッシュ コネクタに、メッセージが**コネクタ カード**メッセージと呼ばれる特殊なメッセージとしてチャネル会話ボックスの一覧で表示されます。</span><span class="sxs-lookup"><span data-stu-id="e96d6-133">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![コネクタのカードのメッセージが表示されているチーム インターフェイスのスクリーン ショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

<span data-ttu-id="e96d6-p108">開発者は、Microsoft チームの Webhook アドレスに、ウィザードによって提供されるエンドポイントの一意の URL で単純な JSON ペイロード HTTP 要求を送信して、これらのカードを作成するのには、アプリケーションを構成できます。[チームの Microsoft Office 365 のコネクタの使用を開始する](https://go.microsoft.com/fwlink/?linkid=855783)、ネットワーク上で Microsoft 開発、詳細な手順と、コネクタのサンプルを参照して、開発者があります。その他のリソースには、 [Outlook でグループへの接続アプリ](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)と[Office デベロッパー センター – Microsoft チーム](https://go.microsoft.com/fwlink/?linkid=855784)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e96d6-p108">Developers can configure their applications to create these cards, by sending an HTTP request with a simple JSON payload to a Microsoft Team’s Webhook address, that is a unique URL of that endpoint provided by the wizard. Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783), on the Microsoft Developer Network, with detailed instructions and connector samples. Other resources include [Connect apps to your groups in Outlook](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
