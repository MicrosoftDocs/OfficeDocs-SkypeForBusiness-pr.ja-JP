---
title: 共通領域電話のライセンスをセットアップする
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: 'ロビー、受付エリア、会議室に共通領域電話を設定する方法について説明します '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117115"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="bbb21-103">Microsoft Teams での共通領域電話のライセンスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="bbb21-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="bbb21-104">共通領域電話はボイスメールをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="bbb21-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="bbb21-105">通常、共通領域電話はロビーなどのエリアや、多くの人が通話できる別のエリアに配置されます。たとえば、受付エリア、ロビー、会議電話などです。</span><span class="sxs-lookup"><span data-stu-id="bbb21-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="bbb21-106">共通領域電話は、共通領域電話ライセンスに関連付けられているアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="bbb21-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="bbb21-107">また、電話が共通領域のユーザー エクスペリエンスを提供できるように適切に TeamsIPPhone ポリシーが設定されている必要もあります。</span><span class="sxs-lookup"><span data-stu-id="bbb21-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="bbb21-108">以下の手順では、組織の共通領域電話を展開するための電話システムのアカウントを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="bbb21-109">電話会議を含む、より完全な会議室エクスペリエンスを実現するには、会議室デバイスで専用のミーティング ルーム ライセンスのご購入を検討してください。</span><span class="sxs-lookup"><span data-stu-id="bbb21-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="bbb21-110">まず、共通領域電話 (CAP) のライセンスを購入し、認定された電話があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbb21-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="bbb21-111">認定された電話の検索方法、および詳細情報を確認するには、[Microsoft Teams デバイス](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="bbb21-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="bbb21-112">手順 1 - ライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="bbb21-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="bbb21-113">Microsoft 365 管理センターで、[**課金情報**]  >  [**サービスの購入**] と進み、[**他のプラン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![[共通領域電話] のタイルを示すスクリーンショット](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="bbb21-115">[**共通領域電話**]  >  [**今すぐ購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="bbb21-116">[チェックアウト] ページで、[**今すぐ購入**] クリックします。</span><span class="sxs-lookup"><span data-stu-id="bbb21-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="bbb21-117">**アドオン サブスクリプション** を展開し、クリックして通話プランを購入します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="bbb21-118">[**国内通話プラン**] または [**国内および国際通話プラン**] のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="bbb21-119">Microsoft 電話システム ダイレクト ルーティングを使用している場合は、通話プランのライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bbb21-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="bbb21-120">電話システムのライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bbb21-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="bbb21-121">共通領域電話のライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="bbb21-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="bbb21-122">ライセンスの詳細については、「[Microsoft Teams のアドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbb21-122">For more information on licenses, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="bbb21-123">共通領域電話のライセンスは以下をサポートしています:</span><span class="sxs-lookup"><span data-stu-id="bbb21-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="bbb21-124">共通領域電話</span><span class="sxs-lookup"><span data-stu-id="bbb21-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="bbb21-125">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="bbb21-125">Skype for Business</span></span> |   <span data-ttu-id="bbb21-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="bbb21-126">&#x2714;</span></span> |
|<span data-ttu-id="bbb21-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bbb21-127">Microsoft Teams</span></span> |   <span data-ttu-id="bbb21-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="bbb21-128">&#x2714;</span></span> |
|<span data-ttu-id="bbb21-129">電話システム</span><span class="sxs-lookup"><span data-stu-id="bbb21-129">Phone System</span></span> |    <span data-ttu-id="bbb21-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="bbb21-130">&#x2714;</span></span> |
|<span data-ttu-id="bbb21-131">電話会議</span><span class="sxs-lookup"><span data-stu-id="bbb21-131">Audio Conferencing</span></span> |       <span data-ttu-id="bbb21-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="bbb21-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="bbb21-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bbb21-133">Microsoft Intune</span></span> |    <span data-ttu-id="bbb21-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="bbb21-134">&#x2718;</span></span> |
|<span data-ttu-id="bbb21-135">世界的な可用性</span><span class="sxs-lookup"><span data-stu-id="bbb21-135">Worldwide Availability</span></span> |       <span data-ttu-id="bbb21-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="bbb21-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="bbb21-137">チャネルの可用性</span><span class="sxs-lookup"><span data-stu-id="bbb21-137">Channel Availability</span></span> |    <span data-ttu-id="bbb21-138">EA、EAS、CSP、GCC、EES、Web Direct</span><span class="sxs-lookup"><span data-stu-id="bbb21-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="bbb21-139">&sup1;共通領域電話は、会議開催者が提供するダイヤルイン番号を使用して音声会議に参加できます</span><span class="sxs-lookup"><span data-stu-id="bbb21-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="bbb21-140">&sup2; ソブリン クラウドでは使用できません</span><span class="sxs-lookup"><span data-stu-id="bbb21-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="bbb21-141">手順 2 - 電話機の新しいユーザ アカウントを作成し、ライセンスを割り当てます</span><span class="sxs-lookup"><span data-stu-id="bbb21-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="bbb21-142">Microsoft 365 管理センターで、[**ユーザー**]  >  [**アクティブ ユーザー**]  >  [**ユーザーの追加**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="bbb21-143">名に "メイン" のようなユーザー名を入力し、姓に "受け付け" と入力します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="bbb21-144">"受け付け メイン" のように自動生成されない場合は、表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="bbb21-145">"MainReception" や "Mainlobby" などのユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="bbb21-146">共通領域電話では、パスワードを手動で設定するか、すべての共電話機に対して同じパスワードを設定した方がよい場合があります。</span><span class="sxs-lookup"><span data-stu-id="bbb21-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="bbb21-147">また、[**ユーザーが初回サインイン時にパスワードを変更する**] のチェック ボックスをオフにしてもよいでしょう。</span><span class="sxs-lookup"><span data-stu-id="bbb21-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="bbb21-148">ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="bbb21-148">Assign the licenses to the user.</span></span> <span data-ttu-id="bbb21-149">同じページで、**[製品ライセンス]** をクリックして展開してください。</span><span class="sxs-lookup"><span data-stu-id="bbb21-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="bbb21-150">共通領域電話の電源を入れ、 **国内通話プラン** または **国内および国際通話プラン** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="bbb21-152">Microsoft 電話システム ダイレクト ルーティングを使用している場合は、通話プランのライセンスを割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bbb21-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="bbb21-153">詳細については、「[ユーザーにライセンスを割り当てる](/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbb21-153">For more information, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="bbb21-154">手順 3 - 共通エリア電話機のユーザー アカウントに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="bbb21-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="bbb21-155">Teams 管理センターを使用して、ユーザーに番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="bbb21-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="bbb21-156">Teams 管理センターで、[**音声**]  >  [**電話番号**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="bbb21-157">電話番号のリストから番号を選択し、[**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bbb21-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="bbb21-158">[**割り当て**] ページで、[音声ユーザー] ボックスに、電話を使用するユーザーの名前を入力し、[**音声ユーザーの選択**] のドロップダウン リストでユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="bbb21-159">次に、緊急アドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbb21-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="bbb21-160">[**都市で検索**]、[**説明で検索**]、またはドロップダウン リストから [**場所で検索**] をし、テキスト ボックスに都市、説明、または場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="bbb21-161">検索したら、 [**緊急住所の選択**] の下を見て、適切な住所を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbb21-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="bbb21-162">[**保存**] をクリックすると、ユーザーが以下のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="bbb21-162">Click **Save** and your user should look like this:</span></span>

   ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="bbb21-164">電話システム ライセンスが適用さている場合のみ、ユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bbb21-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="bbb21-165">この操作を実行したばかりだと、ユーザーがリストに表示されるまでに少し時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="bbb21-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="bbb21-166">詳細については、「[ユーザーの電話番号を取得する](getting-phone-numbers-for-your-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbb21-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="bbb21-167">迷っている場合は、別のキャリアや "ポート " で持っている電話番号を使用するか、それらを Microsoft 365 から Office 365 へ転送することもできます。</span><span class="sxs-lookup"><span data-stu-id="bbb21-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="bbb21-168">「[Teamsに電話番号を転送する](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbb21-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>