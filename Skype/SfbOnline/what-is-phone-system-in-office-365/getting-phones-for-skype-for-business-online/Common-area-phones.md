---
title: 共通領域電話を設定します。
description: 適切なファームウェアを取得し、更新が必要な場合、ライセンスを割り当てる共通領域電話の設定を構成、展開の手順を説明します。
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
- Strat_SB_PSTN
ms.openlocfilehash: 12ed7d5c24649903f7cd3020d66ee4e9fcb77b6f
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="a97a8-103">共通領域電話を設定します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-103">Set up Common Area Phones</span></span>

<span data-ttu-id="a97a8-104">共通領域電話、または、CAP 共有領域では通常、配置は、個々 のユーザーに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="a97a8-104">A common area phone, or CAP, is typically placed in a shared area and not associated with an individual user.</span></span> <span data-ttu-id="a97a8-105">例では、受信エリアの電話番号、ドアの電話や会議室電話、Cap は、ユーザーではなくデバイスとして設定して、ネットワークに自動的にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a97a8-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically  sign in to the network.</span></span> <span data-ttu-id="a97a8-106">以下の手順でお手伝いプランを呼び出すことでマイクロソフトの電話システムのアカウントを設定し、CAP を展開し、します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-106">In the steps below, we’ll help you set up an account for Microsoft Phone System with Calling Plans and then deploy a CAP.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="a97a8-107">共通領域電話のための前提条件</span><span class="sxs-lookup"><span data-stu-id="a97a8-107">Prerequisites for Common Area Phones</span></span>

<span data-ttu-id="a97a8-108">次があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-108">Confirm that you have the following:</span></span>

    - <span data-ttu-id="a97a8-109">共通領域電話の SKU を購入しました。</span><span class="sxs-lookup"><span data-stu-id="a97a8-109">Purchased Common Area Phone SKU</span></span> 
    - <span data-ttu-id="a97a8-110">更新されたファームウェア (を参照してくださいサポートされているファームウェアのトピックhttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="a97a8-110">Updated firmware (See Supported Firmware in topichttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span></span>
    - <span data-ttu-id="a97a8-111">承認済の電話 (にあるリストを表示します。https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span><span class="sxs-lookup"><span data-stu-id="a97a8-111">Approved  phones (view the list at https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span></span> 

## <a name="check-the-firmware-for-your-phone"></a><span data-ttu-id="a97a8-112">自分の携帯電話のファームウェアを確認します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-112">Check the firmware for your phone</span></span>
- <span data-ttu-id="a97a8-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span><span class="sxs-lookup"><span data-stu-id="a97a8-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
- <span data-ttu-id="a97a8-114">**Yealink 電話機** の場合は、メインの電話画面で [ **Status (情報)** ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
- <span data-ttu-id="a97a8-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="a97a8-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
- <span data-ttu-id="a97a8-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="a97a8-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

<span data-ttu-id="a97a8-117">ファームウェアの更新プログラムは、ビジネス サービス、Skype で管理されます。</span><span class="sxs-lookup"><span data-stu-id="a97a8-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="a97a8-118">ビジネスのすべての Skype は、ビジネスの更新のサーバーでは、Skype を携帯電話のファームウェアをアップロードし、デバイスの更新プログラムが既定で有効にすべての電話で認定します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

<span data-ttu-id="a97a8-119">電話とポーリング間隔の待ち時間によって、電話が自動的にダウンロードして認定された最新のビルドがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a97a8-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="a97a8-120">[セット CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)コマンドレットを使用して、 _EnableDeviceUpdate_パラメーターを設定してデバイスの更新の設定を無効にすることができます`false`。</span><span class="sxs-lookup"><span data-stu-id="a97a8-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>

## <a name="create-cap"></a><span data-ttu-id="a97a8-121">キャップを作成します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-121">Create CAP</span></span>
<span data-ttu-id="a97a8-122">CAP を作成するには、物理的な電話を設定する前に設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-122">You create the CAP by configuring the settings before you set up the physical phone.</span></span>

#### <a name="purchase-the-common-area-phone-sku"></a><span data-ttu-id="a97a8-123">共通領域電話の SKU を購入します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-123">Purchase the Common Area Phone SKU.</span></span> 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a><span data-ttu-id="a97a8-124">共通領域電話を設定します。<!-- this section could use a screen shot--></span><span class="sxs-lookup"><span data-stu-id="a97a8-124">Set up the common area phone  <!-- this section could use a screen shot--></span></span>

<span data-ttu-id="a97a8-125">**ユーザーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="a97a8-125">**Create user**</span></span> 
1. <span data-ttu-id="a97a8-126">共通領域電話の SKU を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a97a8-126">Assign Common Area Phone SKU</span></span>
2. <span data-ttu-id="a97a8-127">(マイクロソフトの電話システムを使用して、計画を呼び出すことで) 場合は、計画を呼び出すことを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a97a8-127">Assign Calling Plan (if using Microsoft Phone System with Calling Plans).</span></span> 
3. <span data-ttu-id="a97a8-128">ビジネス管理センターでは、Skype で利用可能な電話番号を割り当てますか、新しい電話番号を要求します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-128">Assign an available telephone number in the Skype for Business Admin Center, or request a new telephone number.</span></span>

<span data-ttu-id="a97a8-129">**新しいユーザーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="a97a8-129">**Create New User**</span></span>

1. <span data-ttu-id="a97a8-130">プロビジョニングのウィンドウでは、最初と最後の名前 (たとえば、受信のメイン) を入力するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a97a8-130">In the provisioning pane, you have an option to enter a first and last name (for example, Reception Main).</span></span>
2. <span data-ttu-id="a97a8-131">表示名を入力 (必須)、「メイン受信」などです。</span><span class="sxs-lookup"><span data-stu-id="a97a8-131">Enter a display name (required), for example, "Main Reception."</span></span>
3. <span data-ttu-id="a97a8-132">ユーザー名を入力 (必須)、たとえば"MainReception"@"ドメイン"(会社名や企業名)</span><span class="sxs-lookup"><span data-stu-id="a97a8-132">Enter a username (required), for example “MainReception” @” domain” (company or enterprise name)</span></span>
4. <span data-ttu-id="a97a8-133">(国) の場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-133">Enter Location (country).</span></span>

<span data-ttu-id="a97a8-134">**共通領域電話の SKU を割り当てる**Office 365 管理センターに移動**請求 > 購買サービス****共通領域電話**の追加</span><span class="sxs-lookup"><span data-stu-id="a97a8-134">**Assign Common Area Phone SKU** In the Office 365 admin center, go to **Billing > Purchase Services** and add **Common Area Phone**</span></span>

<span data-ttu-id="a97a8-135">**CAP の SKU での通話プランを割り当てる**</span><span class="sxs-lookup"><span data-stu-id="a97a8-135">**Assign Calling Plan in CAP SKU**</span></span>

1. <span data-ttu-id="a97a8-136">携帯電話を有効にする計画を呼び出すことを選択します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-136">Select a Calling Plan to enable the phone.</span></span> 
2. <span data-ttu-id="a97a8-137">ビジネス オンライン計画 2 キャップ SKU での電話システムと Skype を有効にするキャップを追加します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-137">Add the CAP to enable the Phone System and Skype for Business Online Plan 2 in the CAP SKU.</span></span> <!-- odd order for step -->

<span data-ttu-id="a97a8-138">**電話番号を割り当てる**</span><span class="sxs-lookup"><span data-stu-id="a97a8-138">**Assign a telephone number**</span></span>
1. <span data-ttu-id="a97a8-139">[使用可能な電話番号を確認**音声 > 電話番号**です。</span><span class="sxs-lookup"><span data-stu-id="a97a8-139">Check for available phone numbers under **Voice > Phone Numbers**.</span></span>
2. <span data-ttu-id="a97a8-140">電話番号の番号の一覧から番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-140">Select a number from the available list of phone numbers number.</span></span>
3. <span data-ttu-id="a97a8-141">**音声**と**電話番号**を選択して選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-141">Confirm your selection by selecting **Voice** and **Phone Numbers**.</span></span>

    ><span data-ttu-id="a97a8-142">[メモ]音声ユーザーは、適用した後でも更新するのには時間がかかることができますが適用されると、電話システムのライセンスがあるかどうかのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a97a8-142">[Note] Voice users only show if they have the Phone System licence applied, although even after applying, it can take time to refresh.</span></span> <span data-ttu-id="a97a8-143">センターは、ビジネス管理者のいずれかの時点 Skype を再び開くことができます。</span><span class="sxs-lookup"><span data-stu-id="a97a8-143">Sometime reopening Skype for Business Admin center helps.</span></span>
    
## <a name="configure-phone"></a><span data-ttu-id="a97a8-144">電話を構成します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-144">Configure Phone</span></span>

<span data-ttu-id="a97a8-145">**物理的な電話を準備します。**</span><span class="sxs-lookup"><span data-stu-id="a97a8-145">**Prepare the physical phones**</span></span>

<span data-ttu-id="a97a8-146">選択された電話は、共通領域電話モードである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a97a8-146">Your chosen phone needs to have the Common Area Phone mode.</span></span> 

<span data-ttu-id="a97a8-147">***VVX のポリコム電話の例***</span><span class="sxs-lookup"><span data-stu-id="a97a8-147">***Example Polycom VVX phone***</span></span>

<span data-ttu-id="a97a8-148">次の手順で、ポリコム VVX の共通領域電話のモードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a97a8-148">Enable Common Area Phone Mode for the Polycom VVX by following these steps:</span></span>
1. <span data-ttu-id="a97a8-149">お使いのブラウザーで web インターフェイスを使用、VVX のキャップのモードを有効にするには</span><span class="sxs-lookup"><span data-stu-id="a97a8-149">In your browser, use the web interface to enable CAP mode on the VVX</span></span>
2. <span data-ttu-id="a97a8-150">**設定**にし、ビジネスの設定オプションの Skype で、**共通領域電話**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-150">Go to **Setting**  and in the Skype for Business Setting option, select **Common Area Phone**.</span></span>
3. <span data-ttu-id="a97a8-151">**[はい]** の構成設定を保存する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a97a8-151">Click **Yes** to save your configuration settings.</span></span>

<span data-ttu-id="a97a8-152">キャップ電話モードを有効にすると、これでは、携帯電話のディスプレイを使用して電話を設定します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-152">Now that the CAP phone mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="a97a8-153">「CaAP が有効な"表示が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a97a8-153">The display should show "CaAP is enabled."</span></span>

1. <span data-ttu-id="a97a8-154">[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a97a8-154">Click **Settings**.</span></span>
2. <span data-ttu-id="a97a8-155">**詳細設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-155">Select **Advanced**.</span></span>
3. <span data-ttu-id="a97a8-156">パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-156">Enter the password.</span></span>
4. <span data-ttu-id="a97a8-157">管理の設定では、**共通領域電話の設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-157">In Administration settings, select **Common Area Phone Settings**.</span></span>
5. <span data-ttu-id="a97a8-158">**キャップ**と**キャップの管理モード**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a97a8-158">Enable **CAP** and **CAP Admin Mode**.</span></span>
6. <span data-ttu-id="a97a8-159">**設定を保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a97a8-159">Click **Save Config**.</span></span>

<span data-ttu-id="a97a8-160">自分の携帯電話は、次のようなホーム画面にサインインするときの操作を準備する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="a97a8-160">Your phone is ready to be provisioned, which you'll do when you sign in on the home screen.</span></span>

1. <span data-ttu-id="a97a8-161">**設定**を選択してサインイン > **機能** > **ビジネス用の Skype** 。</span><span class="sxs-lookup"><span data-stu-id="a97a8-161">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
2. <span data-ttu-id="a97a8-162">**ユーザーの資格情報**を選択し選択**web サインイン (CAP)** コードを生成する.</span><span class="sxs-lookup"><span data-stu-id="a97a8-162">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code..</span></span>
3. <span data-ttu-id="a97a8-163">プロビジョニングのポータルに移動http://aka.ms/skypecap、し、**管理者**としてサインインします。</span><span class="sxs-lookup"><span data-stu-id="a97a8-163">Go to the provisioning portal at http://aka.ms/skypecap, and sign in as **admin**.</span></span>
4. <span data-ttu-id="a97a8-164">キャップを表示するのには (たとえば、メインの受信) の表示名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-164">Enter display name (for example, Main Reception) to view your CAP.</span></span>

><span data-ttu-id="a97a8-165">[メモ]場合 [共通領域電話でのみの検索] がチェック ボックスをオフにして再度検索をオンになっている。</span><span class="sxs-lookup"><span data-stu-id="a97a8-165">[Note] If “Search for Common Area Phones only” is checked, clear the checkbox and search again.</span></span>

5. <span data-ttu-id="a97a8-166">ペアリング コード ウィンドウで、携帯電話に表示されるコードを入力し、[**準備**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a97a8-166">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

<span data-ttu-id="a97a8-167">この最後のステップでは、次の電話は自動的にサインインします。</span><span class="sxs-lookup"><span data-stu-id="a97a8-167">Following this last step, the phone should sign in automatically.</span></span>

<span data-ttu-id="a97a8-168">使用可能な電話の詳細については[](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)です。</span><span class="sxs-lookup"><span data-stu-id="a97a8-168">Learn more about available phones at [](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span></span>


