---
title: Microsoft 365 ユーザーを作成し、Business Voice ライセンスを追加し、電話番号を割り当てる
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb8277c11cbcc459da9da8fd8d4f5b9c329470f3
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269283"
---
# <a name="create-and-license-business-voice-users-and-assign-them-phone-numbers"></a><span data-ttu-id="9f9b3-102">Business Voice ユーザーの作成と割り当てを行い、電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="9f9b3-102">Create and license users and assign phone numbers to them</span></span>

<span data-ttu-id="9f9b3-103">:::no-loc text="Microsoft 365 Business Voice"::: を使用するには、:::no-loc text="Microsoft 365 Business Voice with SMS"::: ライセンスを持つ :::no-loc text="Microsoft 365"::: アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-103">To use :::no-loc text="Microsoft 365 Business Voice":::, you need a :::no-loc text="Microsoft 365"::: account that has a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license.</span></span> <span data-ttu-id="9f9b3-104">ライセンスとアカウントを取得すると、そのアカウントに電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-104">When you have an account and license, you can assign a phone number to it.</span></span>

## <a name="create-and-license-users"></a><span data-ttu-id="9f9b3-105">ユーザーの作成とユーザーへのライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="9f9b3-105">Create and license users</span></span>

<span data-ttu-id="9f9b3-106">「[:::no-loc text="Office 365"::: にユーザーを個別に、または一括して追加する](https://docs.microsoft.com/office365/admin/add-users/add-users)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-106">Follow the steps in [Add users individually or in bulk to :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users) to add one or more users.</span></span>

> [!NOTE]
> <span data-ttu-id="9f9b3-107">**[製品ライセンスの割り当て]** ウィンドウで、**:::no-loc text="Microsoft 365 Business Voice with SMS":::** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-107">In the **Assign product licenses** pane, be sure to select **:::no-loc text="Microsoft 365 Business Voice with SMS":::**.</span></span>

## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="9f9b3-108">ユーザーに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="9f9b3-108">Assign phone numbers to users</span></span>

<span data-ttu-id="9f9b3-109">ユーザーの作成とユーザーへの :::no-loc text="Microsoft 365 Business Voice with SMS"::: ライセンスの割り当てが完了すると、ユーザーに電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-109">After users have been created and assigned a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license, you can assign phone numbers to them.</span></span> <span data-ttu-id="9f9b3-110">外部電話番号に対し発信または受信する必要がある各ユーザーに、割り当てられていない電話番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-110">You need one unassigned phone number for each user that needs to make or receive calls to or from external phone numbers.</span></span> <span data-ttu-id="9f9b3-111">未使用の電話番号が十分ない場合、この記事で後述する「[追加の電話番号を取得する](#get-more-phone-numbers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-111">If you don't have enough unassigned phone numbers, see [Get more phone numbers](#get-more-phone-numbers) later in this article.</span></span>

1. <span data-ttu-id="9f9b3-112">https://admin.teams.microsoft.com に移動します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-112">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="9f9b3-113">電話番号の要求の名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-113">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="9f9b3-114">**[音声]**  >  **[電話番号]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-114">Select **Voice** > **Phone numbers**</span></span>
4. <span data-ttu-id="9f9b3-115">ユーザーに割り当てる電話番号を選択し、次に **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-115">Select a phone number you want to assign to a user and select **Edit**</span></span>
5. <span data-ttu-id="9f9b3-116">**[編集]** パネルで、その電話番号を割り当てるユーザーの名前を **[割り当て先]** に入力します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-116">In the **Edit** panel, enter the name of the user you want to assign the number to in **Assigned to** and select Assign</span></span> <span data-ttu-id="9f9b3-117">**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-117">Then select **Assign**.</span></span>
6. <span data-ttu-id="9f9b3-118">**[緊急対応の場所]** に、ユーザーの所在地を入力し、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-118">In **Emergency location**, enter the location where the user is located, and then select **Apply**</span></span>

## <a name="get-more-phone-numbers"></a><span data-ttu-id="9f9b3-119">追加の電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="9f9b3-119">Get more phone numbers</span></span>

<span data-ttu-id="9f9b3-120">新しいユーザーに割り当てるための電話番号が十分にない場合は、追加の電話番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-120">If you don't have enough phone numbers to assign to new users, you can get more.</span></span> <span data-ttu-id="9f9b3-121">ご注文の番号が利用可能になるまでに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-121">It may take up to 24 hours for numbers that you order to become available.</span></span>

1. <span data-ttu-id="9f9b3-122">https://admin.teams.microsoft.com に移動します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-122">Go to https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="9f9b3-123">電話番号の要求の名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-123">Enter a name and description for the phone number request</span></span>
3. <span data-ttu-id="9f9b3-124">**[音声]**  >  **[電話番号]**  >  **[追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-124">Select **Voice** > **Phone numbers** > **Add**.</span></span>
4. <span data-ttu-id="9f9b3-125">電話番号の国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-125">Choose the country or region where the phone number should be created</span></span>
5. <span data-ttu-id="9f9b3-126">**[番号の種類]** で、**[ユーザー (サブスクライバー)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-126">In **Number type**, select **User (subscriber)**</span></span>
6. <span data-ttu-id="9f9b3-127">**[場所]** では、ユーザーの場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-127">In **Location**, search for the location of the user and select it.</span></span> <span data-ttu-id="9f9b3-128">また、**[場所の追加]** を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-128">You can also choose to **Add a location**.</span></span>
7. <span data-ttu-id="9f9b3-129">市外局番を選択し、必要な電話番号の数を入力し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-129">Choose an area code, enter the number of phone numbers to get, and then click **Next**</span></span>
8. <span data-ttu-id="9f9b3-130">電話番号が予約されるのを待ってから、取得した番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-130">Wait for the phone numbers to be reserved, and then view the numbers that you get.</span></span> <span data-ttu-id="9f9b3-131">すべて正常であれば、**[発注]**、**[完了]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="9f9b3-131">If everything looks ok, select **Place order** and then **Finish**.</span></span>
