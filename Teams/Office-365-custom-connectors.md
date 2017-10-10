---
title: "Microsoft Teams で Office 365 コネクタとカスタム コネクタを使用する | Microsoft サポート"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "コネクタは、頻繁に使用するサービスからのコンテンツや更新をチャネルに直接配信して、チームを最新の状態に保ちます。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 08f2526686c894e44193fb53d51f9f59d6960279
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2017
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="04ed0-103">Microsoft Teams で Office 365 コネクタとカスタム コネクタを使用する</span><span class="sxs-lookup"><span data-stu-id="04ed0-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="04ed0-p101">コネクタは、頻繁に使用するサービスからのコンテンツや更新をチャネルに直接配信して、チームを最新の状態に保ちます。コネクタを使用すると、Microsoft Teams ユーザーは Twitter、Trelloｍ、Wunderlistｍ、GitHub、VSTS などの人気のサービスからの更新情報をチームのチャット ストリームで受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="04ed0-p101">Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and VSTS within the chat stream in their team.</span></span>

<span data-ttu-id="04ed0-p102">チームのどのメンバーも、コネクタを使用して人気のあるクラウド サービスにチームを接続できます。すべてのチーム メンバーはそのようなサービスからアクティビティの通知を受信します。チームから特定のメンバーを削除すると、そのメンバーがチームに追加したコネクタの機能が停止します。予約済みの会議は、グループのカレンダーに取り入れられるため、そのまま有効です。</span><span class="sxs-lookup"><span data-stu-id="04ed0-p102">Any member of a team can connect their team to popular cloud services with the connectors, and all team members are notified of activities from that service. If a user is removed from a team, any connectors added to the team by the removed user do stop working. Scheduled meetings continue to work because they're on the group calendar.</span></span>

<span data-ttu-id="04ed0-p103">Office 365 コネクタは、Microsoft Teams と Office 365 グループの両方で使用できます。そのため、すべてのメンバーが同期された状態を容易に保つことができ、関連情報をすばやく受信できます。Microsoft Teams と Exchange は同じコネクタ モデルを使用するため、両方のプラットフォームで同一のコネクタを使用できます。</span><span class="sxs-lookup"><span data-stu-id="04ed0-p103">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly. Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span>

<span data-ttu-id="04ed0-p104">現時点では、コネクタは Microsoft Teams デスクトップと Web クライアントでのみ追加できます。ただし、コネクタによって投稿された情報はモバイルを含む**すべてのクライアント**で表示できます。</span><span class="sxs-lookup"><span data-stu-id="04ed0-p104">Currently, connectors can be added by using Microsoft Teams desktop and web clients. However, information posted by these connectors can be viewed using **all clients** including mobile.</span></span>

1.  <span data-ttu-id="04ed0-113">チャネルにコネクタを追加するには、チャネル名の横にある**楕円 (…)** をクリックし、[**コネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04ed0-113">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors.**</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  <span data-ttu-id="04ed0-114">ユーザーは利用可能なさまざまなコネクタから選択できます。コネクタを選択して [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04ed0-114">Users can select from a variety of available connectors, then click **Add**.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  <span data-ttu-id="04ed0-p105">選択したコネクタについて必須情報を入力し、[**保存**] をクリックします。各コネクタは、正常に機能するためにさまざまな必須情報を要求します。一部のコネクタでは、コネクタの構成ページに掲載されるリンクを使用してサービスにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04ed0-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  <span data-ttu-id="04ed0-117">コネクタによって提供されるデータはチャネルに自動的に投稿されます。</span><span class="sxs-lookup"><span data-stu-id="04ed0-117">Data provided by the connector is automatically posted to the channel.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="04ed0-118">カスタム コネクタを開発する</span><span class="sxs-lookup"><span data-stu-id="04ed0-118">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="04ed0-p106">基幹業務 (LOB) アプリケーションに統合できるカスタム コネクタを作成することは極めて簡単です。内蔵の**着信 Web フック** コネクタを使用してチャネルのエンドポイントを作成し、HTTP 投稿メソッドを使用して任意のアプリケーションからデータを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="04ed0-p106">It is very easy to develop custom connectors that can integrate into your Line-of-Business (LOB) applications. You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel, that pulls data from any application using HTTP post methods.</span></span>

1.  <span data-ttu-id="04ed0-121">**着信 Web フック**をその他のコネクタと同じ方法で追加します。</span><span class="sxs-lookup"><span data-stu-id="04ed0-121">Add the **Incoming Webhook** like any other connector.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  <span data-ttu-id="04ed0-122">Web フックを作成するには、**名前**を指定し、必要に応じて Web フックの画像を更新します。続けて [**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04ed0-122">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  <span data-ttu-id="04ed0-p107">このチャネルにデータをプッシュするアプリケーションは Web フック コネクタの URL を必要とします。**Web フック** を作成したときに、**固有の URL** が作成されます。この URL を開発者と共有して、開発者が必要に応じてアプリケーションによるデータのプッシュを構成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="04ed0-p107">Applications that push data to this channel, require the Webhook connector URL. A **unique URL** is created when you created the **Webhook**. Share this URL with your developers, so that they can configure their applications to push data, as needed.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  <span data-ttu-id="04ed0-126">外部アプリケーションによってコネクタへのデータのプッシュが実行されると、**コネクタ カード** メッセージと呼ばれる特別なメッセージがチャネルの会話リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="04ed0-126">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

<span data-ttu-id="04ed0-p108">開発者は、Microsoft Team の Web フック アドレスへの簡潔な JSON ペイロードを含む HTTP 要求を送信することで、このカードを作成するようにアプリケーションを構成することができます。この Web フック アドレスは、ウィザードによって提供される当該エンドポイントの固有 URL です。開発者は、Microsoft Developer Network の「[Getting started with Office 365 Connectors for Microsoft Teams (Microsoft Teams 用の Office 365 コネクタの使用を開始する)](https://go.microsoft.com/fwlink/?linkid=855783)」(英語版) で詳細な手順とコネクタのサンプルを参照できます。その他にも「[Outlook でグループにアプリを接続します](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)」および「[Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784)」というリソースが提供されています。</span><span class="sxs-lookup"><span data-stu-id="04ed0-p108">Developers can configure their applications to create these cards, by sending an HTTP request with a simple JSON payload to a Microsoft Team’s Webhook address, that is a unique URL of that endpoint provided by the wizard. Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783), on the Microsoft Developer Network, with detailed instructions and connector samples. Other resources include [Connect apps to your groups in Outlook](https://support.office.com/en-us/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
