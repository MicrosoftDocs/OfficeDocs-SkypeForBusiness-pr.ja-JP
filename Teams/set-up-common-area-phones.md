---
title: 共通の市外局番のライセンスを設定する
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
description: 'ロビー、受付領域、会議室の一般的なエリア電話を設定する方法について説明します。 '
ms.openlocfilehash: ef75c23ff72d9b640fb5a53feff7cf46fec43292
ms.sourcegitcommit: 2cc36c954200f50de33b909856b33fe0a9a6b7a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45125990"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a><span data-ttu-id="ba77c-103">Microsoft Teams での共通領域電話のライセンスをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ba77c-103">Set up the Common Area Phone license for Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="ba77c-104">一般的なエリア電話ではボイスメールはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ba77c-104">Common area phones do not support voicemail.</span></span>

<span data-ttu-id="ba77c-105">通常、一般的なエリアの電話は、ロビーや、多くの参加者が通話を発信するために利用できる別の領域に配置されます。たとえば、受付領域、ロビー、会議電話などです。</span><span class="sxs-lookup"><span data-stu-id="ba77c-105">A common area phone is typically placed in an area like a lobby or another area that is available to many people to make a call; for example, a reception area, lobby, or conference phone.</span></span> <span data-ttu-id="ba77c-106">一般的なエリア携帯電話は、ユーザーではなくデバイスとして設定されるため、ネットワークに自動的にサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="ba77c-106">Common area phones are set up as devices rather than users, and can automatically sign into a network.</span></span>

<span data-ttu-id="ba77c-107">以下の手順では、組織の一般的なエリア電話を展開するために電話システムのアカウントをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-107">In the steps below, we'll help you set up an account for Phone System to deploy common area phones for your organization.</span></span> <span data-ttu-id="ba77c-108">電話会議など、会議室の完全なエクスペリエンスを実現するには、会議室のデバイスを使用して、専用の会議室ライセンスを購入することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="ba77c-108">For a more complete meeting room experience, including audio conferencing, consider purchasing the dedicated Meeting Room license with a meeting room device.</span></span> 

<span data-ttu-id="ba77c-109">まず、一般的なエリア電話 (CAP) ライセンスを購入し、認定された電話があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba77c-109">First, you need to purchase a Common Area Phone (CAP) license and make sure that you have a certified phone.</span></span> <span data-ttu-id="ba77c-110">認定された電話の検索および詳細については、「 [Microsoft Teams デバイス](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba77c-110">To search for and learn more about certified phones, go to [Microsoft Teams devices](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).</span></span> 

## <a name="step-1---buy-the-licenses"></a><span data-ttu-id="ba77c-111">手順 1  - ライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="ba77c-111">Step 1 - Buy the licenses</span></span>

1. <span data-ttu-id="ba77c-112">Microsoft 365 管理センターで、[**課金**サービス] に移動し、  >  **Purchase services** [**その他のプラン**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-112">In the Microsoft 365 admin center, go to **Billing** > **Purchase services** and then expand **Other plans**.</span></span>

    ![一般的なエリア電話のタイルを示すスクリーンショット](media/set-up-common-area-phone-image1.png)

2. <span data-ttu-id="ba77c-114">[**一般的な市外局番**を  >  **今すぐ購入**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-114">Select **Common Area Phone** > **Buy now**.</span></span>

3. <span data-ttu-id="ba77c-115">[チェックアウト] ページで、[**今すぐ購入**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba77c-115">On the Checkout page, click **Buy now**.</span></span>

4. <span data-ttu-id="ba77c-116">**アドオンサブスクリプション**を展開し、をクリックして通話プランを購入します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-116">Expand **Add-on subscriptions** and then click to buy a Calling Plan.</span></span> <span data-ttu-id="ba77c-117">**国内通話プラン**または**国内および国際通話プラン**のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-117">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!NOTE]
> <span data-ttu-id="ba77c-118">Microsoft Phone システムのダイレクトルーティングを使用している場合は、通話プランのライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ba77c-118">If you are using Microsoft Phone System Direct Routing, you do not need a Calling Plan license.</span></span>

> [!NOTE]
> <span data-ttu-id="ba77c-119">電話システムのライセンスを追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ba77c-119">You don't need to add a Phone System license.</span></span> <span data-ttu-id="ba77c-120"> 共用エリア電話機  のライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ba77c-120">It's included with the Common Area Phone license.</span></span>

<span data-ttu-id="ba77c-121">ライセンスの詳細については、「 [Microsoft Teams のアドオンライセンス](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba77c-121">For more information on licenses, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

<span data-ttu-id="ba77c-122">一般的な市外局番のライセンスは次の機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ba77c-122">The Common Area Phone license supports:</span></span> 


|   |  <span data-ttu-id="ba77c-123">共用エリア電話機</span><span class="sxs-lookup"><span data-stu-id="ba77c-123">Common Area Phone</span></span>  |
|---------|---------|
|<span data-ttu-id="ba77c-124">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ba77c-124">Skype for Business</span></span> |   <span data-ttu-id="ba77c-125">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="ba77c-125">&#x2714;</span></span> |
|<span data-ttu-id="ba77c-126">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ba77c-126">Microsoft Teams</span></span> |   <span data-ttu-id="ba77c-127">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="ba77c-127">&#x2714;</span></span> |
|<span data-ttu-id="ba77c-128">電話システム</span><span class="sxs-lookup"><span data-stu-id="ba77c-128">Phone System</span></span> |    <span data-ttu-id="ba77c-129">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="ba77c-129">&#x2714;</span></span> |
|<span data-ttu-id="ba77c-130">電話会議</span><span class="sxs-lookup"><span data-stu-id="ba77c-130">Audio Conferencing</span></span> |       <span data-ttu-id="ba77c-131">&#x2718; &sup1;</span><span class="sxs-lookup"><span data-stu-id="ba77c-131">&#x2718; &sup1;</span></span>  |
|<span data-ttu-id="ba77c-132">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ba77c-132">Microsoft Intune</span></span> |        <span data-ttu-id="ba77c-133">&#x2718; &sup2;</span><span class="sxs-lookup"><span data-stu-id="ba77c-133">&#x2718; &sup2;</span></span> |
|<span data-ttu-id="ba77c-134">世界的な可用性</span><span class="sxs-lookup"><span data-stu-id="ba77c-134">Worldwide Availability</span></span> |    <span data-ttu-id="ba77c-135">&#x2714;</span><span class="sxs-lookup"><span data-stu-id="ba77c-135">&#x2714;</span></span> |
|<span data-ttu-id="ba77c-136">チャネルの可用性</span><span class="sxs-lookup"><span data-stu-id="ba77c-136">Channel Availability</span></span> |    <span data-ttu-id="ba77c-137">EA、EAS、CSP、GCC、EES、Web ダイレクト</span><span class="sxs-lookup"><span data-stu-id="ba77c-137">EA, EAS, CSP, GCC, EES, Web Direct</span></span>  |
|      |         |

<span data-ttu-id="ba77c-138">&sup1;一般的なエリア電話では、会議の開催者によって提供されるダイヤルイン番号を使用して、音声会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="ba77c-138">&sup1; Common Area Phones can join audio conferences via dial-in number provided by the meeting organizer</span></span>

<span data-ttu-id="ba77c-139">&sup2; ソブリン クラウドでは使用不可</span><span class="sxs-lookup"><span data-stu-id="ba77c-139">&sup2; Not available in sovereign clouds</span></span>  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="ba77c-140">手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます</span><span class="sxs-lookup"><span data-stu-id="ba77c-140">Step 2 - Create a new user account for the phone and assign the licenses</span></span>

1. <span data-ttu-id="ba77c-141">Microsoft 365 管理センターで、[アクティブな**ユーザー] に移動**  >  **active users**  >  して**ユーザーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-141">In the Microsoft 365 admin center, go to **users** > **active users** > **add a user**.</span></span>

2. <span data-ttu-id="ba77c-142">名として "Main" のようなユーザー名を入力し、2番目の名前に "受信" と入力します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-142">Enter a user name like "Main" for the first name and "Reception" for the second name.</span></span>

3. <span data-ttu-id="ba77c-143">表示名は、"Main 受付" のように自動生成されない場合に入力します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-143">Enter a display name if it doesn't autogenerate one like "Main Reception."</span></span>

4. <span data-ttu-id="ba77c-144">"MainReception" または "Mainreception" のようなユーザー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-144">Enter a user name like "MainReception" or "Mainlobby."</span></span>

5. <span data-ttu-id="ba77c-145">一般的な市外局番については、手動でパスワードを設定するか、すべての共通エリア電話に同じパスワードを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="ba77c-145">For common area phones, you might want to set a password manually or have the same password for all your common area phones.</span></span> <span data-ttu-id="ba77c-146">また、[**ユーザーが最初にサインインしたときにパスワードの変更を行う**] チェックボックスをオフにすることも考えられます。</span><span class="sxs-lookup"><span data-stu-id="ba77c-146">Also, you might think about clearing the **Make this user change their password when they first sign in** check box.</span></span>

6. <span data-ttu-id="ba77c-147">ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ba77c-147">Assign the licenses to the user.</span></span> <span data-ttu-id="ba77c-148">同じページで、**[製品ライセンス]** をクリックして拡大してください。</span><span class="sxs-lookup"><span data-stu-id="ba77c-148">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="ba77c-149">共通の市外局番をオンにして、**国内通話プラン**または**国内および国際通話プラン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-149">Turn on the Common Area Phone and pick either a **Domestic Calling Plan** or a **Domestic and International Calling Plan**.</span></span> 

    ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> <span data-ttu-id="ba77c-151">Microsoft Phone システムのダイレクトルーティングを使用している場合は、通話プランライセンスを割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ba77c-151">If you are using Microsoft Phone System Direct Routing, you do not need to assign a Calling Plan license.</span></span>

<span data-ttu-id="ba77c-152">詳細については、「[ユーザーにライセンスを割り当てる](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba77c-152">For more information, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="ba77c-153">手順 3  - 共用エリア電話機のユーザー アカウントに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="ba77c-153">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="ba77c-154">Teams 管理センターを使用して、ユーザーに番号を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ba77c-154">Use the Teams admin center to assign a number to the user.</span></span>

1. <span data-ttu-id="ba77c-155">Teams 管理センターで、[電話番号]**を選択し**  >  **Phone numbers**ます。</span><span class="sxs-lookup"><span data-stu-id="ba77c-155">In the Teams admin center, select **Voice** > **Phone numbers**.</span></span>

3.    <span data-ttu-id="ba77c-156">電話番号のリストから番号を選択し、\*\* [割り当て]\*\*  をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba77c-156">Select a number from the list of phone numbers and click **Assign**.</span></span>

4. <span data-ttu-id="ba77c-157">[**割り当て**] ページの [音声ユーザー] ボックスに電話を使用するユーザーの名前を入力し、[**音声ユーザーの選択**] ドロップダウンリストでユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-157">On the **Assign** page, in the Voice user box, type the name of the user who will be using the phone, and then select the user in the **Select a voice user** drop-down list.</span></span>

5. <span data-ttu-id="ba77c-158">次に、緊急対応の住所を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba77c-158">Next, you need to add an emergency address.</span></span> <span data-ttu-id="ba77c-159">[**都市で検索**する]、[説明] で**検索**する、またはドロップダウンリストから**場所で検索**する、テキストボックスに市区町村、説明、または場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="ba77c-159">Choose **Search by city**, **Search by description**, or **Search by location** from the drop-down list, and then enter the city, description, or location in the text box.</span></span> <span data-ttu-id="ba77c-160">検索が完了したら、[**緊急対応の住所の選択]** の下で、適切なものを選びます。</span><span class="sxs-lookup"><span data-stu-id="ba77c-160">Once you search, look under **Select emergency address** to pick the right one for you.</span></span>

6. <span data-ttu-id="ba77c-161">**[保存]** をクリックすると、ユーザーが以下のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba77c-161">Click **Save** and your user should look like this:</span></span>

   ![ライセンスの割り当てを示すスクリーンショット](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> <span data-ttu-id="ba77c-163">ユーザーは、電話システムのライセンスが適用されている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba77c-163">Users will only show up if they have a Phone System license applied.</span></span> <span data-ttu-id="ba77c-164">この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="ba77c-164">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="ba77c-165">詳細については、「[ユーザー用に電話番号を取得](getting-phone-numbers-for-your-users.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba77c-165">For more information, see [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="ba77c-166">他の電話会社と共に使用している電話番号を、「port」または Microsoft 365 または Office 365 に転送することもできます。</span><span class="sxs-lookup"><span data-stu-id="ba77c-166">You can also take your phone number that you have with another carrier and "port" or transfer it over to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ba77c-167">「[チームに電話番号を転送する」を](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba77c-167">See [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
