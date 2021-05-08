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
description: 電話番号を電話番号に移植するために必要なガイダンスをMicrosoft Teams。
ms.openlocfilehash: bb63e22b7cc3aa787ddb984f82180937c5aaf9fc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802517"
---
# <a name="more-information-about-porting"></a><span data-ttu-id="18d86-103">移植の詳細</span><span class="sxs-lookup"><span data-stu-id="18d86-103">More information about porting</span></span>

<span data-ttu-id="18d86-104">電話番号を電話番号に移植する方法の詳細については、こちらをMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="18d86-104">Here you'll find more information about porting your phone numbers to Microsoft Teams.</span></span>

<span data-ttu-id="18d86-105">詳しい手順については、「電話番号を電話番号に転送する」を[参照Teams。](transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="18d86-105">For complete step-by-step instructions, see [Transfer phone numbers to Teams](transfer-phone-numbers-to-teams.md).</span></span>

<span data-ttu-id="18d86-106">サポートが必要な場合、またはさらに電話番号を取得する必要がある場合は、PSTN サービス デスクの [ヘルプ にお問い合わせください](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。</span><span class="sxs-lookup"><span data-stu-id="18d86-106">If you need help or if you need to get more phone numbers, contact the [PSTN service desk help](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).</span></span>

## <a name="port-order-account-information"></a><span data-ttu-id="18d86-107">ポート注文アカウント情報</span><span class="sxs-lookup"><span data-stu-id="18d86-107">Port order account information</span></span>

<span data-ttu-id="18d86-108">移植ウィザードの [アカウント情報の追加] ページでポート注文を送信する場合は、LOA で指定するのとほぼ同じ情報 (次を含む) を入力します。</span><span class="sxs-lookup"><span data-stu-id="18d86-108">When you're on the **Add account information** page of the porting wizard to submit a port order, you'll  enter almost all the same information that you would provide in the LOA, including:</span></span>
  
- <span data-ttu-id="18d86-109">サービス プロバイダーまたは通信事業者のアカウント番号</span><span class="sxs-lookup"><span data-stu-id="18d86-109">Account number for the service provider or carrier</span></span>
    
- <span data-ttu-id="18d86-110">請求先電話番号 (BTN)</span><span class="sxs-lookup"><span data-stu-id="18d86-110">Billing Telephone Number (BTN)</span></span>
    
- <span data-ttu-id="18d86-111">PIN - 現在のサービス プロバイダーまたは通信事業者が必要とする場合</span><span class="sxs-lookup"><span data-stu-id="18d86-111">PIN - if needed by your current service provider or carrier</span></span>
    
- <span data-ttu-id="18d86-112">組織名</span><span class="sxs-lookup"><span data-stu-id="18d86-112">Organization name</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18d86-113">これには、スペースを含む 25 文字のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="18d86-113">This will only accept 25 characters, including spaces.</span></span> <span data-ttu-id="18d86-114">組織名が 25 文字を超える場合、名前の最初の 25 文字が送信され、ポートの順序は引き続き処理されます。</span><span class="sxs-lookup"><span data-stu-id="18d86-114">If the organization name is longer than 25 characters, the first 25 characters of the name will be submitted and the port order will still be processed.</span></span>
  
- <span data-ttu-id="18d86-115">アカウントを変更する権限を持つユーザーの名前</span><span class="sxs-lookup"><span data-stu-id="18d86-115">Name of person authorized to make changes to the account</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="18d86-116">スペースを含む 15 文字のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="18d86-116">This will only accept 15 characters, including spaces.</span></span> <span data-ttu-id="18d86-117">認証する人物の名前が 15 文字より長い場合は、名前の最初の 15 文字が発行され、番号移行注文が処理されます。</span><span class="sxs-lookup"><span data-stu-id="18d86-117">If the authorized person's name is longer than 15 characters, the first 15 characters of the name will be submitted and the port order will still be processed.</span></span> 
  
- <span data-ttu-id="18d86-118">サービス アドレス</span><span class="sxs-lookup"><span data-stu-id="18d86-118">Service address</span></span>
  
<span data-ttu-id="18d86-119">ポート注文の送信を簡単にし、エラーを回避するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18d86-119">To make submitting the port order easy and avoid errors, make sure you do the following:</span></span>
  
- <span data-ttu-id="18d86-120">番号に関連付けられている機能 (Hunt Groups など) を削除します。</span><span class="sxs-lookup"><span data-stu-id="18d86-120">Remove any features (such as Hunt Groups) associated with your numbers.</span></span> <span data-ttu-id="18d86-121">これらの電話番号で通話の検索や独特の呼び出しなどの高度な通話制御機能が有効になっていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="18d86-121">Make sure there are no advanced call control features, such as Call Hunt or Distinctive Ring, enabled on these phone numbers.</span></span>
    
- <span data-ttu-id="18d86-122">新しいサービス注文を行っていないか、現在のサービス プロバイダーとの接続が切断されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="18d86-122">Ensure that you haven't placed any new service orders or disconnects with your current service provider.</span></span>
    
- <span data-ttu-id="18d86-123">すべての電話番号が、同じ携帯電話会社および同じアカウントのものであること。</span><span class="sxs-lookup"><span data-stu-id="18d86-123">Make sure all numbers are from the same carrier and the same account.</span></span>
    
- <span data-ttu-id="18d86-124">入力したアカウント情報が電話会社に登録されている内容と正確に一致することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="18d86-124">Make sure the account information you give matches exactly what your phone carrier has on record.</span></span> <span data-ttu-id="18d86-125">情報の不一致は、エラーの最も一般的な原因であり、ポートの順序を遅らせる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-125">Mismatched information is the most common cause of errors and can delay your port order.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="18d86-126">サービス プロバイダーまたは通信事業者との間でサービスを切断しない。</span><span class="sxs-lookup"><span data-stu-id="18d86-126">Don't disconnect your services with your service provider or carrier.</span></span> <span data-ttu-id="18d86-127">電話番号を新しい電話番号に移植するには、以前のサービスをアクティブな状態Teams。</span><span class="sxs-lookup"><span data-stu-id="18d86-127">You must keep your previous service active in order to port your phone numbers to Teams.</span></span> <span data-ttu-id="18d86-128">サービス プロバイダーまたは通信事業者でアカウントを凍結しないでください。</span><span class="sxs-lookup"><span data-stu-id="18d86-128">Don't freeze your account with your service provider or carrier.</span></span> <span data-ttu-id="18d86-129">アカウントを凍結すると、アカウント上で携帯電話会社を変更できません。</span><span class="sxs-lookup"><span data-stu-id="18d86-129">Freezing the account prevents the change of carriers on the account.</span></span> <span data-ttu-id="18d86-130">認定ユーザーは、凍結を解除するために、現在の携帯電話会社に注文を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-130">The authorized user will need to submit an order to the current carrier to remove the freeze.</span></span> <span data-ttu-id="18d86-131">このプロセスは、運送業者によっては 1 ~ 3 週間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-131">This process can take one to three weeks, depending on the carrier.</span></span>

## <a name="authorized-person-on-the-account"></a><span data-ttu-id="18d86-132">アカウントの承認されたユーザー</span><span class="sxs-lookup"><span data-stu-id="18d86-132">Authorized person on the account</span></span>

<span data-ttu-id="18d86-133">移植ウィザードで、サービス プロバイダーまたは通信事業者のアカウントを変更する権限を持つユーザーの名前を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-133">In the porting wizard, you must enter the name of the person who is authorized to make changes to the account with the service provider or carrier.</span></span> <span data-ttu-id="18d86-134">この名前は、ポート注文の処理には使用されませんが、争議の場合、または番号の移植時に何かが正しくない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="18d86-134">The name isn't used to process the port order, but is used in the case of a dispute, or if something is incorrect when numbers are ported.</span></span> <span data-ttu-id="18d86-135">このユーザーは、ポート注文の承認状 (LOA) に対して責任を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-135">This person is accountable for the Letter of Authorization (LOA) for a port order.</span></span>
  
> [!NOTE]
> <span data-ttu-id="18d86-136">ボックスは 15 文字 (スペースを含む) に制限されています。</span><span class="sxs-lookup"><span data-stu-id="18d86-136">The box is limited to 15 characters (including spaces).</span></span> <span data-ttu-id="18d86-137">ボックスに完全な名前を付けなかった場合、ポートの注文が遅れることも取り消される場合も、この問題は発生し得ない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-137">Not having the complete name in the box won't delay or cancel the port order.</span></span>
  
## <a name="whats-my-billing-telephone-number"></a><span data-ttu-id="18d86-138">請求先電話番号は何ですか?</span><span class="sxs-lookup"><span data-stu-id="18d86-138">What's my billing telephone number?</span></span>

<span data-ttu-id="18d86-139">請求先電話番号 (BTN) は、請求書に含まれており、サービス プロバイダーまたは通信事業者によって請求されるメイン電話番号です。</span><span class="sxs-lookup"><span data-stu-id="18d86-139">The billing telephone number (BTN) is the main phone number that's included on your bill and billed by your service provider or carrier.</span></span> <span data-ttu-id="18d86-140">電話番号が 1 つのみであるアカウントから電話番号を転送する場合は、この電話番号を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-140">If you're transferring a phone number from an account that has only one phone number, you need to enter this phone number.</span></span> <span data-ttu-id="18d86-141">複数の電話番号を持つアカウントから電話番号を転送する場合は、請求書を確認するか、サービス プロバイダーまたは通信事業者に連絡して、アカウントの BTN が何かを判断できます。</span><span class="sxs-lookup"><span data-stu-id="18d86-141">If you're transferring phone numbers from an account that has more than one, you can look at your bill or contact your service provider or carrier to determine what the BTN is for your account.</span></span>

## <a name="what-should-i-put-in-for-the-account-number"></a><span data-ttu-id="18d86-142">アカウント番号には何を入力する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="18d86-142">What should I put in for the account number?</span></span>

<span data-ttu-id="18d86-143">通常、アカウント番号は、サービス プロバイダーまたは運送業者から取得した請求書または請求書で確認できます。また、運送業者の Web サイトにログオンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="18d86-143">Typically, you can find the account number on any bill or invoice you have from your service provider or carrier, or you can log on to your carrier's website.</span></span> <span data-ttu-id="18d86-144">それでもアカウント番号が分からない場合は、サービス プロバイダーまたは通信事業者に連絡して取得できます。</span><span class="sxs-lookup"><span data-stu-id="18d86-144">If you still don't know the account number, you can contact your service provider or carrier to get it.</span></span>
  
> [!CAUTION]
>  <span data-ttu-id="18d86-145">サービス プロバイダーまたは運送業者のアカウント番号を入力するときに、スペース、ダッシュ、ハイフンを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="18d86-145">It's important that you make sure you don't use spaces, dashes, or hyphens when entering your service provider or carrier account number.</span></span>

## <a name="what-should-i-put-in-for-the-organization-name"></a><span data-ttu-id="18d86-146">組織名には何を入力する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="18d86-146">What should I put in for the organization name?</span></span>

<span data-ttu-id="18d86-147">これは組織の名前です。</span><span class="sxs-lookup"><span data-stu-id="18d86-147">This is the name of your organization.</span></span> <span data-ttu-id="18d86-148">組織名は、スペースを含む 25 文字に制限されています。</span><span class="sxs-lookup"><span data-stu-id="18d86-148">The organization name is limited to 25 characters, which includes spaces.</span></span> <span data-ttu-id="18d86-149">会社の名前は、ポート注文要求の処理には使用されません。</span><span class="sxs-lookup"><span data-stu-id="18d86-149">The name of the company isn't used to process the port order request.</span></span> <span data-ttu-id="18d86-150">これは、紛争が発生した場合、または電話番号の移植時に何かが正しくない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="18d86-150">It's used in the case of a dispute or if something is incorrect when the phone numbers are being ported over.</span></span> <span data-ttu-id="18d86-151">ボックスに会社の名前全体を入力できない場合は、ポート注文を遅らせ、取り消す必要があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-151">If you can't fit the entire name of the company in the box, it won't delay or cancel the port order.</span></span>
  
## <a name="what-should-i-put-in-for-the-service-address"></a><span data-ttu-id="18d86-152">サービス アドレスには何を入力する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="18d86-152">What should I put in for the service address?</span></span>

<span data-ttu-id="18d86-153">サービス アドレスは、電話サービス プロバイダーまたは通信事業者に登録した請求先または緊急対応の住所とは異なります。</span><span class="sxs-lookup"><span data-stu-id="18d86-153">The service address is different from the billing or emergency address that you have registered with your phone service provider or carrier.</span></span> <span data-ttu-id="18d86-154">これを知らない場合は、サービス プロバイダーまたは通信事業者に問い合わせ、アカウントに記載されているサービス アドレスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="18d86-154">If you don't know this, contact your service provider or carrier to find out the service address listed on your account.</span></span>

## <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="18d86-155">電話番号を入力する方法</span><span class="sxs-lookup"><span data-stu-id="18d86-155">How should I enter the phone numbers?</span></span>
<span data-ttu-id="18d86-156"><a name="bkadding"> </a></span><span class="sxs-lookup"><span data-stu-id="18d86-156"><a name="bkadding"> </a></span></span>

<span data-ttu-id="18d86-157">ポート注文を送信する場合は、適切に書式設定された CSV ファイルを使用して電話番号を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-157">When you submit a port order, you must use a properly formatted CSV file to submit your phone numbers.</span></span> <span data-ttu-id="18d86-158">CSV ファイルの要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="18d86-158">Here are the requirements for the CSV file:</span></span>

 - <span data-ttu-id="18d86-159">ファイルには任意の名前を付けできます。</span><span class="sxs-lookup"><span data-stu-id="18d86-159">You can give the file any name that you want.</span></span>
 - <span data-ttu-id="18d86-160">このファイルには、PhoneNumber という名前のヘッダーを含む 1 つの列のみを含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-160">The file must only have one column with a header named PhoneNumber.</span></span>
 - <span data-ttu-id="18d86-161">各電話番号は個別の行に入る必要があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-161">Each phone number must be on a separate row.</span></span>
 - <span data-ttu-id="18d86-162">電話は、数字のみ、または E.164 形式で指定できます。</span><span class="sxs-lookup"><span data-stu-id="18d86-162">Phone numbers can be digits only or in E.164 format.</span></span>
 - <span data-ttu-id="18d86-163">電話番号の形式は、選択した国または地域と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="18d86-163">The phone number format must match the country or region you selected.</span></span> <span data-ttu-id="18d86-164">たとえば、移植ウィザードで英国を選択した場合は、国コードである 44 を使用し、その後に正しい桁数の電話番号を使用します。</span><span class="sxs-lookup"><span data-stu-id="18d86-164">For example, if you choose the United Kingdom in the porting wizard, use 44, which is the country code, followed by the phone number with the correct number of digits.</span></span> <span data-ttu-id="18d86-165">たとえば、4420812341234 などです。</span><span class="sxs-lookup"><span data-stu-id="18d86-165">For example, 4420812341234.</span></span>

## <a name="how-do-i-see-the-status-of-my-port-order"></a><span data-ttu-id="18d86-166">ポート注文の状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="18d86-166">How do I see the status of my port order?</span></span>

<span data-ttu-id="18d86-167">「 [ポート注文の状態は何ですか?」を参照してください。](port-order-status.md)</span><span class="sxs-lookup"><span data-stu-id="18d86-167">See [What's the status of your port orders?](port-order-status.md)</span></span>

## <a name="related-topics"></a><span data-ttu-id="18d86-168">関連トピック</span><span class="sxs-lookup"><span data-stu-id="18d86-168">Related topics</span></span>

- [<span data-ttu-id="18d86-169">番号移行注文について</span><span class="sxs-lookup"><span data-stu-id="18d86-169">What's a port order?</span></span>](port-order-overview.md)
- [<span data-ttu-id="18d86-170">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="18d86-170">Different kinds of phone numbers used for Calling Plans</span></span>](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="18d86-171">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="18d86-171">Manage phone numbers for your organization</span></span>](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="18d86-172">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="18d86-172">Emergency calling terms and conditions</span></span>](../emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="18d86-173">[緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="18d86-173">[Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
