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
f1.keywords:
- NOCSH
description: コネクタは、頻繁に使用するサービスからのコンテンツや更新をチャネルに直接配信して、チームを最新の状態に保ちます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc65939048fd8e54bd122a4dc52d2a611b8453cc
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834377"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="9c001-103">Microsoft Teams で Office 365 コネクタとカスタム コネクタを使用する</span><span class="sxs-lookup"><span data-stu-id="9c001-103">Use Office 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="9c001-104">コネクタは、頻繁に使用されるコンテンツとサービスの更新をチャネルに直接配信することで、チームを最新の状態に維持します。</span><span class="sxs-lookup"><span data-stu-id="9c001-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="9c001-105">コネクタを使用すると、Microsoft Teams ユーザーは、Twitter、Trello、Wunderlist、GitHub、Azure DevOps サービスなどの一般的なサービスからの更新情報を、チームのチャットストリームで受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="9c001-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="9c001-106">チームの権限が許可されていて、すべてのチームメンバーがそのサービスのアクティビティについて通知する場合は、チームのメンバー全員がそのコネクタを使用して、チームの主要なクラウドサービスに接続できます。</span><span class="sxs-lookup"><span data-stu-id="9c001-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="9c001-107">コネクタを最初に設定したメンバーが残っている場合でも、コネクタは引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="9c001-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="9c001-108">権限を持つすべてのチームメンバーは、他のメンバーによるコネクタの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9c001-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="9c001-109">Office 365 コネクタは Microsoft Teams と Office 365 の両方のグループで使用できるため、すべてのメンバーが簡単に同期して関連情報を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="9c001-109">Office 365 connectors can be used with both Microsoft Teams and Office 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="9c001-110">Microsoft Teams と Exchange は両方とも同じコネクタモデルを使用しており、両方のプラットフォームで同じコネクタを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c001-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="9c001-111">ただし、チームが依存している Office 365 グループのコネクタを無効にすると、そのチームのコネクタの作成機能も無効になります。</span><span class="sxs-lookup"><span data-stu-id="9c001-111">It is worth noting, however, that disabling connectors for the Office 365 Group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="9c001-112">チャネルにコネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="9c001-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="9c001-113">現時点では、Microsoft Teams のデスクトップと web クライアントを使用してコネクタを追加できます。</span><span class="sxs-lookup"><span data-stu-id="9c001-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="9c001-114">ただし、これらのコネクタによって投稿された情報は、mobile を含む**すべてのクライアント**で表示できます。</span><span class="sxs-lookup"><span data-stu-id="9c001-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="9c001-115">チャネルにコネクタを追加するには、チャネル名の右にある**省略記号 (...)** をクリックし、[**コネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c001-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![[コネクタ] オプションが選択されている Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="9c001-117">さまざまなコネクタから選んで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c001-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![使用可能なコネクタが表示されている [コネクタ] ダイアログのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="9c001-p105">選択したコネクタについて必須情報を入力し、[**保存**] をクリックします。各コネクタは、正常に機能するためにさまざまな必須情報を要求します。一部のコネクタでは、コネクタの構成ページに掲載されるリンクを使用してサービスにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c001-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![RSS コネクタの [構成] ページのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="9c001-122">コネクタによって提供されるデータはチャネルに自動的に投稿されます。</span><span class="sxs-lookup"><span data-stu-id="9c001-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![チャネル内の会話を示す Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="9c001-124">カスタム コネクタを開発する</span><span class="sxs-lookup"><span data-stu-id="9c001-124">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="9c001-125">カスタムコネクタや、受信および送信の web フックを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c001-125">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="9c001-126">詳細については、「[開発者向けドキュメント](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)」を参照してください:</span><span class="sxs-lookup"><span data-stu-id="9c001-126">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
