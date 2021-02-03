---
title: Microsoft 365 とカスタム コネクタを使用する
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 908469913944aea2a27feb8a35b0e5e5620aae3f
ms.sourcegitcommit: 44de1da5617f57f8c37780ad3451c0128f60b1f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2021
ms.locfileid: "50076419"
---
<a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="584f4-103">Microsoft Teams で Microsoft 365 とカスタム コネクタを使用する</span><span class="sxs-lookup"><span data-stu-id="584f4-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>
=======================================================

<span data-ttu-id="584f4-104">コネクタは、頻繁に使用されるコンテンツとサービスの更新をチャネルに直接配信することで、チームを最新の状態に保つ。</span><span class="sxs-lookup"><span data-stu-id="584f4-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="584f4-105">コネクタを使用すると、Microsoft Teams ユーザーは、チームのチャット ストリーム内で Trello、Wunderlist、GitHub、Azure DevOps Services などの一般的なサービスから更新プログラムを受信できます。</span><span class="sxs-lookup"><span data-stu-id="584f4-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="584f4-106">チームのアクセス許可が許可されている場合、チームのメンバーは誰でも、人気のあるクラウド サービスにコネクタを接続できます。また、すべてのチーム メンバーに、そのサービスからのアクティビティが通知されます。</span><span class="sxs-lookup"><span data-stu-id="584f4-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="584f4-107">コネクタを最初にセットアップしたメンバーが残った後でも、コネクタは引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="584f4-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="584f4-108">追加\削除する権限を持つチーム メンバーは、他のメンバーによるコネクタのセットアップを変更できます。</span><span class="sxs-lookup"><span data-stu-id="584f4-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="584f4-109">Microsoft 365 コネクタは、Microsoft Teams と Microsoft 365 グループの両方で使用することができるので、すべてのメンバーの同期を簡単に行い、関連する情報をすばやく受信できます。</span><span class="sxs-lookup"><span data-stu-id="584f4-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="584f4-110">Microsoft Teams と Exchange の両方で同じコネクタ モデルが使用され、両方のプラットフォーム内で同じコネクタを使用できます。</span><span class="sxs-lookup"><span data-stu-id="584f4-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="584f4-111">ただし、チームが依存している Microsoft 365 グループのコネクタを無効にすると、そのチームのコネクタを作成する機能も無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="584f4-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

<a name="add-a-connector-to-a-channel"></a><span data-ttu-id="584f4-112">チャネルにコネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="584f4-112">Add a connector to a channel</span></span>
----------------------------

<span data-ttu-id="584f4-113">現在、Microsoft Teams デスクトップおよび Web クライアントを使用してコネクタを追加できます。</span><span class="sxs-lookup"><span data-stu-id="584f4-113">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="584f4-114">ただし、これらのコネクタによって投稿された情報は、モバイルを含むすべての **クライアントで** 表示できます。</span><span class="sxs-lookup"><span data-stu-id="584f4-114">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="584f4-115">チャネルにコネクタを追加するには、チャネル名の右側にある省略記号 **(...)** をクリックし、[コネクタ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="584f4-115">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="584f4-116">![[コネクタ] オプションが選択された Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="584f4-116">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="584f4-117">使用可能なさまざまなコネクタから選び、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="584f4-117">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="584f4-118">![使用可能なコネクタを示す [コネクタ] ダイアログのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="584f4-118">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="584f4-p105">選択したコネクタについて必須情報を入力し、[**保存**] をクリックします。各コネクタは、正常に機能するためにさまざまな必須情報を要求します。一部のコネクタでは、コネクタの構成ページに掲載されるリンクを使用してサービスにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="584f4-p105">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="584f4-121">![RSS コネクタの [構成] ページのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="584f4-121">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="584f4-122">コネクタによって提供されるデータはチャネルに自動的に投稿されます。</span><span class="sxs-lookup"><span data-stu-id="584f4-122">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="584f4-123">![チャネル内の会話を示す Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="584f4-123">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="584f4-124">**コネクタの URL 更新通知**</span><span class="sxs-lookup"><span data-stu-id="584f4-124">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="584f4-125">Teams コネクタは、セキュリティを強化するために新しい URL に移行しています。</span><span class="sxs-lookup"><span data-stu-id="584f4-125">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="584f4-126">この移行中に、新しい URL を使用するように構成されたコネクタを更新する特定の通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="584f4-126">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="584f4-127">コネクタ サービスが中断されるのを防ぐために、コネクタを直ちに更新してください。</span><span class="sxs-lookup"><span data-stu-id="584f4-127">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="584f4-128">URL を更新するには、次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="584f4-128">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="584f4-129">コネクタの構成ページで、更新する必要がある接続の [管理] ボタンの下に "注意が必要です" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="584f4-129">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="584f4-130">!["要注意" メッセージのスクリーンショット。](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="584f4-130">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="584f4-131">受信 Webhook コネクタの場合は、[URL の更新]を選択し、新しく生成された Webhook URL を使用するだけで、接続を再作成できます。</span><span class="sxs-lookup"><span data-stu-id="584f4-131">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="584f4-132">![[URL の更新] ボタンのスクリーンショット。](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="584f4-132">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="584f4-133">その他の種類のコネクタの場合、ユーザーはコネクタを削除し、コネクタの構成を再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="584f4-133">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="584f4-134">URL が正常に更新されると、"URL は最新です" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="584f4-134">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="584f4-135">!["URL は最新の情報です" というメッセージのスクリーンショット。](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="584f4-135">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


<a name="develop-custom-connectors"></a><span data-ttu-id="584f4-136">カスタム コネクタを開発する</span><span class="sxs-lookup"><span data-stu-id="584f4-136">Develop custom connectors</span></span>
----------------------------

<span data-ttu-id="584f4-137">また、カスタム コネクタだけでなく、受信および送信 Webhook を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="584f4-137">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="584f4-138">詳細については、「[開発者向けドキュメント](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)」を参照してください:</span><span class="sxs-lookup"><span data-stu-id="584f4-138">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
