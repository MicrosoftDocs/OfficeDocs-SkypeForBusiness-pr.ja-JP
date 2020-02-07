---
title: Microsoft 365 ユーザーを作成し、Business Voice ライセンスを追加し、電話番号を割り当てる
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 851c661a2a75a3dfe82212b896041ddd2516c678
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824835"
---
# <a name="create-and-license-business-voice-users-and-assign-them-phone-numbers"></a><span data-ttu-id="afd8a-102">Business Voice ユーザーの作成と割り当てを行い、電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="afd8a-102">Create and license Business Voice users and assign them phone numbers</span></span>

<span data-ttu-id="afd8a-103">:::no-loc text="Microsoft 365 Business Voice"::: を使用するには、:::no-loc text="Microsoft 365 Business Voice with SMS"::: ライセンスを持つ :::no-loc text="Microsoft 365"::: アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="afd8a-103">To use :::no-loc text="Microsoft 365 Business Voice":::, you need a :::no-loc text="Microsoft 365"::: account that has a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license.</span></span> <span data-ttu-id="afd8a-104">ライセンスとアカウントを取得すると、そのアカウントに電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="afd8a-104">When you have an account and license, you can assign a phone number to it.</span></span>

## <a name="create-and-license-users"></a><span data-ttu-id="afd8a-105">ユーザーの作成とユーザーへのライセンスの割り当て</span><span class="sxs-lookup"><span data-stu-id="afd8a-105">Create and license users</span></span>

<span data-ttu-id="afd8a-106">「[:::no-loc text="Office 365"::: にユーザーを個別に、または一括して追加する](https://docs.microsoft.com/office365/admin/add-users/add-users)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="afd8a-106">Follow the steps in [Add users individually or in bulk to :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users).</span></span>

> [!NOTE]
> <span data-ttu-id="afd8a-107">**[製品ライセンスの割り当て]** ウィンドウで、**:::no-loc text="Microsoft 365 Business Voice with SMS":::** を選択します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-107">In the **Assign product licenses** pane,  select **:::no-loc text="Microsoft 365 Business Voice with SMS":::**.</span></span>

## <a name="assign-phone-numbers-to-users"></a><span data-ttu-id="afd8a-108">ユーザーに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="afd8a-108">Assign phone numbers to users</span></span>

<span data-ttu-id="afd8a-109">ユーザーの作成とユーザーへの :::no-loc text="Microsoft 365 Business Voice with SMS"::: ライセンスの割り当てが完了すると、ユーザーに電話番号を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="afd8a-109">After you create users and assigned them a :::no-loc text="Microsoft 365 Business Voice with SMS"::: license, you can assign phone numbers to them.</span></span> <span data-ttu-id="afd8a-110">外部電話番号に対し発信または受信する必要がある各ユーザーに、割り当てられていない電話番号が必要です。</span><span class="sxs-lookup"><span data-stu-id="afd8a-110">You need one unassigned phone number for each user that needs to make or receive calls to or from external phone numbers.</span></span> <span data-ttu-id="afd8a-111">未使用の電話番号が十分ない場合、この記事で後述する「[追加の電話番号を取得する](#get-more-phone-numbers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="afd8a-111">If you don't have enough unassigned phone numbers, see [Get more phone numbers](#get-more-phone-numbers) later in this article.</span></span>

1. <span data-ttu-id="afd8a-112">https://admin.teams.microsoft.com に移動します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-112">Go to https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="afd8a-113">電話番号の要求の名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-113">Enter a name and description for the phone number request.</span></span>
3. <span data-ttu-id="afd8a-114">**[音声]**  >  **[電話番号]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-114">Select **Voice** > **Phone numbers**.</span></span>
4. <span data-ttu-id="afd8a-115">ユーザーに割り当てる電話番号を選択し、次に **[編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-115">Select a phone number that you want to assign to a user, and then select **Edit**.</span></span>
5. <span data-ttu-id="afd8a-116">**[編集]** パネルで、その電話番号を割り当てるユーザーの名前を **[割り当て先]** に入力します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-116">In the **Edit** panel, enter the name of the user that you want to assign the number to in **Assigned to**.</span></span> <span data-ttu-id="afd8a-117">**[割り当て]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-117">Then select **Assign**.</span></span>
6. <span data-ttu-id="afd8a-118">**[緊急対応の場所]** に、ユーザーの所在地を入力し、**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-118">For **Emergency location**, enter the location where the user is located, and then select **Apply**</span></span>

## <a name="get-more-phone-numbers"></a><span data-ttu-id="afd8a-119">追加の電話番号を取得する</span><span class="sxs-lookup"><span data-stu-id="afd8a-119">Get more phone numbers</span></span>

<span data-ttu-id="afd8a-120">新しいユーザーに割り当てるための電話番号が十分にない場合は、追加の電話番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="afd8a-120">If you don't have enough phone numbers to assign to new users, you can get more.</span></span> <span data-ttu-id="afd8a-121">ご注文の番号が利用可能になるまでに最大 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="afd8a-121">It may take up to 24 hours for numbers that you order to become available.</span></span>

1. <span data-ttu-id="afd8a-122">https://admin.teams.microsoft.com に移動します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-122">Go to https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="afd8a-123">電話番号の要求の名前と説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-123">Enter a name and description for the phone number request.</span></span>
3. <span data-ttu-id="afd8a-124">**[音声]**  >  **[電話番号]**  >  **[追加]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-124">Select **Voice** > **Phone numbers** > **Add**.</span></span>
4. <span data-ttu-id="afd8a-125">電話番号の国または地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-125">Choose the country or region for the phone number.</span></span>
5. <span data-ttu-id="afd8a-126">**[番号の種類]** で、**[ユーザー (サブスクライバー)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-126">For **Number type**, select **User (subscriber)**.</span></span>
6. <span data-ttu-id="afd8a-127">**[場所]** では、ユーザーの場所を検索して選択します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-127">For **Location**, search for the location of the user and select it.</span></span> <span data-ttu-id="afd8a-128">また、**[場所の追加]** を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="afd8a-128">You can also choose to **Add a location**.</span></span>
7. <span data-ttu-id="afd8a-129">市外局番を選択し、必要な電話番号の数を入力し、**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-129">Choose an area code, enter the number of phone numbers that you need, and then select **Next**.</span></span>
8. <span data-ttu-id="afd8a-130">電話番号が予約されるのを待ってから、取得した番号を表示します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-130">Wait for the phone numbers to be reserved, and then view the numbers that you get.</span></span> <span data-ttu-id="afd8a-131">すべて正常であれば、**[発注]**、**[完了]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="afd8a-131">If everything looks ok, select **Place order** and then **Finish**.</span></span>
