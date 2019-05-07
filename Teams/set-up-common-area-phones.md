---
title: Microsoft Teams での共通領域電話のライセンスをセットアップする
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'ロビー、受付、および会議室の共通領域電話を設定する方法を学習します。 '
ms.openlocfilehash: 9e68d5bc4ef0355e80e1fe6359385c10a339c0fe
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632378"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="3a63d-103">Microsoft Teams での共通領域電話のライセンスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="3a63d-103">Set up the Common Area Phone license for Microsoft Teams</span></span>

<span data-ttu-id="3a63d-104">共通領域電話は通常、ロビーのような領域、またはをかけるには多くの人々 に利用できる別の領域に配置しています。たとえば、受信エリア、ロビー、または会議電話します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-104">A common area phone is typically placed in an area like a lobby or another area which is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="3a63d-105">共通領域電話は、ユーザーではなくデバイスとして設定して、ネットワークに自動的に署名できます。</span><span class="sxs-lookup"><span data-stu-id="3a63d-105">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="3a63d-106">以下の手順でお手伝いの組織の共通領域電話を展開する電話システムのアカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-106">In the steps below, we’ll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="3a63d-107">包括的な会議室の経験、音声会議を含む会議では、専用の会議室ライセンスの購入を検討してくださいルーム デバイスです。</span><span class="sxs-lookup"><span data-stu-id="3a63d-107">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="3a63d-108">最初に作業を実行する必要がありますは、共通領域電話 (CAP) のライセンスを購入には、認定の電話があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-108">The first things you need to do are purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="3a63d-109">検索し、認定された電話の詳細についてには、[マイクロソフトのチームのデバイス](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)に移動します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-109">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="3a63d-110">手順 1  - ライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="3a63d-110">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="3a63d-111">Microsoft 365 管理センターでは、**請求先**に移動 > **購買サービス**し、**他の計画**を展開します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-111">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![共通領域電話を示すスクリーン ショットを並べて表示します。](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="3a63d-113">**共通領域電話**を選択して > **今すぐ購入**します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-113">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="3a63d-114">[**チェック アウト**] ページで、**今すぐ購入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a63d-114">On the **Checkout** page click **Buy now**.</span></span>

4. <span data-ttu-id="3a63d-115">**アドオンのサブスクリプション**を展開し、呼び出す計画を購入する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a63d-115">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="3a63d-116">**国内計画を呼び出す**か、**国内または国際通話プラン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-116">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="3a63d-117">電話システムのライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3a63d-117">You don't need a Phone System license.</span></span> <span data-ttu-id="3a63d-118"> 共用エリア電話機  のライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a63d-118">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="3a63d-119">ライセンスの詳細については、[マイクロソフトのチームのアドオンのライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a63d-119">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="3a63d-120">手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます</span><span class="sxs-lookup"><span data-stu-id="3a63d-120">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="3a63d-121">Microsoft 365 管理センターでは、**ユーザー**に移動 > **アクティブなユーザー** > **ユーザーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-121">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="3a63d-122">ユーザー名"Main"のように [名] および [受信] の 2 番目の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-122">Enter a user name like “Main" for the first name and "Reception” for the second name.</span></span>

3. <span data-ttu-id="3a63d-123">「メインの受信」のような 1 つを自動生成していない場合は、表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-123">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="3a63d-124">"MainReception"または"Mainlobby です"のようにユーザー名を入力してください。</span><span class="sxs-lookup"><span data-stu-id="3a63d-124">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="3a63d-125">共通領域電話のパスワードを手動で設定するか、すべての共通領域電話に対して同じパスワードを入力する場合。</span><span class="sxs-lookup"><span data-stu-id="3a63d-125">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="3a63d-126">また、**このユーザーが最初にサインインするときにパスワードを変更する**] チェック ボックスをオフにする考えてください。</span><span class="sxs-lookup"><span data-stu-id="3a63d-126">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="3a63d-127">ユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3a63d-127">Assign the licenses to the user.</span></span> <span data-ttu-id="3a63d-128">同じページで、**[製品ライセンス]** をクリックして拡大してください。</span><span class="sxs-lookup"><span data-stu-id="3a63d-128">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="3a63d-129">共通領域電話をオンにし、**国内の計画を呼び出す**か**国内および国際を呼び出す計画**を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-129">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![スクリーン ショットの表示されているライセンスの割り当て](media/set-up-common-area-phone-image2.png)

<span data-ttu-id="3a63d-131">詳細については、[ユーザーの追加](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a63d-131">For more information, see [Add a user](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="3a63d-132">手順 3  - 共用エリア電話機のユーザー アカウントに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="3a63d-132">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="3a63d-133">番号をユーザーに割り当てるには、ビジネス管理センターの Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-133">Use the Skype for Business admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="3a63d-134">Microsoft 365 管理センターの**管理センター**を選択して > **チーム & Skype** > **従来のポータル**です。</span><span class="sxs-lookup"><span data-stu-id="3a63d-134">In the Microsoft 365 admin center, select **Admin centers** > **Teams & Skype** > **Legacy portal**.</span></span>

2. <span data-ttu-id="3a63d-135">ビジネス管理センターの Skype での**音声**を選択して > **の電話番号**です。</span><span class="sxs-lookup"><span data-stu-id="3a63d-135">In the Skype for Business admin center, select **Voice** > **Phone numbers**.</span></span>

3.  <span data-ttu-id="3a63d-136">電話番号のリストから番号を選択し、\*\* [割り当て]\*\*  をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a63d-136">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="3a63d-137">[**割り当てる**] ページで、音声ユーザー ボックスで、**音声ユーザーを選択**」ドロップ ダウン リストで、電話番号、し、ユーザーを選択に使用したユーザーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-137">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="3a63d-138">この作業の間に、緊急アドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a63d-138">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="3a63d-139">」ドロップ ダウン リストから、**市区町村別の検索\*\*\*\*の説明で検索**、または**別の場所の検索**を選択し、テキスト ボックスに、市区町村、説明、または場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-139">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="3a63d-140">検索すると後、は、[**緊急時のアドレスを選択**するにふさわしいものを選択するのには確認します。</span><span class="sxs-lookup"><span data-stu-id="3a63d-140">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="3a63d-141">**[保存]** をクリックすると、ユーザーが以下のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a63d-141">Click **Save** and your user should look like this:</span></span>

   ![スクリーン ショットの表示されているライセンスの割り当て](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="3a63d-143">ユーザーのみが表示されます適用電話システムのライセンスがあるかどうか。</span><span class="sxs-lookup"><span data-stu-id="3a63d-143">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="3a63d-144">この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="3a63d-144">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="3a63d-145">詳細については、[ユーザーの電話番号の取得](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a63d-145">For more information, see [Getting phone numbers for your users](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).</span></span>

<span data-ttu-id="3a63d-146">別のキャリアと「ポート」を持っているか、Office 365 に転送する電話番号を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a63d-146">You can also take your phone number that you have with another carrier and "port" or transfer it over to Office 365.</span></span> <span data-ttu-id="3a63d-147">[Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a63d-147">See [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


