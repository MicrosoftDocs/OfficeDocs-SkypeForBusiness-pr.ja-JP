---
title: 共通領域電話のライセンスを設定する
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
description: 'ロビー、受付領域、会議室の共通領域電話を設定する方法について学習します。 '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117115"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="44f4e-103">Microsoft Teams での共通領域電話のライセンスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="44f4e-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="44f4e-104">一般的な地域の電話ではボイスメールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="44f4e-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="44f4e-105">一般的な地域の電話は、ロビーや、多くの人が通話できる別の場所に置かれるのが一般的です。たとえば、受付領域、ロビー、電話会議などです。</span><span class="sxs-lookup"><span data-stu-id="44f4e-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="44f4e-106">共通領域の電話は、共通領域の電話ライセンスに関連付られたアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="44f4e-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="44f4e-107">また、スマートフォンで共通の領域のユーザー エクスペリエンスを利用するには、TeamsIPPhone ポリシーも適切に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f4e-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="44f4e-108">以下の手順では、組織の共通領域の電話を展開する電話システムのアカウントを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="44f4e-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="44f4e-109">より完全な会議室エクスペリエンス (電話会議を含む) を行う場合は、会議室デバイスで専用の会議室ライセンスを購入する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="44f4e-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="44f4e-110">まず、共通領域電話 (CAP) ライセンスを購入し、認定された電話を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f4e-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="44f4e-111">認定された電話を検索して詳細を確認するには [、Microsoft Teams デバイスを参照してください](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="44f4e-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="44f4e-112">手順 1  - ライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="44f4e-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="44f4e-113">Microsoft 365 管理センターで、[課金 **購入サービス**] に移動し、[その他のプラン]  >  **を展開します**。</span><span class="sxs-lookup"><span data-stu-id="44f4e-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![[共通領域の電話] タイルを示すスクリーンショット](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="44f4e-115">[今すぐ **購入] を選択**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="44f4e-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="44f4e-116">[チェックアウト] ページで、[今すぐ購入 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="44f4e-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="44f4e-117">アドオン **サブスクリプションを展開し、** クリックして通話プランを購入します。</span><span class="sxs-lookup"><span data-stu-id="44f4e-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="44f4e-118">国内通話プラン **または国内通話プランと** 国際通話 **プランのいずれかを選択します**。</span><span class="sxs-lookup"><span data-stu-id="44f4e-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="44f4e-119">Microsoft 電話システム ダイレクト ルーティングを使用している場合は、通話プランのライセンスは必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="44f4e-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="44f4e-120">電話システム ライセンスを追加する必要はない。</span><span class="sxs-lookup"><span data-stu-id="44f4e-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="44f4e-121"> 共用エリア電話機  のライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="44f4e-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="44f4e-122">ライセンスの詳細については [、Microsoft Teams のアドオン ライセンスを参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="44f4e-122">For more information on licenses, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="44f4e-123">共通領域電話のライセンスでは、次の機能がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="44f4e-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="44f4e-124">共用エリア電話機</span><span class="sxs-lookup"><span data-stu-id="44f4e-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="44f4e-125">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="44f4e-125">Skype for Business</span></span> |   <span data-ttu-id="44f4e-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="44f4e-126">&#x2714;</span></span> |
|<span data-ttu-id="44f4e-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="44f4e-127">Microsoft Teams</span></span> |   <span data-ttu-id="44f4e-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="44f4e-128">&#x2714;</span></span> |
|<span data-ttu-id="44f4e-129">電話システム</span><span class="sxs-lookup"><span data-stu-id="44f4e-129">Phone System</span></span> |    <span data-ttu-id="44f4e-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="44f4e-130">&#x2714;</span></span> |
|<span data-ttu-id="44f4e-131">電話会議</span><span class="sxs-lookup"><span data-stu-id="44f4e-131">Audio Conferencing</span></span> |       <span data-ttu-id="44f4e-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="44f4e-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="44f4e-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="44f4e-133">Microsoft Intune</span></span> |    <span data-ttu-id="44f4e-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="44f4e-134">&#x2718;</span></span> |
|<span data-ttu-id="44f4e-135">世界的な可用性</span><span class="sxs-lookup"><span data-stu-id="44f4e-135">Worldwide Availability</span></span> |       <span data-ttu-id="44f4e-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="44f4e-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="44f4e-137">チャネルの可用性</span><span class="sxs-lookup"><span data-stu-id="44f4e-137">Channel Availability</span></span> |    <span data-ttu-id="44f4e-138">EA、EAS、CSP、GCC、EES、Web Direct</span><span class="sxs-lookup"><span data-stu-id="44f4e-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="44f4e-139">&sup1;共通領域電話は、会議開催者から提供されたダイヤルイン番号を使用して音声会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="44f4e-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="44f4e-140">&sup2; ソブリン クラウドでは使用不可</span><span class="sxs-lookup"><span data-stu-id="44f4e-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="44f4e-141">手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます</span><span class="sxs-lookup"><span data-stu-id="44f4e-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="44f4e-142">Microsoft 365 管理センターで、アクティブなユーザーがユーザーを追加  >    >  **するユーザーに移動します**。</span><span class="sxs-lookup"><span data-stu-id="44f4e-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="44f4e-143">名の場合は "メイン"、2 番目の名前には "受信" のようなユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="44f4e-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="44f4e-144">"メイン受付" のように自動生成しない場合は、表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="44f4e-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="44f4e-145">"MainReception" や "Mainlobby" のようなユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="44f4e-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="44f4e-146">一般的な地域の電話の場合は、手動でパスワードを設定するか、すべての一般的な地域の電話に同じパスワードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="44f4e-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="44f4e-147">また、[このユーザーが最初にサインインするときにパスワードを変更する] チェック ボックス **をオフにすることもできます** 。</span><span class="sxs-lookup"><span data-stu-id="44f4e-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="44f4e-148">ユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="44f4e-148">Assign the licenses to the user.</span></span> <span data-ttu-id="44f4e-149">同じページで、**[製品ライセンス]** をクリックして拡大してください。</span><span class="sxs-lookup"><span data-stu-id="44f4e-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="44f4e-150">Common Area Phone をオンにし、国内通話プランまたは国内通話プランと国際通話プラン **のいずれかを選択します**。</span><span class="sxs-lookup"><span data-stu-id="44f4e-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="44f4e-152">Microsoft 電話システム ダイレクト ルーティングを使用している場合は、通話プランのライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f4e-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="44f4e-153">詳細については、「ライセンスをユーザーに割り [当てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="44f4e-153">For more information, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="44f4e-154">手順 3  - 共用エリア電話機のユーザー アカウントに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="44f4e-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="44f4e-155">Teams 管理センターを使用して、ユーザーに番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="44f4e-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="44f4e-156">Teams 管理センターで、[音声電話番号 **] を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="44f4e-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="44f4e-157">電話番号のリストから番号を選択し、**[割り当て]**  をクリックします。</span><span class="sxs-lookup"><span data-stu-id="44f4e-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="44f4e-158">[割 **り当** て] ページの [音声ユーザー] ボックスに、電話を使用するユーザーの名前を入力し、[音声ユーザーの選択] ドロップダウン リストでユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="44f4e-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="44f4e-159">次に、緊急対応の住所を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44f4e-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="44f4e-160">ドロップダウン **リストから [\*\*\*\*市区町** 地で検索]、[説明で検索]、または [場所で検索] を選択し、テキスト ボックスに市区町町区町間、説明、または場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="44f4e-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="44f4e-161">検索が完了したら、[緊急対応の住所 **の選択]** の下で、適切な緊急対応の住所を選択します。</span><span class="sxs-lookup"><span data-stu-id="44f4e-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="44f4e-162">**[保存]** をクリックすると、ユーザーが以下のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f4e-162">Click **Save** and your user should look like this:</span></span>

   ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="44f4e-164">電話システム のライセンスが適用されている場合にのみ、ユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44f4e-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="44f4e-165">この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="44f4e-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="44f4e-166">詳細については、「ユーザーの [電話番号を取得する」を参照してください](getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="44f4e-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="44f4e-167">また、別の携帯電話会社で使用している電話番号を「ポート」したり、Microsoft 365 または Office 365 に転送したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="44f4e-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="44f4e-168">「 [電話番号を Teams に転送する」を参照してください](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="44f4e-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>