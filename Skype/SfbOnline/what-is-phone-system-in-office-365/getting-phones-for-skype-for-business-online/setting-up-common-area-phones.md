---
title: 共通領域電話を設定します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="68b5c-103">共通領域電話を設定します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-103">Set up common area phones</span></span>
<span data-ttu-id="68b5c-104">共通領域電話 (CAP) は通常、ロビーのような領域、または多くの人々 に提供される別の領域に配置します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="68b5c-105">例では、受信エリアの電話番号、ドアの電話や会議室電話、Cap は、ユーザーではなくデバイスとして設定して、ネットワークに自動的にサインインします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="68b5c-106">以下の手順ですることができますので、これらの種類の電話を配置するには、組織の計画を呼び出すと、電話システムのアカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="68b5c-107">共通領域電話のための前提条件</span><span class="sxs-lookup"><span data-stu-id="68b5c-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="68b5c-108">最初を実行する必要がありますが、次のことを確認するのには。</span><span class="sxs-lookup"><span data-stu-id="68b5c-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="68b5c-109">共通領域電話のライセンスを購入、呼び出すようにしてください。</span><span class="sxs-lookup"><span data-stu-id="68b5c-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="68b5c-110">検索し、承認された電話の購入 (一覧を表示する[ここでは](deploying-skype-for-business-online-phones.md))。</span><span class="sxs-lookup"><span data-stu-id="68b5c-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="68b5c-111">電話のファームウェアを更新 (サポートされているを参照してくださいファームウェア[ここで](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="68b5c-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md).</span></span>  <span data-ttu-id="68b5c-112">電話のファームウェアを確認するには、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="68b5c-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="68b5c-113">**VVX のポリコム電話**:**設定**に移動し > **ステータス** > **プラットフォーム** > **アプリケーション** > **メイン**です。</span><span class="sxs-lookup"><span data-stu-id="68b5c-113">**Polycom VVX phones**: Go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="68b5c-114">**Yealink 電話**: 電話のメイン画面の**ステータス**に移動します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-114">**Yealink phones**: Go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="68b5c-115">**電話**: **] メニュー**に移動 > **デバイスの状態** > 開始画面から、**ファームウェアのバージョン**です。</span><span class="sxs-lookup"><span data-stu-id="68b5c-115">**AudioCodes phones**: Go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="68b5c-116">**Lync の電話のエディション (LPE) 電話**: **] メニュー**に移動 > 開始画面から**システム情報**です。</span><span class="sxs-lookup"><span data-stu-id="68b5c-116">**Lync Phone Edition (LPE) phones**: Go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="68b5c-117">ファームウェアの更新プログラムは、ビジネス サービス、Skype で管理されます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="68b5c-118">ビジネスのすべての Skype は、ビジネスの更新のサーバーでは、Skype を携帯電話のファームウェアをアップロードし、デバイスの更新プログラムが既定で有効にすべての電話で認定します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="68b5c-119">電話とポーリング間隔の待ち時間によって、電話が自動的にダウンロードして認定された最新のビルドがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="68b5c-120">[セット CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy)コマンドレットを使用して、 *EnableDeviceUpdate*パラメーターを設定してデバイスの更新の設定を無効にすることができます`false`。</span><span class="sxs-lookup"><span data-stu-id="68b5c-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="68b5c-121">共通領域電話の設定</span><span class="sxs-lookup"><span data-stu-id="68b5c-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="68b5c-122">以下の手順が必要になります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-122">You will need to follow these steps:</span></span>

### <a name="set-up-your-user-account-for-the-phone"></a><span data-ttu-id="68b5c-123">携帯電話のユーザー アカウントを設定します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-123">Set up your user account for the phone</span></span>

#### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="68b5c-124">手順 1 - ライセンスの購入</span><span class="sxs-lookup"><span data-stu-id="68b5c-124">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="68b5c-125">Office 365 管理センターでは、**請求先**に移動 > **発注サービス**、**その他のプラン**を追加するとします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-125">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![キャップ license.png](../../images/cap-license.png)
2. <span data-ttu-id="68b5c-127">**共通領域電話**でをクリックして > **今すぐ購入する**>**チェック アウト**ページの [**今すぐ購入する**のです。</span><span class="sxs-lookup"><span data-stu-id="68b5c-127">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="68b5c-128">**アドオンのサブスクリプション**を展開し、[呼び出す計画を購入する] をクリックするをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-128">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="68b5c-129">**国内計画を呼び出す**か、**国内または国際通話プラン**を選択します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-129">Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.</span></span>

> [!Note]
> <span data-ttu-id="68b5c-130">電話システムのライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="68b5c-130">You don't need a Phone System license.</span></span> <span data-ttu-id="68b5c-131">**共通領域電話**のライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="68b5c-131">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="68b5c-132">ライセンスの詳細については、 [Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68b5c-132">For more info on licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="68b5c-133">手順 2 - 携帯電話用の新しいユーザー アカウントを作成し、ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="68b5c-133">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="68b5c-134">**ユーザー**には、Office 365 管理センターで、 > **アクティブなユーザー** > **ユーザーを追加**します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-134">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="68b5c-135">2 番目の名前を [名] および [受信] の「メイン」のように**ユーザー名**を配置します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-135">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="68b5c-136">「メインの受信」のような 1 つを自動生成されていない場合は、**表示名**を配置します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-136">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="68b5c-137">**ユーザー名**"MainReception"または"Mainlobby"のように配置します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-137">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="68b5c-138">共通領域電話、パスワードを手動で設定をする共通領域電話のすべての同じパスワードを使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-138">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="68b5c-139">また、**最初にサインインするときにパスワードを変更するユーザーはこの**選択を解除するを考えてください。</span><span class="sxs-lookup"><span data-stu-id="68b5c-139">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="68b5c-140">待機!</span><span class="sxs-lookup"><span data-stu-id="68b5c-140">WAIT!!</span></span> <span data-ttu-id="68b5c-141">**追加**を] をクリックしてしないで!</span><span class="sxs-lookup"><span data-stu-id="68b5c-141">Don't click **Add**!!</span></span> <span data-ttu-id="68b5c-142">う、**追加**しないでをクリックした場合は、この: Office 365 管理者センター >**ユーザー** > **作業中のユーザー**とユーザーを探します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-142">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="68b5c-143">[ユーザーのプロパティ] ページで [**製品ライセンス**] をクリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-143">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="68b5c-144">[**製品ライセンス**] ページで、**共通領域電話**をオンにし、**国内を呼び出すことを計画**または国内と**国際の計画を呼び出すこと**を選択します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-144">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="68b5c-145">まだある場合は、このユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-145">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="68b5c-146">同じページで、**製品のライセンス**を展開する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-146">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="68b5c-147">次の条件にします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-147">Turn on the following:</span></span>
    - <span data-ttu-id="68b5c-148">共通領域電話</span><span class="sxs-lookup"><span data-stu-id="68b5c-148">Common Area Phone</span></span>
    - <span data-ttu-id="68b5c-149">**国内を呼び出すことを計画**または国内と**国際の計画を呼び出すこと**を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-149">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="68b5c-150">ライセンスを割り当てるようになります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-150">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="68b5c-152">だけわかっていれば、Skype のビジネス計画の 2 は、**共通領域電話**のライセンスに含まれてます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-152">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="68b5c-153">詳細については、[ユーザーの追加](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68b5c-153">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

#### <a name="step-3---assign-a-phone-number-to-the-user"></a><span data-ttu-id="68b5c-154">手順 3 - ユーザーに電話番号を割り当てる</span><span class="sxs-lookup"><span data-stu-id="68b5c-154">Step 3 - Assign a phone number to the user</span></span>
<span data-ttu-id="68b5c-155">![デバイスのロゴ-30x30.png](../../images/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。**</span><span class="sxs-lookup"><span data-stu-id="68b5c-155">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
1. <span data-ttu-id="68b5c-156">Office 365 管理センター >**管理センター** > **ビジネス用の Skype**です。</span><span class="sxs-lookup"><span data-stu-id="68b5c-156">In the Office 365 admin center > **Admin centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="68b5c-157">**ビジネス管理センターの Skype**の >  **音声** > **の電話番号**です。</span><span class="sxs-lookup"><span data-stu-id="68b5c-157">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="68b5c-158">電話番号の一覧から番号を選択して、[**割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-158">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="68b5c-159">[**割り当てる**] ページで、**音声ユーザー** ] ボックスで、電話、**音声ユーザーを選択**することでユーザーがドロップダウン リストの選択に使用されるユーザーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-159">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="68b5c-160">そこは、緊急時のアドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-160">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="68b5c-161">検索すると、**緊急時のアドレスを選択**するにふさわしいものを選択する下を確認します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-161">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="68b5c-162">[**保存**] をクリックし、ユーザーは次のようにします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-162">Click **Save** and your user should look like this:</span></span>

    ![キャップ-ユーザー-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="68b5c-164">ユーザーのみが表示されます**電話システム**は、適用されるライセンスがあるかどうか。</span><span class="sxs-lookup"><span data-stu-id="68b5c-164">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="68b5c-165">だけでこれをやった場合、かかる場合があります少し一覧に表示します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="68b5c-166">詳細情報は、[ユーザーの電話番号の取得](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68b5c-166">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="68b5c-167">ご参考までに場合、別のキャリアと「*ポート*」を持っているか、Office 365 に転送する電話番号をすることもできます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-167">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="68b5c-168">参照してください、 [Office 365 に電話番号を転送](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-168">See, [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).</span></span>

## <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="68b5c-169">ステップ 4 - 携帯電話の設定</span><span class="sxs-lookup"><span data-stu-id="68b5c-169">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="68b5c-170">**電話モードの設定**</span><span class="sxs-lookup"><span data-stu-id="68b5c-170">**Setting the mode on a phone**</span></span>

<span data-ttu-id="68b5c-171">電話や電話がある場合に、共通領域電話モードが有効になって必要があります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-171">The phone or phones you have must have the Common Area Phone mode turned on.</span></span> <span data-ttu-id="68b5c-172">これらの操作を行うかどうかを確認することを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-172">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="68b5c-173">**VVX のポリコム電話を設定する方法の例を次のとおりです。**</span><span class="sxs-lookup"><span data-stu-id="68b5c-173">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="68b5c-174">次の手順で、ポリコム VVX の共通領域電話のモードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-174">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="68b5c-175">お使いのブラウザーでは、CAP のモードを有効にすることができるように、web インターフェイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-175">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="68b5c-176">**設定**して、 **Skype**ビジネス設定のオプションでを**共通領域電話**を選択します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-176">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="68b5c-177">**[はい]** の設定を保存する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-177">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="68b5c-178">キャップ モードを有効にすると、これでは、携帯電話のディスプレイを使用して電話を設定します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-178">Now that the CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="68b5c-179">**CaAP が有効になっている**が表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68b5c-179">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="68b5c-180">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="68b5c-180">Then do the following:</span></span>

    1. <span data-ttu-id="68b5c-181">[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-181">Click **Settings**.</span></span>
    2. <span data-ttu-id="68b5c-182">**詳細設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-182">Select **Advanced**.</span></span>
    3. <span data-ttu-id="68b5c-183">パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-183">Enter the password.</span></span>
    4. <span data-ttu-id="68b5c-184">**管理の設定**] では、**共通領域電話の設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-184">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="68b5c-185">**キャップ**と**キャップの管理モード**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-185">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="68b5c-186">**設定を保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-186">Click **Save Config**.</span></span>

- <span data-ttu-id="68b5c-187">[Ok] を今すぐ電話の準備がホーム画面にサインインすることができますのでです。</span><span class="sxs-lookup"><span data-stu-id="68b5c-187">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="68b5c-188">**設定**を選択してサインイン > **機能** > **ビジネス用の Skype** 。</span><span class="sxs-lookup"><span data-stu-id="68b5c-188">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="68b5c-189">**ユーザーの資格情報**を選択し**web でサインイン (CAP)** コードを生成するを選択します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-189">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="68b5c-190">[プロビジョニングのポータル](http://aka.ms/skypecap)に移動し、**管理者**としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-190">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="68b5c-191">(メインの受信など) の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-191">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="68b5c-192">**共通領域電話でのみの検索**がオンの場合] チェック ボックスをオフにし、もう一度検索します '。</span><span class="sxs-lookup"><span data-stu-id="68b5c-192">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.\`</span></span>

    5. <span data-ttu-id="68b5c-193">ペアリング コード ウィンドウで、携帯電話に表示されるコードを入力し、[**準備**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-193">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="68b5c-194">この最後のステップでは、次の電話は自動的にサインインします。</span><span class="sxs-lookup"><span data-stu-id="68b5c-194">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="68b5c-195">このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="68b5c-195">Related topics</span></span>

- <span data-ttu-id="68b5c-196">[オンライン ビジネス電話の Skype の展開](deploying-skype-for-business-online-phones.md)で使用可能な電話の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="68b5c-196">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="68b5c-197">Skype for Business Online で使う電話を入手する</span><span class="sxs-lookup"><span data-stu-id="68b5c-197">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


