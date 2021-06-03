---
title: 組織での発信者番号の利用方法
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 発信者番号通知は、CallingLineIdentity と呼ばれるポリシーを使用して、電話システム ユーザーの着信と発信の両方で制御できます。
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723548"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="b9bb3-103">組織での発信者番号の利用方法</span><span class="sxs-lookup"><span data-stu-id="b9bb3-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="b9bb3-104">呼び出し元 ID は、次の 2 つのユーザー向け識別可能な情報で構成されます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="b9bb3-105">電話番号 (通常は CLID または通話回線 ID と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="b9bb3-106">これは、発信者の識別として表示される公衆交換電話番号 (PSTN) です。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="b9bb3-107">呼び出し元の名前 (通常は CNAM と呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="b9bb3-108">発信者番号機能は、PSTN 接続オプション電話システム、すべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="b9bb3-109">Microsoft 通話プラン</span><span class="sxs-lookup"><span data-stu-id="b9bb3-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="b9bb3-110">電話システムのダイレクト ルーティング</span><span class="sxs-lookup"><span data-stu-id="b9bb3-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="b9bb3-111">CallingLineIdentity というポリシーを使用して、着信呼び出しと送信呼び出しの両方の呼び出し元 ID を制御できます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="b9bb3-112">詳細については、「通話回線 [ID」と「通話相手名」を参照してください](more-about-calling-line-id-and-calling-party-name.md)。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="b9bb3-113">発信 PSTN 発信者番号</span><span class="sxs-lookup"><span data-stu-id="b9bb3-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="b9bb3-114">発信 PSTN 発信者番号については、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-114">For the outbound PSTN caller ID, the following options are available.</span></span> 
  
- <span data-ttu-id="b9bb3-115">ユーザーに割り当てられた電話番号。既定です。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-115">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="b9bb3-116">匿名。ユーザーの PSTN 番号のプレゼンテーションを削除することで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-116">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="b9bb3-117">代わりの電話番号。次の場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-117">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="b9bb3-118">通話プランの電話番号インベントリでサービスとして分類される電話番号と無料電話番号。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-118">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="b9bb3-119">通常は、通話キューまたは通話キュー Teams 自動応答割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-119">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="b9bb3-120">直接ルーティングを介したオンプレミスの電話番号。この電話番号は、Teams 自動応答 または通話キューによって使用されるリソース アカウントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-120">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="b9bb3-121">発信 PSTN 通話で設定された発信側名または CNAM。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-121">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="b9bb3-122">詳細については、「ユーザーの発信者 [番号を設定する」を参照してください](./set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-122">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="b9bb3-123">送信呼び出し元 ID のエンド ユーザー制御</span><span class="sxs-lookup"><span data-stu-id="b9bb3-123">End user control of outbound caller ID</span></span>

<span data-ttu-id="b9bb3-124">ユーザーは、EnableUserOverride 属性を **設定することで** 、発信者番号の設定を Anonymous に変更できます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-124">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="b9bb3-125">発信呼び出し元 ID が Anonymous に設定されている場合、EnableUserOverride は効果を持たず、呼び出し元 ID は常に Anonymous に設定されます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-125">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="b9bb3-126">EnableUserOverride の既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-126">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="b9bb3-127">エンド ユーザーは **、[設定 >** 通話] に進み、[発信者番号] で [すべての通話の電話番号とプロファイル情報を非表示にする] を選択して、発信者番号を匿名に **設定できます**。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-127">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="b9bb3-128">備考</span><span class="sxs-lookup"><span data-stu-id="b9bb3-128">Notes</span></span>

<span data-ttu-id="b9bb3-129">以下の点について留意してください。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-129">Keep the following in mind:</span></span>

- <span data-ttu-id="b9bb3-130">発信発信者番号には、次の種類の電話番号を割り当てできません。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-130">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="b9bb3-131">通話プランの電話番号インベントリでユーザーとして分類される電話番号。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-131">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="b9bb3-132">ユーザーに割り当てられている直接ルーティングによるオンプレミスの電話番号。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-132">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="b9bb3-133">オンプレミスSkype for Business Server電話番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-133">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="b9bb3-134">リソース アカウントの電話番号の置き換えの使用は、ユーザーがTeamsします。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-134">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="b9bb3-135">サービス電話番号の置き換えは、オンラインとユーザー Skype for Business両方Teams機能します。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-135">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="b9bb3-136">発信者名は、発信者 ID が LineUri、サービスまたはリソース アカウントの電話番号に置き換わり、発信者が Teams ユーザーである場合にのみ送信されます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-136">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="b9bb3-137">通話パーティー名の最大文字数は 200 文字ですが、ダウンストリーム システムではサポートされる文字が少ない場合があります。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-137">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="b9bb3-138">ダイレクト ルーティングの場合、電話番号の置き換えと通話相手名は FROM SIP ヘッダーで送信されます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-138">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="b9bb3-139">対応する OnlinePstnGateway が ForwardPai = True で構成されている場合、P-ASSERTED-IDENTITY SIP ヘッダーには実際の呼び出し元ユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-139">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="b9bb3-140">EnableUserOverride は、置換が Anonymous に設定されていない限り、ポリシー内の他の設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-140">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="b9bb3-141">たとえば、ポリシー インスタンスがリソース アカウントを使用して置き換え、EnableUserOverride がユーザーによって設定および有効になっているとします。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-141">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="b9bb3-142">この場合、発信呼び出し元 ID はブロックされ、Anonymous が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-142">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="b9bb3-143">ポリシー インスタンスで置換が Anonymous に設定され、EnableUserOverride が設定されている場合、送信呼び出し元 ID はエンド ユーザーの設定に関係なく常に Anonymous になります。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-143">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="b9bb3-144">受信呼び出し元 ID</span><span class="sxs-lookup"><span data-stu-id="b9bb3-144">Inbound caller ID</span></span>

<span data-ttu-id="b9bb3-145">電話システム、着信した外部電話番号が発信者番号として表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-145">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="b9bb3-146">番号が Azure AD または個人の連絡先のユーザーまたは連絡先に関連付けられている場合、Skype for Business クライアントと Teams クライアントには、その情報に基づいて発信者番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-146">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="b9bb3-147">電話番号が Azure AD または個人の連絡先に含されていない場合は、電話会社が提供する表示名が表示されます (使用可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-147">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="b9bb3-148">BlockIncomingCallerID 属性を使用すると、着信した PSTN 通話の発信者番号通知をブロックできます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-148">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="b9bb3-149">この属性を設定することはできますが、ユーザー設定ページではエンド ユーザーには使用できません。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-149">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="b9bb3-150">この設定を有効にすると、着信 PSTN 発信者は匿名からの発信元として表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-150">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="b9bb3-151">受信呼び出し元 ID をブロックするには、「 [ユーザーの発信者番号を設定する」を参照してください](./set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="b9bb3-151">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b9bb3-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9bb3-152">Related topics</span></span>
[<span data-ttu-id="b9bb3-153">電話番号の移行に関するよくある質問</span><span class="sxs-lookup"><span data-stu-id="b9bb3-153">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="b9bb3-154">通話プランで使用されるさまざまな種類の電話番号</span><span class="sxs-lookup"><span data-stu-id="b9bb3-154">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="b9bb3-155">組織の電話番号を管理する</span><span class="sxs-lookup"><span data-stu-id="b9bb3-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="b9bb3-156">緊急通話の利用条件</span><span class="sxs-lookup"><span data-stu-id="b9bb3-156">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="b9bb3-157">[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="b9bb3-157">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
