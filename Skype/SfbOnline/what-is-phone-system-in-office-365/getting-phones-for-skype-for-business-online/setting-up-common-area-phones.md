---
title: 共通エリア電話機を設定する
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 適切なファームウェアを取得し、更新が必要な場合、ライセンスを割り当てる共通領域電話の設定を構成、展開の手順を説明します。
ms.openlocfilehash: d741b2ea76b8824ed36252d1d53e3f66e0118401
ms.sourcegitcommit: cba568455949deab3c47777cb6504b4ed889bdbd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2018
ms.locfileid: "25552440"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="20154-103">共通エリア電話機を設定する</span><span class="sxs-lookup"><span data-stu-id="20154-103">Set up common area phones</span></span>
<span data-ttu-id="20154-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span><span class="sxs-lookup"><span data-stu-id="20154-p101">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="20154-107">共用エリア電話の前提条件</span><span class="sxs-lookup"><span data-stu-id="20154-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="20154-108">まずはじめに、次のことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20154-108">The first thing you need to do is to confirm that you have the following:</span></span>

- <span data-ttu-id="20154-109">共用エリア電話のライセンスとコールプランを購入してください。</span><span class="sxs-lookup"><span data-stu-id="20154-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
- <span data-ttu-id="20154-110">承認された電話機を検索して購入してください（リストを表示する [ここに](deploying-skype-for-business-online-phones.md)）。</span><span class="sxs-lookup"><span data-stu-id="20154-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>
- <span data-ttu-id="20154-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span><span class="sxs-lookup"><span data-stu-id="20154-p102">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:</span></span>
  - <span data-ttu-id="20154-113">**VVX のポリコム電話**:**設定**に移動し > **ステータス** > **プラットフォーム** > **アプリケーション** > **メイン**です。</span><span class="sxs-lookup"><span data-stu-id="20154-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
  - <span data-ttu-id="20154-114">**Yealink 電話**: 電話のメイン画面の**ステータス**に移動します。</span><span class="sxs-lookup"><span data-stu-id="20154-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
  - <span data-ttu-id="20154-115">**電話**: **] メニュー**に移動 > **デバイスの状態** > 開始画面から、**ファームウェアのバージョン**です。</span><span class="sxs-lookup"><span data-stu-id="20154-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
  - <span data-ttu-id="20154-116">**Lync の電話のエディション (LPE) 電話**: **] メニュー**に移動 > 開始画面から**システム情報**です。</span><span class="sxs-lookup"><span data-stu-id="20154-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="20154-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span><span class="sxs-lookup"><span data-stu-id="20154-p103">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span>

    <span data-ttu-id="20154-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="20154-p104">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="20154-121">共用エリア電話機の設定</span><span class="sxs-lookup"><span data-stu-id="20154-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="20154-122">以下の手順を実行する必要があります：</span><span class="sxs-lookup"><span data-stu-id="20154-122">You will need to follow these steps:</span></span>

### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="20154-123">手順 1  - ライセンスを購入する</span><span class="sxs-lookup"><span data-stu-id="20154-123">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="20154-124">Office 365の管理センターでは、 **[請求]** > **[購入サービス]** に移動し、**[その他の計画]** を追加してください。</span><span class="sxs-lookup"><span data-stu-id="20154-124">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="20154-126">**[共用エリア電話機]** > **[今すぐ購入]** をクリックし、**[チェックアウト]** ページで **[今すぐ購入]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20154-126">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="20154-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span><span class="sxs-lookup"><span data-stu-id="20154-p105">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="20154-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span><span class="sxs-lookup"><span data-stu-id="20154-p106">You don't need a Phone System license. It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="20154-131">ライセンスの詳細については、 [Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20154-131">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="20154-132">手順 2  - 電話機の新しいユーザアカウントを作成し、ライセンスを割り当てます</span><span class="sxs-lookup"><span data-stu-id="20154-132">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="20154-133">Office 365の管理センターでは、 **[ユーザー]** > **[アクティブユーザー]** > **[ユーザーを追加する]** に移動してください。</span><span class="sxs-lookup"><span data-stu-id="20154-133">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="20154-134">**ユーザー名** に、最初の名前を "Main"、2番目の名前を"Reception" のように入力します。</span><span class="sxs-lookup"><span data-stu-id="20154-134">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="20154-135">"Main Reception" のように自動生成しない場合は、**表示名** に入力してください。</span><span class="sxs-lookup"><span data-stu-id="20154-135">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="20154-136">**[ユーザー名]** に "Main Reception" または"Mainlobby" のように入力します。</span><span class="sxs-lookup"><span data-stu-id="20154-136">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="20154-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span><span class="sxs-lookup"><span data-stu-id="20154-p107">For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>
6. <span data-ttu-id="20154-139">[追加] をクリックしていない場合は、このユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="20154-139">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="20154-140">同じページで、**[製品ライセンス]** をクリックして拡大してください。</span><span class="sxs-lookup"><span data-stu-id="20154-140">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="20154-141">次の機能をオンにします。</span><span class="sxs-lookup"><span data-stu-id="20154-141">Turn on the following:</span></span>
   - <span data-ttu-id="20154-142">共用エリア電話機</span><span class="sxs-lookup"><span data-stu-id="20154-142">Common Area Phone</span></span>
   - <span data-ttu-id="20154-143">そして、 **[国内電話プラン]** または [国内および **国際電話プラン**] のいずれかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20154-143">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

     <span data-ttu-id="20154-144">ライセンスの割り当ては次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="20154-144">Assigning the licenses will look like:</span></span>

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > <span data-ttu-id="20154-146">ご存知のように、Skype for Business Plan 2 は、 **共用エリア電話機** のライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="20154-146">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="20154-147">詳細については、「[ユーザーを追加する](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20154-147">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a><span data-ttu-id="20154-148">手順 3  - 共用エリア電話機のユーザー アカウントに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="20154-148">Step 3 - Assign a phone number to the Common Area Phone user account</span></span>

<span data-ttu-id="20154-149">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) 電話番号を割り当てるには、 **Skype for Business 管理センター** を使用してください。</span><span class="sxs-lookup"><span data-stu-id="20154-149">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="20154-150">Office 365 管理センター >**管理センター** > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="20154-150">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="20154-151">**[Skype for Business 管理センター]** >  **[音声]** > **[電話番号]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="20154-151">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="20154-152">電話番号のリストから番号を選択し、\*\* [割り当て]\*\*  をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20154-152">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="20154-153">**[割り当て]** ページで、**[音声ユーザー]** ボックスに電話機に使用するユーザーの名前を入力し、**[音声ユーザーを選択]** ドロップダウンでユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="20154-153">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span>
5. <span data-ttu-id="20154-154">この作業の間に、緊急アドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20154-154">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="20154-155">一度検索すると、 **[緊急アドレスを選択]** を参照して自分に合うものを選択します。</span><span class="sxs-lookup"><span data-stu-id="20154-155">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="20154-156">**[保存]** をクリックすると、ユーザーが以下のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="20154-156">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="20154-158">**電話システム** ライセンスが適用さている場合のみ、ユーザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20154-158">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="20154-159">この操作を実行したばかりだと、ユーザーがリストに表示されるまでに時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="20154-159">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="20154-160">さらなる情報については、 [[ユーザーの電話番号を取得する]](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="20154-160">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="20154-161">迷っている場合は、別のキャリアや "*ポート* " で持っている電話番号を使用するか、それらをOffice 365 へ移行することもできます。</span><span class="sxs-lookup"><span data-stu-id="20154-161">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="20154-162">参照してください、 [Office 365 に電話番号を転送](/microsoftteams/transfer-phone-numbers-to-office-365)します。</span><span class="sxs-lookup"><span data-stu-id="20154-162">See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>

### <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="20154-163">手順 4  - 電話機を設定する</span><span class="sxs-lookup"><span data-stu-id="20154-163">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="20154-164">**電話機のモードを設定する**</span><span class="sxs-lookup"><span data-stu-id="20154-164">**Setting the mode on a phone**</span></span>

<span data-ttu-id="20154-165">電話機の**共用エリア電話機モード** をオンになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="20154-165">The phone or phones you have must have the **Common Area Phone mode** turned on.</span></span> <span data-ttu-id="20154-166">オンになっているかどうか確認した方がよいかもしれません。</span><span class="sxs-lookup"><span data-stu-id="20154-166">You might want to check on that to make sure they do.</span></span>

<span data-ttu-id="20154-167">**Polycom VVX 電話を設定する方法の例を次に示します**</span><span class="sxs-lookup"><span data-stu-id="20154-167">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="20154-168">Polycom VVX の共用エリア電話機モードを有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="20154-168">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="20154-169">ブラウザで、CAP モードを有効にできるように Web インターフェイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="20154-169">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="20154-170">次に **[設定]** に移動し、 **[Skype for Business 設定]** オプションで、**[共用エリア電話]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="20154-170">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="20154-171">**[はい]**  をクリックして設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="20154-171">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="20154-172">以上で CAP モードが有効になったので、電話機のディスプレイを使用して電話機を設定します。</span><span class="sxs-lookup"><span data-stu-id="20154-172">Now that CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="20154-173">ディスプレイに「 **CaAPが有効です**」と表示されます。</span><span class="sxs-lookup"><span data-stu-id="20154-173">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="20154-174">次に、以下を実行してください。</span><span class="sxs-lookup"><span data-stu-id="20154-174">Then do the following:</span></span>

    1. <span data-ttu-id="20154-175">**[設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20154-175">Click **Settings**.</span></span>
    2. <span data-ttu-id="20154-176">**詳細設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="20154-176">Select **Advanced**.</span></span>
    3. <span data-ttu-id="20154-177">パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="20154-177">Enter the password.</span></span>
    4. <span data-ttu-id="20154-178">**[管理設定]** で、**[共用エリア電話機の設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="20154-178">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="20154-179">**[CAP]** および **[CAP管理モード]** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="20154-179">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="20154-180">**[設定を保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20154-180">Click **Save Config**.</span></span>

- <span data-ttu-id="20154-181">さて、電話機の準備ができたので、ホームスクリーンにサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="20154-181">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="20154-182">**[設定]** > **[機能]** > **[Skype for Business]** を選択してサインインします。</span><span class="sxs-lookup"><span data-stu-id="20154-182">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="20154-183">**[ユーザーの資格情報]** を選択し、さらに **[ウェブサインイン（CAP）]** を選択してコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="20154-183">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="20154-184">[[事前設定ポータル]](https://aka.ms/skypecap) に移動し、**管理者** としてログインします。</span><span class="sxs-lookup"><span data-stu-id="20154-184">Go to the [provisioning portal](https://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="20154-185">表示名（Main Reception など）を入力します。</span><span class="sxs-lookup"><span data-stu-id="20154-185">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="20154-186">「**共通エリア電話のみを検索する**」がチェックされている場合は、 チェックボックスをオフにして再度検索します。</span><span class="sxs-lookup"><span data-stu-id="20154-186">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.</span></span>

    5. <span data-ttu-id="20154-187">ペアリング コード ウィンドウで、電話機に表示されているコードを入力して **[事前設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="20154-187">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="20154-188">この最後の手順の後、電話機は自動的にサインインします。</span><span class="sxs-lookup"><span data-stu-id="20154-188">Following this last step, the phone should sign in automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="20154-189">CAP 事前設定サイトには、CAP アカウントのパスワードがランダムなパスワードにリセットされると記載されています。</span><span class="sxs-lookup"><span data-stu-id="20154-189">The CAP provisioning site states it will reset the CAP account's password to a random password.</span></span> <span data-ttu-id="20154-190">CAP が参照しているアカウントが Azure Active Directory（AAD）アカウントであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="20154-190">Take note that the account the CAP is referring is the Azure Active Directory (AAD) account.</span></span> <span data-ttu-id="20154-191">AAD でアカウントを作成した場合は、そのプロセスは簡単です。</span><span class="sxs-lookup"><span data-stu-id="20154-191">If you created the account in AAD only then the process is straightforward.</span></span> <span data-ttu-id="20154-192">オンプレミス Active Directory を AAD に同期させている場合は、CAP 事前設定によって変更される使用している資格情報に注意してください。</span><span class="sxs-lookup"><span data-stu-id="20154-192">If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.</span></span>


### <a name="related-topics"></a><span data-ttu-id="20154-193">関連トピック</span><span class="sxs-lookup"><span data-stu-id="20154-193">Related topics</span></span>

- <span data-ttu-id="20154-194">利用可能な電話の詳細については  「[Skype for Business Online 電話の導入](deploying-skype-for-business-online-phones.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="20154-194">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="20154-195">Skype for Business Online を利用できる電話機の取得</span><span class="sxs-lookup"><span data-stu-id="20154-195">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


