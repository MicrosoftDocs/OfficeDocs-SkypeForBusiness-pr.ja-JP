---
title: Microsoft 365 とカスタムコネクタを使用する
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
description: コネクタにより、頻繁に使用するサービスからコンテンツと更新内容がチャネルに直接配信されるため、チームは最新の状態に保たれます。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9ea72fbe054e3a6d0e89f87f1a8c23303ef55c5c
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637756"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="97b12-103">Microsoft Teams で Microsoft 365 とカスタムコネクタを使用する</span><span class="sxs-lookup"><span data-stu-id="97b12-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="97b12-104">コネクタは、頻繁に使用されるコンテンツとサービスの更新をチャネルに直接配信することで、チームを最新の状態に維持します。</span><span class="sxs-lookup"><span data-stu-id="97b12-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="97b12-105">コネクタを使用すると、Microsoft Teams ユーザーは、Twitter、Trello、Wunderlist、GitHub、Azure DevOps サービスなどの一般的なサービスからの更新情報を、チームのチャットストリームで受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="97b12-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Twitter, Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="97b12-106">チームの権限が許可されていて、すべてのチームメンバーがそのサービスのアクティビティについて通知する場合は、チームのメンバー全員がそのコネクタを使用して、チームの主要なクラウドサービスに接続できます。</span><span class="sxs-lookup"><span data-stu-id="97b12-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="97b12-107">コネクタを最初に設定したメンバーが残っている場合でも、コネクタは引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="97b12-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="97b12-108">権限を持つすべてのチームメンバーは、他のメンバーによるコネクタの設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="97b12-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="97b12-109">Microsoft 365 コネクタは、Microsoft Teams と Microsoft 365 グループの両方で使用できます。すべてのメンバーが同期して、関連する情報をすばやく受け取ることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="97b12-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="97b12-110">Microsoft Teams と Exchange は両方とも同じコネクタモデルを使用しており、両方のプラットフォームで同じコネクタを使用できます。</span><span class="sxs-lookup"><span data-stu-id="97b12-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="97b12-111">ただし、チームが依存している Microsoft 365 グループのコネクタを無効にすると、そのチームのコネクタの作成機能も無効になります。</span><span class="sxs-lookup"><span data-stu-id="97b12-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="97b12-112">チャネルにコネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="97b12-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="97b12-113">現時点では、Microsoft Teams のデスクトップと web クライアントを使用してコネクタを追加できます。</span><span class="sxs-lookup"><span data-stu-id="97b12-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="97b12-114">ただし、これらのコネクタによって投稿された情報は、mobile を含む**すべてのクライアント**で表示できます。</span><span class="sxs-lookup"><span data-stu-id="97b12-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="97b12-115">チャネルにコネクタを追加するには、チャネル名の右にある**省略記号 (...)** をクリックし、[**コネクタ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97b12-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    ![[コネクタ] オプションが選択されている Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. <span data-ttu-id="97b12-117">さまざまなコネクタから選んで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="97b12-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    ![使用可能なコネクタが表示されている [コネクタ] ダイアログのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. <span data-ttu-id="97b12-p105">選択したコネクタについて必須情報を入力し、[**保存**] をクリックします。各コネクタは、正常に機能するためにさまざまな必須情報を要求します。一部のコネクタでは、コネクタの構成ページに掲載されるリンクを使用してサービスにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97b12-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    ![RSS コネクタの [構成] ページのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. <span data-ttu-id="97b12-122">コネクタによって提供されるデータはチャネルに自動的に投稿されます。</span><span class="sxs-lookup"><span data-stu-id="97b12-122">Data provided by the connector is automatically posted to the channel.</span></span>

    ![チャネル内の会話を示す Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a><span data-ttu-id="97b12-124">カスタム コネクタを開発する</span><span class="sxs-lookup"><span data-stu-id="97b12-124">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="97b12-125">カスタムコネクタや、受信および送信の web フックを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="97b12-125">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="97b12-126">詳細については、「[開発者向けドキュメント](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)」を参照してください:</span><span class="sxs-lookup"><span data-stu-id="97b12-126">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
