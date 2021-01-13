---
title: 番号移行注文について
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: ポート注文の概要と、サービス プロバイダーから Teams に電話番号を転送する方法について説明します。
ms.openlocfilehash: 4f1f8ca843db8c2b27eaa467b0014befe6f2b519
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802507"
---
# <a name="whats-a-port-order"></a><span data-ttu-id="2e29a-103">番号移行注文について</span><span class="sxs-lookup"><span data-stu-id="2e29a-103">What's a port order?</span></span>

<span data-ttu-id="2e29a-104">現在、電話サービス プロバイダーまたは通信事業者をお持ちで、ユーザーまたはサービスの電話番号を既に持っている場合、それらの電話番号を Microsoft Teams に転送するには、"番号移動 *注文"* を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-104">If you currently have a phone service provider or carrier and already have phone numbers for your users or services, you need to create a "*port order*" to transfer those phone numbers to Microsoft Teams.</span></span> <span data-ttu-id="2e29a-105">番号が移植された場合、これらの電話番号を電話会議 (電話会議ブリッジ用)、自動応答、通話キューなどのサービスに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="2e29a-105">When the numbers are ported over, you can assign those phone numbers to your users and services such as audio conferencing (for conference bridges), auto attendants, and call queues.</span></span>
  
<span data-ttu-id="2e29a-106">電話番号を Teams に移植すると、Microsoft がサービス プロバイダーになり、古いサービス プロバイダーまたは通信事業者とのサービスを切断することができます。</span><span class="sxs-lookup"><span data-stu-id="2e29a-106">After you port your phone numbers over to Teams, Microsoft becomes your service provider and you can disconnect your service with your old service provider or carrier.</span></span>

<span data-ttu-id="2e29a-107">番号の移植について理解するために、この記事の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2e29a-107">Review the information in this article to get familiar with number porting.</span></span> <span data-ttu-id="2e29a-108">その後は、番号番号の番号を転送するポート注文を作成する準備が整っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-108">After that, you should be ready to create a port order and transfer your phone numbers.</span></span> <span data-ttu-id="2e29a-109">詳 [しい手順については、「電話番号を Teams](transfer-phone-numbers-to-teams.md) に転送する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e29a-109">See [Transfer phone numbers to Teams](transfer-phone-numbers-to-teams.md) for step-by-step instructions.</span></span>
  
## <a name="what-countries-or-regions-support-number-porting"></a><span data-ttu-id="2e29a-110">番号の移植をサポートしている国または地域</span><span class="sxs-lookup"><span data-stu-id="2e29a-110">What countries or regions support number porting?</span></span>

<span data-ttu-id="2e29a-111">サポートされている国または地域すべてで電話番号を移植または転送できますが、番号の注文依頼を送信する方法は、電話番号が届く国または地域によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-111">You can port or transfer phone numbers in all the supported countries or regions, but how you submit a port order request depend on the country or region where the phone numbers come from.</span></span> <span data-ttu-id="2e29a-112">番号の移植をサポートする国と地域の一覧については、「組織の電話番号を管理する」 [を参照してください](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="2e29a-112">For a list of  countries and regions that support number porting, see [Manage phone numbers for your organization](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>  

<span data-ttu-id="2e29a-113">現在 [、Microsoft](transfer-phone-numbers-to-teams.md) Teams 管理センターの移植ウィザードは、英国、米国、およびカナダの電話番号の取得をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2e29a-113">Currently, [the porting wizard](transfer-phone-numbers-to-teams.md) in the Microsoft Teams admin center supports getting phone numbers for the United Kingdom, United States, and Canada.</span></span> <span data-ttu-id="2e29a-114">他の国や地域の電話番号を取得するには、ポート [注文を手動で送信します](manually-submit-port-order.md)。</span><span class="sxs-lookup"><span data-stu-id="2e29a-114">To get phone numbers for other countries and regions, you can [manually submit a port order](manually-submit-port-order.md).</span></span>
  
## <a name="what-numbers-can-be-transferred"></a><span data-ttu-id="2e29a-115">どの番号を移行できますか?</span><span class="sxs-lookup"><span data-stu-id="2e29a-115">What numbers can be transferred?</span></span>

 <span data-ttu-id="2e29a-116">**転送可能**</span><span class="sxs-lookup"><span data-stu-id="2e29a-116">**You can transfer**</span></span>
  
<span data-ttu-id="2e29a-117">一般に、サポートされているプロバイダーから、次の電話番号を転送できます。</span><span class="sxs-lookup"><span data-stu-id="2e29a-117">In general, you can transfer any phone number that's from a supported provider, including:</span></span>
  
- <span data-ttu-id="2e29a-118">固定電話の番号です。</span><span class="sxs-lookup"><span data-stu-id="2e29a-118">Land line phone numbers.</span></span>

- <span data-ttu-id="2e29a-119">携帯電話やタブレットで使用される携帯電話の電話番号など。</span><span class="sxs-lookup"><span data-stu-id="2e29a-119">Mobile device phone numbers such as those used for cell phone and tablets.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e29a-120">携帯電話番号の移行は、米国とプエルトリコでのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="2e29a-120">Transferring mobile numbers is only available in the United States and Puerto Rico.</span></span>
  
- <span data-ttu-id="2e29a-121">有料電話番号。</span><span class="sxs-lookup"><span data-stu-id="2e29a-121">Toll phone numbers.</span></span>

- <span data-ttu-id="2e29a-122">フリー ダイヤル電話番号。</span><span class="sxs-lookup"><span data-stu-id="2e29a-122">Toll-free phone numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e29a-123">UIFN (世界共通国際フリーダイヤル番号) はマイクロソフトに移すことができません。</span><span class="sxs-lookup"><span data-stu-id="2e29a-123">Universal International Freephone Number (UIFN) can't be transferred to us.</span></span> 
  
- <span data-ttu-id="2e29a-124">会議ブリッジや自動応答などで使用されるサービス電話番号。</span><span class="sxs-lookup"><span data-stu-id="2e29a-124">Service phone numbers such as those used for conference bridges, auto attendants, etc.</span></span>

- <span data-ttu-id="2e29a-125">Fax 電話番号 (ただし Fax 送信に使用することはできません)。</span><span class="sxs-lookup"><span data-stu-id="2e29a-125">Fax phone numbers, but they can't be used for faxing.</span></span> <span data-ttu-id="2e29a-126">ユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-126">They have to be assigned to a user.</span></span>

- <span data-ttu-id="2e29a-127">Vonage や RingCentral などの電話会社からの VoIP 電話番号。</span><span class="sxs-lookup"><span data-stu-id="2e29a-127">VoIP phone numbers from a phone provider such as Vonage or RingCentral.</span></span>

- <span data-ttu-id="2e29a-128">Skype for Business のハイブリッド電話番号。</span><span class="sxs-lookup"><span data-stu-id="2e29a-128">Skype for Business hybrid phone numbers.</span></span> <span data-ttu-id="2e29a-129">これらの番号を転送する場合は、メールでお問い合わせください <ptn@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="2e29a-129">If you want to transfer these numbers, email us at <ptn@microsoft.com>.</span></span>

  <span data-ttu-id="2e29a-130">**次の情報を転送できます。**</span><span class="sxs-lookup"><span data-stu-id="2e29a-130">**You can't transfer:**</span></span>
  
    > [!NOTE]
    > <span data-ttu-id="2e29a-131">現時点では、VoIP 電話プロバイダーからの電話番号を含め、サポートされている国または地域から電話番号や電話番号を転送できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-131">At this time, you can't transfer any phone number or numbers that aren't from a supported country or region, including phone numbers from a VoIP phone provider.</span></span> <span data-ttu-id="2e29a-132">サポートされている国/地域の一覧については、「電話会議と通話プランの国と地域の利用可」[を参照してください](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。</span><span class="sxs-lookup"><span data-stu-id="2e29a-132">For a list of supported countries/regions, see [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span></span>
  
- <span data-ttu-id="2e29a-133">DSL 回線やブロードバンド インターネット接続などのデータ接続で使用される電話番号を移転することもできません。</span><span class="sxs-lookup"><span data-stu-id="2e29a-133">Phone numbers used for data connections like for DSL lines or broadband Internet connections.</span></span>

- <span data-ttu-id="2e29a-134">FAX 専用の電話番号。</span><span class="sxs-lookup"><span data-stu-id="2e29a-134">Phone numbers dedicated to faxing.</span></span>

    <span data-ttu-id="2e29a-135">FAX に使用されている既存の専用電話番号がある場合は、これらの番号をTeams に転送できますが、FAX サービスは期待した通り動作し続けません。</span><span class="sxs-lookup"><span data-stu-id="2e29a-135">If you have existing dedicated phone numbers that are being used for faxing, you  *can*  transfer these numbers over to Teams but your fax services won't continue to work as expected.</span></span> <span data-ttu-id="2e29a-136">電話システム、国内通話プラン、または国際通話プランのライセンスを持っている場合でも、Teams のお客様は FAX サービスを利用できません。</span><span class="sxs-lookup"><span data-stu-id="2e29a-136">Faxing services aren't available to Teams customers, even if you have licenses for Phone System, Domestic Calling Plan, or International Calling Plan.</span></span>

    <span data-ttu-id="2e29a-137">電話番号を Teams に移植する場合は、FAX 送信に使用する代わりに、この電話番号を組織内のユーザーに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="2e29a-137">If you port the phone number to Teams, you can assign this phone number to a user in your organization instead of using it for faxing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e29a-138">現在、英国では、市外コード 0843、0844、0845、0870、0871、0872 の共有コスト番号を含む、英国以外の電話番号の移行は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2e29a-138">At this time in the United Kingdom, we currently don't support transferring UK non-geographic numbers including shared cost numbers for area codes 0843, 0844, 0845, 0870, 0871, 0872.</span></span>
  
## <a name="what-information-do-i-need-to-provide"></a><span data-ttu-id="2e29a-139">どのような情報を提供する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="2e29a-139">What information do I need to provide?</span></span>

<span data-ttu-id="2e29a-140">現在の通信事業者のすべてのアカウント情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e29a-140">You need to have all the account information for your current carrier.</span></span> <span data-ttu-id="2e29a-141">ポート注文に入力した情報は、現在のサービス プロバイダーからの最新の請求書に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e29a-141">The information that you enter in the port order is mostly found on the most recent bill or invoice from your current service provider.</span></span> <span data-ttu-id="2e29a-142">また、アカウントに登録されている名前とポートする番号も確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-142">You also need to know whose name is on the account and what numbers you want to port.</span></span>
  
## <a name="what-are-full-port-and-partial-port-transfers"></a><span data-ttu-id="2e29a-143">フルポート移行およびパーシャルポート移行とは何ですか?</span><span class="sxs-lookup"><span data-stu-id="2e29a-143">What are full-port and partial-port transfers?</span></span>

<span data-ttu-id="2e29a-144">電話番号を Teams に移植する場合、すべての番号または一部を転送するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-144">When you're porting phone numbers to Teams, you have the option to transfer all your numbers or some of them.</span></span>
  
- <span data-ttu-id="2e29a-145">**完全なポート** これは、現在のサービス プロバイダーから Teams にすべての番号を転送する場合です。</span><span class="sxs-lookup"><span data-stu-id="2e29a-145">**Full-port** This is when you transfer all of your numbers from your current service provider to Teams.</span></span> <span data-ttu-id="2e29a-146">転送する電話番号を求めるメッセージが表示された場合は、請求先電話番号(BTN) とアカウントの他のすべての電話番号を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-146">When you're asked for the phone numbers you want to transfer, you *must include* the billing telephone number (BTN) along with all of the other phone numbers on your account.</span></span>

    <span data-ttu-id="2e29a-147">たとえば、BTN が  *+1 425-555-1234*  で、25 の電話番号 *(+1 425-555-1235 ~ 1259)* を移植するとします。</span><span class="sxs-lookup"><span data-stu-id="2e29a-147">For example, let's say your BTN is  *+1 425-555-1234*  and you want to port all of your 25 phone numbers (*+1 425-555-1235 through 1259*).</span></span> <span data-ttu-id="2e29a-148">下の手順に従って番号を移行する場合、次のように入力します: **+14255551234 - +14255551259** 。</span><span class="sxs-lookup"><span data-stu-id="2e29a-148">When you follow the instructions below to transfer your numbers, you would enter: **+14255551234 - +14255551259**.</span></span>

- <span data-ttu-id="2e29a-149">**部分的なポート** これは、現在のサービス プロバイダーから Teams に電話番号の一部のみを転送する場合です。</span><span class="sxs-lookup"><span data-stu-id="2e29a-149">**Partial-port** This is when you're only transferring some of your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="2e29a-150">同じ BTN に関連付けられている電話番号の一部を移植する場合は *、*\*\* BTN をアカウントの他のすべての電話番号と共に含めすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2e29a-150">When you want to port some of the phone numbers tied to the same BTN, you \*\* *must not include* \*\* the BTN along with all of the other phone numbers on your account.</span></span>

    <span data-ttu-id="2e29a-151">たとえば、BTN が  *+1 425-555-1234 で*  、25 の電話番号 *(+1 425-555-1235 ~ 1259)* の 5 つのみを移植したいとします。</span><span class="sxs-lookup"><span data-stu-id="2e29a-151">For example, let's say your BTN is  *+1 425-555-1234*  and you want to port only 5 of your 25 phone numbers (*+1 425-555-1235 through 1259*).</span></span> <span data-ttu-id="2e29a-152">下の手順に従って番号を移行する場合、次のように入力します: **+1 425 555 1235 - +1 425 555 1239** 。</span><span class="sxs-lookup"><span data-stu-id="2e29a-152">When you follow the instructions below to transfer your numbers, you would enter: **+1 425 555 1235 - +1 425 555 1239**.</span></span>
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a><span data-ttu-id="2e29a-153">すべての電話番号の移行を単一の要求で送信できますか?</span><span class="sxs-lookup"><span data-stu-id="2e29a-153">Can I submit a single number porting request for all of my numbers at one time?</span></span>
<span data-ttu-id="2e29a-154"><a name="bkmk_type_1"> </a></span><span class="sxs-lookup"><span data-stu-id="2e29a-154"><a name="bkmk_type_1"> </a></span></span>

<span data-ttu-id="2e29a-155">移行する電話番号のそれぞれの電話会社と種類に対して個別の要求が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e29a-155">A unique request is needed for each carrier and type of number being ported.</span></span>
  
<span data-ttu-id="2e29a-156">たとえば、次のそれぞれの種類の電話番号に対して、個別の番号移行要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-156">For example, you need to submit a unique number porting request for each of the following types of numbers:</span></span>
  
- <span data-ttu-id="2e29a-157">ローカル有料電話番号 (サブスクライバー番号または地理的番号とも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="2e29a-157">Local toll numbers, also known as subscriber numbers or geographic numbers</span></span>

- <span data-ttu-id="2e29a-158">800、844、855、866、877、および 888 のような市外局番を含むフリーダイヤル番号</span><span class="sxs-lookup"><span data-stu-id="2e29a-158">Toll Free numbers with area codes such as: 800, 844, 855, 866, 877 and 888</span></span>

- <span data-ttu-id="2e29a-159">携帯電話番号</span><span class="sxs-lookup"><span data-stu-id="2e29a-159">Mobile numbers</span></span>

- <span data-ttu-id="2e29a-160">Microsoft 365 または Office 365 の電話会議に使用できるサービス番号。</span><span class="sxs-lookup"><span data-stu-id="2e29a-160">Service numbers that can be used for Audio Conferencing in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="2e29a-161">これらの種類の番号ごとに番号の移植要求を送信する方法の詳細を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2e29a-161">Here's more information about how to submit number porting requests for each of these types of numbers:</span></span>
  
- <span data-ttu-id="2e29a-162">**異なる携帯電話** 会社によって提供される電話番号には、各通信事業者の番号に対して一意の移植要求が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e29a-162">**Phone numbers** provided by different carriers require a unique porting request for numbers with each carrier.</span></span>

- <span data-ttu-id="2e29a-163">市 **番** が 800、844、855、866、877、888 などの市番を含む無料電話番号は、他の種類の番号との番号の移植要求に含めません。</span><span class="sxs-lookup"><span data-stu-id="2e29a-163">**Toll-free numbers** with area codes such as: 800, 844, 855, 866, 877 and 888 can't be included in a number porting request with other types of numbers.</span></span> <span data-ttu-id="2e29a-164">これらの無料電話番号を移植するには、ポート注文を [手動で送信する必要があります](manually-submit-port-order.md)。</span><span class="sxs-lookup"><span data-stu-id="2e29a-164">To port these toll-free numbers, you must [manually submit a port order](manually-submit-port-order.md).</span></span> <span data-ttu-id="2e29a-165">Microsoft Teams 管理センターでこれらの番号を移植できない。</span><span class="sxs-lookup"><span data-stu-id="2e29a-165">You can't port these numbers in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2e29a-166">詳細については、「[組織のために電話番号を管理する](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2e29a-166">For more information, see [Manage phone numbers for your organization](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

    <span data-ttu-id="2e29a-167">国とポートする電話番号の種類に適切な承認状 (LOA) を使用することが重要です。</span><span class="sxs-lookup"><span data-stu-id="2e29a-167">It's important to use the correct Letter of Authorization (LOA) for the country and type of phone numbers that you want to port.</span></span> <span data-ttu-id="2e29a-168">必要な [LOA はここでダウンロードできます](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="2e29a-168">You can [download the LOA that you need here](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

- <span data-ttu-id="2e29a-169">**携帯電話番号** には、移行を承認するための PIN コードが必要です。</span><span class="sxs-lookup"><span data-stu-id="2e29a-169">**Mobile numbers** require a PIN code to authorize the transfer.</span></span> <span data-ttu-id="2e29a-170">したがって、個別の番号移行要求が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e29a-170">Therefore, they need separate number porting request.</span></span>

- <span data-ttu-id="2e29a-171">**サービス電話番号** の移行要求は、別に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-171">**Service number** porting requests need to be submitted by themselves.</span></span> <span data-ttu-id="2e29a-172">他の種類の数値と一緒に送信できません。</span><span class="sxs-lookup"><span data-stu-id="2e29a-172">They can't be submitted with other types of numbers.</span></span>

## <a name="how-long-does-it-take-to-port-numbers"></a><span data-ttu-id="2e29a-173">番号の移行にはどれくらいかかりますか?</span><span class="sxs-lookup"><span data-stu-id="2e29a-173">How long does it take to port numbers?</span></span>
<span data-ttu-id="2e29a-174"><a name="bkmk_type_1"> </a></span><span class="sxs-lookup"><span data-stu-id="2e29a-174"><a name="bkmk_type_1"> </a></span></span>

<span data-ttu-id="2e29a-175">番号移動注文の要求が完了したら、処理には 7 ~ 14 日かかります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-175">After you've completed the port order request, it takes between 7-14 days to be processed.</span></span> <span data-ttu-id="2e29a-176">ただし、サービス プロバイダーによっては、最大 30 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-176">However, depending on your service provider it may take up to 30 days.</span></span> <span data-ttu-id="2e29a-177">電話番号を移植した後は、メールでお知らせします。</span><span class="sxs-lookup"><span data-stu-id="2e29a-177">After the phone numbers are ported over, you'll get an email from us to let you that you're good to go.</span></span>
  
<span data-ttu-id="2e29a-178">ポート注文の状態を確認するには、Microsoft Teams 管理センターの左側のナビゲーションで、[音声電話番号] に移動し、[注文履歴] を  >  **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="2e29a-178">To check the status of your port order, in the left navigation of the Microsoft Teams admin center, go to **Voice** > **Phone numbers**, and then click **Order history**.</span></span> <span data-ttu-id="2e29a-179">各ポート注文の状態が [状態] 列に **一覧表示** されます。</span><span class="sxs-lookup"><span data-stu-id="2e29a-179">Each port order status is listed in the **Status** column.</span></span>
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a><span data-ttu-id="2e29a-180">ユーザー (加入者番号) の電話番号をサービス番号に変更できますか?</span><span class="sxs-lookup"><span data-stu-id="2e29a-180">Can user (subscriber) phone numbers be converted to service numbers?</span></span>
<span data-ttu-id="2e29a-181"><a name="bkmk_type_1"> </a></span><span class="sxs-lookup"><span data-stu-id="2e29a-181"><a name="bkmk_type_1"> </a></span></span>

<span data-ttu-id="2e29a-182">はい、できます。</span><span class="sxs-lookup"><span data-stu-id="2e29a-182">Yes they can.</span></span> <span data-ttu-id="2e29a-183">変換したい組織のテナント GUID と電話番号を含んでいるサービス要求を送信するだけです。</span><span class="sxs-lookup"><span data-stu-id="2e29a-183">All you need to do is submit a service request that includes your organization's tenant GUID and the phone numbers you want converted.</span></span> <span data-ttu-id="2e29a-184">これを行うには、「組織の電話番号 [を管理する」を参照してください](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="2e29a-184">To do this, see [Manage phone numbers for your organization](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span></span>

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a><span data-ttu-id="2e29a-185">Teams から別の電話サービス プロバイダーまたは通信事業者に自分の番号を移植できますか?</span><span class="sxs-lookup"><span data-stu-id="2e29a-185">Can I port out my numbers from Teams to a different phone service provider or carrier?</span></span>

<span data-ttu-id="2e29a-186">Teams から別の通信事業者に番号を移植するには、新しい通信事業者にリクエストを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-186">To port out your numbers from Teams to a different carrier, you must submit a request with the new carrier.</span></span> <span data-ttu-id="2e29a-187">また、Microsoft Teams 管理センターで移植 PIN を設定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-187">You'll also need to set a porting PIN in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="2e29a-188">移植 PIN を定義するには、Microsoft Teams 管理センターの左側のナビゲーションで、[音声電話番号] に移動し、ページの右上隅にある [PIN の移植の管理] を選択し  >  、10 桁の PINを入力します。</span><span class="sxs-lookup"><span data-stu-id="2e29a-188">To define your porting PIN, in the left navigation of the Microsoft Teams admin center, go to **Voice** > **Phone numbers**, on the upper-right corner of the page, select **Manage porting PIN**, and then enter a 10-digit PIN.</span></span>

<span data-ttu-id="2e29a-189">新しい通信事業者から移植要求を受け取った場合は、定義した PIN の入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e29a-189">When your new carrier contacts us with the porting request, we'll ask them to provide the PIN you defined.</span></span>

## <a name="common-mistakes-to-watch-out-for"></a><span data-ttu-id="2e29a-190">注意すべきよくあるミス</span><span class="sxs-lookup"><span data-stu-id="2e29a-190">Common mistakes to watch out for</span></span>
<span data-ttu-id="2e29a-191"><a name="bkmk_type_1"> </a></span><span class="sxs-lookup"><span data-stu-id="2e29a-191"><a name="bkmk_type_1"> </a></span></span>

<span data-ttu-id="2e29a-192">番号の移行は簡単です。</span><span class="sxs-lookup"><span data-stu-id="2e29a-192">Number porting is easy to do.</span></span> <span data-ttu-id="2e29a-193">ただし、電話サービス プロバイダーに問題がある場合、注文が不完全で情報が不足している場合、または入力ミスがある場合は、ご注文が乱れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-193">Your order can get messed up, however, if there's a problem with the phone service provider, the order is incomplete and missing information, or there are typos.</span></span>
  
<span data-ttu-id="2e29a-p123">お客様が番号を移行される場合に最もよくあるミスを以下に示します。カスタマー サポートに問い合わせずにすむように、これらのミスについて慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="2e29a-p123">Here are the most common mistakes we see customers make when they port numbers. Save yourself a call to customer support and double-check for these errors.</span></span>
  
- <span data-ttu-id="2e29a-p124">入力したアカウント情報が電話会社に登録されている内容と正確に一致することを確認してください。これらの情報の不一致が、番号移行注文のエラーや遅延の最も一般的な原因です。以下の情報が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2e29a-p124">Make sure the account information you give matches exactly what your phone carrier has on record. Mismatched information is the most common cause of errors and delay your port order. Verify the following is true:</span></span>

  - <span data-ttu-id="2e29a-199">アカウントを変更する権限を持つ名前またはユーザーが正しい。</span><span class="sxs-lookup"><span data-stu-id="2e29a-199">Name or person authorized to make changes to the account is correct.</span></span>

  - <span data-ttu-id="2e29a-200">住所があっている。</span><span class="sxs-lookup"><span data-stu-id="2e29a-200">Address is correct.</span></span>

  - <span data-ttu-id="2e29a-201">アカウント番号が正しい。</span><span class="sxs-lookup"><span data-stu-id="2e29a-201">Account number is correct.</span></span>

  - <span data-ttu-id="2e29a-202">BTN は正しい。</span><span class="sxs-lookup"><span data-stu-id="2e29a-202">BTN is correct.</span></span>

- <span data-ttu-id="2e29a-203">これらの電話番号で有効になっている高度な通話制御機能 (通話探し、特有の呼び出しなど) が設定になっていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="2e29a-203">Make sure there are no advanced call control features, for example, Call Hunt, Distinctive Ring, that are enabled on these phone numbers.</span></span>

- <span data-ttu-id="2e29a-204">現在のサービス プロバイダーとの新しいサービス オーダーの発注またはサービスの解除の発注を行っていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2e29a-204">Make sure you haven't placed any new service orders or disconnects with your current service provider.</span></span>

- <span data-ttu-id="2e29a-205">すべての電話番号が、同じ携帯電話会社および同じアカウントのものであること。</span><span class="sxs-lookup"><span data-stu-id="2e29a-205">Make sure all numbers are from the same carrier and the same account.</span></span>

- <span data-ttu-id="2e29a-206">サービスが有効になっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2e29a-206">Make sure your service is active.</span></span> <span data-ttu-id="2e29a-207">アカウントを凍結すると、アカウント上で携帯電話会社を変更できません。</span><span class="sxs-lookup"><span data-stu-id="2e29a-207">Freezing the account prevents the change of carriers on the account.</span></span> <span data-ttu-id="2e29a-208">アカウントを変更する権限を持つユーザーは、凍結を削除するために、現在の通信事業者に注文を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-208">The person authorized to make changes to the account must submit an order to the current carrier to remove the freeze.</span></span> <span data-ttu-id="2e29a-209">このプロセスは、通信事業者によって 1 から 3 週間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e29a-209">This process can take one to three weeks depending on the carrier.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2e29a-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e29a-210">Related topics</span></span>

- [<span data-ttu-id="2e29a-211">番号移行注文の状況</span><span class="sxs-lookup"><span data-stu-id="2e29a-211">What's the status of your port orders?</span></span>](port-order-status.md)
- [<span data-ttu-id="2e29a-212">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="2e29a-212">Different kinds of phone numbers used for Calling Plans</span></span>](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="2e29a-213">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="2e29a-213">Manage phone numbers for your organization</span></span>](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="2e29a-214">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="2e29a-214">Emergency calling terms and conditions</span></span>](../emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="2e29a-215">[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="2e29a-215">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>