---
title: "Office 365 に電話番号を転送します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 47b3af8e-4171-4dec-8333-c956f108664e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.PortingNumbersOverview
ms.custom:
- Calling Plans
- Strat_SB_PSTN
- LIL_Placement
description: Learn what you need to know and do before porting phone numbers to Skype for Business, and how to create a port order to transfer them.
ms.openlocfilehash: 962e2347aa8eb6396c5ed3a5e8bba46eb18a65c5
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
# <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="89c1e-103">Office 365 に電話番号を転送します。</span><span class="sxs-lookup"><span data-stu-id="89c1e-103">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="89c1e-p101">[] 電話番号を現在のサービス プロバイダーから Skype for Business に移行するのは簡単です。電話番号を Skype for Business に移行した後、マイクロソフトがサービスプロバイダーになり、それらの電話番号に対する請求を行います。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p101">It's easy to transfer your phone numbers from your current service provider to Skype for Business. After you port your phone numbers to Skype for Business, Microsoft will become your service provider and will bill you for those phone numbers.</span></span>
  
<span data-ttu-id="89c1e-106">電話番号の転送を開始する前に[転送する電話番号のよくある質問](transferring-phone-numbers-common-questions.md)の情報を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89c1e-106">Before you start transferring phone numbers, we recommend that you review the information in [Transferring phone numbers common questions](transferring-phone-numbers-common-questions.md).</span></span> <span data-ttu-id="89c1e-107">ダイヤルイン会議用ブリッジ、自動応答、またはその他のサービス番号の番号をサービスがあれば、無料電話番号も[管理用の電話番号を参照してくださいビジネス用の Skype に転送する必要がありますが 999 を超える数のユーザー (サブスクライバー) の電話番号組織](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)に正しいフォームをダウンロードし、お知らせします。</span><span class="sxs-lookup"><span data-stu-id="89c1e-107">If you have service numbers for dial-in conferencing bridges, auto attendants or other service numbers, toll-free phone numbers or have more than 999 user (subscriber) phone numbers that you need to transfer to Skype for Business, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to download the correct forms and send them to us.</span></span>
  > [!NOTE]
  > <span data-ttu-id="89c1e-108">私たちは、u. s. 営業日以内にのみ、パブリックの休日や週末ではなく、電話番号を転送するためのポートの注文を処理します。</span><span class="sxs-lookup"><span data-stu-id="89c1e-108">We process port orders for transferring phone numbers only on U.S. business days and not on public holidays or weekends.</span></span> 
  
## <a name="how-to-create-a-port-order-and-transfer-your-phone-numbers-to-skype-for-business"></a><span data-ttu-id="89c1e-109">ポート注文を作成して、Skype for Business に電話番号を移行する方法</span><span class="sxs-lookup"><span data-stu-id="89c1e-109">How to create a port order and transfer your phone numbers to Skype for Business</span></span>
<span data-ttu-id="89c1e-110"><a name="bk_LNPcountries_1"> </a></span><span class="sxs-lookup"><span data-stu-id="89c1e-110"></span></span>

  > [!NOTE]
  > <span data-ttu-id="89c1e-111">ダイヤルイン会議用ブリッジ、自動応答、またはその他のサービス番号の番号をサービスがあれば、無料電話番号も[管理用の電話番号を参照してくださいビジネス用の Skype に転送する必要がありますが 999 を超える数のユーザー (サブスクライバー) の電話番号組織](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)) 正しい国/地域を選択し、正しいフォームをダウンロード、お知らせします。</span><span class="sxs-lookup"><span data-stu-id="89c1e-111">If you have service numbers for dial-in conferencing bridges, auto attendants or other service numbers, toll-free phone numbers or have more than 999 user (subscriber) phone numbers that you need to transfer to Skype for Business, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)) to select the correct country/region and download the correct forms and send them to us.</span></span>
  
1. <span data-ttu-id="89c1e-112">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="89c1e-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="89c1e-113">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="89c1e-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="89c1e-114">In the left navigation go to **Voice** > **Port orders** > click **Add**.</span><span class="sxs-lookup"><span data-stu-id="89c1e-114">In the left navigation go to **Voice** > **Port orders** > click **Add**.</span></span>
    
4. <span data-ttu-id="89c1e-115">[ **新しい電話番号のポート注文**] ページで、情報を読んで確認してから、[ **作業を開始する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89c1e-115">On the **New Local Number Port Order** page, read the information and then click **Let's get started**.</span></span>
    
5. <span data-ttu-id="89c1e-116">[ **アカウント情報**] ページで以下の情報を入力し、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89c1e-116">On the **Account info** page, enter the following and then click **Next**:</span></span>
    
  - <span data-ttu-id="89c1e-117">[ **アカウント番号**] サービス プロバイダーまたは電話会社のアカウント番号。</span><span class="sxs-lookup"><span data-stu-id="89c1e-117">**Account number** Account number for the service provider or carrier.</span></span>
    
  - <span data-ttu-id="89c1e-p103">[ **請求先電話番号**] は E.164 形式である必要があります (番号の先頭に + 記号が必要です)。たとえば、北アメリカの電話番号には +1XXXYYYZZZZ の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p103">**Billing telephone number** must be in the E.164 format (requires a + sign to prepend the number). For example, for a North America number, use the format +1XXXYYYZZZZ.</span></span>
    
  - <span data-ttu-id="89c1e-120">[ **番号をブロック解除する PIN**] - 現在のサービス プロバイダーまたは電話会社で必要な場合の PIN。</span><span class="sxs-lookup"><span data-stu-id="89c1e-120">**PIN to unblock number** PIN - if needed by your current service provider or carrier.</span></span>
    
  - <span data-ttu-id="89c1e-121">[ **会社名**] 会社または組織の名前。</span><span class="sxs-lookup"><span data-stu-id="89c1e-121">**Company name** This is the name of your company or organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89c1e-p104">[ **会社名**] ボックスに入力できるのは、スペースを含めて 25 文字までです。会社の名前が 25 文字より長い場合は、名前の最初の 25 文字が送信され、番号移行注文が処理されます。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p104">The **Company name** box will only accept 25 characters that includes spaces. If the company's name is longer than 25 characters, the first 25 characters of the name will be submitted and the port order will still be processed.</span></span>
  
  - <span data-ttu-id="89c1e-124">[ **認証する人物**] 認証されたユーザーの名前。</span><span class="sxs-lookup"><span data-stu-id="89c1e-124">**Authorizing person** Authorized user's name.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89c1e-p105">[ **認証する人物**] ボックスに入力できるのは、スペースを含めて 15 文字以下です。認証する人物の名前が 15 文字より長い場合は、名前の最初の 15 文字が発行され、番号移行注文が処理されます。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p105">The **Authorizing person** box will only accept 15 characters that includes spaces. If the authorized person's name is longer than 15 characters, the first 15 characters of the name will be submitted and the port order will still be processed.</span></span>
  
  - <span data-ttu-id="89c1e-p106">[ **サービス アドレス**] アカウントのサービス アドレス。これは、サービス プロバイダーまたは電話会社からの請求書に記載されます。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p106">**Service address** Service address for the account. This will be listed on the bill from your service provider or carrier.</span></span>
    
  - <span data-ttu-id="89c1e-129">サービス アドレスの [ **市区町村**]、[ **都道府県**]、[ **郵便番号**]。</span><span class="sxs-lookup"><span data-stu-id="89c1e-129">**City**, **State**, **Zip** of the service address.</span></span>
    
6. <span data-ttu-id="89c1e-p107">[ **番号**] ページで、移行する電話番号を E.164 形式で入力します。たとえば、北アメリカの電話番号には +1XXXYYYZZZZ の形式を使用します。複数の電話番号はカンマを使用して区切ります。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p107">On the **Numbers** page, enter the phone numbers that you want to transfer in E.164 format. For example, for a North America number, use the format +1XXXYYYZZZZ. Separate multiple phone numbers by using a comma.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89c1e-p108">完全な移行を行う場合は、リストにサービスの請求先電話番号 (BTN) を含める必要があります。部分的な移行を行う場合は、リストからサービスの請求先電話番号 (BTN) を除外します。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p108">If you are doing a full-port, you need to include the service Billing Telephone Number (BTN) in the list. If you are doing a partial-port, leave the service Billing Telephone Number (BTN) out of this list.</span></span> 
  
    <span data-ttu-id="89c1e-p109">完全な移行を行う場合は、[ **現在の電話会社からすべての番号を転送する**] を選びます。部分的な移行を行う場合は、[ **一部の番号のみを転送する**] を選びます。適切な選択を行った後、[ **番号を移行できるかを確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p109">If you are doing a full-port, select **I am transferring all my numbers from my current carrier**. If you are doing a partial-port, select **I'm only transferring some of my numbers**. After you choose the right one, click **Check number portability**.</span></span>
    
7. <span data-ttu-id="89c1e-138">[ **続行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89c1e-138">Click **Proceed**.</span></span>
    
8. <span data-ttu-id="89c1e-139">[ **転送日**] ページの [ **日**] ボックスでは、[ **開始時間**] ボックスで日付を選び、時間 (EST) を選んでから、[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89c1e-139">On the **Transfer date** page, on the **Day** drop down, select the date and under the **Start time** drop down, select the time (EST) and then click **Next**.</span></span>
    
9. <span data-ttu-id="89c1e-p110">[ **承認状**] ページで、各ボックスをオンにします。続いて [ **署名**] ボックスの下で、アカウントを変更することが承認されているユーザーを入力します。これは、[ **アカウント情報**] ページの [ **認証する人物**] で使う同じ名前です。続いて [ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p110">On the **Letter of authorization** page, check each of the following boxes. Then under the **Signature** box, type the person that is authorized to make changes to the account. This is the same name that is used on the **Account Information** page > **Authorizing person**. Then click **Next**.</span></span>
    
10. <span data-ttu-id="89c1e-p111">[ **送信**] ページの [ **その他の通知対象ユーザー**] に必要なユーザーの電子メール アドレスを入力し、[ **移行注文の送信**] をクリックします。移行注文は、[ **移行注文**] ページに一覧表示されます。[ **状態**] 列の下で状態をい表示できます。[ **注文 ID**]、[ **送信済み**]、[ **移行日**] および [ **状態**] などの移行注文の詳細を表示できます。操作ペインで携帯電話会社名などのさらに詳しい情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p111">On the **Submit** page under **Other people to notify** enter any other email address of the people you want to and click **Submit port order**. The port order will now be listed on the **Port orders** page. You can view the status of the order under **Status** column. You can view details of the port order such as the **Order ID**, **Submitted**, **Transfer date** and **Status**. You can see more details for the port order in the Action pane, including the name of the carrier.</span></span>
    
## <a name="what-happens-next"></a><span data-ttu-id="89c1e-149">この後のステップは？</span><span class="sxs-lookup"><span data-stu-id="89c1e-149">What happens next?</span></span>
<span data-ttu-id="89c1e-150"><a name="bk_LNPcountries_1"> </a></span><span class="sxs-lookup"><span data-stu-id="89c1e-150"></span></span>

<span data-ttu-id="89c1e-151">ポート注文を送信し、受信されると、ポート注文を確認する電子メールを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="89c1e-151">Once your port order has been submitted and received, you will be sent an email that verifies your port order.</span></span> 
  
<span data-ttu-id="89c1e-p112">Your port order request will be checked and updated daily and you will be notified of its progress and status in email. If your request is rejected, you will be asked to open a support ticket and in that support ticket we ask that you provide **Port Order ID**. The port order ID can be found in the Skype for Business admin center under **Voice** > **Port orders** > **Order ID** column.</span><span class="sxs-lookup"><span data-stu-id="89c1e-p112">Your port order request will be checked and updated daily and you will be notified of its progress and status in email. If your request is rejected, you will be asked to open a support ticket and in that support ticket we ask that you provide **Port Order ID**. The port order ID can be found in the Skype for Business admin center under **Voice** > **Port orders** > **Order ID** column.</span></span>
  
## <a name="what-if-i-have-problems"></a><span data-ttu-id="89c1e-155">問題が発生した場合</span><span class="sxs-lookup"><span data-stu-id="89c1e-155">What if I have problems?</span></span>
<span data-ttu-id="89c1e-156"><a name="bk_LNPcountries_1"> </a></span><span class="sxs-lookup"><span data-stu-id="89c1e-156"></span></span>

 <span data-ttu-id="89c1e-p113">**サービス アドレスが請求先住所と違っている。注文時に送信した住所情報が、顧客の請求書のコピーと一致するのに拒否されることがあります。** ほとんどの携帯電話会社は、請求先住所ではなくサービス アドレスの情報に基づいて移行情報を特定します。請求書のコピーは請求の記録であるため、移行する電話番号のサービス アドレスと同じ情報が提供されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p113">**The service address isn't the same as the billing address. The address information I submitted on the order matches my customer's bill copy, why is it still rejecting?** Most carriers will identify the porting information based on the service address information, not the billing address. Since a bill copy is a billing record, it may not provide the same information as the service address for the telephone number(s) being ported.</span></span>
  
 <span data-ttu-id="89c1e-p114">**注文の処理に時間がかかり過ぎる場合** Microsoft では、注文の発行から、ステータス更新を知らせるメールの受信、電話番号の移転の確認まで、電話番号の移転を簡潔かつ迅速に処理したいと考えています。注文の処理に時間がかかりすぎると思われ、Skype for Business 管理センターでステータスが完了になっていない場合は、サポート チケットを開いて番号移行注文 ID を入力してください。</span><span class="sxs-lookup"><span data-stu-id="89c1e-p114">**What should I do if my order is taking too long to process?** We want number porting to be very simple and quick process. If your order is taking longer than you think it should and the status still doesn't show as complete in the Skype for Business admin center, please open support ticket and include the port order ID.</span></span>


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="89c1e-163">[米国 (無料の電話番号) 用の承認状 (LOA) (v.2.0)](http://download.microsoft.com/download/F/0/1/F01AE714-0F3C-4D9D-B41A-DFD180EC1622/Letter of Authorization %28LOA%29 for the U.S. (Toll Free numbers) (v.3.1) (en-US).pdf)</span><span class="sxs-lookup"><span data-stu-id="89c1e-163">Related topics</span></span>
<span data-ttu-id="89c1e-164">電話番号の管理フォームのダウンロード</span><span class="sxs-lookup"><span data-stu-id="89c1e-164">[Transferring phone numbers common questions](transferring-phone-numbers-common-questions.md)</span></span>

[<span data-ttu-id="89c1e-165">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="89c1e-165">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="89c1e-166">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="89c1e-166">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="89c1e-167">Skype for Business Online: 緊急通話の免責事項ラベル</span><span class="sxs-lookup"><span data-stu-id="89c1e-167">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
