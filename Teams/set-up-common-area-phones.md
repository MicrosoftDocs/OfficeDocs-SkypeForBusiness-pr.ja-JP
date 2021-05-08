---
title: 共通領域のライセンスを電話する
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
description: 'ロビー、受信エリア、会議室の共通領域電話を設定する方法について学習する '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117115"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="59344-103">Microsoft Teams での共通領域電話のライセンスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="59344-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="59344-104">一般的なエリアの電話ではボイスメールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="59344-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="59344-105">一般的なエリアの電話は、通常、ロビーや、多くのユーザーが通話を行える別のエリアに配置されます。たとえば、受信エリア、ロビー、電話会議などです。</span><span class="sxs-lookup"><span data-stu-id="59344-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="59344-106">共通領域の電話は、共通領域のライセンスに関連付電話されます。</span><span class="sxs-lookup"><span data-stu-id="59344-106">Common area phones are signed in with accounts tied to a Common Area Phone license.</span></span> <span data-ttu-id="59344-107">また、TeamsIPPhone ポリシーは、共通の領域のユーザー エクスペリエンスを持つ携帯電話に対して適切に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59344-107">The TeamsIPPhone policy must also be appropriately set for the phone to have a common area user experience.</span></span>

<span data-ttu-id="59344-108">以下の手順では、組織の共通エリア電話を展開電話システムアカウントを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="59344-108">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="59344-109">電話会議など、より完全な会議室エクスペリエンスを得る場合は、会議室デバイスで専用の会議室ミーティング ルームライセンスを購入してください。</span><span class="sxs-lookup"><span data-stu-id="59344-109">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="59344-110">まず、Common Area 電話 (CAP) ライセンスを購入し、認定された電話を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="59344-110">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="59344-111">認定された電話を検索して詳細を確認するには、デバイスのMicrosoft Teams[してください](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。</span><span class="sxs-lookup"><span data-stu-id="59344-111">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="59344-112">手順 1  - ライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="59344-112">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="59344-113">管理センター Microsoft 365、[課金購入サービス] に移動 **し**、[その他のプラン]  >  **を展開します**。</span><span class="sxs-lookup"><span data-stu-id="59344-113">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![[共通領域] タイルを電話スクリーンショット](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="59344-115">[共通 **領域] を選択電話**  >  **購入] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="59344-115">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="59344-116">[チェックアウト] ページで、[今すぐ購入 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="59344-116">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="59344-117">[ **アドオン サブスクリプション] を展開し** 、[通話プラン] をクリックして購入します。</span><span class="sxs-lookup"><span data-stu-id="59344-117">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="59344-118">[国内通話プラン **] または [** 国内通話プラン] または [ **国際通話プラン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="59344-118">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="59344-119">システム ダイレクト ルーティングMicrosoft 電話使用している場合は、通話プランライセンスは必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="59344-119">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="59344-120">ライセンスを追加する必要電話システム。</span><span class="sxs-lookup"><span data-stu-id="59344-120">You don't need to add a Phone System license.</span></span> <span data-ttu-id="59344-121"> 共用エリア電話機  のライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="59344-121">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="59344-122">ライセンスの詳細については、「Microsoft Teams[ライセンス」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="59344-122">For more information on licenses, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="59344-123">共通領域ライセンスでは電話サポートされます。</span><span class="sxs-lookup"><span data-stu-id="59344-123">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="59344-124">共用エリア電話機</span><span class="sxs-lookup"><span data-stu-id="59344-124">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="59344-125">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="59344-125">Skype for Business</span></span> |   <span data-ttu-id="59344-126">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="59344-126">&#x2714;</span></span> |
|<span data-ttu-id="59344-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="59344-127">Microsoft Teams</span></span> |   <span data-ttu-id="59344-128">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="59344-128">&#x2714;</span></span> |
|<span data-ttu-id="59344-129">電話システム</span><span class="sxs-lookup"><span data-stu-id="59344-129">Phone System</span></span> |    <span data-ttu-id="59344-130">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="59344-130">&#x2714;</span></span> |
|<span data-ttu-id="59344-131">電話会議</span><span class="sxs-lookup"><span data-stu-id="59344-131">Audio Conferencing</span></span> |       <span data-ttu-id="59344-132">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="59344-132">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="59344-133">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="59344-133">Microsoft Intune</span></span> |    <span data-ttu-id="59344-134">&#x2718;</span><span class="sxs-lookup"><span data-stu-id="59344-134">&#x2718;</span></span> |
|<span data-ttu-id="59344-135">世界的な可用性</span><span class="sxs-lookup"><span data-stu-id="59344-135">Worldwide Availability</span></span> |       <span data-ttu-id="59344-136">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="59344-136">&#x2718; &sup2;</span></span>  |
|<span data-ttu-id="59344-137">チャネルの可用性</span><span class="sxs-lookup"><span data-stu-id="59344-137">Channel Availability</span></span> |    <span data-ttu-id="59344-138">EA、EAS、CSP、GCC、EES、Web Direct</span><span class="sxs-lookup"><span data-stu-id="59344-138">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="59344-139">&sup1;共通領域電話は、会議開催者から提供されたダイヤルイン番号を介して音声会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="59344-139">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="59344-140">&sup2; ソブリン クラウドでは使用不可</span><span class="sxs-lookup"><span data-stu-id="59344-140">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="59344-141">手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます</span><span class="sxs-lookup"><span data-stu-id="59344-141">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="59344-142">管理センター Microsoft 365、アクティブなユーザーに **ユーザーを追加**  >    >  **するに移動します**。</span><span class="sxs-lookup"><span data-stu-id="59344-142">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="59344-143">名には "Main" のようなユーザー名を入力し、2 番目の名前には "受信" を入力します。</span><span class="sxs-lookup"><span data-stu-id="59344-143">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="59344-144">"メイン の受信" のように自動生成しない場合は、表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="59344-144">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="59344-145">"MainReception" や "Mainlobby" のようなユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="59344-145">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="59344-146">一般的な地域の電話の場合は、パスワードを手動で設定するか、すべての共通領域の電話に同じパスワードを設定できます。</span><span class="sxs-lookup"><span data-stu-id="59344-146">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="59344-147">また、[このユーザーが初めてサインインするときにパスワードを変更する] チェック ボックスをオフ **にすることもできます** 。</span><span class="sxs-lookup"><span data-stu-id="59344-147">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="59344-148">ライセンスをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="59344-148">Assign the licenses to the user.</span></span> <span data-ttu-id="59344-149">同じページで、**[製品ライセンス]** をクリックして拡大してください。</span><span class="sxs-lookup"><span data-stu-id="59344-149">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="59344-150">[共通エリア] をオン電話国内通話プランまたは国内通話プランと国際通話プラン **のいずれかを選択します**。</span><span class="sxs-lookup"><span data-stu-id="59344-150">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="59344-152">システム ダイレクト ルーティングMicrosoft 電話使用している場合は、通話プランライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="59344-152">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="59344-153">詳細については、「ユーザーにライセンスを [割り当てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="59344-153">For more information, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="59344-154">手順 3  - 共用エリア電話機のユーザー アカウントに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="59344-154">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="59344-155">管理センター Teamsを使用して、ユーザーに番号を割り当てる。</span><span class="sxs-lookup"><span data-stu-id="59344-155">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="59344-156">[Teams 管理センターで、[Voice 電話  >  **numbers] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="59344-156">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="59344-157">電話番号のリストから番号を選択し、**[割り当て]**  をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59344-157">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="59344-158">[割 **り** 当て] ページの [音声ユーザー] ボックスに、電話を使用するユーザーの名前を入力し、[音声ユーザーの選択] ドロップダウン リストでユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="59344-158">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="59344-159">次に、緊急対応の住所を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="59344-159">Next, you need to add an emergency address.</span></span> <span data-ttu-id="59344-160">ドロップダウン **リストから [市\*\*\*\*区町** 町地で検索]、説明で検索、または [場所で検索] を選択し、テキスト ボックスに都市、説明、または場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="59344-160">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="59344-161">検索したら、[緊急対応の住所 **の選択] を見** て、適切な住所を選択します。</span><span class="sxs-lookup"><span data-stu-id="59344-161">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="59344-162">**[保存]** をクリックすると、ユーザーが以下のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="59344-162">Click **Save** and your user should look like this:</span></span>

   ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="59344-164">ユーザーは、ライセンスが適用されている場合電話システム表示されます。</span><span class="sxs-lookup"><span data-stu-id="59344-164">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="59344-165">この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="59344-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="59344-166">詳細については、「ユーザーの [電話番号を取得する」を参照してください](getting-phone-numbers-for-your-users.md)。</span><span class="sxs-lookup"><span data-stu-id="59344-166">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="59344-167">また、別の携帯電話会社と一緒に持っている電話番号を受け取り、"ポート" したり、携帯電話や携帯電話にMicrosoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="59344-167">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="59344-168">「[電話番号を電話番号に転送する」をTeams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="59344-168">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>