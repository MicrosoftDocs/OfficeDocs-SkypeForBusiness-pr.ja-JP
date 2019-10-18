---
title: Microsoft Teams で Office 365 コネクタとカスタム コネクタを使用する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: コネクタは、頻繁に使用するサービスからのコンテンツや更新をチャネルに直接配信して、チームを最新の状態に保ちます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b1dc57bbe3d216ee779f962ef4b2fc1152e2161
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563856"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="95b92-103">Microsoft Teams で Office 365 コネクタとカスタム コネクタを使用する</span><span class="sxs-lookup"><span data-stu-id="95b92-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="95b92-104">コネクタは、頻繁に使用されるコンテンツとサービスの更新をチャネルに直接配信することで、チームを最新の状態に維持します。</span><span class="sxs-lookup"><span data-stu-id="95b92-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="95b92-105">コネクタを使用すると、Microsoft Teams ユーザーは、Twitter、Trello、Wunderlist、GitHub、Azure DevOps サービスなどの一般的なサービスからの更新情報を、チームのチャットストリームで受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="95b92-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="95b92-106">チームの権限が許可されていて、すべてのチームメンバーがそのサービスのアクティビティについて通知する場合は、チームのメンバー全員がそのコネクタを使用して、チームの主要なクラウドサービスに接続できます。</span><span class="sxs-lookup"><span data-stu-id="95b92-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="95b92-107">コネクタを最初に設定したメンバーが残っている場合でも、コネクタは引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="95b92-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="95b92-108">権限を持つすべてのチームメンバーは、他のメンバーによるコネクタの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="95b92-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="95b92-109">Office 365 コネクタは Microsoft Teams と Office 365 の両方のグループで使用できるため、すべてのメンバーが簡単に同期して関連情報を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="95b92-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="95b92-110">Microsoft Teams と Exchange は両方とも同じコネクタモデルを使用しており、両方のプラットフォームで同じコネクタを使用できます。</span><span class="sxs-lookup"><span data-stu-id="95b92-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="95b92-111">ただし、チームが依存している Office 365 グループのコネクタを無効にすると、そのチームのコネクタの作成機能も無効になります。</span><span class="sxs-lookup"><span data-stu-id="95b92-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="95b92-112">チャネルにコネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="95b92-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="95b92-113">現時点では、Microsoft Teams のデスクトップと web クライアントを使用してコネクタを追加できます。</span><span class="sxs-lookup"><span data-stu-id="95b92-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="95b92-114">ただし、これらのコネクタによって投稿された情報は、mobile を含む**すべてのクライアント**で表示できます。</span><span class="sxs-lookup"><span data-stu-id="95b92-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="95b92-115">チャネルにコネクタを追加するには、チャネル名の右にある**省略記号 (...)** をクリックし、[**コネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95b92-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![[コネクタ] オプションが選択されている Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="95b92-117">さまざまなコネクタから選んで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95b92-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![使用可能なコネクタが表示されている [コネクタ] ダイアログのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="95b92-p105">選択したコネクタについて必須情報を入力し、[**保存**] をクリックします。各コネクタは、正常に機能するためにさまざまな必須情報を要求します。一部のコネクタでは、コネクタの構成ページに掲載されるリンクを使用してサービスにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="95b92-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![RSS コネクタの [構成] ページのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="95b92-122">コネクタによって提供されるデータはチャネルに自動的に投稿されます。</span><span class="sxs-lookup"><span data-stu-id="95b92-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![チャネル内の会話を示す Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="95b92-124">カスタム コネクタを開発する</span><span class="sxs-lookup"><span data-stu-id="95b92-124">Develop custom connectors</span></span>
-----------------------------

<span data-ttu-id="95b92-125">基幹業務 (LOB) アプリケーションと統合できるカスタムコネクタの開発は非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="95b92-125">It is very easy to develop custom connectors that can integrate with your line-of-business (LOB) applications.</span></span> <span data-ttu-id="95b92-126">組み込みの**受信 Webhook**コネクタを使って、HTTP post メソッドを使って任意のアプリケーションからデータを引き出すチャネルのエンドポイントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="95b92-126">You can use the built-in **Incoming Webhook** connector to create an endpoint for a channel that pulls data from any application using HTTP post methods.</span></span>

1. <span data-ttu-id="95b92-127">**着信 Web フック**をその他のコネクタと同じ方法で追加します。</span><span class="sxs-lookup"><span data-stu-id="95b92-127">Add the **Incoming Webhook** like any other connector.</span></span>

    ![着信 Web フック コネクタを追加するオプションのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. <span data-ttu-id="95b92-129">Web フックを作成するには、**名前**を指定し、必要に応じて Web フックの画像を更新します。続けて [**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95b92-129">To create a Webhook, specify a **name**, update the Webhook image, if necessary, and click **Create**.</span></span>

    ![受信 Webhook コネクタの構成ページのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. <span data-ttu-id="95b92-131">このチャネルにデータをプッシュするアプリケーションには、Webhook コネクタ URL が必要です。</span><span class="sxs-lookup"><span data-stu-id="95b92-131">Applications that push data to this channel require the Webhook connector URL.</span></span> <span data-ttu-id="95b92-132">Webhook の作成時に一意の URL が作成されます。</span><span class="sxs-lookup"><span data-stu-id="95b92-132">A unique URL is created when you create the Webhook.</span></span> <span data-ttu-id="95b92-133">必要に応じて、データをプッシュするようにアプリケーションを構成できるように、この URL を開発者と共有します。</span><span class="sxs-lookup"><span data-stu-id="95b92-133">Share this URL with your developers so that they can configure their applications to push data, as needed.</span></span>

    ![Web フックの固有 URL のスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. <span data-ttu-id="95b92-135">外部アプリケーションによってコネクタへのデータのプッシュが実行されると、**コネクタ カード** メッセージと呼ばれる特別なメッセージがチャネルの会話リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="95b92-135">When an external application pushes data to a connector, the message is shown in the channel conversation list as a special message called a **Connector Card** message.</span></span>

    ![コネクタ カード メッセージを示す Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     <span data-ttu-id="95b92-137">開発者は、ウィザードによって提供されるエンドポイントの固有の URL である、単純な JSON ペイロードの HTTP 要求をチームの Webhook アドレスに送信することによって、これらのカードを作成するようにアプリケーションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="95b92-137">Developers can configure their applications to create these cards by sending an HTTP request with a simple JSON payload to a team’s Webhook address, which is a unique URL of that endpoint provided by the wizard.</span></span> <span data-ttu-id="95b92-138">詳細な手順とコネクタのサンプルが含まれている Microsoft Developer ネットワークで、 [Microsoft Teams の Office 365 コネクタの使用を開始](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors)することを開発者に確認してください。</span><span class="sxs-lookup"><span data-stu-id="95b92-138">Have your developers refer to [Getting started with Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), on the Microsoft Developer Network, which has detailed instructions and connector samples.</span></span> <span data-ttu-id="95b92-139">その他のリソースには、Outlook および[Office デベロッパーセンター– Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784)の[グループへのアプリの接続](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="95b92-139">Other resources include [Connect apps to your groups in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) and the [Office Dev Center – Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).</span></span>
