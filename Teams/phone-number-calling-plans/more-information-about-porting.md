---
title: 移植の詳細
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: tonysmit,jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.phonenumbers.porting.moreinfo
description: 電話番号を Microsoft Teams に移植するために必要なガイダンスを取得します。
ms.openlocfilehash: bb63e22b7cc3aa787ddb984f82180937c5aaf9fc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802517"
---
# <a name="more-information-about-porting"></a><span data-ttu-id="13951-103">移植の詳細</span><span class="sxs-lookup"><span data-stu-id="13951-103">More information about porting</span></span>

<span data-ttu-id="13951-104">ここでは、電話番号を Microsoft Teams に移植する方法の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="13951-104">Here you'll find more information about porting your phone numbers to Microsoft Teams.</span></span>

<span data-ttu-id="13951-105">詳しい手順については、「電話番号を Teams に転送 [する」を参照してください](transfer-phone-numbers-to-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="13951-105">For complete step-by-step instructions, see [Transfer phone numbers to Teams](transfer-phone-numbers-to-teams.md).</span></span>

<span data-ttu-id="13951-106">サポートが必要な場合、または電話番号を追加する必要がある場合は、PSTN サービス デスクの [ヘルプにお問い合わせください](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。</span><span class="sxs-lookup"><span data-stu-id="13951-106">If you need help or if you need to get more phone numbers, contact the [PSTN service desk help](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>

## <a name="port-order-account-information"></a><span data-ttu-id="13951-107">番号注文のアカウント情報</span><span class="sxs-lookup"><span data-stu-id="13951-107">Port order account information</span></span>

<span data-ttu-id="13951-108">移植注文を送信するために、移植ウィザードの [アカウント情報の追加] ページを開き、LOA で提供するのとほぼ同じ情報を入力します。次に示します。</span><span class="sxs-lookup"><span data-stu-id="13951-108">When you're on the **Add account information** page of the porting wizard to submit a port order, you'll  enter almost all the same information that you would provide in the LOA, including:</span></span>
  
- <span data-ttu-id="13951-109">サービス プロバイダーまたは通信事業者のアカウント番号</span><span class="sxs-lookup"><span data-stu-id="13951-109">Account number for the service provider or carrier</span></span>
    
- <span data-ttu-id="13951-110">請求先電話番号 (BTN)</span><span class="sxs-lookup"><span data-stu-id="13951-110">Billing Telephone Number (BTN)</span></span>
    
- <span data-ttu-id="13951-111">PIN - 現在のサービス プロバイダーまたは通信事業者が必要とする場合</span><span class="sxs-lookup"><span data-stu-id="13951-111">PIN - if needed by your current service provider or carrier</span></span>
    
- <span data-ttu-id="13951-112">組織名</span><span class="sxs-lookup"><span data-stu-id="13951-112">Organization name</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="13951-113">この場合、スペースを含めて 25 文字のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="13951-113">This will only accept 25 characters, including spaces.</span></span> <span data-ttu-id="13951-114">組織名が 25 文字を超える場合、名前の最初の 25 文字が送信され、番号の注文は処理されます。</span><span class="sxs-lookup"><span data-stu-id="13951-114">If the organization name is longer than 25 characters, the first 25 characters of the name will be submitted and the port order will still be processed.</span></span>
  
- <span data-ttu-id="13951-115">アカウントを変更する権限を持つユーザーの名前</span><span class="sxs-lookup"><span data-stu-id="13951-115">Name of person authorized to make changes to the account</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="13951-116">この場合、スペースを含めて 15 文字しか使用できません。</span><span class="sxs-lookup"><span data-stu-id="13951-116">This will only accept 15 characters, including spaces.</span></span> <span data-ttu-id="13951-117">認証する人物の名前が 15 文字より長い場合は、名前の最初の 15 文字が発行され、番号移行注文が処理されます。</span><span class="sxs-lookup"><span data-stu-id="13951-117">If the authorized person's name is longer than 15 characters, the first 15 characters of the name will be submitted and the port order will still be processed.</span></span> 
  
- <span data-ttu-id="13951-118">サービス アドレス</span><span class="sxs-lookup"><span data-stu-id="13951-118">Service address</span></span>
  
<span data-ttu-id="13951-119">移行注文を簡単に送信し、エラーを回避するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="13951-119">To make submitting the port order easy and avoid errors, make sure you do the following:</span></span>
  
- <span data-ttu-id="13951-120">電話番号に関連付けられている機能 (Hunt Groups など) を削除します。</span><span class="sxs-lookup"><span data-stu-id="13951-120">Remove any features (such as Hunt Groups) associated with your numbers.</span></span> <span data-ttu-id="13951-121">これらの電話番号で有効になっている通話の高度な通話制御機能 (通話探しや特有の呼び出しなど) が行えなかからず確認します。</span><span class="sxs-lookup"><span data-stu-id="13951-121">Make sure there are no advanced call control features, such as Call Hunt or Distinctive Ring, enabled on these phone numbers.</span></span>
    
- <span data-ttu-id="13951-122">現在のサービス プロバイダーとの新しいサービス注文や切断を行っていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="13951-122">Ensure that you haven't placed any new service orders or disconnects with your current service provider.</span></span>
    
- <span data-ttu-id="13951-123">すべての電話番号が、同じ携帯電話会社および同じアカウントのものであること。</span><span class="sxs-lookup"><span data-stu-id="13951-123">Make sure all numbers are from the same carrier and the same account.</span></span>
    
- <span data-ttu-id="13951-124">入力したアカウント情報が電話会社に登録されている内容と正確に一致することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="13951-124">Make sure the account information you give matches exactly what your phone carrier has on record.</span></span> <span data-ttu-id="13951-125">情報の不一致がエラーの最も一般的な原因であり、ポート注文が遅れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="13951-125">Mismatched information is the most common cause of errors and can delay your port order.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="13951-126">サービス プロバイダーまたは通信事業者との間でサービスを切断しない。</span><span class="sxs-lookup"><span data-stu-id="13951-126">Don't disconnect your services with your service provider or carrier.</span></span> <span data-ttu-id="13951-127">電話番号を Teams に移植するには、以前のサービスをアクティブな状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="13951-127">You must keep your previous service active in order to port your phone numbers to Teams.</span></span> <span data-ttu-id="13951-128">サービス プロバイダーまたは通信事業者でアカウントを凍結しないでください。</span><span class="sxs-lookup"><span data-stu-id="13951-128">Don't freeze your account with your service provider or carrier.</span></span> <span data-ttu-id="13951-129">アカウントを凍結すると、アカウント上で携帯電話会社を変更できません。</span><span class="sxs-lookup"><span data-stu-id="13951-129">Freezing the account prevents the change of carriers on the account.</span></span> <span data-ttu-id="13951-130">認定ユーザーは、凍結を解除するために、現在の携帯電話会社に注文を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13951-130">The authorized user will need to submit an order to the current carrier to remove the freeze.</span></span> <span data-ttu-id="13951-131">このプロセスには、通信事業者によっては 1 ~ 3 週間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="13951-131">This process can take one to three weeks, depending on the carrier.</span></span>

## <a name="authorized-person-on-the-account"></a><span data-ttu-id="13951-132">アカウントの認証されたユーザー</span><span class="sxs-lookup"><span data-stu-id="13951-132">Authorized person on the account</span></span>

<span data-ttu-id="13951-133">移植ウィザードで、サービス プロバイダーまたは通信事業者でアカウントを変更する権限を持つユーザーの名前を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13951-133">In the porting wizard, you must enter the name of the person who is authorized to make changes to the account with the service provider or carrier.</span></span> <span data-ttu-id="13951-134">この名前はポート注文の処理には使用されませんが、争議が発生した場合、または番号を移植するときに何かが間違っている場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="13951-134">The name isn't used to process the port order, but is used in the case of a dispute, or if something is incorrect when numbers are ported.</span></span> <span data-ttu-id="13951-135">このユーザーは、ポート注文の承認状 (LOA) に対して責任を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="13951-135">This person is accountable for the Letter of Authorization (LOA) for a port order.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13951-136">ボックスの文字数は 15 文字までです (スペースを含む)。</span><span class="sxs-lookup"><span data-stu-id="13951-136">The box is limited to 15 characters (including spaces).</span></span> <span data-ttu-id="13951-137">ボックスに完全な名前が入力されていないと、ポート注文が遅れることや取り消されるという問題は発生し得ない。</span><span class="sxs-lookup"><span data-stu-id="13951-137">Not having the complete name in the box won't delay or cancel the port order.</span></span>
  
## <a name="whats-my-billing-telephone-number"></a><span data-ttu-id="13951-138">請求先電話番号は何ですか?</span><span class="sxs-lookup"><span data-stu-id="13951-138">What's my billing telephone number?</span></span>

<span data-ttu-id="13951-139">請求先電話番号 (BTN) は、請求書に含まれており、サービス プロバイダーまたは通信事業者が請求するメインの電話番号です。</span><span class="sxs-lookup"><span data-stu-id="13951-139">The billing telephone number (BTN) is the main phone number that's included on your bill and billed by your service provider or carrier.</span></span> <span data-ttu-id="13951-140">電話番号が 1 つのみであるアカウントから電話番号を移行する場合は、この電話番号を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13951-140">If you're transferring a phone number from an account that has only one phone number, you need to enter this phone number.</span></span> <span data-ttu-id="13951-141">複数の電話番号を持つアカウントから電話番号を移行する場合は、請求書を確認するか、サービス プロバイダーまたは通信事業者に問い合わせ、アカウントの BTN を決定できます。</span><span class="sxs-lookup"><span data-stu-id="13951-141">If you're transferring phone numbers from an account that has more than one, you can look at your bill or contact your service provider or carrier to determine what the BTN is for your account.</span></span>

## <a name="what-should-i-put-in-for-the-account-number"></a><span data-ttu-id="13951-142">アカウント番号に何を入力する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="13951-142">What should I put in for the account number?</span></span>

<span data-ttu-id="13951-143">通常、アカウント番号は、サービス プロバイダーまたは通信事業者の請求書や請求書で確認できます。また、通信事業者の Web サイトにログオンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="13951-143">Typically, you can find the account number on any bill or invoice you have from your service provider or carrier, or you can log on to your carrier's website.</span></span> <span data-ttu-id="13951-144">それでもアカウント番号が分からない場合は、サービス プロバイダーまたは通信事業者に問い合わせ、番号を取得できます。</span><span class="sxs-lookup"><span data-stu-id="13951-144">If you still don't know the account number, you can contact your service provider or carrier to get it.</span></span>
  
> [!CAUTION]
>  <span data-ttu-id="13951-145">サービス プロバイダーまたは通信事業者のアカウント番号を入力するときに、スペース、ダッシュ、ハイフンを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="13951-145">It's important that you make sure you don't use spaces, dashes, or hyphens when entering your service provider or carrier account number.</span></span>

## <a name="what-should-i-put-in-for-the-organization-name"></a><span data-ttu-id="13951-146">組織名に何を入力する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="13951-146">What should I put in for the organization name?</span></span>

<span data-ttu-id="13951-147">これは組織の名前です。</span><span class="sxs-lookup"><span data-stu-id="13951-147">This is the name of your organization.</span></span> <span data-ttu-id="13951-148">組織名は、スペースを含む 25 文字に制限されます。</span><span class="sxs-lookup"><span data-stu-id="13951-148">The organization name is limited to 25 characters, which includes spaces.</span></span> <span data-ttu-id="13951-149">会社の名前は、ポート注文要求の処理には使用されません。</span><span class="sxs-lookup"><span data-stu-id="13951-149">The name of the company isn't used to process the port order request.</span></span> <span data-ttu-id="13951-150">争議が発生した場合、または電話番号の移植時に問題が発生した場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="13951-150">It's used in the case of a dispute or if something is incorrect when the phone numbers are being ported over.</span></span> <span data-ttu-id="13951-151">ボックスに会社の名前全体を入れ替えきれな場合、ポート注文を遅らせ、取り消す必要があります。</span><span class="sxs-lookup"><span data-stu-id="13951-151">If you can't fit the entire name of the company in the box, it won't delay or cancel the port order.</span></span>
  
## <a name="what-should-i-put-in-for-the-service-address"></a><span data-ttu-id="13951-152">サービス アドレスに何を入力する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="13951-152">What should I put in for the service address?</span></span>

<span data-ttu-id="13951-153">サービス アドレスは、電話サービス プロバイダーまたは通信事業者に登録した請求先または緊急対応の住所とは異なります。</span><span class="sxs-lookup"><span data-stu-id="13951-153">The service address is different from the billing or emergency address that you have registered with your phone service provider or carrier.</span></span> <span data-ttu-id="13951-154">この情報が分からない場合は、サービス プロバイダーまたは通信事業者に問い合わせ、アカウントに記載されているサービス アドレスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="13951-154">If you don't know this, contact your service provider or carrier to find out the service address listed on your account.</span></span>

## <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="13951-155">電話番号を入力する方法</span><span class="sxs-lookup"><span data-stu-id="13951-155">How should I enter the phone numbers?</span></span>
<span data-ttu-id="13951-156"><a name="bkadding"> </a></span><span class="sxs-lookup"><span data-stu-id="13951-156"><a name="bkadding"> </a></span></span>

<span data-ttu-id="13951-157">ポート注文を送信する場合、電話番号を送信するには、適切に書式設定された CSV ファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13951-157">When you submit a port order, you must use a properly formatted CSV file to submit your phone numbers.</span></span> <span data-ttu-id="13951-158">CSV ファイルの要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="13951-158">Here are the requirements for the CSV file:</span></span>

 - <span data-ttu-id="13951-159">ファイルには任意の名前を付けできます。</span><span class="sxs-lookup"><span data-stu-id="13951-159">You can give the file any name that you want.</span></span>
 - <span data-ttu-id="13951-160">ファイルには、PhoneNumber という名前のヘッダーを含む 1 つの列のみを含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="13951-160">The file must only have one column with a header named PhoneNumber.</span></span>
 - <span data-ttu-id="13951-161">各電話番号は個別の行に入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13951-161">Each phone number must be on a separate row.</span></span>
 - <span data-ttu-id="13951-162">電話番号には、数字のみ、または E.164 形式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="13951-162">Phone numbers can be digits only or in E.164 format.</span></span>
 - <span data-ttu-id="13951-163">電話番号の形式は、選択した国または地域と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="13951-163">The phone number format must match the country or region you selected.</span></span> <span data-ttu-id="13951-164">たとえば、移植ウィザードで英国を選ぶ場合は、国コードである 44 を使用し、その後に正しい桁数で電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="13951-164">For example, if you choose the United Kingdom in the porting wizard, use 44, which is the country code, followed by the phone number with the correct number of digits.</span></span> <span data-ttu-id="13951-165">たとえば、4420812341234 などです。</span><span class="sxs-lookup"><span data-stu-id="13951-165">For example, 4420812341234.</span></span>

## <a name="how-do-i-see-the-status-of-my-port-order"></a><span data-ttu-id="13951-166">ポート注文の状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="13951-166">How do I see the status of my port order?</span></span>

<span data-ttu-id="13951-167">ポート [注文の状態を確認する](port-order-status.md)</span><span class="sxs-lookup"><span data-stu-id="13951-167">See [What's the status of your port orders?](port-order-status.md)</span></span>

## <a name="related-topics"></a><span data-ttu-id="13951-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="13951-168">Related topics</span></span>

- [<span data-ttu-id="13951-169">番号移行注文について</span><span class="sxs-lookup"><span data-stu-id="13951-169">What's a port order?</span></span>](port-order-overview.md)
- [<span data-ttu-id="13951-170">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="13951-170">Different kinds of phone numbers used for Calling Plans</span></span>](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="13951-171">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="13951-171">Manage phone numbers for your organization</span></span>](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="13951-172">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="13951-172">Emergency calling terms and conditions</span></span>](../emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="13951-173">[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="13951-173">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
