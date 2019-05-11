---
title: 先進認証でサポートされる Skype for Business トポロジ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: この記事では、どのオンラインおよびオンプレミス トポロジが Skype for Business での先進認証でサポートされるかを、各トポロジに適用されるセキュリティ機能とともに一覧表示します。
ms.openlocfilehash: ca7c89ce8f7f7681463bbdc87518f42130bf310e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929056"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a><span data-ttu-id="399da-103">Skype for Business topologies supported with Modern Authentication</span><span class="sxs-lookup"><span data-stu-id="399da-103">Skype for Business topologies supported with Modern Authentication</span></span>
 
<span data-ttu-id="399da-104">この記事では、どのオンラインおよびオンプレミス トポロジが Skype for Business での先進認証でサポートされるかを、各トポロジに適用されるセキュリティ機能とともに一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="399da-104">This article lists what online and on-premises topologies are supported with Modern Authentication in Skype for Business, as well as security features that apply to each topology.</span></span>
  
## <a name="modern-authentication-in-skype-for-business"></a><span data-ttu-id="399da-105">Skype for Business での先進認証</span><span class="sxs-lookup"><span data-stu-id="399da-105">Modern Authentication in Skype for Business</span></span>

<span data-ttu-id="399da-p101">Skype for Business は先進認証のセキュリティ上の長所を活用します。Skype for Business は Exchange と密接に動作するため、Skype for Business クライアントのユーザーに表示されるログイン動作は、MA status of Exchange の MA の状態による影響も受けます。これは、Skype for Business の分割ドメイン ハイブリッドを利用している場合にも適用されます。これは動きのある部分が多いですが、ここでの目的としてはサポートされるトポロジを簡単に見ることができる一覧を提供することです。</span><span class="sxs-lookup"><span data-stu-id="399da-p101">Skype for Business can leverage security advantages of Modern Authentication. Because Skype for Business works closely with Exchange, the login behaviour Skype for Business client users will see will also be effected by the MA status of Exchange. This will also apply if you have a Skype for Business split-domain hybrid. That's a lot of moving parts, but the aim here is an easy to visualize list of supported topologies.</span></span>
  
<span data-ttu-id="399da-110">Skype for Business、Skype for Business Online、Exchange Server、Exchange Online の場合に、どのトポロジが MA でサポートされますか?</span><span class="sxs-lookup"><span data-stu-id="399da-110">Given Skype for Business, Skype for Business online, Exchange Server, and Exchange online, what topologies are supported with MA?</span></span>
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a><span data-ttu-id="399da-111">Skype for Business でサポートされる MA トポロジ</span><span class="sxs-lookup"><span data-stu-id="399da-111">Supported MA topologies in Skype for Business</span></span>

<span data-ttu-id="399da-112">2 つのサーバー アプリケーション、MA によって使用される Skype for Business トポロジを含む、2 つの Office 365 ワークロードで構成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="399da-112">There are potentially two server applications, and two Office 365 workloads, involved with Skype for Business topologies used by MA.</span></span>
  
- <span data-ttu-id="399da-113">Skype ビジネス サーバー (CU 5) 設置</span><span class="sxs-lookup"><span data-stu-id="399da-113">Skype for Business server (CU 5) on-premises</span></span>
    
- <span data-ttu-id="399da-114">Skype for Business Online (SFBO)</span><span class="sxs-lookup"><span data-stu-id="399da-114">Skype for Business online (SFBO)</span></span>
    
- <span data-ttu-id="399da-115">Exchange Server オンプレミス</span><span class="sxs-lookup"><span data-stu-id="399da-115">Exchange server on-premises</span></span>
    
- <span data-ttu-id="399da-116">Exchange Server Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="399da-116">Exchange server online (EXO)</span></span>
    
<span data-ttu-id="399da-p102">MA のもう 1 つの重要な部分は、ユーザーの認証 (authN) と承認 (authZ) がどこで発生するかを理解していることです。次の 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="399da-p102">Another important part of MA is knowing where the authentication (authN) and authorization (authZ) of users will take place. The two options are:</span></span>
  
- <span data-ttu-id="399da-119">Azure AD、Microsoft Cloud でオンライン</span><span class="sxs-lookup"><span data-stu-id="399da-119">Azure AD, online in the Microsoft Cloud</span></span>
    
- <span data-ttu-id="399da-120">Active Directory フェデレーション サーバー (ADFS) オンプレミス</span><span class="sxs-lookup"><span data-stu-id="399da-120">Active Directory Federation Server (ADFS) on-premises</span></span>
    
<span data-ttu-id="399da-121">EXO と SFBO と Azure AD は、雲の中で、次のようになる少しようと Exchange Server (EXCH) およびビジネス サーバー (デバイス) の prem. 上の Skype</span><span class="sxs-lookup"><span data-stu-id="399da-121">So it looks a bit like this, with EXO and SFBO in the Cloud with Azure AD, and Exchange Server (EXCH) and Skype for Business server (SFB) on-prem.</span></span>
  
![すべてのアプリケーション (Exchange および Skype for Business) とワークロード (EXO および SFBO)、および MA をオンにするときに関与させられる両方の認証サーバー (ADFS および evoSTS) の例。](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
<span data-ttu-id="399da-p103">サポートされるトポロジを以下に示します。これらの図では、次の重要な点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="399da-p103">Here are the supported topologies. Please note the key for the graphics:</span></span>
  
- <span data-ttu-id="399da-125">薄い、またはグレー表示のアイコンは、シナリオで使用されていません。</span><span class="sxs-lookup"><span data-stu-id="399da-125">If the icon is dimmed or grey, it is not used in the scenario.</span></span>
    
- <span data-ttu-id="399da-126">EXO は Exchange Online です。</span><span class="sxs-lookup"><span data-stu-id="399da-126">EXO is Exchange Online.</span></span>
    
- <span data-ttu-id="399da-127">SFBO は Skype for Business Online です。</span><span class="sxs-lookup"><span data-stu-id="399da-127">SFBO is Skype for Business Online.</span></span>
    
- <span data-ttu-id="399da-128">EXCH は Exchange オンプレミスです。</span><span class="sxs-lookup"><span data-stu-id="399da-128">EXCH is Exchange on-premises.</span></span>
    
- <span data-ttu-id="399da-129">SFB は Skype for Business オンプレミスです。</span><span class="sxs-lookup"><span data-stu-id="399da-129">SFB is Skype for Business on-premises.</span></span>
    
- <span data-ttu-id="399da-130">認証サーバーは三角形で表されます。たとえば、Azure AD は後ろに雲マークが付いた三角形になります。</span><span class="sxs-lookup"><span data-stu-id="399da-130">Authorizing servers are represented by triangles, for example, the Azure AD is a triangle with a cloud behind it.</span></span>
    
- <span data-ttu-id="399da-131">矢印は、クライアントが指定されたサーバー リソースに到達しようと試みるときに使用する認証サーバーを指します。</span><span class="sxs-lookup"><span data-stu-id="399da-131">Arrows point at the authorizing server that will be used when clients try to reach the specified server resource.</span></span>
    
<span data-ttu-id="399da-132">最初に、オンプレミスのみ、クラウドのみの両方のトポロジの Skype for Business での MA について見ていきましょう。</span><span class="sxs-lookup"><span data-stu-id="399da-132">First, let's cover MA with Skype for Business in both On-premises-only or Cloud-only topologies.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="399da-133">ビジネス オンラインの Skype での最新の認証を設定する準備ができているでしょうか。</span><span class="sxs-lookup"><span data-stu-id="399da-133">Are you ready to set up Modern Authentication in Skype for Business Online?</span></span> <span data-ttu-id="399da-134">この機能を有効にする手順は[ここで](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)。</span><span class="sxs-lookup"><span data-stu-id="399da-134">The steps to enable this feature are right [here](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span> 
  
|<span data-ttu-id="399da-135">トポロジの名前</span><span class="sxs-lookup"><span data-stu-id="399da-135">Topology name</span></span>  <br/> |<span data-ttu-id="399da-136">例</span><span class="sxs-lookup"><span data-stu-id="399da-136">Example</span></span>  <br/> |<span data-ttu-id="399da-137">説明</span><span class="sxs-lookup"><span data-stu-id="399da-137">Description</span></span>  <br/> |<span data-ttu-id="399da-138">サポート対象</span><span class="sxs-lookup"><span data-stu-id="399da-138">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="399da-139">クラウドのみ</span><span class="sxs-lookup"><span data-stu-id="399da-139">Cloud only</span></span>  <br/> |![MA トポロジのある SFB をサポート (クラウド限定)。](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)<span data-ttu-id="399da-141">ユーザーの所属/メールボックスの場所: オンライン </span><span class="sxs-lookup"><span data-stu-id="399da-141">Users homed/mailboxes located: Online</span></span>  <br/> |<span data-ttu-id="399da-142">MA は EXO と SFBO の両方でオンです。</span><span class="sxs-lookup"><span data-stu-id="399da-142">MA is on for both EXO and SFBO.</span></span>  <br/> <span data-ttu-id="399da-143">このため、認証サーバーは Azure AD です。</span><span class="sxs-lookup"><span data-stu-id="399da-143">Therefore, the authorization server is Azure AD.</span></span>  <br/> |<span data-ttu-id="399da-144">多要素認証 (MFA)、クライアント証明書を使用した認証 (CBA)、Intune での条件付きアクセス (CA)/モバイル アプリケーション管理 (MAM)。</span><span class="sxs-lookup"><span data-stu-id="399da-144">Multi-factor authentication (MFA), Client-certificate based authentication (CBA), Conditional Access (CA)/Mobile Application Management (MAM) with Intune.</span></span> <span data-ttu-id="399da-145">\*</span><span class="sxs-lookup"><span data-stu-id="399da-145"></span></span>  <br/> |
|<span data-ttu-id="399da-146">オンプレミスのみ</span><span class="sxs-lookup"><span data-stu-id="399da-146">On-prem only</span></span>  <br/> |![MA トポロジがある SFB をサポート (オンプレミス限定)。](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)<span data-ttu-id="399da-148">ユーザーの所属/メールボックスの場所: オンプレミス</span><span class="sxs-lookup"><span data-stu-id="399da-148">Users homed/mailboxes located: On-premises</span></span>  <br/> |<span data-ttu-id="399da-149">MA が SFB オンプレミスでオンになります。</span><span class="sxs-lookup"><span data-stu-id="399da-149">MA is on for SFB on-premises.</span></span>  <br/> <span data-ttu-id="399da-150">このため、認証サーバーは ADFS です。</span><span class="sxs-lookup"><span data-stu-id="399da-150">Therefore, the authorization server is ADFS.</span></span>  <br/> <span data-ttu-id="399da-151">構成の詳細についてを参照してください[この記事](https://technet.microsoft.com/en-us/library/mt710548.aspx)。</span><span class="sxs-lookup"><span data-stu-id="399da-151">For configuration details, please see [this article.](https://technet.microsoft.com/en-us/library/mt710548.aspx)</span></span> <br/> |<span data-ttu-id="399da-p106">MFA (Windows デスクトップのみ。モバイル クライアントはサポートされません)。Exchange 統合の機能はサポート対象外です。</span><span class="sxs-lookup"><span data-stu-id="399da-p106">MFA (Windows Desktop only - mobile clients are not supported). No Exchange integration features.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="399da-154">プロンプトの数を減らせるように、Skype for Business と Exchange (およびその他のオンライン上の同等製品) にわたり MA の状態が同じであることを推奨します。</span><span class="sxs-lookup"><span data-stu-id="399da-154">It's recommended that the MA state be the same across Skype for Business and Exchange (and their online counterparts) to reduce the number of prompts.</span></span> 
  
<span data-ttu-id="399da-p107">混合トポロジでは、SFB 分割ドメインのハイブリッドの組み合わせが含まれます。現在サポートされている混合トポロジを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="399da-p107">Mixed topologies involve combinations of SFB split-domain hybrids. These are the Mixed topologies currently supported:</span></span>
  
|<span data-ttu-id="399da-157">トポロジの名前</span><span class="sxs-lookup"><span data-stu-id="399da-157">Topology name</span></span>  <br/> |<span data-ttu-id="399da-158">例</span><span class="sxs-lookup"><span data-stu-id="399da-158">Example</span></span>  <br/> |<span data-ttu-id="399da-159">説明</span><span class="sxs-lookup"><span data-stu-id="399da-159">Description</span></span>  <br/> |<span data-ttu-id="399da-160">サポート対象</span><span class="sxs-lookup"><span data-stu-id="399da-160">Supported</span></span>  <br/> |
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="399da-161">混合 1</span><span class="sxs-lookup"><span data-stu-id="399da-161">Mixed 1</span></span>  <br/> |![混合型 1 (EXO + SFB) の MA トポロジのある SFB をサポート。](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> <span data-ttu-id="399da-163">ユーザーの所属/メールボックスの場所: EXO および SFB</span><span class="sxs-lookup"><span data-stu-id="399da-163">Users homed/mailboxes located: EXO and SFB</span></span>  <br/> |<span data-ttu-id="399da-164">MA は SFB で有効ではありません。このトポロジで利用できる SFB の MA 機能はありません。</span><span class="sxs-lookup"><span data-stu-id="399da-164">MA is not enabled for SFB; no SFB MA features available in this topology.</span></span>  <br/> |<span data-ttu-id="399da-165">SFB の MA 機能はサポート対象外です。</span><span class="sxs-lookup"><span data-stu-id="399da-165">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="399da-166">混合 2</span><span class="sxs-lookup"><span data-stu-id="399da-166">Mixed 2</span></span>  <br/> |![SFBO にオンプレミスの EXCH と連動する MA が加わった S4B 混合型トポロジ 2 のある MA をサポート。](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> <span data-ttu-id="399da-168">ユーザーの所属/メールボックスの場所: EXCH および SFB</span><span class="sxs-lookup"><span data-stu-id="399da-168">Users homed/mailboxes located: EXCH and SFBO</span></span>  <br/> |<span data-ttu-id="399da-169">MA は SFBO のみでオンになります。</span><span class="sxs-lookup"><span data-stu-id="399da-169">MA is on for SFBO only.</span></span> <span data-ttu-id="399da-170">認証サーバーは Azure AD SFBO、EXCH オンプレミスの AD に置かれているユーザーです。</span><span class="sxs-lookup"><span data-stu-id="399da-170">The authorization server is Azure AD for users homed in SFBO, but AD for EXCH on-premises.</span></span>  <br/> |<span data-ttu-id="399da-171">MFA、同行では、CA/Intune で MAM です。\*</span><span class="sxs-lookup"><span data-stu-id="399da-171">MFA, CBA, CA/MAM with Intune.\*</span></span>  <br/> |
|<span data-ttu-id="399da-172">混合 3</span><span class="sxs-lookup"><span data-stu-id="399da-172">Mixed 3</span></span>  <br/> |![SFB がある MA、MA がオンの EXO、さらに EXCH とオンプレミスの SFB をサポート。](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> <span data-ttu-id="399da-174">ユーザーの所属/メールボックスの場所: EXO + SFB または EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="399da-174">Users homed/mailboxes located: EXO + SFB, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="399da-175">このトポロジでは利用できる SFB の MA 機能はありません</span><span class="sxs-lookup"><span data-stu-id="399da-175">No SFB MA features available in this topology</span></span>  <br/> |<span data-ttu-id="399da-176">SFB の MA 機能はサポート対象外です。</span><span class="sxs-lookup"><span data-stu-id="399da-176">No MA features for SFB.</span></span>  <br/> |
|<span data-ttu-id="399da-177">混合 4</span><span class="sxs-lookup"><span data-stu-id="399da-177">Mixed 4</span></span>  <br/> |![SFB がある MA、MA がオンの SFBO、さらに EXCH と SFB をサポート。](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> <span data-ttu-id="399da-179">ユーザーの所属/メールボックスの場所: EXCH + SFBO または EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="399da-179">Users homed/mailboxes located: EXCH +SFBO or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="399da-180">MA が SFBO のでは、そのため、認証サーバーは、Azure AD SFBO に置かれているユーザーのです。</span><span class="sxs-lookup"><span data-stu-id="399da-180">MA is on for SFBO, therefore the authorization server is Azure AD for users homed in SFBO.</span></span> <span data-ttu-id="399da-181">デバイスと EXO prem のユーザーは、AD を使用します。</span><span class="sxs-lookup"><span data-stu-id="399da-181">On-prem users in SFB and EXO use AD.</span></span>  <br/> |<span data-ttu-id="399da-182">MFA、同行では、CA/Intune オンラインのユーザーのみに MAM です。\*</span><span class="sxs-lookup"><span data-stu-id="399da-182">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="399da-183">混合 5</span><span class="sxs-lookup"><span data-stu-id="399da-183">Mixed 5</span></span>  <br/> |![SFB の MA、MA がオンの EXO、MA がある SFBO、さらに EXCH とオンプレミスの SFB をサポート。](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> <span data-ttu-id="399da-185">ユーザーの所属/メールボックスの場所: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="399da-185">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="399da-186">MA は EXO と SFBO、したがって SFBO; に置かれているユーザーの認証サーバーは、Azure AD です。EXCH とデバイスの prem のユーザーは、AD を使用します。</span><span class="sxs-lookup"><span data-stu-id="399da-186">MA is on in both EXO and SFBO, therefore the authorization server is Azure AD for users homed in SFBO; on-prem users in EXCH and SFB use AD.</span></span>  <br/> |<span data-ttu-id="399da-187">MFA、同行では、CA/Intune オンラインのユーザーのみに MAM です。\*</span><span class="sxs-lookup"><span data-stu-id="399da-187">MFA, CBA, CA/MAM with Intune for online users only.\*</span></span>  <br/> |
|<span data-ttu-id="399da-188">混合 6</span><span class="sxs-lookup"><span data-stu-id="399da-188">Mixed 6</span></span>  <br/> |![Mixed 6 トポロジでは、先進認証は 4 つの可能な場所すべてにおいてオンになります。先進認証の場合には、理想的な状況です。](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> <span data-ttu-id="399da-190">ユーザーの所属/メールボックスの場所: EXO + SFBO、EXO + SFB、EXCH + SFBO、または EXCH + SFB</span><span class="sxs-lookup"><span data-stu-id="399da-190">Users homed/mailboxes located: EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB</span></span>  <br/> |<span data-ttu-id="399da-191">MA は、すべての場所では、そのため、認証サーバーはすべてのユーザーは Azure AD。</span><span class="sxs-lookup"><span data-stu-id="399da-191">MA is on everywhere, therefore the authorization server is Azure AD for all users.</span></span> <span data-ttu-id="399da-192">(オンラインと設置型)</span><span class="sxs-lookup"><span data-stu-id="399da-192">(online and on-premises)</span></span>  <br/>  <span data-ttu-id="399da-193">参照してください[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)の展開手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="399da-193">Please see [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) for deployment steps.</span></span> <br/> |<span data-ttu-id="399da-194">MFA、同行および CA と MAM (Intune) 経由ですべてのユーザー用です。</span><span class="sxs-lookup"><span data-stu-id="399da-194">MFA, CBA and CA/MAM (via Intune) for all users.</span></span>  <br/> |
   
<span data-ttu-id="399da-195">\*-MFA は、Windows デスクトップ、MAC、iOS、Android デバイス、および Windows の電話は含まれています。同行には、Windows デスクトップ、iOS および Android デバイスが含まれています。CA と MAM Intune とには、Android と iOS のデバイスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="399da-195">\* - MFA includes Windows Desktop, MAC, iOS, Android devices, and Windows Phones; CBA includes Windows Desktop, iOS and Android devices; CA/MAM with Intune, includes Android and iOS devices.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="399da-196">一部の場合において、ユーザーに対して**複数のプロンプト**が表示される可能性があることに注意してください。これは特に、すべてのバージョンの混合トポロジでの場合と同様に、クライアントで必要され要求されるすべてのサーバー リソースにわたり MA の状態が同じではない場合に発生します。 </span><span class="sxs-lookup"><span data-stu-id="399da-196">It's very important to note that users may see **multiple prompts** in some cases, notably where the MA state is not the same across all the server resources that clients may need and request, as is the case with all versions of the Mixed topologies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="399da-197">場合によっては注意してください (具体的には混合し、1、3、5) [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online)のレジストリ キーは、Windows デスクトップ クライアントの構成が適切に設定しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="399da-197">Also note that in some cases (Mixed 1, 3, and 5 specifically) an [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) registry key must be set for proper configuration for Windows Desktop Clients.</span></span>
  

