---
title: 組織のために通信クレジットをセットアップする
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 98591d7603cdf63a76bef3478834f37504d8ff6c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117105"
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="78a76-103">組織のために通信クレジットをセットアップする</span><span class="sxs-lookup"><span data-stu-id="78a76-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="78a76-p101">Skype for Business または Microsoft Teams で無料番号を使用する場合は、コミュニケーション クレジットを設定する必要があります。通話プラン (国内または国際) と電話会議のユーザーのうち、**すべての発信先** にダイヤルアウトできるようにする必要があるユーザーについてもコミュニケーション クレジットを設定することをお勧めします。通話プランと電話会議のサブクリプションには多くの国や地域が含まれていますが、一部の発信先は含まれていない場合があります。コミュニケーション クレジットの請求に関する設定をせずに **コミュニケーション クレジット** ライセンスをユーザーに割り当ている状態で組織の持つ分数 (使用する国/地域の通話プランまたは電話会議プランにより異なります) が使い切られた場合、これらのユーザーは電話会議から発信またはダイヤルアウトできなくなります。推奨される入金額などの詳細情報については、「[コミュニケーション クレジットについて](what-are-communications-credits.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78a76-p101">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="78a76-109">必要なコストを確認するには、[こちらで料金を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。</span><span class="sxs-lookup"><span data-stu-id="78a76-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a><span data-ttu-id="78a76-110">手順 1: 電話会議または通話プランのライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="78a76-110">Step 1: Assign an Audio Conferencing or Calling Plan license to your users</span></span>

<span data-ttu-id="78a76-111">サインアップすると、お住まいの国や地域により異なる、通話可能分数を取得します。</span><span class="sxs-lookup"><span data-stu-id="78a76-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="78a76-112">[電話会議] と [通話プラン] の [国または [地域](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) ] の一覧で国または地域を検索して、取得する分数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="78a76-112">You can search for your country or region in the [Country or region availability list for Audio Conferencing and Calling Plans](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization) to see the number of minutes you will get.</span></span> <span data-ttu-id="78a76-113">この通話可能分数を使い切ると、通話は切断されます。</span><span class="sxs-lookup"><span data-stu-id="78a76-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="78a76-114">これを回避するには、コミュニケーション クレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78a76-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="78a76-115">これを実行するには、 **電話会議または電話システムのライセンス** をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="78a76-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="78a76-116">**電話会議** ライセンスをユーザーに自分に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="78a76-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="78a76-117">「[アドオン ライセンスMicrosoft Teams割り当てる」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="78a76-117">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    <span data-ttu-id="78a76-118">このライセンスを割り当てた後、電話会議を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78a76-118">After you assign this license, you will need to set up audio conferencing.</span></span> <span data-ttu-id="78a76-119">詳しい手順については、「電話会議を試用または購入する」を参照Microsoft 365[または Office 365。](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)</span><span class="sxs-lookup"><span data-stu-id="78a76-119">For step-by-step instructions, see [Try or purchase Audio Conferencing in Microsoft 365 or Office 365](try-or-purchase-audio-conferencing-in-office-365-for-teams.md).</span></span>
    
- <span data-ttu-id="78a76-120">ユーザー **電話システム** 国内通話プランまたは国内 **通話** プランと国際通話プランのライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="78a76-120">Assign **Phone System** and a **Domestic or Domestic and International** Calling Plan license to your users.</span></span> <span data-ttu-id="78a76-121">「[アドオン ライセンスMicrosoft Teams割り当てる」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="78a76-121">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78a76-122">通信クレジットには必要ありませんが、国内通話プランまたは国内および国際通話プランのライセンスも割り当てる **必要** があります。</span><span class="sxs-lookup"><span data-stu-id="78a76-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="78a76-p106">これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号組織内のユーザーに割り当てる必要があります。詳しい手順については、「[通話プランのセットアップ](set-up-calling-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="78a76-p106">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="78a76-125">詳細については、「Microsoft Teams[ライセンス」を参照してください。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="78a76-125">For more information, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="78a76-126">手順 2: 組織のためにコミュニケーション クレジットをセットアップする</span><span class="sxs-lookup"><span data-stu-id="78a76-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="78a76-127">管理者センターに[Microsoft 365または](https://portal.office.com/Adminportal)学校アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="78a76-127">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="78a76-128">管理センターの左側のナビゲーションMicrosoft 365、Billing Purchase Services に  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="78a76-128">In the left navigation of the Microsoft 365 admin center, go to **Billing** > **Purchase Services**.</span></span> <span data-ttu-id="78a76-129">下にスクロールし、[ **アドオン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="78a76-129">Scroll down and select **Add-Ons**.</span></span>

3. <span data-ttu-id="78a76-130">[通信 **クレジット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="78a76-130">Select **Communications Credits**.</span></span>
    
4. <span data-ttu-id="78a76-131">[ **通信クレジット] サブスクリプション** ページで、情報を入力し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="78a76-131">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
   - <span data-ttu-id="78a76-p108">**預金**: アカウントに投入する金額を入力します。自動再チャージを有効にしない場合、これらの利用可能残高が使い果たされると、コミュニケーション クレジットを使用して有効になっている通話機能に支障が生じます (着信無料通話サービスなど)。残高が 0 になるたびにコミュニケーション クレジットの残高を手動で補充することを回避するには、自動再チャージ機能を有効にすることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="78a76-p108">**Add funds** Enter the amount that you want to add to your account. If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service). To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
   - <span data-ttu-id="78a76-135">**自動再チャージ**: 自動再チャージを有効にすると、お使いのアカウントに対して設定したしきい値を下回ると自動的に再補充されます。</span><span class="sxs-lookup"><span data-stu-id="78a76-135">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
     <span data-ttu-id="78a76-p109">コミュニケーション クレジットの残高が 0 になることで発生するサービスの支障を回避するために [ **自動再チャージ** ] 設定を使用することを推奨します。再チャージ トランザクションが成功した場合、失敗した場合 (クレジット カードの有効期限が切れているなど)、およびコミュニケーション クレジットの残高が 0 になったときに、それぞれ電子メールを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="78a76-p109">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero). You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
   - <span data-ttu-id="78a76-138">**リチャージ金額**: [ **リチャージの方法**] ボックスに、お使いのアカウントで下限額を下回ると追加される金額を入力します。</span><span class="sxs-lookup"><span data-stu-id="78a76-138">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
   - <span data-ttu-id="78a76-p110">**下限額**: [ **残高が次の金額以下になったときに充填**] ボックスに、自動再チャージを「 *トリガー*  」する基準として使用される金額を入力します。残高がこの金額を下回ると、再チャージの金額が自動的にお使いのアカウントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="78a76-p110">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge. Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
     > <span data-ttu-id="78a76-p111">利用可能残高は、サービス利用時の Microsoft が公開しているレートで、コミュニケーション クレジットのみに適用されます。購入日から 12 か月以内に使用されなかった残高は、有効期限切れとなり、使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="78a76-p111">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used. Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
     > 
     > <span data-ttu-id="78a76-143">通信クレジットの毎月の課金は、関連付けられている資金が使用されている場合にのみ適用されます。毎月の使用状況を確認する方法については、「PSTN 使用状況レポートSkype for Business[参照してください](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)。</span><span class="sxs-lookup"><span data-stu-id="78a76-143">Monthly billing for Communication Credits will only be applied if the alloted fund has been used, to learn how to check your monthly usage, read [Skype for Business PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)</span></span>
    
5. <span data-ttu-id="78a76-144">支払い情報を入力して、[**注文**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="78a76-144">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="78a76-p112">ボリューム ライセンスをお持ちのお客様は、支払い方法としてエンタープライズ契約番号を選択できます。エンタープライズ契約番号が複数ある場合は、支払いに使用するエンタープライズ契約番号を選択できます。(該当する場合は) エンタープライズ契約番号に関連付ける発注書番号を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="78a76-p112">If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="78a76-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span><span class="sxs-lookup"><span data-stu-id="78a76-148">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="78a76-149">You will need to get this type of usage data from your current service provider.</span><span class="sxs-lookup"><span data-stu-id="78a76-149">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="78a76-150">サービス プロバイダーとして Skype for Business Online を既に使用している組織は、Microsoft Teams **管理** センターの [PSTN 使用状況の詳細レポート] レポートで確認することで使用状況データを  >    >  **取得** できます。</span><span class="sxs-lookup"><span data-stu-id="78a76-150">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Microsoft Teams admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="78a76-151">通信クレジットを設定する場合は、組織の通話の使用状況を調査して、必要な金額を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="78a76-151">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts you need.</span></span> <span data-ttu-id="78a76-152">通話の利用状況の情報は、[ **PSTN 利用状況の詳細**] レポートで確認できます。</span><span class="sxs-lookup"><span data-stu-id="78a76-152">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="78a76-153">このレポートを使用すると、データを保存したり、カスタム レポートExcelを作成したりする必要がある場合に、通話データ レコードをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="78a76-153">This report lets you export the call data records to Excel if you need to store the data or create custom reports.</span></span> <span data-ttu-id="78a76-154">使用状況を確認する方法については、「PSTN 使用状況レポート [」を参照してください](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)。</span><span class="sxs-lookup"><span data-stu-id="78a76-154">To learn how to see usage, read [PSTN usage report](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report).</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="78a76-155">手順 3: コミュニケーション クレジットのライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="78a76-155">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="78a76-156">管理者センターに[Microsoft 365または](https://portal.office.com/Adminportal)学校アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="78a76-156">Sign in to the [Microsoft 365 admin center](https://portal.office.com/Adminportal) with your work or school account.</span></span>
    
2. <span data-ttu-id="78a76-157">管理センターの左側のナビゲーションMicrosoft 365[アクティブなユーザー] に移動し、  >  一覧からユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="78a76-157">In the left navigation of the Microsoft 365 admin center, go to **Users** > **Active users**, and then select a user from the list.</span></span>
    
3. <span data-ttu-id="78a76-158">[ライセンス **とアプリ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="78a76-158">Choose **Licenses and Apps**.</span></span>
    
4. <span data-ttu-id="78a76-159">[ **通信クレジット] を** **[オン] に** 切り替え、このライセンスを割り当て、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="78a76-159">Toggle **Communications Credits** to **On** to assign this license, and then select **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78a76-160">**Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、これを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="78a76-160">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>

    > [!TIP]
    > <span data-ttu-id="78a76-161">PowerShell を使用 [して、1](/powershell/module/skype/?view=skype-ps) つのコマンドで複数のユーザーにライセンスとアプリを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="78a76-161">You can use [Powershell](/powershell/module/skype/?view=skype-ps) to assign licenses and apps to multiple users with one command.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="78a76-162">プランと価格の詳細情報</span><span class="sxs-lookup"><span data-stu-id="78a76-162">Want to know about plans and pricing?</span></span>

<span data-ttu-id="78a76-163">次のいずれかのリンクにアクセスすると、プランと価格を確認できます。</span><span class="sxs-lookup"><span data-stu-id="78a76-163">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="78a76-164">通話プラン</span><span class="sxs-lookup"><span data-stu-id="78a76-164">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="78a76-165">電話会議プラン</span><span class="sxs-lookup"><span data-stu-id="78a76-165">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="78a76-166">電話システム プラン</span><span class="sxs-lookup"><span data-stu-id="78a76-166">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="78a76-167">また、管理センターにサインイン [し、[課金サブスクリプション] [サブスクリプションの追加] Microsoft 365](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)に移動して、情報  >    >  **を確認できます**。</span><span class="sxs-lookup"><span data-stu-id="78a76-167">You can also see information by [signing in to the Microsoft 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="78a76-168">各機能に必要なライセンスまたはライセンスを含むテーブルを表示するには[、「Microsoft Teams」を参照してください](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="78a76-168">To see a table with the license or licenses you will need for each feature, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="78a76-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="78a76-169">Related topics</span></span>

- [<span data-ttu-id="78a76-170">Skype for Business Online をセットアップする</span><span class="sxs-lookup"><span data-stu-id="78a76-170">Set up Skype for Business Online</span></span>](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [<span data-ttu-id="78a76-171">クラウド ボイスメールの設定 - Admin ヘルプ</span><span class="sxs-lookup"><span data-stu-id="78a76-171">Set up Cloud Voicemail - Admin help</span></span>](set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="78a76-172">[通話プランと通話](set-up-calling-plans.md)プラン[を設定して、Microsoft 365またはOffice 365](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="78a76-172">[Set up Calling Plans](set-up-calling-plans.md) and [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="78a76-173">資金を追加してコミュニケーション クレジットを管理する</span><span class="sxs-lookup"><span data-stu-id="78a76-173">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
  
