---
title: 共有エリア電話のセットアップ
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
description: 共有エリア電話について、適切なファームウェアを入手し、必要に応じて更新し、ライセンスを割り当て、設定を行うための導入手順を学びます。
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 265fbdc1a8ac566751e707874656bd6b90de980d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
ms.locfileid: "19170538"
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="11af4-103">共有エリア電話のセットアップ</span><span class="sxs-lookup"><span data-stu-id="11af4-103">Set up common area phones</span></span>
<span data-ttu-id="11af4-104">共有エリア電話機（CAP）は一般に、多くの人々が利用できるロビーなどの領域に置かれます。</span><span class="sxs-lookup"><span data-stu-id="11af4-104">A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people.</span></span> <span data-ttu-id="11af4-105">たとえば、受付の電話機、ドアホン（インターホン）または会議室の電話機、CAP は、ユーザーではなくデバイスとしてセットアップされ、自動的にネットワークにサインインされます。</span><span class="sxs-lookup"><span data-stu-id="11af4-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network.</span></span> <span data-ttu-id="11af4-106">以下の手順では、これらのタイプの電話機をユーザーが組織に導入できるように、通話プラン付きの電話システムのアカウントを設定する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="11af4-106">In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="11af4-107">共有エリア電話の必須条件</span><span class="sxs-lookup"><span data-stu-id="11af4-107">Prerequisites for common area phones</span></span>

<span data-ttu-id="11af4-108">まず、以下の事柄を行ったことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11af4-108">The first thing you need to do is to confirm that you have the following:</span></span>

 - <span data-ttu-id="11af4-109">共有エリア電話のライセンスと通話プランを購入します。</span><span class="sxs-lookup"><span data-stu-id="11af4-109">Purchase Common Area Phone license and a Calling Plan.</span></span>
 - <span data-ttu-id="11af4-110">承認済みの電話機を検索して購入します（[こちら](deploying-skype-for-business-online-phones.md) で一覧を表示してください）。</span><span class="sxs-lookup"><span data-stu-id="11af4-110">Search for and buy approved phones (view the list [here](deploying-skype-for-business-online-phones.md)).</span></span>         
 - <span data-ttu-id="11af4-111">電話機のファームウェアを更新します（[このトピックで](getting-phones-for-skype-for-business-online.md) サポートされているファームウェアをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11af4-111">Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md).</span></span>  <span data-ttu-id="11af4-112">お手持ちの電話機のファームウェアは次のように確認できます。</span><span class="sxs-lookup"><span data-stu-id="11af4-112">You can check the firmware on you phone by doing this:</span></span>       
    - <span data-ttu-id="11af4-113">**Polycom VVX の電話機** の場合は、[ **設定** > ][**状態** > ][**プラットフォーム** > ][**アプリケーション** > ][**メイン**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="11af4-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    - <span data-ttu-id="11af4-114">**Yealink の電話機**の場合は、メイン電話画面で [ **状態（情報）** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="11af4-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    - <span data-ttu-id="11af4-115">**AudioCodes の電話機** の場合は、スタート画面から [**メニュー** > ][**デバイス状態** > ][**ファームウェア バージョン** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="11af4-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
    - <span data-ttu-id="11af4-116">**Lync Phone Edition (LPE) の電話機** の場合は、スタート画面から [**メニュー** > ][**システム情報** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="11af4-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

    <span data-ttu-id="11af4-117">ファームウェアの更新は、Skype for Business のサービスによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="11af4-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="11af4-118">Skype for Business のすべての認定電話機のファームウェアは、Skype for Business の更新サーバーにアップロードされており、既定ではすべての電話機についてデバイス更新が有効となっています。</span><span class="sxs-lookup"><span data-stu-id="11af4-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

    <span data-ttu-id="11af4-119">電話機の非アクティブ時間とポーリング間隔に応じて、電話機は最新の認定ビルドを自動的にダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="11af4-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="11af4-120">デバイスの更新設定を無効にするには、 [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) コマンドレットを使用して、 *EnableDeviceUpdate* パラメータを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="11af4-120">You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.</span></span>

## <a name="setting-up-a-common-area-phone"></a><span data-ttu-id="11af4-121">共有エリア電話のセットアップ</span><span class="sxs-lookup"><span data-stu-id="11af4-121">Setting up a Common Area Phone</span></span>
<span data-ttu-id="11af4-122">以下の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11af4-122">You will need to follow these steps:</span></span>

### <a name="set-up-your-user-account-for-the-phone"></a><span data-ttu-id="11af4-123">電話機のユーザー アカウントをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="11af4-123">Set up your user account for the phone</span></span>

#### <a name="step-1---buy-the-licenses"></a><span data-ttu-id="11af4-124">ステップ 1  - ライセンスを購入します</span><span class="sxs-lookup"><span data-stu-id="11af4-124">Step 1 - Buy the licenses</span></span>
1. <span data-ttu-id="11af4-125">Office 365 管理センターで、[ **請求書** > ][**購入サービス**] に移動し、**その他のプラン** を追加します。</span><span class="sxs-lookup"><span data-stu-id="11af4-125">In the Office 365 admin center, go to **Billing** > **Purchase services**, and add **Other plans**.</span></span>

    ![CAP-license.png](../../images/cap-license.png)
2. <span data-ttu-id="11af4-127">[ **共有エリア電話** >  ][**今購入する** ] をクリックします。> [ **チェックアウト** ] ページで [**今購入する** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11af4-127">Click on **Common Area Phone** > **Buy now** > on the **Checkout** page click on **Buy now**.</span></span>
3. <span data-ttu-id="11af4-128">[ **アドオン購読** ] をクリックして展開し、さらにクリックして通話プランを購入します。</span><span class="sxs-lookup"><span data-stu-id="11af4-128">Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan.</span></span> <span data-ttu-id="11af4-129">[**国内通話プラン** ] または [ **国内および国際通話プラン** ] のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="11af4-129">Domestic Calling Plan, or Domestic and International Calling Plan</span></span>

> [!Note]
> <span data-ttu-id="11af4-130">電話システムのライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="11af4-130">You don't need a Phone System license.</span></span> <span data-ttu-id="11af4-131">それは **共通エリア電話** のライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="11af4-131">It's included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="11af4-132">ライセンスの詳細については、「[Skype for Business および Microsoft Teams のアドオンのライセンス](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11af4-132">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a><span data-ttu-id="11af4-133">ステップ 2  - 電話の新しいユーザー アカウントを作成してライセンスを割り当てます</span><span class="sxs-lookup"><span data-stu-id="11af4-133">Step 2 - Create a new user account for the phone and assign the licenses</span></span>
1. <span data-ttu-id="11af4-134">Office 365 管理センターで、[**ユーザー** > ][**アクティブ ユーザー** > ][**ユーザーを追加** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="11af4-134">In the Office 365 admin center, go to **Users** > **Active Users** > **Add a user**.</span></span>
2. <span data-ttu-id="11af4-135">最初の名前に「Main」のような **ユーザー名** を入力し、2番目の名前に「Reception」を入力します。</span><span class="sxs-lookup"><span data-stu-id="11af4-135">Put in a **User name** like “Main" for the first name and "Reception” for the second name.</span></span>
3. <span data-ttu-id="11af4-136">「Main Reception」のような名前を自動生成しない場合は、**表示名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="11af4-136">Put in a **Display name** if it doesn't autogenerate one like "Main Reception".</span></span>
4. <span data-ttu-id="11af4-137">「MainReception」や「Mainlobby」のような **ユーザー名** を入力します。</span><span class="sxs-lookup"><span data-stu-id="11af4-137">Put in a **User name** like "MainReception" or "Mainlobby".</span></span>
5. <span data-ttu-id="11af4-138">共有エリア電話機については、パスワードを手動で設定するか、すべての共通エリア電話機に対して同じパスワードを設定すると便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="11af4-138">For common area phones, you might want to set a password manually or have the same password for all of you common area phones.</span></span> <span data-ttu-id="11af4-139">また、**このユーザーが最初にサインインしたときにパスワードを変更する** の選択を解除すると良い場合もあります。</span><span class="sxs-lookup"><span data-stu-id="11af4-139">Also, you might think about unselecting **Make this user change their password when they first sign in**.</span></span>

    > [!Tip]
    > <span data-ttu-id="11af4-140">待って!!</span><span class="sxs-lookup"><span data-stu-id="11af4-140">WAIT!!</span></span> <span data-ttu-id="11af4-141">[**追加**] をクリックしないでください!!</span><span class="sxs-lookup"><span data-stu-id="11af4-141">Don't click **Add**!!</span></span> <span data-ttu-id="11af4-142">おっと、[ **追加** ] をクリックしてしまったら、こうしてください： Office 365 管理センターで > [ **ユーザー** >  ][**アクティブ ユーザー** ] を選択して、ユーザーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="11af4-142">Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user.</span></span> <span data-ttu-id="11af4-143">次に、ユーザーのプロパティ ページで、[**製品ライセンス** ] をクリックして、[ **編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11af4-143">Then on the user's properties page, click **Product licenses** and then click **Edit**.</span></span> <span data-ttu-id="11af4-144">[**製品ライセンス** ] ページで [ **共通エリア電話** ] をオンにして、[ **国内通話プラン** ] または [国内および **国際通話プラン** ] のいずれかを選びます。</span><span class="sxs-lookup"><span data-stu-id="11af4-144">On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>

6. <span data-ttu-id="11af4-145">まだそこにいる場合は、このユーザーにライセンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="11af4-145">If you are still there, assign the licenses to this user.</span></span> <span data-ttu-id="11af4-146">同じページで [**製品ライセンス**] をクリックして展開します。</span><span class="sxs-lookup"><span data-stu-id="11af4-146">On the same page, click to expand **Product licenses**.</span></span> <span data-ttu-id="11af4-147">次の機能をオンにします:</span><span class="sxs-lookup"><span data-stu-id="11af4-147">Turn on the following:</span></span>
    - <span data-ttu-id="11af4-148">共有エリア電話</span><span class="sxs-lookup"><span data-stu-id="11af4-148">Common Area Phone</span></span>
    - <span data-ttu-id="11af4-149">次に、[**国内通話プラン** ] または [国内および **国際通話プラン** ] のいずれかを選ぶ必要があります。</span><span class="sxs-lookup"><span data-stu-id="11af4-149">Then you need to pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.</span></span>
     
    <span data-ttu-id="11af4-150">ライセンスの割り当ては次のようになります。</span><span class="sxs-lookup"><span data-stu-id="11af4-150">Assigning the licenses will look like:</span></span>

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > <span data-ttu-id="11af4-152">ご存知のように、Skype for Business のプラン 2 は、 **共有エリア電話** のライセンスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="11af4-152">Just so you know, Skype for Business Plan 2 is included with the **Common Area Phone** license.</span></span>

<span data-ttu-id="11af4-153">詳細については、「[ユーザーを追加](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11af4-153">For more details, see [Add a user](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

#### <a name="step-3---assign-a-phone-number-to-the-user"></a><span data-ttu-id="11af4-154">ステップ 3  - ユーザーに電話番号を割り当てます</span><span class="sxs-lookup"><span data-stu-id="11af4-154">Step 3 - Assign a phone number to the user</span></span>
<span data-ttu-id="11af4-155">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**</span><span class="sxs-lookup"><span data-stu-id="11af4-155">![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
1. <span data-ttu-id="11af4-156">Office 365 管理センターで、[**管理センター**]  >  [**Skype for Business**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="11af4-156">In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.</span></span>
2. <span data-ttu-id="11af4-157">[**Skype for Business 管理センター** >  ][**音声** > ][**電話番号**] で、</span><span class="sxs-lookup"><span data-stu-id="11af4-157">In the **Skype for Business admin center** >  **Voice** > **Phone numbers**.</span></span>
3. <span data-ttu-id="11af4-158">電話番号のリストから番号を選択し、[**割り当てる** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11af4-158">Select a number from the list of phone numbers and click **Assign**.</span></span>
4. <span data-ttu-id="11af4-159">[ **割り当てる** ] ページの [ **音声ユーザー** ] ボックスに、電話機に用いるユーザーの名前を入力し、[ **音声ユーザーを選択する** ] コンボボックスからユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="11af4-159">On the **Assign** page, in the **Voice user** box enter the name of the user that is used for the phone then select the user in the **Select a voice user** drop down.</span></span> 
5. <span data-ttu-id="11af4-160">そこにいる間に、緊急アドレスを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11af4-160">While you're there you will need to add an emergency address.</span></span> <span data-ttu-id="11af4-161">一度検索したら、[ **緊急アドレスを選択** ] の下から適切なものを選びます。</span><span class="sxs-lookup"><span data-stu-id="11af4-161">Once you search, look under the **Select emergency address** to pick the right one for you.</span></span>
6. <span data-ttu-id="11af4-162">[ **保存** ] をクリックすると、あなたのユーザーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="11af4-162">Click **Save** and your user should look like this:</span></span>

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > <span data-ttu-id="11af4-164">ユーザーは **電話システム** ライセンスが適用されたときにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="11af4-164">Users will only show up if they have a **Phone System** licence applied.</span></span> <span data-ttu-id="11af4-165">これを行ったばかりのときは、ユーザーがリストに表示されるまでに時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="11af4-165">If you just did this, then sometimes it takes a bit for the user to show up in the list.</span></span>

<span data-ttu-id="11af4-166">より詳しくは、 「[ユーザーの電話番号を取得する](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11af4-166">For more stuff, see [Getting phone numbers for your users](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).</span></span>

<span data-ttu-id="11af4-167">不思議に思う場合は、別の通信事業者に使用しているあなたの電話番号を、Office 365 に*移植*または移行することができます。</span><span class="sxs-lookup"><span data-stu-id="11af4-167">If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365.</span></span> <span data-ttu-id="11af4-168">「[Office 365 に電話番号を移行する](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) 」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11af4-168">See [Transfer phone numbers to Office 365](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) for more information.</span></span>

## <a name="step-4---setting-up-your-phone"></a><span data-ttu-id="11af4-169">ステップ 4  - 電話機をセットアップします</span><span class="sxs-lookup"><span data-stu-id="11af4-169">Step 4 - Setting up your phone</span></span>

<span data-ttu-id="11af4-170">**電話機のモードの設定**</span><span class="sxs-lookup"><span data-stu-id="11af4-170">**Setting the mode on a phone**</span></span>

<span data-ttu-id="11af4-171">使用する電話機で、共通エリア電話モードをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="11af4-171">The phone or phones you have must have the Common Area Phone mode turned on.</span></span> <span data-ttu-id="11af4-172">オンになっていることを確認したい場合もあるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="11af4-172">You might want to check on that to make sure they do.</span></span> 

<span data-ttu-id="11af4-173">**Polycom VVX の電話機をセットアップする方法の例を次に示します。**</span><span class="sxs-lookup"><span data-stu-id="11af4-173">**Here's an example for how to set up a Polycom VVX phone**</span></span>

- <span data-ttu-id="11af4-174">Polycom VVX の共有エリア電話モードを有効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="11af4-174">Enable Common Area Phone mode for the Polycom VVX by following these steps:</span></span>
    1. <span data-ttu-id="11af4-175">ブラウザで、CAP モードを有効にできるように Web インターフェイスに接続します。</span><span class="sxs-lookup"><span data-stu-id="11af4-175">In your browser, connect to the web interface so that you can enable CAP mode.</span></span>
    2. <span data-ttu-id="11af4-176">次に [**設定**] へ移動し、[**Skype for Business の設定**] オプションで [**共有エリア電話**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11af4-176">Then go to **Setting**  and in the **Skype for Business Setting** option, select **Common Area Phone**.</span></span>
    3. <span data-ttu-id="11af4-177">[ **はい** ] をクリックして設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="11af4-177">Click **Yes** to save your settings.</span></span>

- <span data-ttu-id="11af4-178">CAP モードが有効になりましたので、電話機のディスプレイを使用して電話機をセットアップします。</span><span class="sxs-lookup"><span data-stu-id="11af4-178">Now that the CAP mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="11af4-179">ディスプレイには「**CAP が有効になってます** 」と表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="11af4-179">The display should show **CaAP is enabled**.</span></span> <span data-ttu-id="11af4-180">その後以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="11af4-180">Then do the following:</span></span>

    1. <span data-ttu-id="11af4-181">[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11af4-181">Click **Settings**.</span></span>
    2. <span data-ttu-id="11af4-182">[**詳細設定** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11af4-182">Select **Advanced Request**.</span></span>
    3. <span data-ttu-id="11af4-183">パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="11af4-183">Enter the password.</span></span>
    4. <span data-ttu-id="11af4-184">[**管理設定**] で [**共有エリア電話の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11af4-184">In **Administration settings**, select **Common Area Phone Settings**.</span></span>
    5. <span data-ttu-id="11af4-185">[**CAP** ] と [ **CAP 管理者モード** ] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="11af4-185">Enable **CAP** and **CAP Admin Mode**.</span></span>
    6. <span data-ttu-id="11af4-186">[**設定を保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11af4-186">Click **Save Config**.</span></span>

- <span data-ttu-id="11af4-187">さて、電話機の準備が整いましたので、ホーム画面でサインインすることができます。</span><span class="sxs-lookup"><span data-stu-id="11af4-187">Ok, now your phone is ready so you can sign in on the home screen.</span></span>

    1. <span data-ttu-id="11af4-188">[**設定** > ][**機能** > ][**Skype for Business**] を選択してサインインします。</span><span class="sxs-lookup"><span data-stu-id="11af4-188">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
    2. <span data-ttu-id="11af4-189">[ **ユーザー資格情報**] を選択した後 [ **Web サインイン（CAP）** ] を選択してコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="11af4-189">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code.</span></span>
    3. <span data-ttu-id="11af4-190">[[プロビジョニング ポータル](http://aka.ms/skypecap)] へ行き、[**管理者**] としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="11af4-190">Go to the [provisioning portal](http://aka.ms/skypecap), and sign in as **admin**.</span></span>
    4. <span data-ttu-id="11af4-191">表示名（「Main Reception」など）を入力します。</span><span class="sxs-lookup"><span data-stu-id="11af4-191">Enter the display name (for example, Main Reception).</span></span>

       > [!Note]
       > <span data-ttu-id="11af4-192"> **共有エリア電話のみを検索する** チェックボックスにチェックが入っていた場合は、クリアして再び検索します。</span><span class="sxs-lookup"><span data-stu-id="11af4-192">If **Search for Common Area Phones only** is checked, clear the checkbox and search again.\`</span></span>

    5. <span data-ttu-id="11af4-193">ペアリング コード ウィンドウで、電話機に表示されているコードを入力して [**対応** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11af4-193">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

        <span data-ttu-id="11af4-194">この最後の手順の後、電話機は自動的にサインインされます。</span><span class="sxs-lookup"><span data-stu-id="11af4-194">Following this last step, the phone should sign in automatically.</span></span>

### <a name="related-topics"></a><span data-ttu-id="11af4-195">関連するトピック</span><span class="sxs-lookup"><span data-stu-id="11af4-195">Related topics</span></span>

- <span data-ttu-id="11af4-196">使用可能な電話機の詳細については、「[Skype for Business Online の電話機の導入](deploying-skype-for-business-online-phones.md)」ををご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11af4-196">Learn more about available phones at [Deploying Skype for Business Online phones](deploying-skype-for-business-online-phones.md).</span></span>
- [<span data-ttu-id="11af4-197">Skype for Business Online で使う電話を入手する</span><span class="sxs-lookup"><span data-stu-id="11af4-197">Getting phones for Skype for Business Online</span></span>](getting-phones-for-skype-for-business-online.md)


