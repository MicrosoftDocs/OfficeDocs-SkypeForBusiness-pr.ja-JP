---
title: 電話システムのダイレクト ルーティング
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: ダイレクト ルーティング プロトコル
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04e9507595ef721ced5d47eb58646559601c5cab
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899128"
---
# <a name="direct-routing---sip-protocol"></a><span data-ttu-id="6839f-103">ダイレクト ルーティング - SIP プロトコル</span><span class="sxs-lookup"><span data-stu-id="6839f-103">Direct Routing - SIP protocol</span></span>

<span data-ttu-id="6839f-104">この記事では、ダイレクト ルーティングでセッション開始プロトコル (SIP) を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6839f-104">This article describes how Direct Routing implements the Session Initiation Protocol (SIP).</span></span> <span data-ttu-id="6839f-105">セッション ボーダー コントローラー (SBC) と SIP プロキシの間でトラフィックを適切にルーティングするには、一部の SIP パラメーターに特定の値が必要です。</span><span class="sxs-lookup"><span data-stu-id="6839f-105">To properly route traffic between a Session Border Controller (SBC) and the SIP proxy, some SIP parameters must have specific values.</span></span> <span data-ttu-id="6839f-106">この記事は、オンプレミスの SBC と SIP プロキシ サービス間の接続の構成を担当する音声管理者を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="6839f-106">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a><span data-ttu-id="6839f-107">受信要求の処理: テナントとユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="6839f-107">Processing the incoming request: finding the tenant and user</span></span>

<span data-ttu-id="6839f-108">着信または送信呼び出しを処理する前に、SIP プロキシと SBC の間で OPTIONS メッセージが交換されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-108">Before an incoming or outbound call can be processed, OPTIONS messages are exchanged between SIP Proxy and the SBC.</span></span> <span data-ttu-id="6839f-109">これらの OPTIONS メッセージにより、SIP プロキシは SBC に許可される機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="6839f-109">These OPTIONS messages allow SIP Proxy to provide the allowed capabilities to SBC.</span></span> <span data-ttu-id="6839f-110">OPTIONS ネゴシエーションが成功し (200OK 応答)、SBC と SIP プロキシ間の通信を可能にし、呼び出しを確立することが重要です。</span><span class="sxs-lookup"><span data-stu-id="6839f-110">It is important for OPTIONS negotiation to be successful (200OK response), allowing for further communication between SBC and SIP Proxy for establishing calls.</span></span> <span data-ttu-id="6839f-111">SIP プロキシへの OPTIONS メッセージの SIP ヘッダーを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="6839f-111">The SIP headers in an OPTIONS messages to SIP Proxy are provided as an example below:</span></span>

| <span data-ttu-id="6839f-112">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="6839f-112">Parameter name</span></span> | <span data-ttu-id="6839f-113">値の例</span><span class="sxs-lookup"><span data-stu-id="6839f-113">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="6839f-114">Request-URI</span><span class="sxs-lookup"><span data-stu-id="6839f-114">Request-URI</span></span> | <span data-ttu-id="6839f-115">OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="6839f-115">OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0</span></span> |
| <span data-ttu-id="6839f-116">ヘッダー経由</span><span class="sxs-lookup"><span data-stu-id="6839f-116">Via Header</span></span> | <span data-ttu-id="6839f-117">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="6839f-117">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="6839f-118">Max-Forwards ヘッダー</span><span class="sxs-lookup"><span data-stu-id="6839f-118">Max-Forwards header</span></span> | <span data-ttu-id="6839f-119">Max-Forwards:68</span><span class="sxs-lookup"><span data-stu-id="6839f-119">Max-Forwards:68</span></span> |
| <span data-ttu-id="6839f-120">ヘッダーから</span><span class="sxs-lookup"><span data-stu-id="6839f-120">From Header</span></span> | <span data-ttu-id="6839f-121">From Header From: <sip:sbc1.adatum.biz:5058></span><span class="sxs-lookup"><span data-stu-id="6839f-121">From Header From: <sip:sbc1.adatum.biz:5058></span></span> |
| <span data-ttu-id="6839f-122">To Header</span><span class="sxs-lookup"><span data-stu-id="6839f-122">To Header</span></span> | <span data-ttu-id="6839f-123">宛先： <sip:sip.pstnhub.microsoft.com:5061></span><span class="sxs-lookup"><span data-stu-id="6839f-123">To: <sip:sip.pstnhub.microsoft.com:5061></span></span> |
| <span data-ttu-id="6839f-124">CSeq ヘッダー</span><span class="sxs-lookup"><span data-stu-id="6839f-124">CSeq header</span></span> | <span data-ttu-id="6839f-125">CSeq: 1 INVITE</span><span class="sxs-lookup"><span data-stu-id="6839f-125">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="6839f-126">連絡先ヘッダー</span><span class="sxs-lookup"><span data-stu-id="6839f-126">Contact Header</span></span> | <span data-ttu-id="6839f-127">連絡先: <sip:sbc1.adatum.biz:50588;transport=tls></span><span class="sxs-lookup"><span data-stu-id="6839f-127">Contact: <sip:sbc1.adatum.biz:50588;transport=tls></span></span> |

> [!NOTE]
> <span data-ttu-id="6839f-128">SIP ヘッダーには、使用されている SIP URI に userinfo が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6839f-128">The SIP headers do not contain userinfo in the SIP URI in use.</span></span> <span data-ttu-id="6839f-129">RFC [3261、セクション 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1)のように、URI の userinfo 部分は省略可能であり、宛先ホストにユーザーの考え方が存在しない場合や、hosst 自体が識別されるリソースである場合は存在しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-129">As per [RFC 3261, section 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1), the userinfo part of a URI is optional and MAY be absent when the destination host does not have a notion of users or when the hosst itself is the resource being identified.</span></span> <span data-ttu-id="6839f-130">@ 記号が SIP URI に存在する場合、ユーザー フィールドは空にすることはできません (MUST NOT)。</span><span class="sxs-lookup"><span data-stu-id="6839f-130">If the @ sign is present in a SIP URI, the user field MUST NOT be empty.</span></span>

<span data-ttu-id="6839f-131">着信呼び出しでは、SIP プロキシは、呼び出しの宛先であるテナントを検索し、このテナント内の特定のユーザーを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-131">On an incoming call, the SIP proxy needs to find the tenant to which the call is destined and find the specific user within this tenant.</span></span> <span data-ttu-id="6839f-132">テナント管理者は、複数のテナントで非 DID 番号 (+1001 など) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6839f-132">The tenant administrator might configure non-DID numbers, for example +1001, in multiple tenants.</span></span> <span data-ttu-id="6839f-133">そのため、複数の組織または組織で DID 以外の番号が同じになる可能性があるため、番号検索を実行する特定のテナントを見Microsoft 365重要Office 365。</span><span class="sxs-lookup"><span data-stu-id="6839f-133">Therefore, it is important to find the specific tenant on which to perform the number lookup because the non-DID numbers might be the same in multiple Microsoft 365 or Office 365 organizations.</span></span>  

<span data-ttu-id="6839f-134">このセクションでは、SIP プロキシがテナントとユーザーを検索し、受信接続で SBC の認証を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6839f-134">This section describes how the SIP proxy finds the tenant and the user, and performs authentication of the SBC on the incoming connection.</span></span>

<span data-ttu-id="6839f-135">着信通話での SIP 招待メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6839f-135">The following is an example of the SIP Invite message on an incoming call:</span></span>

| <span data-ttu-id="6839f-136">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="6839f-136">Parameter name</span></span> | <span data-ttu-id="6839f-137">値の例</span><span class="sxs-lookup"><span data-stu-id="6839f-137">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="6839f-138">Request-URI</span><span class="sxs-lookup"><span data-stu-id="6839f-138">Request-URI</span></span> | <span data-ttu-id="6839f-139">SIP sip:+18338006777@sip.pstnhub.microsoft.com /2.0 を招待する</span><span class="sxs-lookup"><span data-stu-id="6839f-139">INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0</span></span> |
| <span data-ttu-id="6839f-140">ヘッダー経由</span><span class="sxs-lookup"><span data-stu-id="6839f-140">Via Header</span></span> | <span data-ttu-id="6839f-141">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="6839f-141">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="6839f-142">Max-Forwards ヘッダー</span><span class="sxs-lookup"><span data-stu-id="6839f-142">Max-Forwards header</span></span> | <span data-ttu-id="6839f-143">Max-Forwards:68</span><span class="sxs-lookup"><span data-stu-id="6839f-143">Max-Forwards:68</span></span> |
| <span data-ttu-id="6839f-144">ヘッダーから</span><span class="sxs-lookup"><span data-stu-id="6839f-144">From Header</span></span> | <span data-ttu-id="6839f-145">From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span><span class="sxs-lookup"><span data-stu-id="6839f-145">From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span></span> |
| <span data-ttu-id="6839f-146">To Header</span><span class="sxs-lookup"><span data-stu-id="6839f-146">To Header</span></span> | <span data-ttu-id="6839f-147">To: sip:+183338006777@sbc1.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="6839f-147">To: sip:+183338006777@sbc1.adatum.biz</span></span> | 
| <span data-ttu-id="6839f-148">CSeq ヘッダー</span><span class="sxs-lookup"><span data-stu-id="6839f-148">CSeq header</span></span> | <span data-ttu-id="6839f-149">CSeq: 1 INVITE</span><span class="sxs-lookup"><span data-stu-id="6839f-149">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="6839f-150">連絡先ヘッダー</span><span class="sxs-lookup"><span data-stu-id="6839f-150">Contact Header</span></span> | <span data-ttu-id="6839f-151">連絡先: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls></span><span class="sxs-lookup"><span data-stu-id="6839f-151">Contact: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls></span></span> | 

<span data-ttu-id="6839f-152">招待を受信すると、SIP プロキシは次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6839f-152">On receiving the invite, the SIP proxy performs the following steps:</span></span>

1. <span data-ttu-id="6839f-153">証明書を確認します。</span><span class="sxs-lookup"><span data-stu-id="6839f-153">Check the certificate.</span></span> <span data-ttu-id="6839f-154">最初の接続では、ダイレクト ルーティング サービスは、Contact ヘッダーに表示される FQDN 名を受け取り、提示された証明書の共通名またはサブジェクトの代替名と一致します。</span><span class="sxs-lookup"><span data-stu-id="6839f-154">On the initial connection, the Direct Routing service takes the FQDN name presented in the Contact header and matches it to the Common Name or Subject Alternative name of the presented certificate.</span></span> <span data-ttu-id="6839f-155">SBC 名は、次のいずれかのオプションと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-155">The SBC name must match one of the following options:</span></span>

   - <span data-ttu-id="6839f-156">オプション 1。</span><span class="sxs-lookup"><span data-stu-id="6839f-156">Option 1.</span></span> <span data-ttu-id="6839f-157">Contact ヘッダーに表示される完全な FQDN 名は、提示された証明書の共通名/サブジェクトの代替名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-157">The full FQDN name presented in the Contact header must match the Common Name/Subject Alternative name of the presented certificate.</span></span>  

   - <span data-ttu-id="6839f-158">オプション 2.</span><span class="sxs-lookup"><span data-stu-id="6839f-158">Option 2.</span></span> <span data-ttu-id="6839f-159">連絡先ヘッダーに表示される FQDN 名のドメイン部分 (FQDN 名 sbc1.adatum.biz の adatum.biz など) は、共通名/サブジェクトの代替名 (\*.adatum.biz など) のワイルドカード値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-159">The domain portion of the FQDN name presented in the Contact header (for example adatum.biz of the FQDN name sbc1.adatum.biz) must match the wildcard value in Common Name/Subject Alternative Name (for example \*.adatum.biz).</span></span>

2. <span data-ttu-id="6839f-160">Contact ヘッダーに表示される完全な FQDN 名を使用してテナントを検索してみてください。</span><span class="sxs-lookup"><span data-stu-id="6839f-160">Try to find a tenant using the full FQDN name presented in the Contact header.</span></span>  

   <span data-ttu-id="6839f-161">連絡先ヘッダー (sbc1.adatum.biz) の FQDN 名が、任意の組織または組織の DNS Microsoft 365登録Office 365します。</span><span class="sxs-lookup"><span data-stu-id="6839f-161">Check if the FQDN name from the Contact header (sbc1.adatum.biz) is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="6839f-162">見つかった場合、ユーザーの参照は、SBC FQDN がドメイン名として登録されているテナントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-162">If found, the lookup of the user is performed in the tenant that has the SBC FQDN registered as a Domain name.</span></span> <span data-ttu-id="6839f-163">見つからない場合は、手順 3 が適用されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-163">If not found, Step 3 applies.</span></span>   

3. <span data-ttu-id="6839f-164">手順 3 は、手順 2 が失敗した場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-164">Step 3 only applies if Step 2 failed.</span></span> 

   <span data-ttu-id="6839f-165">[連絡先] ヘッダー (FQDN: sbc12.adatum.biz、ホスト部分を削除した後に adatum.biz) に表示されている FQDN からホスト部分を削除し、この名前が Microsoft 365 または Office 365 組織の DNS 名として登録されていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="6839f-165">Remove the host portion from the FQDN, presented in the Contact header (FQDN: sbc12.adatum.biz, after removing the host portion: adatum.biz), and check if this name is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="6839f-166">見つかった場合、ユーザー参照は、このテナントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-166">If found, the user lookup is performed in this tenant.</span></span> <span data-ttu-id="6839f-167">見つからない場合、呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6839f-167">If not found, the call fails.</span></span>

4. <span data-ttu-id="6839f-168">要求 URI に示されている電話番号を使用して、手順 2 または 3 で見つかったテナント内で逆引き番号参照を実行します。</span><span class="sxs-lookup"><span data-stu-id="6839f-168">Using the phone number presented in the Request-URI, perform the reverse number lookup within the tenant found in Step 2 or 3.</span></span> <span data-ttu-id="6839f-169">表示された電話番号を、前の手順で見つかったテナント内のユーザー SIP URI と一致します。</span><span class="sxs-lookup"><span data-stu-id="6839f-169">Match the presented phone number to a user SIP URI within the tenant found on the previous step.</span></span>

5. <span data-ttu-id="6839f-170">トランク設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="6839f-170">Apply trunk settings.</span></span> <span data-ttu-id="6839f-171">この SBC のテナント管理者によって設定されたパラメーターを見つける。</span><span class="sxs-lookup"><span data-stu-id="6839f-171">Find the parameters set by the tenant admin for this SBC.</span></span>

   <span data-ttu-id="6839f-172">Microsoft は、Microsoft SIP プロキシとペアの SBC の間にサードパーティの SIP プロキシまたはユーザー エージェント サーバーを持つことをサポートしません。これは、ペアの SBC によって作成された要求 URI を変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-172">Microsoft does not support having a third-party SIP proxy or User Agent Server between the Microsoft SIP proxy and the paired SBC, which might modify the Request URI created by the paired SBC.</span></span>

   <span data-ttu-id="6839f-173">1 つの SBC が多数のテナント (運送業者のシナリオ) に相互接続されているシナリオに必要な 2 つの参照 (手順 2 と 3) の要件については、この記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="6839f-173">The requirements for the two lookups (steps 2 and 3) needed for the scenario where one SBC is interconnected to many tenants (carrier scenario) are covered later in this article.</span></span>

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a><span data-ttu-id="6839f-174">連絡先ヘッダーと要求 URI の詳細な要件</span><span class="sxs-lookup"><span data-stu-id="6839f-174">Detailed requirements for Contact header and Request-URI</span></span>

#### <a name="contact-header"></a><span data-ttu-id="6839f-175">連絡先ヘッダー</span><span class="sxs-lookup"><span data-stu-id="6839f-175">Contact header</span></span>

<span data-ttu-id="6839f-176">Microsoft SIP プロキシへのすべての着信 SIP メッセージ (オプション、招待) について、Contact ヘッダーには、URI ホスト名にペアの SBC FQDN が必要です。</span><span class="sxs-lookup"><span data-stu-id="6839f-176">For all incoming SIP messages (OPTIONS, INVITE) to the Microsoft SIP proxy, the Contact header must have the paired SBC FQDN in the URI hostname as follows:</span></span>

<span data-ttu-id="6839f-177">構文: 連絡先: <sip:phone または sip address@FQDN SBC;transport=tls></span><span class="sxs-lookup"><span data-stu-id="6839f-177">Syntax: Contact:  <sip:phone or sip address@FQDN of the SBC;transport=tls></span></span> 

<span data-ttu-id="6839f-178">RFC [3261、セクション 11.1](https://tools.ietf.org/html/rfc3261#section-11.1)のように、連絡先ヘッダー フィールドが OPTIONS メッセージに表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-178">As per [RFC 3261, section 11.1](https://tools.ietf.org/html/rfc3261#section-11.1), a Contact header field MAY be present in an OPTIONS message.</span></span> <span data-ttu-id="6839f-179">[ダイレクト ルーティング] では、連絡先ヘッダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="6839f-179">In Direct Routing the contact header is required.</span></span> <span data-ttu-id="6839f-180">上記の形式の INVITE メッセージの場合、OPTIONS メッセージの場合、userinfo を SIP URI から削除し、次のように形式で送信された FQDN のみを削除できます。</span><span class="sxs-lookup"><span data-stu-id="6839f-180">For INVITE messages in format above, for OPTIONS messages the userinfo can be removed from SIP URI and only FQDN sent in format as follows:</span></span>

<span data-ttu-id="6839f-181">構文: Contact: <SBC;transport=tls の sip:FQDN></span><span class="sxs-lookup"><span data-stu-id="6839f-181">Syntax: Contact:  <sip:FQDN of the SBC;transport=tls></span></span>

<span data-ttu-id="6839f-182">この名前 (FQDN) は、提示された証明書の [共通名] フィールドまたは [サブジェクトの代替名] フィールドにも含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-182">This name (FQDN) must also be in the Common Name or Subject Alternative name field(s) of the presented certificate.</span></span> <span data-ttu-id="6839f-183">Microsoft では、証明書の [共通名] フィールドまたは [サブジェクトの代替名] フィールドで、名前のワイルドカード値の使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6839f-183">Microsoft supports using wildcard values of the name(s) in the Common Name or Subject Alternative Name fields of the certificate.</span></span>   

<span data-ttu-id="6839f-184">ワイルドカードのサポートについては [、RFC 2818、セクション 3.1 で説明されています](https://tools.ietf.org/html/rfc2818#section-3.1)。</span><span class="sxs-lookup"><span data-stu-id="6839f-184">The support for wildcards is described in [RFC 2818, section 3.1](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="6839f-185">具体的には：</span><span class="sxs-lookup"><span data-stu-id="6839f-185">Specifically:</span></span>

<span data-ttu-id="6839f-186">*"名前には、単一のドメイン名コンポーネントまたはコンポーネント フラグメントと一致すると見なされるワイルドカード \* 文字が含まれている可能性があります。例: .a.com は foo.a.com と一致 bar.foo.a.com。f .com は foo.com 一致しますが \* \* 、bar.com。*</span><span class="sxs-lookup"><span data-stu-id="6839f-186">*"Names may contain the wildcard character \* which is considered to match any single domain name component or component fragment. E.g., \*.a.com matches foo.a.com but not bar.foo.a.com. f\*.com matches foo.com but not bar.com."*</span></span>

<span data-ttu-id="6839f-187">SIP メッセージに表示される Contact ヘッダーの複数の値が SBC によって送信される場合、Contact ヘッダーの最初の値の FQDN 部分だけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-187">If more than one value in the Contact header presented in a SIP message is sent by the SBC, only the FQDN portion of the first value of the Contact header is used.</span></span>

<span data-ttu-id="6839f-188">直接ルーティングの経験則として、FQDN を使用して IP ではなく SIP URI を設定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="6839f-188">As rule of thumb for Direct Routing, it is important that FQDN is used to populate SIP URI instead of IP.</span></span> <span data-ttu-id="6839f-189">ホスト名は FQDN ではなく IP で表され、接続は 403 Forbidden で拒否されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-189">An incoming INVITE or OPTIONS message to SIP Proxy with Contact header where hostname is represented by IP and not FQDN, the connection will be refused with 403 Forbidden.</span></span>

#### <a name="request-uri"></a><span data-ttu-id="6839f-190">Request-URI</span><span class="sxs-lookup"><span data-stu-id="6839f-190">Request-URI</span></span> 

<span data-ttu-id="6839f-191">すべての着信呼び出しで、要求 URI を使用して、電話番号をユーザーに一致します。</span><span class="sxs-lookup"><span data-stu-id="6839f-191">For all incoming calls, the Request-URI is used to match the phone number to a user.</span></span>   

<span data-ttu-id="6839f-192">現在、次の例に示すように、電話番号にはプラス記号 (+) が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-192">Currently The phone number must contain a plus sign (+) as shown in the following example.</span></span> 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a><span data-ttu-id="6839f-193">連絡先とRecord-Routeに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6839f-193">Contact and Record-Route headers considerations</span></span>

<span data-ttu-id="6839f-194">SIP プロキシは、新しいダイアログ内クライアント トランザクション (Bye や Re-Invite など) と SIP オプションに応答するときに、次ホップ FQDN を計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-194">The SIP proxy needs to calculate the next hop FQDN for new in-dialog client transactions (for example Bye or Re-Invite), and when replying to SIP Options.</span></span> <span data-ttu-id="6839f-195">[連絡先] または [Record-Routeが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-195">Either Contact or Record-Route are used.</span></span> 

<span data-ttu-id="6839f-196">RFC [3261、セクション 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)に従って、新しいダイアログが発生する可能性があるすべての要求に Contact ヘッダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="6839f-196">According to [RFC 3261, section 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8), Contact header is required in any request that can result in a new dialog.</span></span> <span data-ttu-id="6839f-197">このRecord-Routeは、プロキシがダイアログ内の将来の要求のパスにとどまる必要がある場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="6839f-197">The Record-Route is only required if a proxy wants to stay on the path of future requests in a dialog.</span></span> <span data-ttu-id="6839f-198">プロキシ SBC が直接ルーティング用[](./direct-routing-media-optimization.md)のローカル メディア最適化で使用されている場合、プロキシ SBC がルート内に残る必要がある場合、レコード ルートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-198">If a proxy SBC is in use with [Local Media Optimization for Direct Routing](./direct-routing-media-optimization.md), a record route will need to be configured as the proxy SBC needs to stay in the route.</span></span> 

<span data-ttu-id="6839f-199">プロキシ SBC が使用されていない場合は、Contact ヘッダーのみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="6839f-199">Microsoft recommends using only Contact header if a proxy SBC is not used:</span></span>

- <span data-ttu-id="6839f-200">[RFC 3261、セクション 20.30、Record-Route](https://tools.ietf.org/html/rfc3261#section-20.30)では、プロキシがダイアログ内の将来の要求のパスにとどまる場合に使用されます。これは、すべてのトラフィックが Microsoft SIP プロキシとペアの SBC の間を行く際にプロキシ SBC が構成されていない場合は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="6839f-200">Per [RFC 3261, section 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route is used if a proxy wants to stay on the path of future requests in a dialog, which is not essential if no proxy SBC is configured as all traffic goes between the Microsoft SIP proxy and the paired SBC.</span></span> 

- <span data-ttu-id="6839f-201">Microsoft SIP プロキシは、送信 ping オプションを送信するときに、(レコード ルートではなく) 連絡先ヘッダーのみを使用して次ホップを決定します。</span><span class="sxs-lookup"><span data-stu-id="6839f-201">The Microsoft SIP proxy uses only Contact header (not Record-Route) to determine the next hop when sending outbound ping Options.</span></span> <span data-ttu-id="6839f-202">2 つのパラメーター (Contact と Record-Route) の代わりに 1 つのパラメーター (Contact) のみを構成すると、プロキシ SBC が使用されていない場合の管理が簡略化されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-202">Configuring only one parameter (Contact) instead of two (Contact and Record-Route) simplifies the administration if a proxy SBC is not in use.</span></span> 

<span data-ttu-id="6839f-203">次ホップを計算するために、SIP プロキシは次を使用します。</span><span class="sxs-lookup"><span data-stu-id="6839f-203">To calculate the next hop, the SIP proxy uses:</span></span>

- <span data-ttu-id="6839f-204">優先順位 1。</span><span class="sxs-lookup"><span data-stu-id="6839f-204">Priority 1.</span></span> <span data-ttu-id="6839f-205">トップ レベルのレコード ルート。</span><span class="sxs-lookup"><span data-stu-id="6839f-205">Top-level Record-Route.</span></span> <span data-ttu-id="6839f-206">トップ レベルのドメインRecord-Route FQDN 名が含まれている場合は、FQDN 名を使用して、ダイアログ内の送信接続が確立されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-206">If the top-level Record-Route contains the FQDN name, the FQDN name is used to make the outbound in-dialog connection.</span></span>

- <span data-ttu-id="6839f-207">優先度 2.</span><span class="sxs-lookup"><span data-stu-id="6839f-207">Priority 2.</span></span> <span data-ttu-id="6839f-208">連絡先ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="6839f-208">Contact header.</span></span> <span data-ttu-id="6839f-209">存在Record-Route場合、SIP プロキシは Contact ヘッダーの値を参照して送信接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="6839f-209">If Record-Route does not exist, the SIP proxy will look up the value of the Contact header to make the outbound connection.</span></span> <span data-ttu-id="6839f-210">(推奨される構成です)。</span><span class="sxs-lookup"><span data-stu-id="6839f-210">(This is the recommended configuration.)</span></span>

<span data-ttu-id="6839f-211">連絡先と連絡先の両方Record-Route使用する場合、SBC 管理者は値を同じにする必要があります。この場合、管理オーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="6839f-211">If both Contact and Record-Route are used, the SBC administrator must keep their values identical, which causes administrative overhead.</span></span> 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a><span data-ttu-id="6839f-212">連絡先または連絡先で FQDN 名を使用Record-Route</span><span class="sxs-lookup"><span data-stu-id="6839f-212">Use of FQDN name in Contact or Record-Route</span></span>

<span data-ttu-id="6839f-213">IP アドレスの使用は、連絡先または連絡先Record-Routeサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6839f-213">Use of an IP address is not supported in either Record-Route or Contact.</span></span> <span data-ttu-id="6839f-214">サポートされているオプションは FQDN のみです。これは、SBC 証明書の共通名またはサブジェクトの代替名と一致する必要があります (証明書のワイルドカード値がサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="6839f-214">The only supported option is an FQDN, which must match either the Common Name or Subject Alternative Name of the SBC certificate (wildcard values in the certificate are supported).</span></span>

- <span data-ttu-id="6839f-215">IP アドレスが [レコード ルート] または [連絡先] に表示されている場合、証明書のチェックは失敗し、呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6839f-215">If an IP address is presented in Record-route or Contact, the certificate check fails and the call fails.</span></span>

- <span data-ttu-id="6839f-216">FQDN が提示された証明書の共通またはサブジェクトの代替名の値と一致しない場合、呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6839f-216">If the FQDN does not match the value of the Common or Subject Alternative Name in the presented certificate, the call fails.</span></span> 

## <a name="inbound-call-sip-dialog-description"></a><span data-ttu-id="6839f-217">着信呼び出し: SIP ダイアログの説明</span><span class="sxs-lookup"><span data-stu-id="6839f-217">Inbound call: SIP dialog description</span></span>

<span data-ttu-id="6839f-218">次の表は、呼び出しフローの違いと、バイパスモード以外とバイパス モードの類似点をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="6839f-218">The following table below summarizes the call flow differences and similarities between non-bypass and bypass modes:</span></span>

| <span data-ttu-id="6839f-219">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="6839f-219">Parameter name</span></span> | <span data-ttu-id="6839f-220">バイパスモード以外</span><span class="sxs-lookup"><span data-stu-id="6839f-220">Non-bypass mode</span></span> | <span data-ttu-id="6839f-221">バイパス モード</span><span class="sxs-lookup"><span data-stu-id="6839f-221">Bypass mode</span></span>
| :---------------------  |:---------------------- |:----------------|
| <span data-ttu-id="6839f-222">183 および 200 件のメッセージからのメディア候補</span><span class="sxs-lookup"><span data-stu-id="6839f-222">Media candidates in 183 and 200 messages coming from</span></span> | <span data-ttu-id="6839f-223">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="6839f-223">Media processors</span></span> | <span data-ttu-id="6839f-224">クライアント</span><span class="sxs-lookup"><span data-stu-id="6839f-224">Clients</span></span> | 
| <span data-ttu-id="6839f-225">SBC が受信できる 183 メッセージの数</span><span class="sxs-lookup"><span data-stu-id="6839f-225">Number of 183 messages SBC can receive</span></span> | <span data-ttu-id="6839f-226">セッションごとに 1 つ</span><span class="sxs-lookup"><span data-stu-id="6839f-226">One per session</span></span> | <span data-ttu-id="6839f-227">複数</span><span class="sxs-lookup"><span data-stu-id="6839f-227">Multiple</span></span> | 
| <span data-ttu-id="6839f-228">呼び出しは、暫定応答を使用して行えます (183)</span><span class="sxs-lookup"><span data-stu-id="6839f-228">Call can be with provisional answer (183)</span></span> | <span data-ttu-id="6839f-229">はい</span><span class="sxs-lookup"><span data-stu-id="6839f-229">Yes</span></span> | <span data-ttu-id="6839f-230">はい</span><span class="sxs-lookup"><span data-stu-id="6839f-230">Yes</span></span> |
| <span data-ttu-id="6839f-231">呼び出しは、仮回答なしで行えます (183)</span><span class="sxs-lookup"><span data-stu-id="6839f-231">Call can be without provisional answer (183)</span></span> | <span data-ttu-id="6839f-232">はい</span><span class="sxs-lookup"><span data-stu-id="6839f-232">Yes</span></span> | <span data-ttu-id="6839f-233">はい</span><span class="sxs-lookup"><span data-stu-id="6839f-233">Yes</span></span> |

###  <a name="non-media-bypass-flow"></a><span data-ttu-id="6839f-234">メディア以外のバイパス フロー</span><span class="sxs-lookup"><span data-stu-id="6839f-234">Non-media bypass flow</span></span>

<span data-ttu-id="6839f-235">1 Teamsユーザーが同時に複数のエンドポイントを持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-235">A Teams user might have multiple endpoints at the same time.</span></span> <span data-ttu-id="6839f-236">たとえば、Teams クライアントWindows、Teams クライアントiPhone Teams 電話 (Android Teams) を使用します。</span><span class="sxs-lookup"><span data-stu-id="6839f-236">For example, Teams for Windows client, Teams for iPhone client, and Teams Phone (Teams Android client).</span></span> <span data-ttu-id="6839f-237">各エンドポイントは、次のように HTTP の残りを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-237">Each endpoint might signal an HTTP rest as follows:</span></span>

-   <span data-ttu-id="6839f-238">通話の進行状況 – SIP プロキシによって SIP メッセージ 180 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-238">Call progress – converted by the SIP proxy to the SIP message 180.</span></span> <span data-ttu-id="6839f-239">メッセージ 180 を受信する場合、SBC はローカル呼び出し音を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-239">On receiving message 180, the SBC must generate local ringing.</span></span>

-   <span data-ttu-id="6839f-240">メディア応答 – SIP プロキシによって、セッション記述プロトコル (SDP) のメディア候補を含むメッセージ 183 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-240">Media answer – converted by the SIP proxy to message 183 with media candidates in Session Description Protocol (SDP).</span></span> <span data-ttu-id="6839f-241">メッセージ 183 を受信すると、SBC は SDP メッセージで受信したメディア候補に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-241">On receiving message 183, the SBC expects to connect to the media candidates received in the SDP message.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="6839f-242">場合によっては、メディアの回答が生成されない可能性があります。また、エンド ポイントが "受け入れ呼び出し" メッセージで応答する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-242">In some cases the Media answer might not be generated, and the end point might answer with “Call Accepted” message.</span></span>

-   <span data-ttu-id="6839f-243">呼び出しは受け入れ可能です。SDP を使用して SIP プロキシによって SIP メッセージ 200 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-243">Call accepted – converted by the SIP proxy to SIP message 200 with SDP.</span></span> <span data-ttu-id="6839f-244">メッセージ 200 を受信すると、SBC は、提供された SDP 候補とメディアを送受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-244">On receiving message 200, the SBC is expected to send and receive media to and from the provided SDP candidates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6839f-245">ダイレクト ルーティングでは、遅延オファー招待 (SDP を使用しない招待) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6839f-245">Direct Routing does not support Delayed Offer Invite (Invite without SDP).</span></span>

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a><span data-ttu-id="6839f-246">複数のエンドポイントが仮回答で呼び出される</span><span class="sxs-lookup"><span data-stu-id="6839f-246">Multiple endpoints ringing with provisional answer</span></span>

1.  <span data-ttu-id="6839f-247">SBC から最初の招待を受信すると、SIP プロキシは "SIP SIP/2.0 100 Trying" というメッセージを送信し、すべてのエンド ユーザー エンドポイントに着信通話について通知します。</span><span class="sxs-lookup"><span data-stu-id="6839f-247">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="6839f-248">通知すると、各エンドポイントが呼び出し音を鳴らして、SIP プロキシに "通話の進行状況" メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="6839f-248">Upon notification, each endpoint will start ringing and sending "Call progress” messages to the SIP proxy.</span></span> <span data-ttu-id="6839f-249">1 人のTeams複数のエンドポイントを持つ可能性がある場合、SIP プロキシは複数の通話進行状況メッセージを受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-249">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="6839f-250">クライアントから受信した通話の進行状況メッセージごとに、SIP プロキシは通話の進行状況メッセージを SIP メッセージ "SIP SIP/2.0 180 Trying" に変換します。</span><span class="sxs-lookup"><span data-stu-id="6839f-250">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span> <span data-ttu-id="6839f-251">このようなメッセージを送信する間隔は、呼び出しコントローラーからのメッセージを受信する間隔によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-251">The interval for sending such messages is defined by the interval of the receiving messages from the Call Controller.</span></span> <span data-ttu-id="6839f-252">次の図では、SIP プロキシによって 2 つの 180 メッセージが生成されています。</span><span class="sxs-lookup"><span data-stu-id="6839f-252">In the following diagram, there are two 180 messages generated by the SIP proxy.</span></span> <span data-ttu-id="6839f-253">これらのメッセージは、ユーザーの 2 Teamsエンドポイントから送信されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-253">These messages come from the two Teams endpoints of the user.</span></span> <span data-ttu-id="6839f-254">クライアントは、それぞれ一意のタグ ID を持っています。</span><span class="sxs-lookup"><span data-stu-id="6839f-254">The clients each have a unique Tag ID.</span></span>  <span data-ttu-id="6839f-255">別のエンドポイントから送信されるメッセージは、個別のセッションになります ("To" フィールドのパラメーター "tag" は異なります)。</span><span class="sxs-lookup"><span data-stu-id="6839f-255">Every message coming from a different endpoint will be a separate session (the parameter “tag” in the “To” field will be different).</span></span> <span data-ttu-id="6839f-256">ただし、次の図に示すように、エンドポイントによってメッセージ 180 が生成され、メッセージ 183 が送信されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-256">But an endpoint might not generate message 180 and send message 183 right away as shown in the following diagram.</span></span>

4.  <span data-ttu-id="6839f-257">エンドポイントがエンドポイントのメディア候補の IP アドレスを含む Media Answer メッセージを生成すると、SIP プロキシは、受信したメッセージを"SIP 183 Session Progress" メッセージに変換し、クライアントから SDP をメディア プロセッサから SDP に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6839f-257">Once an endpoint generates a Media Answer message with the IP addresses of endpoint’s media candidates, the SIP proxy converts the message received to a "SIP 183 Session Progress" message with the SDP from the client replaced by the SDP from the Media Processor.</span></span> <span data-ttu-id="6839f-258">次の図では、Fork 2 のエンドポイントが呼び出しに応答しました。</span><span class="sxs-lookup"><span data-stu-id="6839f-258">In the following diagram, the endpoint from Fork 2 answered the call.</span></span> <span data-ttu-id="6839f-259">トランクがバイパスされていない場合、183 SIP メッセージは 1 回だけ生成されます (リング ボットまたはクライアント エンドポイント)。</span><span class="sxs-lookup"><span data-stu-id="6839f-259">If the trunk is non-bypassed, the 183 SIP message is generated only once (either Ring Bot or Client End Point).</span></span> <span data-ttu-id="6839f-260">183 は、既存のフォークに接続されている場合や、新しいフォークを開始する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-260">The 183 might come on an existing fork or start a new one.</span></span>

5.  <span data-ttu-id="6839f-261">通話受け入れメッセージが、呼び出しを受け入れるエンドポイントの最終的な候補と一緒に送信されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-261">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="6839f-262">通話受け入れメッセージは SIP メッセージ 200 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-262">The Call Acceptance message is converted to SIP message 200.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6839f-263">![複数のエンドポイントが仮回答で呼び出されている図](media/direct-routing-protocols-1.png)</span><span class="sxs-lookup"><span data-stu-id="6839f-263">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-1.png)</span></span>

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a><span data-ttu-id="6839f-264">複数のエンドポイントが、暫定応答なしで呼び出し音を鳴らしている</span><span class="sxs-lookup"><span data-stu-id="6839f-264">Multiple endpoints ringing without provisional answer</span></span>

1.  <span data-ttu-id="6839f-265">SBC から最初の招待を受信すると、SIP プロキシは "SIP SIP/2.0 100 Trying" というメッセージを送信し、すべてのエンド ユーザー エンドポイントに着信通話について通知します。</span><span class="sxs-lookup"><span data-stu-id="6839f-265">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="6839f-266">通知すると、各エンドポイントが呼び出しを開始し、"通話の進行状況" というメッセージを SIP プロキシに送信します。</span><span class="sxs-lookup"><span data-stu-id="6839f-266">Upon notification, each endpoint will start ringing and sending the message "Call progress” to the SIP proxy.</span></span> <span data-ttu-id="6839f-267">1 人のTeams複数のエンドポイントを持つ可能性がある場合、SIP プロキシは複数の通話進行状況メッセージを受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-267">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="6839f-268">クライアントから受信した通話の進行状況メッセージごとに、SIP プロキシは通話の進行状況メッセージを SIP メッセージ "SIP SIP/2.0 180 Trying" に変換します。</span><span class="sxs-lookup"><span data-stu-id="6839f-268">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span>  <span data-ttu-id="6839f-269">メッセージを送信する間隔は、通話コントローラーからメッセージを受信する間隔によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-269">The interval for sending the messages is defined by the interval of receiving the messages from the Call Controller.</span></span> <span data-ttu-id="6839f-270">次の図では、SIP プロキシによって生成された 2 つの 180 メッセージがあります。つまり、ユーザーは 3 つの Teams クライアントにログインし、各クライアントは通話の進行状況を送信します。</span><span class="sxs-lookup"><span data-stu-id="6839f-270">On the picture below there are two 180 messages generated by the SIP proxy, meaning that user logged into three Teams clients and each client send the call progress.</span></span> <span data-ttu-id="6839f-271">すべてのメッセージは個別のセッションになります ("To" フィールドのパラメーター "tag" は異なります)。</span><span class="sxs-lookup"><span data-stu-id="6839f-271">Every message will be a separate session (parameter “tag” in “To” field is different)</span></span>

4.  <span data-ttu-id="6839f-272">通話受け入れメッセージが、呼び出しを受け入れるエンドポイントの最終的な候補と一緒に送信されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-272">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="6839f-273">通話受け入れメッセージは SIP メッセージ 200 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-273">The Call Acceptance message is converted to SIP message 200.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6839f-274">![暫定応答なしで呼び出される複数のエンドポイントを示す図](media/direct-routing-protocols-2.png)</span><span class="sxs-lookup"><span data-stu-id="6839f-274">![Diagram showing multiple endpoints ringing without provisional answer](media/direct-routing-protocols-2.png)</span></span>

### <a name="media-bypass-flow"></a><span data-ttu-id="6839f-275">メディア バイパス フロー</span><span class="sxs-lookup"><span data-stu-id="6839f-275">Media bypass flow</span></span>

<span data-ttu-id="6839f-276">メディア バイパス シナリオでは、同じメッセージ (100 Trying、180、183) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-276">The same messages (100 Trying, 180, 183) are used in the media bypass scenario.</span></span> 

<span data-ttu-id="6839f-277">次のスキーマは、バイパス呼び出しフローの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="6839f-277">The schema below shows an example of the bypass call flow.</span></span> 

> [!NOTE]
> <span data-ttu-id="6839f-278">メディア候補は、さまざまなエンドポイントから取得できます。</span><span class="sxs-lookup"><span data-stu-id="6839f-278">The media candidates can come from different endpoints.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6839f-279">![複数のエンドポイントが仮回答で呼び出されている図](media/direct-routing-protocols-3.png)</span><span class="sxs-lookup"><span data-stu-id="6839f-279">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-3.png)</span></span>

## <a name="replaces-option"></a><span data-ttu-id="6839f-280">置換オプション</span><span class="sxs-lookup"><span data-stu-id="6839f-280">Replaces option</span></span>

<span data-ttu-id="6839f-281">SBC では、Invite with Replaces をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-281">The SBC must support Invite with Replaces.</span></span>

## <a name="size-of-sdp-considerations"></a><span data-ttu-id="6839f-282">SDP の考慮事項のサイズ</span><span class="sxs-lookup"><span data-stu-id="6839f-282">Size of SDP considerations</span></span>

<span data-ttu-id="6839f-283">ダイレクト ルーティング インターフェイスは、1,500 バイトを超える SIP メッセージを送信する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-283">The Direct Routing interface might send a SIP message exceeding 1,500 bytes.</span></span>  <span data-ttu-id="6839f-284">SDP のサイズは主にこれが原因です。</span><span class="sxs-lookup"><span data-stu-id="6839f-284">The size of SDP primarily causes this.</span></span> <span data-ttu-id="6839f-285">ただし、SBC の背後に UDP トランクがある場合は、メッセージが Microsoft SIP プロキシから変更されていないトランクに転送される場合、メッセージを拒否する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-285">However, if there is a UDP trunk behind the SBC, it might reject the message if it is forwarded from the Microsoft SIP proxy to the trunk unmodified.</span></span> <span data-ttu-id="6839f-286">メッセージを UDP トランクに送信するときに、SBC の SDP で一部の値を除去する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6839f-286">Microsoft recommends stripping some values in SDP on the SBC when sending the message to the UDP trunks.</span></span> <span data-ttu-id="6839f-287">たとえば、ICE 候補や未使用のコーデックは削除できます。</span><span class="sxs-lookup"><span data-stu-id="6839f-287">For example, the ICE candidates or unused codecs can be removed.</span></span>

## <a name="call-transfer"></a><span data-ttu-id="6839f-288">通話転送</span><span class="sxs-lookup"><span data-stu-id="6839f-288">Call transfer</span></span>

<span data-ttu-id="6839f-289">ダイレクト ルーティングでは、呼び出し転送の 2 つの方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6839f-289">Direct Routing supports two methods for call transfer:</span></span>

- <span data-ttu-id="6839f-290">オプション 1。</span><span class="sxs-lookup"><span data-stu-id="6839f-290">Option 1.</span></span> <span data-ttu-id="6839f-291">SIP プロキシ プロセス クライアントからローカルに参照し、RFC 3892 のセクション 7.1 で説明されているレフリーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="6839f-291">SIP proxy processes Refer from the client locally and acts as a Referee as described in section 7.1 of RFC 3892.</span></span>

  <span data-ttu-id="6839f-292">このオプションを使用すると、SIP プロキシは転送を終了し、新しい招待を追加します。</span><span class="sxs-lookup"><span data-stu-id="6839f-292">With this option, the SIP proxy terminates the transfer and adds a new Invite.</span></span> 


- <span data-ttu-id="6839f-293">オプション 2.</span><span class="sxs-lookup"><span data-stu-id="6839f-293">Option 2.</span></span> <span data-ttu-id="6839f-294">SIP プロキシは、「SBC を参照する」を送信し、RFC 5589 のセクション 6 で説明する Transferor として機能します。</span><span class="sxs-lookup"><span data-stu-id="6839f-294">SIP proxy sends the Refer to the SBC and acts as a Transferor as describing in Section 6 of RFC 5589.</span></span>

  <span data-ttu-id="6839f-295">このオプションを使用すると、SIP プロキシは SBC の参照を送信し、SBC が転送を完全に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-295">With this option, the SIP proxy sends a Refer to the SBC and expects the SBC to handle the Transfer fully.</span></span>

<span data-ttu-id="6839f-296">SIP プロキシは、SBC によって報告される機能に基づいてメソッドを選択します。</span><span class="sxs-lookup"><span data-stu-id="6839f-296">The SIP proxy selects the method based on the capabilities reported by the SBC.</span></span> <span data-ttu-id="6839f-297">SBC がメソッド "Refer" をサポートしている場合、SIP プロキシはオプション 2 を呼び出し転送に使用します。</span><span class="sxs-lookup"><span data-stu-id="6839f-297">If the SBC indicates that it supports the method “Refer”, the SIP proxy will use Option 2 for call transfers.</span></span>

<span data-ttu-id="6839f-298">Refer メソッドがサポートされているメッセージを送信する SBC の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6839f-298">The following is an example of an SBC sending the message that the Refer method is supported:</span></span>

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

<span data-ttu-id="6839f-299">SBC がサポートされている方法として参照する方法を示さなかった場合、ダイレクト ルーティングではオプション 1 が使用されます (SIP プロキシはレフリーとして機能します)。</span><span class="sxs-lookup"><span data-stu-id="6839f-299">If the SBC doesn’t indicate that Refer as a supported method, Direct Routing will use Option 1 (SIP proxy acts as a Referee) .</span></span> <span data-ttu-id="6839f-300">SBC は、Notify メソッドをサポートしているという通知も必要です。</span><span class="sxs-lookup"><span data-stu-id="6839f-300">The SBC  must also signal that it supports the Notify method:</span></span>

<span data-ttu-id="6839f-301">Refer メソッドがサポートされていないことを示す SBC の例:</span><span class="sxs-lookup"><span data-stu-id="6839f-301">Example of SBC indicating that Refer method is not supported:</span></span>

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a><span data-ttu-id="6839f-302">SIP プロキシ プロセス クライアントからローカルに参照し、レフリーとして機能する</span><span class="sxs-lookup"><span data-stu-id="6839f-302">SIP proxy processes Refer from the client locally and acts as a Referee</span></span>

<span data-ttu-id="6839f-303">SBC が Refer メソッドがサポートされていないと示した場合、SIP プロキシはレフリーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="6839f-303">If the SBC indicated that the Refer method is not supported, the SIP proxy acts as a Referee.</span></span> 

<span data-ttu-id="6839f-304">クライアントから送信される Refer 要求は、SIP プロキシで終了します。</span><span class="sxs-lookup"><span data-stu-id="6839f-304">The Refer request that comes from the client will be terminated on the SIP proxy.</span></span> <span data-ttu-id="6839f-305">(次の図では、クライアントからの Refer 要求が "Dave への転送を呼び出す" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-305">(The Refer request from the client is shown as “Call transfer to Dave” in the following diagram.</span></span>  <span data-ttu-id="6839f-306">詳細については [、RFC 3892](https://www.ietf.org/rfc/rfc3892.txt)のセクション 7.1 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6839f-306">For more information, see section 7.1 of [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6839f-307">![複数のエンドポイントが仮回答で呼び出されている図](media/direct-routing-protocols-4.png)</span><span class="sxs-lookup"><span data-stu-id="6839f-307">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-4.png)</span></span>

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a><span data-ttu-id="6839f-308">SIP プロキシは、SBC を参照し、Transferor として機能します。</span><span class="sxs-lookup"><span data-stu-id="6839f-308">SIP proxy send the Refer to the SBC and acts as a Transferor</span></span>

<span data-ttu-id="6839f-309">これは呼び出し転送に推奨される方法であり、メディア バイパス認定を求めているデバイスには必須です。</span><span class="sxs-lookup"><span data-stu-id="6839f-309">This is the preferred method for call transfers, and it is mandatory for devices seeking media bypass certification.</span></span> <span data-ttu-id="6839f-310">SBC が Refer を処理できない場合の呼び出し転送は、メディア バイパス モードではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6839f-310">Call Transfer without the SBC being able to handle Refer is not supported in media bypass mode.</span></span> 

<span data-ttu-id="6839f-311">標準については、RFC 5589 のセクション 6 で説明されています。</span><span class="sxs-lookup"><span data-stu-id="6839f-311">The standard is explained in Section 6 of RFC 5589.</span></span> <span data-ttu-id="6839f-312">関連する RFC は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6839f-312">The related RFCs are:</span></span>

- [<span data-ttu-id="6839f-313">セッション開始プロトコル (SIP) 呼び出し制御 - 転送</span><span class="sxs-lookup"><span data-stu-id="6839f-313">Session Initiation Protocol (SIP) Call Control - Transfer</span></span>](https://tools.ietf.org/html/rfc5589)

- [<span data-ttu-id="6839f-314">セッション開始プロトコル (SIP) "Replaces" ヘッダー</span><span class="sxs-lookup"><span data-stu-id="6839f-314">Session Initiation Protocol (SIP) "Replaces" Header</span></span>](https://tools.ietf.org/html/rfc3891)

- [<span data-ttu-id="6839f-315">セッション開始プロトコル (SIP) "参照者" メカニズム</span><span class="sxs-lookup"><span data-stu-id="6839f-315">Session Initiation Protocol (SIP) "Referred-By" mechanism</span></span>](https://tools.ietf.org/html/rfc3892)

<span data-ttu-id="6839f-316">このオプションは、SIP プロキシが Transferor として機能し、参照メッセージを SBC に送信すると想定しています。</span><span class="sxs-lookup"><span data-stu-id="6839f-316">This option assumes that the SIP proxy acts as a Transferor and sends a Refer message to the SBC.</span></span> <span data-ttu-id="6839f-317">SBC は Transferee として機能し、転送の新しいオファーを生成する参照を処理します。</span><span class="sxs-lookup"><span data-stu-id="6839f-317">The SBC acts as a Transferee and handles the Refer to generate a new offer for transfer.</span></span> <span data-ttu-id="6839f-318">次の 2 つのケースが考えられる。</span><span class="sxs-lookup"><span data-stu-id="6839f-318">There are two possible cases:</span></span>

- <span data-ttu-id="6839f-319">通話は外部 PSTN 参加者に転送されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-319">The call is transferred to an external PSTN participant.</span></span> 
- <span data-ttu-id="6839f-320">この呼び出しは、SBC Teams同じテナント内Teams別のユーザーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-320">The call is transferred from one Teams user to another Teams user in the same tenant via the SBC.</span></span> 

<span data-ttu-id="6839f-321">SBC を介して呼び出しが Teams ユーザー間で転送された場合、SBC は、参照メッセージで受信した情報を使用して転送ターゲット (Teams ユーザー) に対して新しい招待 (新しいダイアログを開始) を発行する予定です。</span><span class="sxs-lookup"><span data-stu-id="6839f-321">If the call is transferred from one Teams user to another via the SBC, the SBC is expected to issue a new invite (start a new dialog) for the transfer target (the Teams user) using the information received in the Refer message.</span></span> 

<span data-ttu-id="6839f-322">要求のトランザクションの To/Transferor フィールドを内部的に設定するには、SIP プロキシが REFER-TO/REFERRED-BY ヘッダー内でこの情報を伝達する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-322">To populate the To/Transferor fields for the transaction of the request internally, the SIP proxy needs to convey this information  inside the REFER-TO/REFERRED-BY headers.</span></span> 

<span data-ttu-id="6839f-323">SIP プロキシは、ホスト名内の SIP プロキシ FQDN と次のいずれかで構成される SIP URI として REFER-TO を形成します。</span><span class="sxs-lookup"><span data-stu-id="6839f-323">The SIP proxy will form the REFER-TO as a SIP URI comprised of a SIP proxy FQDN in the hostname and either one of the following:</span></span>

- <span data-ttu-id="6839f-324">転送先が電話番号である場合、URI のユーザー名部分の E.164 電話番号。</span><span class="sxs-lookup"><span data-stu-id="6839f-324">An E.164 phone number in the username part of the URI in case the transfer target is a phone number, or</span></span>

- <span data-ttu-id="6839f-325">x-m パラメーターと x-t パラメーターで、それぞれ完全転送ターゲットのターゲットのサイズとテナント ID をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="6839f-325">x-m and x-t parameters encoding the full transfer target MRI and tenant ID respectively</span></span> 

<span data-ttu-id="6839f-326">REFERRED-BY ヘッダーは、次の表に示すように、転送者のテナント ID と他の転送コンテキスト パラメーターに加え、転送子の URI がエンコードされた SIP URI です。</span><span class="sxs-lookup"><span data-stu-id="6839f-326">The REFERRED-BY header is a SIP URI with transferor MRI encoded in it as well as transferor tenant ID and other transfer context parameters as shown in the following table:</span></span>

| <span data-ttu-id="6839f-327">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6839f-327">Parameter</span></span> | <span data-ttu-id="6839f-328">値</span><span class="sxs-lookup"><span data-stu-id="6839f-328">Value</span></span> | <span data-ttu-id="6839f-329">説明</span><span class="sxs-lookup"><span data-stu-id="6839f-329">Description</span></span> |  
|:---------------------  |:---------------------- |:---------------------- |
| <span data-ttu-id="6839f-330">x-m</span><span class="sxs-lookup"><span data-stu-id="6839f-330">x-m</span></span> | <span data-ttu-id="6839f-331">[PDF]</span><span class="sxs-lookup"><span data-stu-id="6839f-331">MRI</span></span> | <span data-ttu-id="6839f-332">CC によって設定された転送子/転送ターゲットの完全な PDF</span><span class="sxs-lookup"><span data-stu-id="6839f-332">Full MRI of transferor/transfer target as populated by CC</span></span> |
| <span data-ttu-id="6839f-333">x-t</span><span class="sxs-lookup"><span data-stu-id="6839f-333">x-t</span></span> | <span data-ttu-id="6839f-334">テナント ID</span><span class="sxs-lookup"><span data-stu-id="6839f-334">Tenant ID</span></span> | <span data-ttu-id="6839f-335">x-t Tenant ID Optional Tenant ID as populated by CC</span><span class="sxs-lookup"><span data-stu-id="6839f-335">x-t Tenant ID Optional Tenant ID as populated by CC</span></span> |
| <span data-ttu-id="6839f-336">x-ti</span><span class="sxs-lookup"><span data-stu-id="6839f-336">x-ti</span></span> | <span data-ttu-id="6839f-337">Transferor の関連付け ID</span><span class="sxs-lookup"><span data-stu-id="6839f-337">Transferor Correlation Id</span></span> | <span data-ttu-id="6839f-338">転送者への呼び出しの関連付け ID</span><span class="sxs-lookup"><span data-stu-id="6839f-338">Correlation ID of the call to the transferor</span></span> |
| <span data-ttu-id="6839f-339">x-tt</span><span class="sxs-lookup"><span data-stu-id="6839f-339">x-tt</span></span> | <span data-ttu-id="6839f-340">転送先の呼び出し URI</span><span class="sxs-lookup"><span data-stu-id="6839f-340">Transfer target call URI</span></span> | <span data-ttu-id="6839f-341">エンコードされた呼び出し置換 URI</span><span class="sxs-lookup"><span data-stu-id="6839f-341">Encoded call replacement URI</span></span> |

<span data-ttu-id="6839f-342">この場合、Refer Header のサイズは最大 400 シンボルです。</span><span class="sxs-lookup"><span data-stu-id="6839f-342">The size of the Refer Header can be up to 400 symbols in this case.</span></span> <span data-ttu-id="6839f-343">SBC は、最大 400 シンボルのサイズの Refer メッセージの処理をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-343">The SBC must support handling Refer messages with size up to 400 symbols.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6839f-344">![複数のエンドポイントが仮回答で呼び出されている図](media/direct-routing-protocols-5.png)</span><span class="sxs-lookup"><span data-stu-id="6839f-344">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-5.png)</span></span>

## <a name="session-timer"></a><span data-ttu-id="6839f-345">セッション タイマー</span><span class="sxs-lookup"><span data-stu-id="6839f-345">Session timer</span></span>

<span data-ttu-id="6839f-346">SIP プロキシは、バイパス以外の呼び出しでセッション タイマーをサポート (常に提供) しますが、バイパス呼び出しでは提供しません。</span><span class="sxs-lookup"><span data-stu-id="6839f-346">The SIP proxy supports (always offers) the Session Timer on non-bypass calls but does not offer it on bypass calls.</span></span> <span data-ttu-id="6839f-347">SBC によるセッション タイマーの使用は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="6839f-347">Use of the Session Timer by the SBC is not mandatory.</span></span>

##  <a name="use-of-request-uri-parameter-userphone"></a><span data-ttu-id="6839f-348">Request-URI パラメーター user=phone の使用</span><span class="sxs-lookup"><span data-stu-id="6839f-348">Use of Request-URI parameter user=phone</span></span>

<span data-ttu-id="6839f-349">SIP プロキシは要求 URI を分析し、user=phone パラメーターが存在する場合、サービスは要求 URI を電話番号として処理し、その番号をユーザーに照合します。</span><span class="sxs-lookup"><span data-stu-id="6839f-349">The SIP proxy analyses the Request-URI and if the parameter user=phone is present, the service will handle the Request-URI as a phone number, matching the number to a user.</span></span> <span data-ttu-id="6839f-350">パラメーターが存在しない場合、SIP プロキシはヒューリスティックを適用して、要求 URI ユーザーの種類 (電話番号または SIP アドレス) を決定します。</span><span class="sxs-lookup"><span data-stu-id="6839f-350">If parameter is not present the SIP proxy applies heuristics to determine  the Request-URI user type (phone number or a SIP address).</span></span>

<span data-ttu-id="6839f-351">通話設定プロセスを簡略化するために、常に user=phone パラメーターを適用してください。</span><span class="sxs-lookup"><span data-stu-id="6839f-351">Microsoft recommends always applying the user=phone parameter to simplify the call setup process.</span></span>

## <a name="history-info-header"></a><span data-ttu-id="6839f-352">History-Info ヘッダー</span><span class="sxs-lookup"><span data-stu-id="6839f-352">History-Info header</span></span>

<span data-ttu-id="6839f-353">History-Info ヘッダーは、SIP 要求のターゲットを変更するために使用され、"ネットワークとエンド ユーザー向けのさまざまなサービスを有効にするための要求履歴情報をキャプチャするための標準的なメカニズムを提供します"。</span><span class="sxs-lookup"><span data-stu-id="6839f-353">The History-Info header is used for retargeting SIP requests and “provide(s) a standard mechanism for capturing the request history information to enable a wide variety of services for networks and end-users.”</span></span> <span data-ttu-id="6839f-354">詳細については [、RFC 4244 – セクション 1.1 を参照してください](http://www.ietf.org/rfc/rfc4244.txt)。</span><span class="sxs-lookup"><span data-stu-id="6839f-354">For more information, see [RFC 4244 – Section 1.1](http://www.ietf.org/rfc/rfc4244.txt).</span></span> <span data-ttu-id="6839f-355">システムMicrosoft 電話、このヘッダーは、Simulring および Call Forwarding のシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-355">For Microsoft Phone System, this header is used in Simulring and Call Forwarding scenarios.</span></span>  

<span data-ttu-id="6839f-356">送信する場合、History-Info有効になります。</span><span class="sxs-lookup"><span data-stu-id="6839f-356">If sending, the History-Info is enabled as follows:</span></span>

- <span data-ttu-id="6839f-357">SIP プロキシは、PSTN コントローラーに送信される History-Info ヘッダーを構成する個々の History-Info エントリに、関連付けられている電話番号を含むパラメーターを挿入します。</span><span class="sxs-lookup"><span data-stu-id="6839f-357">The SIP proxy will insert a parameter containing the associated phone number in individual History-Info entries that comprise the History-Info header sent to the PSTN Controller.</span></span>  <span data-ttu-id="6839f-358">電話番号パラメーターを持つエントリのみを使用して、PSTN コントローラーは新しい History-Info ヘッダーを再構築し、SIP プロキシ経由で SIP トランク プロバイダーに渡します。</span><span class="sxs-lookup"><span data-stu-id="6839f-358">Using only entries that have the phone number parameter, the PSTN Controller will rebuild a new History-Info header, and pass it on to the SIP trunk provider via SIP proxy.</span></span>

- <span data-ttu-id="6839f-359">History-Info呼び出し転送の場合、同時呼び出しヘッダーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-359">History-Info header will be added for simultaneous ring and call forwarding cases.</span></span>

- <span data-ttu-id="6839f-360">History-Info転送の場合、ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="6839f-360">History-Info header will not be added for call transfer cases.</span></span>

- <span data-ttu-id="6839f-361">再構築された History-Info ヘッダーの個々の履歴エントリには、URI のホスト部分として設定された直接ルーティング FQDN (sip.pstnhub.microsoft.com) と組み合わせて指定された電話番号パラメーターがあります。'user=phone' のパラメーターは、SIP URI の一部として追加されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-361">An individual history entry in the reconstructed History-Info header will have the phone number parameter provided combined with the Direct Routing FQDN (sip.pstnhub.microsoft.com) set as the host part of the URI; a parameter of ‘user=phone’ will be added as part of the SIP URI.</span></span>  <span data-ttu-id="6839f-362">元の History-Info ヘッダーに関連付けられているその他のパラメーター (電話コンテキスト パラメーターを除く) は、構築しHistory-Infoされます。</span><span class="sxs-lookup"><span data-stu-id="6839f-362">Any other parameters associated with the original History-Info header, except for phone context parameters, will be passed through in the re-constructed History-Info header.</span></span>  

  > [!NOTE]
  > <span data-ttu-id="6839f-363">プライベート (RFC 4244 のセクション 3.3 で定義されているメカニズムによって決定される) エントリは、SIP トランク プロバイダーが信頼されたピアなので、この方法で転送されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-363">Entries that are private (as determined by the mechanisms defined in Section 3.3 of RFC 4244) will be forwarded as is because  the SIP trunk provider is a trusted peer.</span></span>

- <span data-ttu-id="6839f-364">受信History-Infoは無視されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-364">Inbound History-Info is ignored.</span></span>

<span data-ttu-id="6839f-365">SIP プロキシによって送信される History-info ヘッダーの形式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6839f-365">Following is the format of the History-info header sent by the SIP proxy:</span></span>

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

<span data-ttu-id="6839f-366">呼び出しが何度かリダイレクトされた場合、すべてのリダイレクトに関する情報が、適切な理由に時系列で含まれます。</span><span class="sxs-lookup"><span data-stu-id="6839f-366">If the call was redirected several times, information about every redirect is included with the appropriate reason in chronological order.</span></span>


<span data-ttu-id="6839f-367">ヘッダーの例:</span><span class="sxs-lookup"><span data-stu-id="6839f-367">Header Example:</span></span>

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

<span data-ttu-id="6839f-368">このHistory-Infoは、必須の TLS メカニズムによって保護されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-368">The History-Info is protected by a mandatory TLS mechanism.</span></span> 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a><span data-ttu-id="6839f-369">ダイレクト ルーティングとフェールオーバー メカニズムへの SBC 接続</span><span class="sxs-lookup"><span data-stu-id="6839f-369">SBC connection to Direct Routing and failover mechanism</span></span>

<span data-ttu-id="6839f-370">「ダイレクト ルーティングの計画」の「SIP シグナリングの [フェールオーバー メカニズム」セクションを参照してください](direct-routing-plan.md#failover-mechanism-for-sip-signaling)。</span><span class="sxs-lookup"><span data-stu-id="6839f-370">See the section Failover mechanism for SIP signaling in [Plan for Direct Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).</span></span>

## <a name="retry-after"></a><span data-ttu-id="6839f-371">Retry-After</span><span class="sxs-lookup"><span data-stu-id="6839f-371">Retry-After</span></span>

<span data-ttu-id="6839f-372">ダイレクト ルーティング データセンターがビジー状態の場合、サービスは 1 秒の間隔Retry-Afterメッセージを SBC に送信できます。</span><span class="sxs-lookup"><span data-stu-id="6839f-372">If a Direct Routing datacenter is busy, the service can send a Retry-After message with a one-second interval to the SBC.</span></span> <span data-ttu-id="6839f-373">SBC が INVITE に応答して Retry-After ヘッダーを含む 503 メッセージを受信した場合、SBC は接続を終了し、次に使用可能な Microsoft データセンターを試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-373">When the SBC receives a 503 message with a Retry-After header in response to an INVITE, the SBC must terminate that connection and try the next available Microsoft datacenter.</span></span>

## <a name="handling-retries-603-response"></a><span data-ttu-id="6839f-374">再試行の処理 (603 応答)</span><span class="sxs-lookup"><span data-stu-id="6839f-374">Handling retries (603 response)</span></span>
<span data-ttu-id="6839f-375">エンド ユーザーが着信呼び出しを拒否した後に 1 回の呼び出しに対して複数の着信ミスを観察した場合、SBC または PSTN トランク プロバイダーの再試行メカニズムが正しく構成されていないという意味です。</span><span class="sxs-lookup"><span data-stu-id="6839f-375">If an end user observes several missed calls for one call after declining the incoming call, it means that the SBC or PSTN trunk provider's retry mechanism is misconfigured.</span></span> <span data-ttu-id="6839f-376">603 応答での再試行を停止するには、SBC を再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-376">The SBC must be reconfigured to stop the retry efforts on the 603 response.</span></span>

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a><span data-ttu-id="6839f-377">ICE Restart: メディア バイパスをサポートしていないエンドポイントに転送されたメディア バイパス呼び出し</span><span class="sxs-lookup"><span data-stu-id="6839f-377">ICE Restart: Media bypass call transferred to an endpoint that does not support media bypass</span></span>

<span data-ttu-id="6839f-378">SBC は [、RFC 5245 セクション 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)で説明されている ICE 再起動をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6839f-378">The SBC must support ICE restarts as described in [RFC 5245, section 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span>

<span data-ttu-id="6839f-379">ダイレクト ルーティングでの再起動は、RFC の次の段落に従って実装されます。</span><span class="sxs-lookup"><span data-stu-id="6839f-379">The restart in Direct Routing is implemented according to the following paragraphs of the RFC:</span></span>

<span data-ttu-id="6839f-380">*ICE を再起動するには、エージェントはオファー内のメディア ストリームの ice-pwd と ice-ufrag の両方を変更する必要があります。 1 つのオファーでセッション レベル属性を使用できますが、後続のオファーではメディア レベル属性と同じ ice-pwd または ice-ufrag を提供できます。 これはパスワードの変更ではなく、単なる表現の変更であり、ICE 再起動の原因となるのではありません。*</span><span class="sxs-lookup"><span data-stu-id="6839f-380">*To restart ICE, an agent MUST change both the ice-pwd and the ice-ufrag for the media stream in an offer.  Note that it is permissible to use a session-level attribute in one offer, but to provide the same ice-pwd or ice-ufrag as a media-level attribute in a subsequent offer.  This is not a change in password, just a change in its representation, and does not cause an ICE restart.*</span></span>

<span data-ttu-id="6839f-381">*エージェントは、このメディア ストリームの最初のオファーと同様に、このメディア ストリームの SDP の残りのフィールドを設定します (セクション 4.3 を参照)。 そのため、一連の候補には、そのストリームの以前の候補の一部、なし、またはすべての候補が含まれる場合があります。また、セクション 4.1.1 で説明したように、収集された全く新しい候補セットが含まれる場合があります(MAY)。*</span><span class="sxs-lookup"><span data-stu-id="6839f-381">*An agent sets the rest of the fields in the SDP for this media stream as it would in an initial offer of this media stream (see Section 4.3).  Consequently, the set of candidates MAY include some, none, or all of the previous candidates for that stream and MAY include a totally new set of candidates gathered as described in Section 4.1.1.*</span></span>

<span data-ttu-id="6839f-382">最初にメディア バイパスを使用して通話が確立され、その呼び出しが Skype for Business クライアントに転送された場合、ダイレクト ルーティングはメディア プロセッサを挿入する必要があります。これは、メディア バイパスを使用して Skype for Business クライアントと直接ルーティングを使用できないためです。</span><span class="sxs-lookup"><span data-stu-id="6839f-382">If the call was initially established with media bypass, and the call is transferred to a Skype for Business client, Direct Routing needs to insert a Media Processor--this is because Direct Routing cannot be used with a Skype for Business client with media bypass.</span></span> <span data-ttu-id="6839f-383">直接ルーティングでは、ice-pwd と ice-ufrag を変更し、新しいメディア候補を再び提供することで、ICE 再起動プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="6839f-383">Direct Routing starts the ICE restart process by  changing the ice-pwd and ice-ufrag and offering new media candidates in a reinvite.</span></span>
