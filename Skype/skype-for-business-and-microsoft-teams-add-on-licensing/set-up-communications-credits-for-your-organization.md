---
title: "組織のために通信クレジットをセットアップする"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 62d8516a2efb7f3a48e301492e602ec957927f37
ms.sourcegitcommit: 35cbf92f5cf295c82d67e9c093e3cea7c5c012eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2018
---
# <a name="set-up-communications-credits-for-your-organization"></a><span data-ttu-id="35d9e-103">組織のために通信クレジットをセットアップする</span><span class="sxs-lookup"><span data-stu-id="35d9e-103">Set up Communications Credits for your organization</span></span>

<span data-ttu-id="35d9e-104">Skype でのフリー ダイヤル番号を使用して、ビジネスおよびマイクロソフトのチームにしたい場合は通信のクレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35d9e-104">You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams.</span></span> <span data-ttu-id="35d9e-105">またを設定することの通信のクレジット (国内または国際) 計画を呼び出すと電話会議の**すべての宛先**にダイアル アウトする機能を必要とするユーザーをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35d9e-105">Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**.</span></span> <span data-ttu-id="35d9e-106">多くの国/地域は含まれていますが、いくつかのデスティネーションが、計画を呼び出すか、オーディオ会議のサブスクリプションに含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35d9e-106">Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions.</span></span> <span data-ttu-id="35d9e-107">実行する組織の分を (、プランの呼び出し、またはオーディオ会議計画に応じて、国/地域で)、それらのユーザーと通信のクレジット課金を設定し、**通信のクレジット**のライセンスをユーザーに割り当てるしない場合呼び出しを行うか、オーディオ会議の会議から発信することができません。</span><span class="sxs-lookup"><span data-stu-id="35d9e-107">If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings.</span></span> <span data-ttu-id="35d9e-108">読み取ることによって資金調達の金額は、推奨などの詳細を取得することができます、[通信のクレジットは何ですか?](what-are-communications-credits.md)</span><span class="sxs-lookup"><span data-stu-id="35d9e-108">You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)</span></span>
  
> [!NOTE]
> <span data-ttu-id="35d9e-109">費用を確認するには、[こちらで料金をご覧ください](https://go.microsoft.com/fwlink/p/?LinkId=799523 )。</span><span class="sxs-lookup"><span data-stu-id="35d9e-109">To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).</span></span> 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a><span data-ttu-id="35d9e-110">手順 1: 電話会議と通話プランのライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="35d9e-110">Step 1: Assign an Audio Conferencing and Calling Plan license to your users</span></span>

<span data-ttu-id="35d9e-111">サインアップするときに、国/地域によって分数を取得します。</span><span class="sxs-lookup"><span data-stu-id="35d9e-111">When you sign up, you get a certain number of minutes depending on your country/region.</span></span> <span data-ttu-id="35d9e-112">国または地域が [ここ] の検索が表示される時間を分単位で表示できます。(../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md))。</span><span class="sxs-lookup"><span data-stu-id="35d9e-112">You can see the number of minutes you will get search for the country or region [here].(../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)).</span></span> <span data-ttu-id="35d9e-113">それらの分を使用すると後の呼び出しは切断されます。</span><span class="sxs-lookup"><span data-stu-id="35d9e-113">After you use those minutes, calls will be disconnected.</span></span> <span data-ttu-id="35d9e-114">これが発生しないように、通信のクレジットを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35d9e-114">To prevent this from happening, you need to set up Communications Credits.</span></span>
  
<span data-ttu-id="35d9e-115">これを実行するには、 **電話会議または電話システムのライセンス** をユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35d9e-115">To do so, **you need to assign an Audio Conferencing or Phone System license** to your users.</span></span>
  
- <span data-ttu-id="35d9e-116">**オーディオ会議**のライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="35d9e-116">Assign an **Audio Conferencing** license to your users.</span></span> <span data-ttu-id="35d9e-117">[ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35d9e-117">See [Assign Skype for Business and Microsoft Teams licenses](assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    <span data-ttu-id="35d9e-p104">このライセンスを割り当てた後、電話会議を設定する必要があります。詳細な手順については、「[Skype for Business および Microsoft Teams の電話会議のセットアップ](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35d9e-p104">After you assign this license, you will need to set up audio conferencing. For step-by-step instructions, see [Set up Audio Conferencing for Skype for Business and Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing.md).</span></span>
    
- <span data-ttu-id="35d9e-120">**電話システム**と国内または国内および海外の計画を呼び出してライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="35d9e-120">Assign **Phone System** and a domestic or domestic and international Calling Plan license to your users.</span></span> <span data-ttu-id="35d9e-121">[ビジネスおよびマイクロソフトのチームのライセンスを Skype を割り当てる](assign-skype-for-business-and-microsoft-teams-licenses.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35d9e-121">See [Assign Skype for Business and Microsoft Teams licenses](assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35d9e-122">通信のクレジットの必須ではありませんが、まだも**国内を呼び出すことを計画**または、**国内および国際を呼び出す予定**のライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35d9e-122">Although it's not required for Communications Credits, you still need to also assign a **Domestic Calling Plan** or an **Domestic and International Calling Plan** license.</span></span>
  
    <span data-ttu-id="35d9e-p106">これらのライセンスを割り当てたら、組織用に電話番号を取得し、それらの番号組織内のユーザーに割り当てる必要があります。詳しい手順については、「[通話プランのセットアップ](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35d9e-p106">After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
<span data-ttu-id="35d9e-125">詳細については、「[Skype for Business と Microsoft Teams のアドオン ライセンス](skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください</span><span class="sxs-lookup"><span data-stu-id="35d9e-125">For more information, see [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a><span data-ttu-id="35d9e-126">手順 2: 組織のためにコミュニケーション クレジットをセットアップする</span><span class="sxs-lookup"><span data-stu-id="35d9e-126">Step 2: Set up Communications Credits for your organization</span></span>

1. <span data-ttu-id="35d9e-127">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="35d9e-127">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35d9e-128">Office 365 の管理ページの左側のナビゲーションでは、**請求**に移動 > **サブスクリプション** > **アドオン** > **アドオンの購入**をするには、**通信のクレジット**をクリックして > **今すぐ購入**。</span><span class="sxs-lookup"><span data-stu-id="35d9e-128">In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add-ons** > **Buy add-ons**, and then choose **Communications Credits** > **Buy now**.</span></span>
    
3. <span data-ttu-id="35d9e-129">**通信のクレジット**申し込みのページでの情報を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35d9e-129">On the **Communications Credits** subscription page, fill in your information, and then click **Next**:</span></span>
    
  - <span data-ttu-id="35d9e-p107">**預金**: アカウントに投入する金額を入力します。自動再チャージを有効にしない場合、これらの利用可能残高が使い果たされると、コミュニケーション クレジットを使用して有効になっている通話機能に支障が生じます (着信無料通話サービスなど)。残高が 0 になるたびにコミュニケーション クレジットの残高を手動で補充することを回避するには、自動再チャージ機能を有効にすることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="35d9e-p107">**Add funds** Enter the amount that you want to add to your account. If you don't enable auto-recharge, once these funds are depleted, calling capabilities that are enabled using Communications Credits will be disrupted (such as inbound toll-free service). To avoid having to manually replenish your Communications Credits balance each time your balance reaches 0 (zero), we recommend you enable the auto-recharge feature.</span></span>
    
  - <span data-ttu-id="35d9e-133">**自動再チャージ**: 自動再チャージを有効にすると、お使いのアカウントに対して設定したしきい値を下回ると自動的に再補充されます。</span><span class="sxs-lookup"><span data-stu-id="35d9e-133">**Auto-recharge** Enabling auto-recharge will automatically refill your account when the balance falls below the threshold that you set.</span></span>
    
    <span data-ttu-id="35d9e-p108">コミュニケーション クレジットの残高が 0 になることで発生するサービスの支障を回避するために [ **自動再チャージ** ] 設定を使用することを推奨します。再チャージ トランザクションが成功した場合、失敗した場合 (クレジット カードの有効期限が切れているなど)、およびコミュニケーション クレジットの残高が 0 になったときに、それぞれ電子メールを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="35d9e-p108">It's recommended that you use the **Auto-recharge** setting to avoid any disruption of service should your Communications Credits balance reach 0 (zero). You will be sent an email when recharge transactions succeed, when recharge transactions fail (such as an expired credit card), and when your Communications Credits balance reaches 0 (zero).</span></span>
    
  - <span data-ttu-id="35d9e-136">**リチャージ金額**: [ **リチャージの方法**] ボックスに、お使いのアカウントで下限額を下回ると追加される金額を入力します。</span><span class="sxs-lookup"><span data-stu-id="35d9e-136">**Recharge amount** Enter the amount in the **Recharge with** box that you want added to your account once it reaches the trigger amount below.</span></span>
    
  - <span data-ttu-id="35d9e-p109">**下限額**: [ **残高が次の金額以下になったときに充填**] ボックスに、自動再チャージを「 *トリガー*  」する基準として使用される金額を入力します。残高がこの金額を下回ると、再チャージの金額が自動的にお使いのアカウントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="35d9e-p109">**Trigger amount** Enter the amount in **When the balance falls below** box that will be used to ' *trigger*  ' the auto-recharge. Once your balance falls below this amount, the recharge amount will be added automatically to your account.</span></span>

      > [!NOTE]
    > <span data-ttu-id="35d9e-p110">利用可能残高は、サービス利用時の Microsoft が公開しているレートで、コミュニケーション クレジットのみに適用されます。購入日から 12 か月以内に使用されなかった残高は、有効期限切れとなり、使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="35d9e-p110">Funds will be applied only to Communications Credits at Microsoft published rates when the services are used. Any funds not used within 12 months of the purchase date will expire and be forfeited.</span></span> 
    
4. <span data-ttu-id="35d9e-141">支払い情報を入力して、[ **注文**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35d9e-141">Enter your payment information and click **Place order**.</span></span>
    >[!IMPORTANT]
    ><span data-ttu-id="35d9e-142">ボリューム ライセンス契約の場合は、支払のエンタープライズ契約番号を選択する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35d9e-142">If you are a volume licensing customer, you may choose your enterprise agreement number for payment.</span></span> <span data-ttu-id="35d9e-143">エンタープライズ契約番号が複数ある場合は、支払に使用するには、エンタープライズ アグリーメントを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="35d9e-143">If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment.</span></span> <span data-ttu-id="35d9e-144">エンタープライズ ライセンス契約番号 (存在する場合) に関連付けるには、発注書番号を指定することを指定するもされます。</span><span class="sxs-lookup"><span data-stu-id="35d9e-144">You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).</span></span>
    
<span data-ttu-id="35d9e-145">各組織は、ボリュームの計画を呼び出すと速度を考慮する別の使用があります。</span><span class="sxs-lookup"><span data-stu-id="35d9e-145">Each organization will have a different usage of Calling Plan volume and rates to consider.</span></span> <span data-ttu-id="35d9e-146">現在、サービス ・ プロバイダーからこの種類の使用状況データを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35d9e-146">You will need to get this type of usage data from your current service provider.</span></span> <span data-ttu-id="35d9e-147">既にを使用して Skype オンライン ビジネスを既に自社のサービス ・ プロバイダーとしての組織は、**ビジネス管理センターの Skype**でそれを確認することによって利用状況データを取得できます > **レポート** > の**PSTN 使用法の詳細**レポートです。</span><span class="sxs-lookup"><span data-stu-id="35d9e-147">Organizations already using Skype for Business Online already as their service provider can get usage data by reviewing it in the **Skype for Business admin center** > **Reports** > **PSTN usage details** report.</span></span>
  
<span data-ttu-id="35d9e-148">通信のクレジットを設定する場合は、組織に配置する必要がある金額を決定するための呼び出しの使用状況を調べる必要があります。</span><span class="sxs-lookup"><span data-stu-id="35d9e-148">When you are setting up Communications Credits, you will need to investigate call usage for your organization to determine the amounts that you will need to put in.</span></span> <span data-ttu-id="35d9e-149">**PSTN 使用法の詳細**レポートを確認することによって、呼び出しの使用状況に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="35d9e-149">You can get call usage information by reviewing the **PSTN usage details** report.</span></span> <span data-ttu-id="35d9e-150">このレポートでは、ストレージのデータをエクスポートまたはカスタム レポートを作成する場合は、呼び出しデータ レコードを Excel にエクスポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="35d9e-150">This report lets you export the call data records to Excel if you want to export the data for storage or create custom reports.</span></span> <span data-ttu-id="35d9e-151">使用状況を表示するには、 [Skype ビジネス PSTN の使用状況レポート](../skype-for-business-online-reporting/pstn-usage-report.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35d9e-151">To see usage, see [Skype for Business PSTN usage report](../skype-for-business-online-reporting/pstn-usage-report.md)</span></span>
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a><span data-ttu-id="35d9e-152">手順 3: コミュニケーション クレジットのライセンスをユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="35d9e-152">Step 3: Assign a Communications Credits license to users</span></span>

1. <span data-ttu-id="35d9e-153">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="35d9e-153">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35d9e-154">Office 365 の管理ページの左側のナビゲーションでは、**ユーザー**に移動 > **アクティブなユーザー**の一覧からユーザーまたはユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="35d9e-154">In the left navigation of the Office 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.</span></span>
    
3. <span data-ttu-id="35d9e-155">操作ウィンドウの [ **製品ライセンス**] で [ **編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35d9e-155">In the Action pane under **Product licenses**, click **Edit**.</span></span>
    
4. <span data-ttu-id="35d9e-156">[**製品ライセンス**] ページで切り替える * * 通信クレジット * ***で**、本ライセンスを割り当てると、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35d9e-156">On the **Product licenses** page, toggle ** Communications Credits** to **On** to assign this license, and then click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35d9e-157">**Enterprise E5** ライセンスが割り当てられているユーザーがいる場合でも、この手順を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35d9e-157">Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.</span></span>
  
## <a name="want-to-know-about-plans-and-pricing"></a><span data-ttu-id="35d9e-158">プランと価格の詳細情報</span><span class="sxs-lookup"><span data-stu-id="35d9e-158">Want to know about plans and pricing?</span></span>

<span data-ttu-id="35d9e-159">次のいずれかのリンクにアクセスすると、プランと価格を確認できます。</span><span class="sxs-lookup"><span data-stu-id="35d9e-159">You can see the plans and pricing by visiting one of the following links:</span></span>
  
- [<span data-ttu-id="35d9e-160">通話プラン</span><span class="sxs-lookup"><span data-stu-id="35d9e-160">Calling Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [<span data-ttu-id="35d9e-161">オーディオ会議の計画</span><span class="sxs-lookup"><span data-stu-id="35d9e-161">Audio Conferencing Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [<span data-ttu-id="35d9e-162">電話システム プラン</span><span class="sxs-lookup"><span data-stu-id="35d9e-162">Phone System Plans</span></span>](https://go.microsoft.com/fwlink/?LinkId=799763)
    
<span data-ttu-id="35d9e-163">[Office 365 の管理センターにサインイン](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)しても情報を確認でき、**課金**しようとしています。 > **サブスクリプション** > **追加のサブスクリプション**。</span><span class="sxs-lookup"><span data-stu-id="35d9e-163">You can also see information by [signing in to the Office 365 admin center](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog) and going to **Billing** > **Subscriptions** > **Add subscriptions**.</span></span>
  
<span data-ttu-id="35d9e-164">各機能に必要なライセンスの表を確認するには、「[Skype for Business と Microsoft Teams のアドオン ライセンス](skype-for-business-and-microsoft-teams-add-on-licensing.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35d9e-164">To see a table with the license or licenses you will need for each feature, see [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="35d9e-165">関連トピック</span><span class="sxs-lookup"><span data-stu-id="35d9e-165">Related topics</span></span>

- [<span data-ttu-id="35d9e-166">Skype for Business Online のセットアップ</span><span class="sxs-lookup"><span data-stu-id="35d9e-166">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [<span data-ttu-id="35d9e-167">Skype for Business および Microsoft Teams の電話会議のセットアップ</span><span class="sxs-lookup"><span data-stu-id="35d9e-167">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
    
- [<span data-ttu-id="35d9e-168">電話システム ボイスメールのセットアップ - 管理者ヘルプ</span><span class="sxs-lookup"><span data-stu-id="35d9e-168">Set up Phone System voicemail - Admin help</span></span>](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md)
    
- <span data-ttu-id="35d9e-169">[プランの呼び出しを設定](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)し、 [Office 365 のプランを呼び出す](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="35d9e-169">[Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md)</span></span>
    
- [<span data-ttu-id="35d9e-170">資金を追加し、通信のクレジットの管理</span><span class="sxs-lookup"><span data-stu-id="35d9e-170">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
    
- <span data-ttu-id="35d9e-171">[クラウド コネクタを構成して](https://technet.microsoft.com/en-us/library/mt605228.aspx)、[クラウドのコネクタをダウンロード](https://aka.ms/CloudConnectorInstaller)</span><span class="sxs-lookup"><span data-stu-id="35d9e-171">[Configure the Cloud Connector](https://technet.microsoft.com/en-us/library/mt605228.aspx) and [Download the Cloud Connector](https://aka.ms/CloudConnectorInstaller)</span></span>
