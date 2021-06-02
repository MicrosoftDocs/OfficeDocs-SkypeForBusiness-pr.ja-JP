---
title: カスタム Microsoft 365を使用する
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
ms.openlocfilehash: df9cdc8bb53ae55acae10b0146655f5e5f3e0346
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717608"
---
# <a name="use-microsoft-365-and-custom-connectors-in-microsoft-teams"></a><span data-ttu-id="a36ca-103">Microsoft 365コネクタとカスタム コネクタを使用Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a36ca-103">Use Microsoft 365 and custom connectors in Microsoft Teams</span></span>

<span data-ttu-id="a36ca-104">コネクタは、頻繁に使用されるコンテンツとサービスの更新をチャネルに直接配信することで、チームを最新の状態に保つ。</span><span class="sxs-lookup"><span data-stu-id="a36ca-104">Connectors keep your team current by delivering frequently used content and service updates directly into a channel.</span></span> <span data-ttu-id="a36ca-105">コネクタを使用すると、Microsoft Teams ユーザーは、チームのチャット ストリーム内で Trello、Wunderlist、GitHub、Azure DevOps Services などの一般的なサービスから更新プログラムを受信できます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-105">With connectors, your Microsoft Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services within the chat stream in their team.</span></span>

<span data-ttu-id="a36ca-106">チームのメンバーは誰でも、チームのアクセス許可が許可されている場合に、人気のあるクラウド サービスにコネクタを接続できます。また、すべてのチーム メンバーには、そのサービスからのアクティビティが通知されます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-106">Any member of a team can connect their team to popular cloud services with the connectors if the team permissions allow, and all team members are notified of activities from that service.</span></span> <span data-ttu-id="a36ca-107">コネクタは、コネクタを最初にセットアップしたメンバーが離した後でも引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="a36ca-107">Connectors will continue to function even after the member who has initially setup the connector has left.</span></span> <span data-ttu-id="a36ca-108">add\remove アクセス許可を持つチーム メンバーは、他のメンバーによるコネクタのセットアップを変更できます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-108">Any team member with the permissions to add\remove can modify connectors setup by other members.</span></span>

<span data-ttu-id="a36ca-109">Microsoft 365コネクタは、Microsoft Teams グループと Microsoft 365 グループの両方で使用することができるので、すべてのメンバーが同期を取り合い、関連する情報をすばやく受信しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="a36ca-109">Microsoft 365 connectors can be used with both Microsoft Teams and Microsoft 365 groups, making it easier for all members to stay in sync and receive relevant information quickly.</span></span> <span data-ttu-id="a36ca-110">両方Microsoft TeamsとExchange同じコネクタ モデルを使用します。これにより、両方のプラットフォーム内で同じコネクタを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-110">Both Microsoft Teams and Exchange use the same connector model, which allows you to use the same connectors within both platforms.</span></span> <span data-ttu-id="a36ca-111">ただし、チームが依存している Microsoft 365 グループのコネクタを無効にすると、そのチーム用のコネクタを作成する機能も無効にされます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-111">It is worth noting, however, that disabling connectors for the Microsoft 365 group that a team is dependent upon will disable the ability to create connectors for that team as well.</span></span>

> [!NOTE]
> <span data-ttu-id="a36ca-112">コネクタは、既定では、一部の環境GCC無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a36ca-112">Connectors are disabled by default in GCC environments.</span></span> <span data-ttu-id="a36ca-113">有効にする必要がある場合は、ConnectorsEnabled または ConnectorsEnabledForTeams パラメーターを [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) コマンドレットを使用$true に設定します。</span><span class="sxs-lookup"><span data-stu-id="a36ca-113">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet.</span></span> <span data-ttu-id="a36ca-114">以前は[、PowerShell に接続Exchange Online必要があります](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a36ca-114">You previously need to [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!NOTE]
> <span data-ttu-id="a36ca-115">Government Cloud Community (GCC) 環境では、コネクタは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="a36ca-115">Connectors are disabled by default in the Government Cloud Community (GCC) environments.</span></span> <span data-ttu-id="a36ca-116">有効にする必要がある場合は、ConnectorsEnabled または ConnectorsEnabledForTeams パラメーターを [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) コマンドレット$trueに設定します。</span><span class="sxs-lookup"><span data-stu-id="a36ca-116">If you need to enable them, set the ConnectorsEnabled or ConnectorsEnabledForTeams parameters to $true with the [SetOrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) cmdlet.</span></span> <span data-ttu-id="a36ca-117">以前は、PowerShell に接続するExchange Online[必要がありました](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="a36ca-117">You previously needed to connect to the [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

## <a name="add-a-connector-to-a-channel"></a><span data-ttu-id="a36ca-118">コネクタをチャネルに追加する</span><span class="sxs-lookup"><span data-stu-id="a36ca-118">Add a connector to a channel</span></span>

<span data-ttu-id="a36ca-119">現時点では、デスクトップクライアントと Web クライアントを使用Microsoft Teamsコネクタを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-119">Currently, you can add connectors by using Microsoft Teams desktop and web clients.</span></span> <span data-ttu-id="a36ca-120">ただし、これらのコネクタによって投稿された情報は、モバイルを含むすべての **クライアントで** 表示できます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-120">However, information posted by these connectors can be viewed in **all clients** including mobile.</span></span>

1. <span data-ttu-id="a36ca-121">チャネルにコネクタを追加するには、チャネル名の右側にある省略記号 **(...)** をクリックし、[コネクタ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="a36ca-121">To add a connector to a channel, click the **ellipses (…),** on the right of a channel name, then click **Connectors**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a36ca-122">![[コネクタ] オプションTeamsインターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span><span class="sxs-lookup"><span data-stu-id="a36ca-122">![Screenshot of the Teams interface with the Connectors option selected.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)</span></span>

2. <span data-ttu-id="a36ca-123">さまざまな使用可能なコネクタから選択し、[追加] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="a36ca-123">You can select from a variety of available connectors, and then click **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a36ca-124">![使用可能なコネクタを示す [コネクタ] ダイアログのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span><span class="sxs-lookup"><span data-stu-id="a36ca-124">![Screenshot of the Connectors dialog showing available the connectors.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)</span></span>

3. <span data-ttu-id="a36ca-p107">選択したコネクタについて必須情報を入力し、[**保存**] をクリックします。各コネクタは、正常に機能するためにさまざまな必須情報を要求します。一部のコネクタでは、コネクタの構成ページに掲載されるリンクを使用してサービスにサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a36ca-p107">Fill in the required information of the selected connector and click **Save**. Each connector requires a diverse set of information to function properly, and some may require you to sign in to the service using the links provided on the connector configuration page.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a36ca-127">![RSS コネクタの [構成] ページのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span><span class="sxs-lookup"><span data-stu-id="a36ca-127">![Screenshot of the configuration page for the RSS connector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)</span></span>

4. <span data-ttu-id="a36ca-128">コネクタによって提供されるデータはチャネルに自動的に投稿されます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-128">Data provided by the connector is automatically posted to the channel.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a36ca-129">![チャネル内の会話を示す Teams インターフェイスのスクリーンショット。](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span><span class="sxs-lookup"><span data-stu-id="a36ca-129">![Screenshot of the Teams interface showing a conversation in a channel.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)</span></span>

<!---Delete this section after customer migration to new Webhook URL is complete--->
> [!IMPORTANT]
> <span data-ttu-id="a36ca-130">**コネクタ URL の更新通知**</span><span class="sxs-lookup"><span data-stu-id="a36ca-130">**Connector URL update notification**</span></span>
>
> <span data-ttu-id="a36ca-131">新Teams、セキュリティを強化するために新しい URL に移行しています。</span><span class="sxs-lookup"><span data-stu-id="a36ca-131">The Teams connectors are transitioning to a new URL to enhance security.</span></span> <span data-ttu-id="a36ca-132">この移行の過程で、新しい URL を使用するように構成されたコネクタを更新する特定の通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-132">During the course of this transition, you will receive certain notifications to update your configured connector to use the new URL.</span></span> <span data-ttu-id="a36ca-133">コネクタ サービスの中断を防ぐために、コネクタを直ちに更新強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="a36ca-133">It is strongly recommended that you update your connector immediately to prevent any disruption to connector services.</span></span> <span data-ttu-id="a36ca-134">URL を更新するには、次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a36ca-134">The following steps need to be followed to update the URL:</span></span>
> 1. <span data-ttu-id="a36ca-135">コネクタの構成ページで、更新する必要がある接続の [管理] ボタンの下に "注意が必要です" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-135">In the connectors configuration page, an "Attention Required" message will be displayed under the "Manage" button for the connections that need to be updated.</span></span>
> <span data-ttu-id="a36ca-136">!["要注意" メッセージのスクリーンショット。](media/Teams_Attention_Required_message.png)</span><span class="sxs-lookup"><span data-stu-id="a36ca-136">![Screenshot of the "Attention Required" message.](media/Teams_Attention_Required_message.png)</span></span>
> 2. <span data-ttu-id="a36ca-137">受信 webhook コネクタの場合、[URL の更新] を選択し、新しく生成された webhook URL を使用するだけで、接続を再作成できます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-137">For incoming webhook connectors, users can recreate the connection by simply selecting **Update URL** and using the newly generated webhook URL.</span></span>
> <span data-ttu-id="a36ca-138">![[URL の更新] ボタンのスクリーンショット。](media/Teams_update_URL_button.png)</span><span class="sxs-lookup"><span data-stu-id="a36ca-138">![Screenshot of the "Update URL" button.](media/Teams_update_URL_button.png)</span></span>
> 3. <span data-ttu-id="a36ca-139">他の種類のコネクタの場合、ユーザーはコネクタを削除し、コネクタの構成を再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a36ca-139">For other connector types, the user would need to remove the connector and recreate the connector configuration.</span></span>
> 4. <span data-ttu-id="a36ca-140">URL が正常に更新されると、"URL は最新の情報です" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-140">You will see a message "URL is up-to-date" after the URL has been successfully updated.</span></span>
> <span data-ttu-id="a36ca-141">!["URL is up-to-date" メッセージのスクリーンショット。](media/Teams_URL_up_to_date.png)</span><span class="sxs-lookup"><span data-stu-id="a36ca-141">![Screenshot of the "URL is up-to-date" message.](media/Teams_URL_up_to_date.png)</span></span>


## <a name="develop-custom-connectors"></a><span data-ttu-id="a36ca-142">カスタム コネクタを開発する</span><span class="sxs-lookup"><span data-stu-id="a36ca-142">Develop custom connectors</span></span>


<span data-ttu-id="a36ca-143">受信および送信 Webhook だけでなく、カスタム コネクタを構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="a36ca-143">You can also build custom connectors, as well as incoming and outgoing webhooks.</span></span> <span data-ttu-id="a36ca-144">詳細については、「[開発者向けドキュメント](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)」を参照してください:</span><span class="sxs-lookup"><span data-stu-id="a36ca-144">See our [developer documentation](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) for more information.</span></span>
