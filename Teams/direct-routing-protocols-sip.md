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
# <a name="direct-routing---sip-protocol"></a><span data-ttu-id="210e3-103">ダイレクト ルーティング - SIP プロトコル</span><span class="sxs-lookup"><span data-stu-id="210e3-103">Direct Routing - SIP protocol</span></span>

<span data-ttu-id="210e3-104">この記事では、ダイレクト ルーティングがセッション開始プロトコル (SIP) を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="210e3-104">This article describes how Direct Routing implements the Session Initiation Protocol (SIP).</span></span> <span data-ttu-id="210e3-105">セッション ボーダー コントローラー (SBC) と SIP プロキシの間でトラフィックを適切にルーティングするには、一部の SIP パラメーターに特定の値が必要です。</span><span class="sxs-lookup"><span data-stu-id="210e3-105">To properly route traffic between a Session Border Controller (SBC) and the SIP proxy, some SIP parameters must have specific values.</span></span> <span data-ttu-id="210e3-106">この記事は、オンプレミスの SBC と SIP プロキシ サービス間の接続を構成する音声管理者を対象にしています。</span><span class="sxs-lookup"><span data-stu-id="210e3-106">This article is intended for voice administrators who are responsible for configuring the connection between the on-premises SBC and the SIP proxy service.</span></span>

## <a name="processing-the-incoming-request-finding-the-tenant-and-user"></a><span data-ttu-id="210e3-107">受信要求の処理: テナントとユーザーの検索</span><span class="sxs-lookup"><span data-stu-id="210e3-107">Processing the incoming request: finding the tenant and user</span></span>

<span data-ttu-id="210e3-108">着信または送信呼び出しを処理する前に、SIP プロキシと SBC の間で OPTIONS メッセージが交換されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-108">Before an incoming or outbound call can be processed, OPTIONS messages are exchanged between SIP Proxy and the SBC.</span></span> <span data-ttu-id="210e3-109">これらの OPTIONS メッセージを使用すると、SIP プロキシは SBC に許可されている機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="210e3-109">These OPTIONS messages allow SIP Proxy to provide the allowed capabilities to SBC.</span></span> <span data-ttu-id="210e3-110">OPTIONS ネゴシエーションが成功する (200OK 応答) ため、SBC と SIP プロキシの間で通話を確立するための通信をさらに可能にすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="210e3-110">It is important for OPTIONS negotiation to be successful (200OK response), allowing for further communication between SBC and SIP Proxy for establishing calls.</span></span> <span data-ttu-id="210e3-111">SIP プロキシへの OPTIONS メッセージの SIP ヘッダーは、次の例として提供されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-111">The SIP headers in an OPTIONS messages to SIP Proxy are provided as an example below:</span></span>

| <span data-ttu-id="210e3-112">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="210e3-112">Parameter name</span></span> | <span data-ttu-id="210e3-113">値の例</span><span class="sxs-lookup"><span data-stu-id="210e3-113">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="210e3-114">Request-URI</span><span class="sxs-lookup"><span data-stu-id="210e3-114">Request-URI</span></span> | <span data-ttu-id="210e3-115">OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="210e3-115">OPTIONS sip:sip.pstnhub.microsoft.com:5061 SIP /2.0</span></span> |
| <span data-ttu-id="210e3-116">ヘッダー経由</span><span class="sxs-lookup"><span data-stu-id="210e3-116">Via Header</span></span> | <span data-ttu-id="210e3-117">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="210e3-117">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="210e3-118">Max-Forwardsヘッダー</span><span class="sxs-lookup"><span data-stu-id="210e3-118">Max-Forwards header</span></span> | <span data-ttu-id="210e3-119">Max-Forwards:68</span><span class="sxs-lookup"><span data-stu-id="210e3-119">Max-Forwards:68</span></span> |
| <span data-ttu-id="210e3-120">[ヘッダーから]</span><span class="sxs-lookup"><span data-stu-id="210e3-120">From Header</span></span> | <span data-ttu-id="210e3-121">From Header From: <sip:sbc1.adatum.biz:5058></span><span class="sxs-lookup"><span data-stu-id="210e3-121">From Header From: <sip:sbc1.adatum.biz:5058></span></span> |
| <span data-ttu-id="210e3-122">ヘッダーへ</span><span class="sxs-lookup"><span data-stu-id="210e3-122">To Header</span></span> | <span data-ttu-id="210e3-123">宛先： <sip:sip.pstnhub.microsoft.com:5061></span><span class="sxs-lookup"><span data-stu-id="210e3-123">To: <sip:sip.pstnhub.microsoft.com:5061></span></span> |
| <span data-ttu-id="210e3-124">CSeq ヘッダー</span><span class="sxs-lookup"><span data-stu-id="210e3-124">CSeq header</span></span> | <span data-ttu-id="210e3-125">CSeq: 1 INVITE</span><span class="sxs-lookup"><span data-stu-id="210e3-125">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="210e3-126">連絡先ヘッダー</span><span class="sxs-lookup"><span data-stu-id="210e3-126">Contact Header</span></span> | <span data-ttu-id="210e3-127">連絡先: <sip:sbc1.adatum.biz:50588;transport=tls></span><span class="sxs-lookup"><span data-stu-id="210e3-127">Contact: <sip:sbc1.adatum.biz:50588;transport=tls></span></span> |

> [!NOTE]
> <span data-ttu-id="210e3-128">SIP ヘッダーには、使用されている SIP URI に userinfo が含まれています。</span><span class="sxs-lookup"><span data-stu-id="210e3-128">The SIP headers do not contain userinfo in the SIP URI in use.</span></span> <span data-ttu-id="210e3-129">RFC [3261、セクション 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1)に基いて、URI の userinfo 部分は省略可能であり、宛先ホストにユーザーの考え方が存在しない場合、または hosst 自体が識別されるリソースである場合は、存在しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-129">As per [RFC 3261, section 19.1.1](https://tools.ietf.org/html/rfc3261#section-19.1.1), the userinfo part of a URI is optional and MAY be absent when the destination host does not have a notion of users or when the hosst itself is the resource being identified.</span></span> <span data-ttu-id="210e3-130">@記号が SIP URI に存在する場合、ユーザー フィールドは空にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="210e3-130">If the @ sign is present in a SIP URI, the user field MUST NOT be empty.</span></span>

<span data-ttu-id="210e3-131">着信呼び出しでは、SIP プロキシは、呼び出しの宛先であるテナントを検索し、このテナント内の特定のユーザーを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-131">On an incoming call, the SIP proxy needs to find the tenant to which the call is destined and find the specific user within this tenant.</span></span> <span data-ttu-id="210e3-132">テナント管理者は、複数のテナントで非 DID 番号 (+1001 など) を構成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-132">The tenant administrator might configure non-DID numbers, for example +1001, in multiple tenants.</span></span> <span data-ttu-id="210e3-133">そのため、複数の Microsoft 365 組織または 365 組織で DID 以外の番号が同じになる可能性があるため、番号検索を実行する特定のテナントを見Office重要です。</span><span class="sxs-lookup"><span data-stu-id="210e3-133">Therefore, it is important to find the specific tenant on which to perform the number lookup because the non-DID numbers might be the same in multiple Microsoft 365 or Office 365 organizations.</span></span>  

<span data-ttu-id="210e3-134">このセクションでは、SIP プロキシがテナントとユーザーを検索し、受信接続で SBC の認証を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="210e3-134">This section describes how the SIP proxy finds the tenant and the user, and performs authentication of the SBC on the incoming connection.</span></span>

<span data-ttu-id="210e3-135">着信呼び出しでの SIP 招待メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="210e3-135">The following is an example of the SIP Invite message on an incoming call:</span></span>

| <span data-ttu-id="210e3-136">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="210e3-136">Parameter name</span></span> | <span data-ttu-id="210e3-137">値の例</span><span class="sxs-lookup"><span data-stu-id="210e3-137">Example of the value</span></span> | 
| :---------------------  |:---------------------- |
| <span data-ttu-id="210e3-138">Request-URI</span><span class="sxs-lookup"><span data-stu-id="210e3-138">Request-URI</span></span> | <span data-ttu-id="210e3-139">SIP sip:+18338006777@sip.pstnhub.microsoft.com /2.0 を招待する</span><span class="sxs-lookup"><span data-stu-id="210e3-139">INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0</span></span> |
| <span data-ttu-id="210e3-140">ヘッダー経由</span><span class="sxs-lookup"><span data-stu-id="210e3-140">Via Header</span></span> | <span data-ttu-id="210e3-141">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span><span class="sxs-lookup"><span data-stu-id="210e3-141">Via: SIP/2.0/TLS sbc1.adatum.biz:5058;alias;branch=z9hG4bKac2121518978</span></span> | 
| <span data-ttu-id="210e3-142">Max-Forwardsヘッダー</span><span class="sxs-lookup"><span data-stu-id="210e3-142">Max-Forwards header</span></span> | <span data-ttu-id="210e3-143">Max-Forwards:68</span><span class="sxs-lookup"><span data-stu-id="210e3-143">Max-Forwards:68</span></span> |
| <span data-ttu-id="210e3-144">[ヘッダーから]</span><span class="sxs-lookup"><span data-stu-id="210e3-144">From Header</span></span> | <span data-ttu-id="210e3-145">From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span><span class="sxs-lookup"><span data-stu-id="210e3-145">From Header From: <sip:7168712781@sbc1.adatum.biz;transport=udp;tag=1c747237679</span></span> |
| <span data-ttu-id="210e3-146">ヘッダーへ</span><span class="sxs-lookup"><span data-stu-id="210e3-146">To Header</span></span> | <span data-ttu-id="210e3-147">To: sip:+183338006777@sbc1.adatum.biz</span><span class="sxs-lookup"><span data-stu-id="210e3-147">To: sip:+183338006777@sbc1.adatum.biz</span></span> | 
| <span data-ttu-id="210e3-148">CSeq ヘッダー</span><span class="sxs-lookup"><span data-stu-id="210e3-148">CSeq header</span></span> | <span data-ttu-id="210e3-149">CSeq: 1 INVITE</span><span class="sxs-lookup"><span data-stu-id="210e3-149">CSeq: 1 INVITE</span></span> | 
| <span data-ttu-id="210e3-150">連絡先ヘッダー</span><span class="sxs-lookup"><span data-stu-id="210e3-150">Contact Header</span></span> | <span data-ttu-id="210e3-151">連絡先: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls></span><span class="sxs-lookup"><span data-stu-id="210e3-151">Contact: <sip: 68712781@sbc1.adatum.biz:5058;transport=tls></span></span> | 

<span data-ttu-id="210e3-152">招待を受信すると、SIP プロキシは次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="210e3-152">On receiving the invite, the SIP proxy performs the following steps:</span></span>

1. <span data-ttu-id="210e3-153">証明書を確認します。</span><span class="sxs-lookup"><span data-stu-id="210e3-153">Check the certificate.</span></span> <span data-ttu-id="210e3-154">最初の接続では、ダイレクト ルーティング サービスは、連絡先ヘッダーに表示される FQDN 名を受け取り、提示された証明書の共通名またはサブジェクト代替名と一致します。</span><span class="sxs-lookup"><span data-stu-id="210e3-154">On the initial connection, the Direct Routing service takes the FQDN name presented in the Contact header and matches it to the Common Name or Subject Alternative name of the presented certificate.</span></span> <span data-ttu-id="210e3-155">SBC 名は、次のいずれかのオプションと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-155">The SBC name must match one of the following options:</span></span>

   - <span data-ttu-id="210e3-156">オプション 1。</span><span class="sxs-lookup"><span data-stu-id="210e3-156">Option 1.</span></span> <span data-ttu-id="210e3-157">連絡先ヘッダーに表示される完全な FQDN 名は、提示された証明書の共通名/サブジェクト代替名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-157">The full FQDN name presented in the Contact header must match the Common Name/Subject Alternative name of the presented certificate.</span></span>  

   - <span data-ttu-id="210e3-158">オプション 2。</span><span class="sxs-lookup"><span data-stu-id="210e3-158">Option 2.</span></span> <span data-ttu-id="210e3-159">連絡先ヘッダー (FQDN 名 sbc1.adatum.biz の adatum.biz など) に表示される FQDN 名のドメイン部分は、共通名/サブジェクト代替名 (例: \*.adatum.biz) のワイルドカード値と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-159">The domain portion of the FQDN name presented in the Contact header (for example adatum.biz of the FQDN name sbc1.adatum.biz) must match the wildcard value in Common Name/Subject Alternative Name (for example \*.adatum.biz).</span></span>

2. <span data-ttu-id="210e3-160">連絡先ヘッダーに表示される完全な FQDN 名を使用してテナントを検索してみてください。</span><span class="sxs-lookup"><span data-stu-id="210e3-160">Try to find a tenant using the full FQDN name presented in the Contact header.</span></span>  

   <span data-ttu-id="210e3-161">連絡先ヘッダー (sbc1.adatum.biz) の FQDN 名が、Microsoft 365 組織または 365 組織の DNS 名として登録Office確認します。</span><span class="sxs-lookup"><span data-stu-id="210e3-161">Check if the FQDN name from the Contact header (sbc1.adatum.biz) is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="210e3-162">見つかった場合は、SBC FQDN がドメイン名として登録されているテナントでユーザーのルックアップが実行されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-162">If found, the lookup of the user is performed in the tenant that has the SBC FQDN registered as a Domain name.</span></span> <span data-ttu-id="210e3-163">見つからない場合は、手順 3 が適用されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-163">If not found, Step 3 applies.</span></span>   

3. <span data-ttu-id="210e3-164">手順 3 は、手順 2 が失敗した場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-164">Step 3 only applies if Step 2 failed.</span></span> 

   <span data-ttu-id="210e3-165">ホスト部分 adatum.biz を削除した後、連絡先ヘッダー (FQDN: sbc12.adatum.biz) に表示されている FQDN からホスト部分を削除し、この名前が Microsoft 365 組織または Office 365 組織で DNS 名として登録Office確認します。</span><span class="sxs-lookup"><span data-stu-id="210e3-165">Remove the host portion from the FQDN, presented in the Contact header (FQDN: sbc12.adatum.biz, after removing the host portion: adatum.biz), and check if this name is registered as a DNS name in any Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="210e3-166">見つかった場合、ユーザールックアップは、このテナントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-166">If found, the user lookup is performed in this tenant.</span></span> <span data-ttu-id="210e3-167">見つからない場合、呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="210e3-167">If not found, the call fails.</span></span>

4. <span data-ttu-id="210e3-168">Request-URI に示されている電話番号を使用して、手順 2 または 3 で見つかったテナント内で逆引き番号ルックアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="210e3-168">Using the phone number presented in the Request-URI, perform the reverse number lookup within the tenant found in Step 2 or 3.</span></span> <span data-ttu-id="210e3-169">前の手順で見つかったテナント内のユーザー SIP URI に、提示された電話番号を一致します。</span><span class="sxs-lookup"><span data-stu-id="210e3-169">Match the presented phone number to a user SIP URI within the tenant found on the previous step.</span></span>

5. <span data-ttu-id="210e3-170">トランク設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="210e3-170">Apply trunk settings.</span></span> <span data-ttu-id="210e3-171">この SBC のテナント管理者によって設定されたパラメーターを見つける。</span><span class="sxs-lookup"><span data-stu-id="210e3-171">Find the parameters set by the tenant admin for this SBC.</span></span>

   <span data-ttu-id="210e3-172">Microsoft は、Microsoft SIP プロキシとペアリングされた SBC の間にサード パーティの SIP プロキシまたはユーザー エージェント サーバーを持つことをサポートしません。これは、ペアの SBC によって作成された要求 URI を変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-172">Microsoft does not support having a third-party SIP proxy or User Agent Server between the Microsoft SIP proxy and the paired SBC, which might modify the Request URI created by the paired SBC.</span></span>

   <span data-ttu-id="210e3-173">1 つの SBC が多数のテナント (キャリア シナリオ) に相互接続されるシナリオに必要な 2 つのルックアップ (手順 2 と 3) の要件については、この記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="210e3-173">The requirements for the two lookups (steps 2 and 3) needed for the scenario where one SBC is interconnected to many tenants (carrier scenario) are covered later in this article.</span></span>

### <a name="detailed-requirements-for-contact-header-and-request-uri"></a><span data-ttu-id="210e3-174">連絡先ヘッダーと Request-URI の詳細な要件</span><span class="sxs-lookup"><span data-stu-id="210e3-174">Detailed requirements for Contact header and Request-URI</span></span>

#### <a name="contact-header"></a><span data-ttu-id="210e3-175">連絡先ヘッダー</span><span class="sxs-lookup"><span data-stu-id="210e3-175">Contact header</span></span>

<span data-ttu-id="210e3-176">Microsoft SIP プロキシへのすべての着信 SIP メッセージ (OPTIONS、INVITE) に対して、連絡先ヘッダーには、次のように URI ホスト名にペアの SBC FQDN が必要です。</span><span class="sxs-lookup"><span data-stu-id="210e3-176">For all incoming SIP messages (OPTIONS, INVITE) to the Microsoft SIP proxy, the Contact header must have the paired SBC FQDN in the URI hostname as follows:</span></span>

<span data-ttu-id="210e3-177">構文: 連絡先: <SIP:phone または sip address@FQDN SBC;transport=tls></span><span class="sxs-lookup"><span data-stu-id="210e3-177">Syntax: Contact:  <sip:phone or sip address@FQDN of the SBC;transport=tls></span></span> 

<span data-ttu-id="210e3-178">RFC [3261、セクション 11.1](https://tools.ietf.org/html/rfc3261#section-11.1)に基い、OPTIONS メッセージに連絡先ヘッダー フィールドが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-178">As per [RFC 3261, section 11.1](https://tools.ietf.org/html/rfc3261#section-11.1), a Contact header field MAY be present in an OPTIONS message.</span></span> <span data-ttu-id="210e3-179">ダイレクト ルーティングでは、連絡先ヘッダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="210e3-179">In Direct Routing the contact header is required.</span></span> <span data-ttu-id="210e3-180">上記の形式の INVITE メッセージの場合、OPTIONS メッセージの場合、ユーザー情報を SIP URI から削除し、次のように形式で送信される FQDN のみを削除できます。</span><span class="sxs-lookup"><span data-stu-id="210e3-180">For INVITE messages in format above, for OPTIONS messages the userinfo can be removed from SIP URI and only FQDN sent in format as follows:</span></span>

<span data-ttu-id="210e3-181">構文: 連絡先: sBC;transport=tls <の sip:FQDN の></span><span class="sxs-lookup"><span data-stu-id="210e3-181">Syntax: Contact:  <sip:FQDN of the SBC;transport=tls></span></span>

<span data-ttu-id="210e3-182">この名前 (FQDN) は、提示された証明書の [共通名] または [サブジェクトの代替名] フィールドにも含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-182">This name (FQDN) must also be in the Common Name or Subject Alternative name field(s) of the presented certificate.</span></span> <span data-ttu-id="210e3-183">Microsoft では、証明書の [共通名] フィールドまたは [サブジェクトの代替名] フィールドで名前のワイルドカード値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="210e3-183">Microsoft supports using wildcard values of the name(s) in the Common Name or Subject Alternative Name fields of the certificate.</span></span>   

<span data-ttu-id="210e3-184">ワイルドカードのサポートについては [、RFC 2818、セクション 3.1 で説明されています](https://tools.ietf.org/html/rfc2818#section-3.1)。</span><span class="sxs-lookup"><span data-stu-id="210e3-184">The support for wildcards is described in [RFC 2818, section 3.1](https://tools.ietf.org/html/rfc2818#section-3.1).</span></span> <span data-ttu-id="210e3-185">具体的には：</span><span class="sxs-lookup"><span data-stu-id="210e3-185">Specifically:</span></span>

<span data-ttu-id="210e3-186">*"名前には、単一のドメイン名コンポーネントまたはコンポーネント フラグメントと一致すると見なされるワイルドカード \* 文字が含まれている場合があります。例: .a.com は、foo.a.com と一致 bar.foo.a.com 一致します。f .com は foo.com 一致しますが \* \* 、bar.com。*</span><span class="sxs-lookup"><span data-stu-id="210e3-186">*"Names may contain the wildcard character \* which is considered to match any single domain name component or component fragment. E.g., \*.a.com matches foo.a.com but not bar.foo.a.com. f\*.com matches foo.com but not bar.com."*</span></span>

<span data-ttu-id="210e3-187">SIP メッセージに表示される連絡先ヘッダーの複数の値が SBC によって送信される場合は、連絡先ヘッダーの最初の値の FQDN 部分だけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-187">If more than one value in the Contact header presented in a SIP message is sent by the SBC, only the FQDN portion of the first value of the Contact header is used.</span></span>

<span data-ttu-id="210e3-188">ダイレクト ルーティングの経験則として、FQDN を使用して IP ではなく SIP URI を設定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="210e3-188">As rule of thumb for Direct Routing, it is important that FQDN is used to populate SIP URI instead of IP.</span></span> <span data-ttu-id="210e3-189">ホスト名が FQDN ではなく IP で表される連絡先ヘッダーを含む SIP プロキシへの着信 INVITE または OPTIONS メッセージは、403 Forbidden で接続が拒否されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-189">An incoming INVITE or OPTIONS message to SIP Proxy with Contact header where hostname is represented by IP and not FQDN, the connection will be refused with 403 Forbidden.</span></span>

#### <a name="request-uri"></a><span data-ttu-id="210e3-190">Request-URI</span><span class="sxs-lookup"><span data-stu-id="210e3-190">Request-URI</span></span> 

<span data-ttu-id="210e3-191">すべての着信呼び出しに対して、Request-URI は電話番号をユーザーに一致するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-191">For all incoming calls, the Request-URI is used to match the phone number to a user.</span></span>   

<span data-ttu-id="210e3-192">現在、電話番号には、次の例に示すようにプラス記号 (+) が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-192">Currently The phone number must contain a plus sign (+) as shown in the following example.</span></span> 

```console
INVITE sip:+18338006777@sip.pstnhub.microsoft.com SIP /2.0
```

## <a name="contact-and-record-route-headers-considerations"></a><span data-ttu-id="210e3-193">連絡先とRecord-Routeに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="210e3-193">Contact and Record-Route headers considerations</span></span>

<span data-ttu-id="210e3-194">SIP プロキシは、新しいダイアログ内クライアント トランザクション (Bye や Re-Invite など) の次ホップ FQDN を計算し、SIP オプションに応答する場合に計算する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-194">The SIP proxy needs to calculate the next hop FQDN for new in-dialog client transactions (for example Bye or Re-Invite), and when replying to SIP Options.</span></span> <span data-ttu-id="210e3-195">[連絡先] または [Record-Route] が使用されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-195">Either Contact or Record-Route are used.</span></span> 

<span data-ttu-id="210e3-196">RFC [3261 セクション 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8)によると、新しいダイアログが発生する可能性がある要求には、連絡先ヘッダーが必要です。</span><span class="sxs-lookup"><span data-stu-id="210e3-196">According to [RFC 3261, section 8.1.1.8](https://tools.ietf.org/html/rfc3261#section-8.1.1.8), Contact header is required in any request that can result in a new dialog.</span></span> <span data-ttu-id="210e3-197">このRecord-Routeは、プロキシがダイアログで将来の要求のパスにとどまる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="210e3-197">The Record-Route is only required if a proxy wants to stay on the path of future requests in a dialog.</span></span> <span data-ttu-id="210e3-198">プロキシ SBC がダイレクト ルーティング[](./direct-routing-media-optimization.md)のローカル メディア最適化で使用されている場合は、プロキシ SBC がルートにとどまる必要がある場合に、レコード ルートを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-198">If a proxy SBC is in use with [Local Media Optimization for Direct Routing](./direct-routing-media-optimization.md), a record route will need to be configured as the proxy SBC needs to stay in the route.</span></span> 

<span data-ttu-id="210e3-199">プロキシ SBC が使用されていない場合は、連絡先ヘッダーのみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="210e3-199">Microsoft recommends using only Contact header if a proxy SBC is not used:</span></span>

- <span data-ttu-id="210e3-200">RFC [3261、セクション 20.30、Record-Route](https://tools.ietf.org/html/rfc3261#section-20.30)では、プロキシがダイアログで将来の要求のパスにとどまる場合に使用されます。すべてのトラフィックが Microsoft SIP プロキシとペアの SBC の間を移動する際にプロキシ SBC が構成されていない場合は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="210e3-200">Per [RFC 3261, section 20.30](https://tools.ietf.org/html/rfc3261#section-20.30), Record-Route is used if a proxy wants to stay on the path of future requests in a dialog, which is not essential if no proxy SBC is configured as all traffic goes between the Microsoft SIP proxy and the paired SBC.</span></span> 

- <span data-ttu-id="210e3-201">Microsoft SIP プロキシでは、送信 ping オプションを送信するときに、連絡先ヘッダー (レコード ルートではなく) のみを使用して次ホップを決定します。</span><span class="sxs-lookup"><span data-stu-id="210e3-201">The Microsoft SIP proxy uses only Contact header (not Record-Route) to determine the next hop when sending outbound ping Options.</span></span> <span data-ttu-id="210e3-202">2 つのパラメーター (連絡先とレコード ルート) の代わりに 1 つのパラメーター (連絡先) のみを構成すると、プロキシ SBC が使用されていない場合の管理が簡素化されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-202">Configuring only one parameter (Contact) instead of two (Contact and Record-Route) simplifies the administration if a proxy SBC is not in use.</span></span> 

<span data-ttu-id="210e3-203">次ホップを計算するために、SIP プロキシは次の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="210e3-203">To calculate the next hop, the SIP proxy uses:</span></span>

- <span data-ttu-id="210e3-204">優先度 1。</span><span class="sxs-lookup"><span data-stu-id="210e3-204">Priority 1.</span></span> <span data-ttu-id="210e3-205">トップ レベルのレコード ルート。</span><span class="sxs-lookup"><span data-stu-id="210e3-205">Top-level Record-Route.</span></span> <span data-ttu-id="210e3-206">トップ レベルのドメインに FQDN Record-Routeが含まれている場合は、FQDN 名を使用して、送信インダイアログ接続を行います。</span><span class="sxs-lookup"><span data-stu-id="210e3-206">If the top-level Record-Route contains the FQDN name, the FQDN name is used to make the outbound in-dialog connection.</span></span>

- <span data-ttu-id="210e3-207">優先度 2。</span><span class="sxs-lookup"><span data-stu-id="210e3-207">Priority 2.</span></span> <span data-ttu-id="210e3-208">連絡先ヘッダー。</span><span class="sxs-lookup"><span data-stu-id="210e3-208">Contact header.</span></span> <span data-ttu-id="210e3-209">このRecord-Route存在しない場合、SIP プロキシは Contact ヘッダーの値を参照して送信接続を行います。</span><span class="sxs-lookup"><span data-stu-id="210e3-209">If Record-Route does not exist, the SIP proxy will look up the value of the Contact header to make the outbound connection.</span></span> <span data-ttu-id="210e3-210">(これは推奨される構成です)。</span><span class="sxs-lookup"><span data-stu-id="210e3-210">(This is the recommended configuration.)</span></span>

<span data-ttu-id="210e3-211">連絡先と連絡先の両方Record-Route使用する場合、SBC 管理者は値を同一に保つ必要があります。この場合、管理者のオーバーヘッドが発生します。</span><span class="sxs-lookup"><span data-stu-id="210e3-211">If both Contact and Record-Route are used, the SBC administrator must keep their values identical, which causes administrative overhead.</span></span> 

### <a name="use-of-fqdn-name-in-contact-or-record-route"></a><span data-ttu-id="210e3-212">連絡先または連絡先で FQDN 名を使用Record-Route</span><span class="sxs-lookup"><span data-stu-id="210e3-212">Use of FQDN name in Contact or Record-Route</span></span>

<span data-ttu-id="210e3-213">IP アドレスの使用は、連絡先または連絡先Record-Routeサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="210e3-213">Use of an IP address is not supported in either Record-Route or Contact.</span></span> <span data-ttu-id="210e3-214">サポートされるオプションは FQDN のみです。これは SBC 証明書の共通名またはサブジェクトの代替名と一致する必要があります (証明書のワイルドカード値はサポートされています)。</span><span class="sxs-lookup"><span data-stu-id="210e3-214">The only supported option is an FQDN, which must match either the Common Name or Subject Alternative Name of the SBC certificate (wildcard values in the certificate are supported).</span></span>

- <span data-ttu-id="210e3-215">[レコード ルート] または [連絡先] に IP アドレスが表示されている場合、証明書のチェックは失敗し、呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="210e3-215">If an IP address is presented in Record-route or Contact, the certificate check fails and the call fails.</span></span>

- <span data-ttu-id="210e3-216">FQDN が提示された証明書の共通またはサブジェクトの代替名の値と一致しない場合、呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="210e3-216">If the FQDN does not match the value of the Common or Subject Alternative Name in the presented certificate, the call fails.</span></span> 

## <a name="inbound-call-sip-dialog-description"></a><span data-ttu-id="210e3-217">着信呼び出し: SIP ダイアログの説明</span><span class="sxs-lookup"><span data-stu-id="210e3-217">Inbound call: SIP dialog description</span></span>

<span data-ttu-id="210e3-218">次の表は、非バイパス モードとバイパス モードの呼び出しフローの違いと類似点をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="210e3-218">The following table below summarizes the call flow differences and similarities between non-bypass and bypass modes:</span></span>

| <span data-ttu-id="210e3-219">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="210e3-219">Parameter name</span></span> | <span data-ttu-id="210e3-220">バイパス以外のモード</span><span class="sxs-lookup"><span data-stu-id="210e3-220">Non-bypass mode</span></span> | <span data-ttu-id="210e3-221">バイパス モード</span><span class="sxs-lookup"><span data-stu-id="210e3-221">Bypass mode</span></span>
| :---------------------  |:---------------------- |:----------------|
| <span data-ttu-id="210e3-222">183 と 200 のメッセージのメディア候補</span><span class="sxs-lookup"><span data-stu-id="210e3-222">Media candidates in 183 and 200 messages coming from</span></span> | <span data-ttu-id="210e3-223">メディア プロセッサ</span><span class="sxs-lookup"><span data-stu-id="210e3-223">Media processors</span></span> | <span data-ttu-id="210e3-224">クライアント</span><span class="sxs-lookup"><span data-stu-id="210e3-224">Clients</span></span> | 
| <span data-ttu-id="210e3-225">SBC が受信できるメッセージ数 183 件</span><span class="sxs-lookup"><span data-stu-id="210e3-225">Number of 183 messages SBC can receive</span></span> | <span data-ttu-id="210e3-226">セッションごとに 1 つ</span><span class="sxs-lookup"><span data-stu-id="210e3-226">One per session</span></span> | <span data-ttu-id="210e3-227">複数のユーザー</span><span class="sxs-lookup"><span data-stu-id="210e3-227">Multiple</span></span> | 
| <span data-ttu-id="210e3-228">呼び出しは、暫定応答を使用できます (183)</span><span class="sxs-lookup"><span data-stu-id="210e3-228">Call can be with provisional answer (183)</span></span> | <span data-ttu-id="210e3-229">はい</span><span class="sxs-lookup"><span data-stu-id="210e3-229">Yes</span></span> | <span data-ttu-id="210e3-230">はい</span><span class="sxs-lookup"><span data-stu-id="210e3-230">Yes</span></span> |
| <span data-ttu-id="210e3-231">呼び出しは、暫定応答なしで実行できます (183)</span><span class="sxs-lookup"><span data-stu-id="210e3-231">Call can be without provisional answer (183)</span></span> | <span data-ttu-id="210e3-232">はい</span><span class="sxs-lookup"><span data-stu-id="210e3-232">Yes</span></span> | <span data-ttu-id="210e3-233">はい</span><span class="sxs-lookup"><span data-stu-id="210e3-233">Yes</span></span> |

###  <a name="non-media-bypass-flow"></a><span data-ttu-id="210e3-234">メディア以外のバイパス フロー</span><span class="sxs-lookup"><span data-stu-id="210e3-234">Non-media bypass flow</span></span>

<span data-ttu-id="210e3-235">Teams ユーザーは、同時に複数のエンドポイントを持つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-235">A Teams user might have multiple endpoints at the same time.</span></span> <span data-ttu-id="210e3-236">たとえば、Teams for Windows クライアント、Teams for iPhone クライアント、Teams Phone (Teams Android クライアント)。</span><span class="sxs-lookup"><span data-stu-id="210e3-236">For example, Teams for Windows client, Teams for iPhone client, and Teams Phone (Teams Android client).</span></span> <span data-ttu-id="210e3-237">各エンドポイントは、次のように HTTP の残りを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-237">Each endpoint might signal an HTTP rest as follows:</span></span>

-   <span data-ttu-id="210e3-238">通話の進行状況 – SIP プロキシによって SIP メッセージ 180 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-238">Call progress – converted by the SIP proxy to the SIP message 180.</span></span> <span data-ttu-id="210e3-239">メッセージ 180 を受信する場合、SBC はローカル 呼び出し音を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-239">On receiving message 180, the SBC must generate local ringing.</span></span>

-   <span data-ttu-id="210e3-240">メディア応答 – SIP プロキシによって、セッション記述プロトコル (SDP) のメディア候補を含むメッセージ 183 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-240">Media answer – converted by the SIP proxy to message 183 with media candidates in Session Description Protocol (SDP).</span></span> <span data-ttu-id="210e3-241">メッセージ 183 を受信すると、SBC は SDP メッセージで受信したメディア候補に接続する予定です。</span><span class="sxs-lookup"><span data-stu-id="210e3-241">On receiving message 183, the SBC expects to connect to the media candidates received in the SDP message.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="210e3-242">場合によっては、メディアの回答が生成されない可能性があります。また、エンド ポイントが "受け入れ呼び出し" メッセージで応答する場合があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-242">In some cases the Media answer might not be generated, and the end point might answer with “Call Accepted” message.</span></span>

-   <span data-ttu-id="210e3-243">受け入れ呼び出し – SDP を使用して SIP プロキシによって SIP メッセージ 200 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-243">Call accepted – converted by the SIP proxy to SIP message 200 with SDP.</span></span> <span data-ttu-id="210e3-244">メッセージ 200 を受信すると、SBC は、指定された SDP 候補者とメディアを送受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-244">On receiving message 200, the SBC is expected to send and receive media to and from the provided SDP candidates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="210e3-245">ダイレクト ルーティングでは、遅延オファーの招待 (SDP なしの招待) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="210e3-245">Direct Routing does not support Delayed Offer Invite (Invite without SDP).</span></span>

#### <a name="multiple-endpoints-ringing-with-provisional-answer"></a><span data-ttu-id="210e3-246">暫定応答で呼び出される複数のエンドポイント</span><span class="sxs-lookup"><span data-stu-id="210e3-246">Multiple endpoints ringing with provisional answer</span></span>

1.  <span data-ttu-id="210e3-247">SBC から最初の招待を受信すると、SIP プロキシは"SIP SIP/2.0 100 Trying" というメッセージを送信し、着信呼び出しについてすべてのエンド ユーザー エンドポイントに通知します。</span><span class="sxs-lookup"><span data-stu-id="210e3-247">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="210e3-248">通知すると、各エンドポイントが呼び出しを開始し、SIP プロキシに "通話の進行状況" メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="210e3-248">Upon notification, each endpoint will start ringing and sending "Call progress” messages to the SIP proxy.</span></span> <span data-ttu-id="210e3-249">Teams ユーザーは複数のエンド ポイントを持つ可能性があるため、SIP プロキシは複数の通話進行状況メッセージを受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-249">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="210e3-250">クライアントから受信した通話進行状況メッセージごとに、SIP プロキシは通話進行状況メッセージを SIP メッセージ "SIP SIP/2.0 180 Trying" に変換します。</span><span class="sxs-lookup"><span data-stu-id="210e3-250">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span> <span data-ttu-id="210e3-251">このようなメッセージを送信する間隔は、呼び出しコントローラーからの受信メッセージの間隔によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-251">The interval for sending such messages is defined by the interval of the receiving messages from the Call Controller.</span></span> <span data-ttu-id="210e3-252">次の図では、SIP プロキシによって生成される 2 つの 180 メッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="210e3-252">In the following diagram, there are two 180 messages generated by the SIP proxy.</span></span> <span data-ttu-id="210e3-253">これらのメッセージは、ユーザーの 2 つの Teams エンドポイントから取得されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-253">These messages come from the two Teams endpoints of the user.</span></span> <span data-ttu-id="210e3-254">クライアントには、それぞれ一意のタグ ID があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-254">The clients each have a unique Tag ID.</span></span>  <span data-ttu-id="210e3-255">別のエンドポイントから送信されるメッセージは、個別のセッションになります ("To" フィールドのパラメーター "tag" は異なります)。</span><span class="sxs-lookup"><span data-stu-id="210e3-255">Every message coming from a different endpoint will be a separate session (the parameter “tag” in the “To” field will be different).</span></span> <span data-ttu-id="210e3-256">ただし、次の図に示すように、エンドポイントでメッセージ 180 が生成され、メッセージ 183 が送信されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-256">But an endpoint might not generate message 180 and send message 183 right away as shown in the following diagram.</span></span>

4.  <span data-ttu-id="210e3-257">エンドポイントがエンドポイントのメディア候補の IP アドレスを含む Media Answer メッセージを生成すると、SIP プロキシは、受信したメッセージを、メディア プロセッサから SDP に置き換えられたクライアントから SDP で "SIP 183 セッション進行状況" メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="210e3-257">Once an endpoint generates a Media Answer message with the IP addresses of endpoint’s media candidates, the SIP proxy converts the message received to a "SIP 183 Session Progress" message with the SDP from the client replaced by the SDP from the Media Processor.</span></span> <span data-ttu-id="210e3-258">次の図では、Fork 2 のエンドポイントが呼び出しに応答しました。</span><span class="sxs-lookup"><span data-stu-id="210e3-258">In the following diagram, the endpoint from Fork 2 answered the call.</span></span> <span data-ttu-id="210e3-259">トランクがバイパスされていない場合、183 SIP メッセージは 1 回だけ生成されます (リング ボットまたはクライアント エンドポイント)。</span><span class="sxs-lookup"><span data-stu-id="210e3-259">If the trunk is non-bypassed, the 183 SIP message is generated only once (either Ring Bot or Client End Point).</span></span> <span data-ttu-id="210e3-260">183 は、既存のフォークに接続されている場合や、新しいフォークを開始する場合があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-260">The 183 might come on an existing fork or start a new one.</span></span>

5.  <span data-ttu-id="210e3-261">呼び出しの受け入れメッセージが、呼び出しを受け入れるエンドポイントの最終的な候補と一緒に送信されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-261">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="210e3-262">通話の受け入れメッセージは、SIP メッセージ 200 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-262">The Call Acceptance message is converted to SIP message 200.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="210e3-263">![暫定回答で呼び出される複数のエンドポイントを示す図](media/direct-routing-protocols-1.png)</span><span class="sxs-lookup"><span data-stu-id="210e3-263">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-1.png)</span></span>

#### <a name="multiple-endpoints-ringing-without-provisional-answer"></a><span data-ttu-id="210e3-264">暫定応答なしで呼び出される複数のエンドポイント</span><span class="sxs-lookup"><span data-stu-id="210e3-264">Multiple endpoints ringing without provisional answer</span></span>

1.  <span data-ttu-id="210e3-265">SBC から最初の招待を受信すると、SIP プロキシは"SIP SIP/2.0 100 Trying" というメッセージを送信し、着信呼び出しについてすべてのエンド ユーザー エンドポイントに通知します。</span><span class="sxs-lookup"><span data-stu-id="210e3-265">On receiving the first Invite from the SBC, the SIP proxy sends the message "SIP SIP/2.0 100 Trying" and notifies all end user endpoints about the incoming call.</span></span> 

2.  <span data-ttu-id="210e3-266">通知すると、各エンドポイントが呼び出しを開始し、メッセージ "通話の進行状況" を SIP プロキシに送信します。</span><span class="sxs-lookup"><span data-stu-id="210e3-266">Upon notification, each endpoint will start ringing and sending the message "Call progress” to the SIP proxy.</span></span> <span data-ttu-id="210e3-267">Teams ユーザーは複数のエンド ポイントを持つ可能性があるため、SIP プロキシは複数の通話進行状況メッセージを受信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-267">Because a Teams user can have multiple end points, the SIP proxy might receive multiple Call Progress messages.</span></span>

3.  <span data-ttu-id="210e3-268">クライアントから受信した通話進行状況メッセージごとに、SIP プロキシは通話進行状況メッセージを SIP メッセージ "SIP SIP/2.0 180 Trying" に変換します。</span><span class="sxs-lookup"><span data-stu-id="210e3-268">For every Call Progress message received from the clients, the SIP proxy converts the Call Progress message to the SIP message "SIP SIP/2.0 180 Trying".</span></span>  <span data-ttu-id="210e3-269">メッセージを送信する間隔は、呼び出しコントローラーからメッセージを受信する間隔によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-269">The interval for sending the messages is defined by the interval of receiving the messages from the Call Controller.</span></span> <span data-ttu-id="210e3-270">次の図では、SIP プロキシによって生成された 2 つの 180 メッセージがあります。つまり、ユーザーが 3 つの Teams クライアントにログインし、各クライアントが通話の進行状況を送信します。</span><span class="sxs-lookup"><span data-stu-id="210e3-270">On the picture below there are two 180 messages generated by the SIP proxy, meaning that user logged into three Teams clients and each client send the call progress.</span></span> <span data-ttu-id="210e3-271">すべてのメッセージは個別のセッションになります ("To" フィールドのパラメーター "tag" は異なります)</span><span class="sxs-lookup"><span data-stu-id="210e3-271">Every message will be a separate session (parameter “tag” in “To” field is different)</span></span>

4.  <span data-ttu-id="210e3-272">呼び出しの受け入れメッセージが、呼び出しを受け入れるエンドポイントの最終的な候補と一緒に送信されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-272">A Call Acceptance message is sent with the final candidates of the endpoint that accepted the call.</span></span> <span data-ttu-id="210e3-273">通話の受け入れメッセージは、SIP メッセージ 200 に変換されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-273">The Call Acceptance message is converted to SIP message 200.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="210e3-274">![暫定応答なしで呼び出される複数のエンドポイントを示す図](media/direct-routing-protocols-2.png)</span><span class="sxs-lookup"><span data-stu-id="210e3-274">![Diagram showing multiple endpoints ringing without provisional answer](media/direct-routing-protocols-2.png)</span></span>

### <a name="media-bypass-flow"></a><span data-ttu-id="210e3-275">メディア バイパス フロー</span><span class="sxs-lookup"><span data-stu-id="210e3-275">Media bypass flow</span></span>

<span data-ttu-id="210e3-276">メディア バイパス シナリオでは、同じメッセージ (100 Trying、180、183) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-276">The same messages (100 Trying, 180, 183) are used in the media bypass scenario.</span></span> 

<span data-ttu-id="210e3-277">次のスキーマは、バイパス呼び出しフローの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="210e3-277">The schema below shows an example of the bypass call flow.</span></span> 

> [!NOTE]
> <span data-ttu-id="210e3-278">メディア候補は、さまざまなエンドポイントから取得できます。</span><span class="sxs-lookup"><span data-stu-id="210e3-278">The media candidates can come from different endpoints.</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="210e3-279">![暫定回答で呼び出される複数のエンドポイントを示す図](media/direct-routing-protocols-3.png)</span><span class="sxs-lookup"><span data-stu-id="210e3-279">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-3.png)</span></span>

## <a name="replaces-option"></a><span data-ttu-id="210e3-280">オプションを置き換える</span><span class="sxs-lookup"><span data-stu-id="210e3-280">Replaces option</span></span>

<span data-ttu-id="210e3-281">SBC は、Invite with Replaces をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-281">The SBC must support Invite with Replaces.</span></span>

## <a name="size-of-sdp-considerations"></a><span data-ttu-id="210e3-282">SDP の考慮事項のサイズ</span><span class="sxs-lookup"><span data-stu-id="210e3-282">Size of SDP considerations</span></span>

<span data-ttu-id="210e3-283">ダイレクト ルーティング インターフェイスは、1,500 バイトを超える SIP メッセージを送信する場合があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-283">The Direct Routing interface might send a SIP message exceeding 1,500 bytes.</span></span>  <span data-ttu-id="210e3-284">SDP のサイズは、主にこれが原因です。</span><span class="sxs-lookup"><span data-stu-id="210e3-284">The size of SDP primarily causes this.</span></span> <span data-ttu-id="210e3-285">ただし、SBC の背後に UDP トランクがある場合は、Microsoft SIP プロキシから変更されていないトランクに転送された場合、メッセージを拒否する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-285">However, if there is a UDP trunk behind the SBC, it might reject the message if it is forwarded from the Microsoft SIP proxy to the trunk unmodified.</span></span> <span data-ttu-id="210e3-286">メッセージを UDP トランクに送信するときに、SBC の SDP で一部の値を削除する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="210e3-286">Microsoft recommends stripping some values in SDP on the SBC when sending the message to the UDP trunks.</span></span> <span data-ttu-id="210e3-287">たとえば、ICE 候補や未使用のコーデックは削除できます。</span><span class="sxs-lookup"><span data-stu-id="210e3-287">For example, the ICE candidates or unused codecs can be removed.</span></span>

## <a name="call-transfer"></a><span data-ttu-id="210e3-288">転送を呼び出す</span><span class="sxs-lookup"><span data-stu-id="210e3-288">Call transfer</span></span>

<span data-ttu-id="210e3-289">ダイレクト ルーティングでは、呼び出し転送の 2 つの方法がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="210e3-289">Direct Routing supports two methods for call transfer:</span></span>

- <span data-ttu-id="210e3-290">オプション 1。</span><span class="sxs-lookup"><span data-stu-id="210e3-290">Option 1.</span></span> <span data-ttu-id="210e3-291">SIP プロキシ プロセス クライアントからローカルに参照し、RFC 3892 のセクション 7.1 で説明されているレフリーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="210e3-291">SIP proxy processes Refer from the client locally and acts as a Referee as described in section 7.1 of RFC 3892.</span></span>

  <span data-ttu-id="210e3-292">このオプションを使用すると、SIP プロキシは転送を終了し、新しい招待を追加します。</span><span class="sxs-lookup"><span data-stu-id="210e3-292">With this option, the SIP proxy terminates the transfer and adds a new Invite.</span></span> 


- <span data-ttu-id="210e3-293">オプション 2。</span><span class="sxs-lookup"><span data-stu-id="210e3-293">Option 2.</span></span> <span data-ttu-id="210e3-294">SIP プロキシは、SBC の参照を送信し、RFC 5589 のセクション 6 で説明されている転送者として機能します。</span><span class="sxs-lookup"><span data-stu-id="210e3-294">SIP proxy sends the Refer to the SBC and acts as a Transferor as describing in Section 6 of RFC 5589.</span></span>

  <span data-ttu-id="210e3-295">このオプションを使用すると、SIP プロキシは SBC を参照し、SBC が転送を完全に処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-295">With this option, the SIP proxy sends a Refer to the SBC and expects the SBC to handle the Transfer fully.</span></span>

<span data-ttu-id="210e3-296">SIP プロキシは、SBC によって報告された機能に基づいてメソッドを選択します。</span><span class="sxs-lookup"><span data-stu-id="210e3-296">The SIP proxy selects the method based on the capabilities reported by the SBC.</span></span> <span data-ttu-id="210e3-297">SBC がメソッド "参照" をサポートすると示す場合、SIP プロキシは呼び出し転送にオプション 2 を使用します。</span><span class="sxs-lookup"><span data-stu-id="210e3-297">If the SBC indicates that it supports the method “Refer”, the SIP proxy will use Option 2 for call transfers.</span></span>

<span data-ttu-id="210e3-298">次に、Refer メソッドがサポートされているメッセージを送信する SBC の例を示します。</span><span class="sxs-lookup"><span data-stu-id="210e3-298">The following is an example of an SBC sending the message that the Refer method is supported:</span></span>

```console
ALLOW: INVITE, OPTIONS, INFO, BYE, CANCEL, ACK, PRACK, UPDATE, REFER, SUBSCRIBE, NOTIFY
```

<span data-ttu-id="210e3-299">SBC がサポートされている方法として参照するを示さなかった場合、ダイレクト ルーティングではオプション 1 が使用されます (SIP プロキシはレフリーとして機能します)。</span><span class="sxs-lookup"><span data-stu-id="210e3-299">If the SBC doesn’t indicate that Refer as a supported method, Direct Routing will use Option 1 (SIP proxy acts as a Referee) .</span></span> <span data-ttu-id="210e3-300">SBC は、Notify メソッドをサポートしているという通知も必要です。</span><span class="sxs-lookup"><span data-stu-id="210e3-300">The SBC  must also signal that it supports the Notify method:</span></span>

<span data-ttu-id="210e3-301">Refer メソッドがサポートされていないことを示す SBC の例:</span><span class="sxs-lookup"><span data-stu-id="210e3-301">Example of SBC indicating that Refer method is not supported:</span></span>

```console
ALLOW: INVITE, ACK, CANCEL, BYE, INFO, NOTIFY, PRACK, UPDATE, OPTIONS
```

### <a name="sip-proxy-processes-refer-from-the-client-locally-and-acts-as-a-referee"></a><span data-ttu-id="210e3-302">SIP プロキシ プロセス クライアントからローカルに参照し、レフリーとして機能する</span><span class="sxs-lookup"><span data-stu-id="210e3-302">SIP proxy processes Refer from the client locally and acts as a Referee</span></span>

<span data-ttu-id="210e3-303">SBC が Refer メソッドがサポートされていないと示した場合、SIP プロキシはレフリーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="210e3-303">If the SBC indicated that the Refer method is not supported, the SIP proxy acts as a Referee.</span></span> 

<span data-ttu-id="210e3-304">クライアントから送信される Refer 要求は、SIP プロキシで終了します。</span><span class="sxs-lookup"><span data-stu-id="210e3-304">The Refer request that comes from the client will be terminated on the SIP proxy.</span></span> <span data-ttu-id="210e3-305">(クライアントからの参照要求は、次の図に"Dave への呼び出し転送" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-305">(The Refer request from the client is shown as “Call transfer to Dave” in the following diagram.</span></span>  <span data-ttu-id="210e3-306">詳細については [、RFC 3892 のセクション 7.1 を参照してください](https://www.ietf.org/rfc/rfc3892.txt)。</span><span class="sxs-lookup"><span data-stu-id="210e3-306">For more information, see section 7.1 of [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="210e3-307">![暫定回答で呼び出される複数のエンドポイントを示す図](media/direct-routing-protocols-4.png)</span><span class="sxs-lookup"><span data-stu-id="210e3-307">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-4.png)</span></span>

### <a name="sip-proxy-send-the-refer-to-the-sbc-and-acts-as-a-transferor"></a><span data-ttu-id="210e3-308">SIP プロキシは、SBC の参照を送信し、Transferor として機能します</span><span class="sxs-lookup"><span data-stu-id="210e3-308">SIP proxy send the Refer to the SBC and acts as a Transferor</span></span>

<span data-ttu-id="210e3-309">これは呼び出し転送に推奨される方法であり、メディア バイパス認定を求めるデバイスでは必須です。</span><span class="sxs-lookup"><span data-stu-id="210e3-309">This is the preferred method for call transfers, and it is mandatory for devices seeking media bypass certification.</span></span> <span data-ttu-id="210e3-310">SBC が Refer を処理できない場合の呼び出し転送は、メディア バイパス モードではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="210e3-310">Call Transfer without the SBC being able to handle Refer is not supported in media bypass mode.</span></span> 

<span data-ttu-id="210e3-311">この標準については、RFC 5589 のセクション 6 で説明されています。</span><span class="sxs-lookup"><span data-stu-id="210e3-311">The standard is explained in Section 6 of RFC 5589.</span></span> <span data-ttu-id="210e3-312">関連する RFC は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="210e3-312">The related RFCs are:</span></span>

- [<span data-ttu-id="210e3-313">セッション開始プロトコル (SIP) 呼び出し制御 - 転送</span><span class="sxs-lookup"><span data-stu-id="210e3-313">Session Initiation Protocol (SIP) Call Control - Transfer</span></span>](https://tools.ietf.org/html/rfc5589)

- [<span data-ttu-id="210e3-314">セッション開始プロトコル (SIP) "Replaces" ヘッダー</span><span class="sxs-lookup"><span data-stu-id="210e3-314">Session Initiation Protocol (SIP) "Replaces" Header</span></span>](https://tools.ietf.org/html/rfc3891)

- [<span data-ttu-id="210e3-315">セッション開始プロトコル (SIP) "referred-By" メカニズム</span><span class="sxs-lookup"><span data-stu-id="210e3-315">Session Initiation Protocol (SIP) "Referred-By" mechanism</span></span>](https://tools.ietf.org/html/rfc3892)

<span data-ttu-id="210e3-316">このオプションは、SIP プロキシが Transferor として機能し、SBC に Refer メッセージを送信すると想定します。</span><span class="sxs-lookup"><span data-stu-id="210e3-316">This option assumes that the SIP proxy acts as a Transferor and sends a Refer message to the SBC.</span></span> <span data-ttu-id="210e3-317">SBC は譲渡先として機能し、[参照] を処理して、新しい譲渡オファーを生成します。</span><span class="sxs-lookup"><span data-stu-id="210e3-317">The SBC acts as a Transferee and handles the Refer to generate a new offer for transfer.</span></span> <span data-ttu-id="210e3-318">次の 2 つのケースが考えられる。</span><span class="sxs-lookup"><span data-stu-id="210e3-318">There are two possible cases:</span></span>

- <span data-ttu-id="210e3-319">呼び出しは、外部 PSTN 参加者に転送されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-319">The call is transferred to an external PSTN participant.</span></span> 
- <span data-ttu-id="210e3-320">呼び出しは、SBC を介して同じテナント内の 1 つの Teams ユーザーから別の Teams ユーザーに転送されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-320">The call is transferred from one Teams user to another Teams user in the same tenant via the SBC.</span></span> 

<span data-ttu-id="210e3-321">通話が SBC を介して Teams ユーザー間で転送される場合、SBC は、参照メッセージで受信した情報を使用して、転送先 (Teams ユーザー) に対して新しい招待 (新しいダイアログを開始) を発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-321">If the call is transferred from one Teams user to another via the SBC, the SBC is expected to issue a new invite (start a new dialog) for the transfer target (the Teams user) using the information received in the Refer message.</span></span> 

<span data-ttu-id="210e3-322">要求のトランザクションの To/Transferor フィールドを内部的に設定するには、SIP プロキシが REFER-TO/REFERRED-BY ヘッダー内でこの情報を伝達する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-322">To populate the To/Transferor fields for the transaction of the request internally, the SIP proxy needs to convey this information  inside the REFER-TO/REFERRED-BY headers.</span></span> 

<span data-ttu-id="210e3-323">SIP プロキシは、ホスト名内の SIP プロキシ FQDN で構成される SIP URI として REFER-TO を形成し、次のいずれかの方法で構成されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-323">The SIP proxy will form the REFER-TO as a SIP URI comprised of a SIP proxy FQDN in the hostname and either one of the following:</span></span>

- <span data-ttu-id="210e3-324">転送先が電話番号である場合の URI のユーザー名部分の E.164 電話番号</span><span class="sxs-lookup"><span data-stu-id="210e3-324">An E.164 phone number in the username part of the URI in case the transfer target is a phone number, or</span></span>

- <span data-ttu-id="210e3-325">完全転送ターゲットの MRI とテナント ID をそれぞれエンコードする x-m パラメーターと x-t パラメーター</span><span class="sxs-lookup"><span data-stu-id="210e3-325">x-m and x-t parameters encoding the full transfer target MRI and tenant ID respectively</span></span> 

<span data-ttu-id="210e3-326">REFERRED-BY ヘッダーは、次の表に示すように、転送者の MRI がエンコードされた SIP URI と、転送者テナント ID と他の転送コンテキスト パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="210e3-326">The REFERRED-BY header is a SIP URI with transferor MRI encoded in it as well as transferor tenant ID and other transfer context parameters as shown in the following table:</span></span>

| <span data-ttu-id="210e3-327">パラメーター</span><span class="sxs-lookup"><span data-stu-id="210e3-327">Parameter</span></span> | <span data-ttu-id="210e3-328">値</span><span class="sxs-lookup"><span data-stu-id="210e3-328">Value</span></span> | <span data-ttu-id="210e3-329">説明</span><span class="sxs-lookup"><span data-stu-id="210e3-329">Description</span></span> |  
|:---------------------  |:---------------------- |:---------------------- |
| <span data-ttu-id="210e3-330">x-m</span><span class="sxs-lookup"><span data-stu-id="210e3-330">x-m</span></span> | <span data-ttu-id="210e3-331">MRI</span><span class="sxs-lookup"><span data-stu-id="210e3-331">MRI</span></span> | <span data-ttu-id="210e3-332">CC で設定された転送または転送ターゲットの完全な MRI</span><span class="sxs-lookup"><span data-stu-id="210e3-332">Full MRI of transferor/transfer target as populated by CC</span></span> |
| <span data-ttu-id="210e3-333">x-t</span><span class="sxs-lookup"><span data-stu-id="210e3-333">x-t</span></span> | <span data-ttu-id="210e3-334">テナント ID</span><span class="sxs-lookup"><span data-stu-id="210e3-334">Tenant ID</span></span> | <span data-ttu-id="210e3-335">x-t テナント ID CC によって設定されたテナント ID (省略可能)</span><span class="sxs-lookup"><span data-stu-id="210e3-335">x-t Tenant ID Optional Tenant ID as populated by CC</span></span> |
| <span data-ttu-id="210e3-336">x-ti</span><span class="sxs-lookup"><span data-stu-id="210e3-336">x-ti</span></span> | <span data-ttu-id="210e3-337">Transferor の関連付け ID</span><span class="sxs-lookup"><span data-stu-id="210e3-337">Transferor Correlation Id</span></span> | <span data-ttu-id="210e3-338">転送者への呼び出しの関連付け ID</span><span class="sxs-lookup"><span data-stu-id="210e3-338">Correlation ID of the call to the transferor</span></span> |
| <span data-ttu-id="210e3-339">x-tt</span><span class="sxs-lookup"><span data-stu-id="210e3-339">x-tt</span></span> | <span data-ttu-id="210e3-340">転送先の呼び出し URI</span><span class="sxs-lookup"><span data-stu-id="210e3-340">Transfer target call URI</span></span> | <span data-ttu-id="210e3-341">エンコードされた呼び出しの置換 URI</span><span class="sxs-lookup"><span data-stu-id="210e3-341">Encoded call replacement URI</span></span> |

<span data-ttu-id="210e3-342">この場合、参照ヘッダーのサイズは最大 400 記号にできます。</span><span class="sxs-lookup"><span data-stu-id="210e3-342">The size of the Refer Header can be up to 400 symbols in this case.</span></span> <span data-ttu-id="210e3-343">SBC は、最大 400 シンボルのサイズの Refer メッセージの処理をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-343">The SBC must support handling Refer messages with size up to 400 symbols.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="210e3-344">![暫定回答で呼び出される複数のエンドポイントを示す図](media/direct-routing-protocols-5.png)</span><span class="sxs-lookup"><span data-stu-id="210e3-344">![Diagram showing multiple endpoints ringing with provisional answer](media/direct-routing-protocols-5.png)</span></span>

## <a name="session-timer"></a><span data-ttu-id="210e3-345">セッション タイマー</span><span class="sxs-lookup"><span data-stu-id="210e3-345">Session timer</span></span>

<span data-ttu-id="210e3-346">SIP プロキシは、バイパス以外の呼び出しでセッション タイマーをサポート (常に提供) しますが、バイパス呼び出しでは提供しません。</span><span class="sxs-lookup"><span data-stu-id="210e3-346">The SIP proxy supports (always offers) the Session Timer on non-bypass calls but does not offer it on bypass calls.</span></span> <span data-ttu-id="210e3-347">SBC によるセッション タイマーの使用は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="210e3-347">Use of the Session Timer by the SBC is not mandatory.</span></span>

##  <a name="use-of-request-uri-parameter-userphone"></a><span data-ttu-id="210e3-348">Request-URI パラメーター user=phone の使用</span><span class="sxs-lookup"><span data-stu-id="210e3-348">Use of Request-URI parameter user=phone</span></span>

<span data-ttu-id="210e3-349">SIP プロキシは Request-URI を分析し、パラメーター user=phone が存在する場合、サービスは電話番号として Request-URI を処理し、その番号をユーザーに照合します。</span><span class="sxs-lookup"><span data-stu-id="210e3-349">The SIP proxy analyses the Request-URI and if the parameter user=phone is present, the service will handle the Request-URI as a phone number, matching the number to a user.</span></span> <span data-ttu-id="210e3-350">パラメーターが存在しない場合、SIP プロキシはヒューリスティックを適用して Request-URI ユーザーの種類 (電話番号または SIP アドレス) を決定します。</span><span class="sxs-lookup"><span data-stu-id="210e3-350">If parameter is not present the SIP proxy applies heuristics to determine  the Request-URI user type (phone number or a SIP address).</span></span>

<span data-ttu-id="210e3-351">呼び出しセットアップ プロセスを簡素化するために、常に user=phone パラメーターを適用してください。</span><span class="sxs-lookup"><span data-stu-id="210e3-351">Microsoft recommends always applying the user=phone parameter to simplify the call setup process.</span></span>

## <a name="history-info-header"></a><span data-ttu-id="210e3-352">History-Infoヘッダー</span><span class="sxs-lookup"><span data-stu-id="210e3-352">History-Info header</span></span>

<span data-ttu-id="210e3-353">History-Info ヘッダーは、SIP 要求のリターゲティングに使用され、「要求履歴情報をキャプチャするための標準的なメカニズムを提供して、ネットワークとエンド ユーザー向けのさまざまなサービスを有効にする」のに使用されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-353">The History-Info header is used for retargeting SIP requests and “provide(s) a standard mechanism for capturing the request history information to enable a wide variety of services for networks and end-users.”</span></span> <span data-ttu-id="210e3-354">詳細については [、RFC 4244 – セクション 1.1 を参照してください](http://www.ietf.org/rfc/rfc4244.txt)。</span><span class="sxs-lookup"><span data-stu-id="210e3-354">For more information, see [RFC 4244 – Section 1.1](http://www.ietf.org/rfc/rfc4244.txt).</span></span> <span data-ttu-id="210e3-355">Microsoft Phone System の場合、このヘッダーは Simulring シナリオと Call Forwarding シナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-355">For Microsoft Phone System, this header is used in Simulring and Call Forwarding scenarios.</span></span>  

<span data-ttu-id="210e3-356">送信する場合、History-Infoが有効になります。</span><span class="sxs-lookup"><span data-stu-id="210e3-356">If sending, the History-Info is enabled as follows:</span></span>

- <span data-ttu-id="210e3-357">SIP プロキシは、PSTN コントローラーに送信される History-Info ヘッダーを構成する個々の History-Info エントリに、関連付けられている電話番号を含むパラメーターを挿入します。</span><span class="sxs-lookup"><span data-stu-id="210e3-357">The SIP proxy will insert a parameter containing the associated phone number in individual History-Info entries that comprise the History-Info header sent to the PSTN Controller.</span></span>  <span data-ttu-id="210e3-358">電話番号パラメーターを持つエントリのみを使用して、PSTN コントローラーは新しい History-Info ヘッダーを再構築し、SIP プロキシを介して SIP トランク プロバイダーに渡します。</span><span class="sxs-lookup"><span data-stu-id="210e3-358">Using only entries that have the phone number parameter, the PSTN Controller will rebuild a new History-Info header, and pass it on to the SIP trunk provider via SIP proxy.</span></span>

- <span data-ttu-id="210e3-359">History-Info呼び出しの転送ケースに対して、このヘッダーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-359">History-Info header will be added for simultaneous ring and call forwarding cases.</span></span>

- <span data-ttu-id="210e3-360">History-Info転送ケースでは、ヘッダーは追加されません。</span><span class="sxs-lookup"><span data-stu-id="210e3-360">History-Info header will not be added for call transfer cases.</span></span>

- <span data-ttu-id="210e3-361">再構築された History-Info ヘッダーの個々の履歴エントリには、URI のホスト部分としてダイレクト ルーティング FQDN (sip.pstnhub.microsoft.com) が設定された電話番号パラメーターが指定されます。'user=phone' のパラメーターが SIP URI の一部として追加されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-361">An individual history entry in the reconstructed History-Info header will have the phone number parameter provided combined with the Direct Routing FQDN (sip.pstnhub.microsoft.com) set as the host part of the URI; a parameter of ‘user=phone’ will be added as part of the SIP URI.</span></span>  <span data-ttu-id="210e3-362">元の History-Info ヘッダーに関連付けられているその他のパラメーター (電話コンテキスト パラメーターを除く) は、再構築されたヘッダーHistory-Infoされます。</span><span class="sxs-lookup"><span data-stu-id="210e3-362">Any other parameters associated with the original History-Info header, except for phone context parameters, will be passed through in the re-constructed History-Info header.</span></span>  

  > [!NOTE]
  > <span data-ttu-id="210e3-363">プライベートなエントリ (RFC 4244 のセクション 3.3 で定義されているメカニズムによって決まります) は、SIP トランク プロバイダーが信頼できるピアなので、この方法で転送されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-363">Entries that are private (as determined by the mechanisms defined in Section 3.3 of RFC 4244) will be forwarded as is because  the SIP trunk provider is a trusted peer.</span></span>

- <span data-ttu-id="210e3-364">受信のHistory-Infoは無視されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-364">Inbound History-Info is ignored.</span></span>

<span data-ttu-id="210e3-365">SIP プロキシによって送信される History-info ヘッダーの形式を次に示します。</span><span class="sxs-lookup"><span data-stu-id="210e3-365">Following is the format of the History-info header sent by the SIP proxy:</span></span>

```console
<sip:UserB@sip.pstnhub.microsoft.com?Privacy=history&Reason=SIP%3B\cause%3D486>;index=1.2,
```

<span data-ttu-id="210e3-366">呼び出しが何度かリダイレクトされた場合、すべてのリダイレクトに関する情報が、適切な理由を時系列順に含まれます。</span><span class="sxs-lookup"><span data-stu-id="210e3-366">If the call was redirected several times, information about every redirect is included with the appropriate reason in chronological order.</span></span>


<span data-ttu-id="210e3-367">ヘッダーの例:</span><span class="sxs-lookup"><span data-stu-id="210e3-367">Header Example:</span></span>

```console
History-info: 
<sip:+14257123456@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=302;text=”Move Temporarily”>;index=1
<sip:+14257123457@sip.pstnhub.microsoft.com;user=phone?Reason=SIP;cause=496;text=”User Busy”>;index=1.1
```

<span data-ttu-id="210e3-368">このHistory-Infoは、必須の TLS メカニズムによって保護されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-368">The History-Info is protected by a mandatory TLS mechanism.</span></span> 

## <a name="sbc-connection-to-direct-routing-and-failover-mechanism"></a><span data-ttu-id="210e3-369">ダイレクト ルーティングとフェールオーバー メカニズムへの SBC 接続</span><span class="sxs-lookup"><span data-stu-id="210e3-369">SBC connection to Direct Routing and failover mechanism</span></span>

<span data-ttu-id="210e3-370">「ダイレクト ルーティングの計画」の SIP シグナリングのフェールオーバー [メカニズムに関するセクションを参照してください](direct-routing-plan.md#failover-mechanism-for-sip-signaling)。</span><span class="sxs-lookup"><span data-stu-id="210e3-370">See the section Failover mechanism for SIP signaling in [Plan for Direct Routing](direct-routing-plan.md#failover-mechanism-for-sip-signaling).</span></span>

## <a name="retry-after"></a><span data-ttu-id="210e3-371">Retry-After</span><span class="sxs-lookup"><span data-stu-id="210e3-371">Retry-After</span></span>

<span data-ttu-id="210e3-372">ダイレクト ルーティング データセンターがビジー状態の場合、サービスは SBC に 1 Retry-After間隔でメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="210e3-372">If a Direct Routing datacenter is busy, the service can send a Retry-After message with a one-second interval to the SBC.</span></span> <span data-ttu-id="210e3-373">SBC が INVITE に応答して Retry-After ヘッダーを含む 503 メッセージを受信すると、SBC は接続を終了し、次に使用可能な Microsoft データセンターを試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-373">When the SBC receives a 503 message with a Retry-After header in response to an INVITE, the SBC must terminate that connection and try the next available Microsoft datacenter.</span></span>

## <a name="handling-retries-603-response"></a><span data-ttu-id="210e3-374">再試行の処理 (603 応答)</span><span class="sxs-lookup"><span data-stu-id="210e3-374">Handling retries (603 response)</span></span>
<span data-ttu-id="210e3-375">エンド ユーザーが着信呼び出しを拒否した後、1 回の呼び出しに対して複数の着信が見つからない場合は、SBC または PSTN トランク プロバイダーの再試行メカニズムが正しく構成されていないという意味です。</span><span class="sxs-lookup"><span data-stu-id="210e3-375">If an end user observes several missed calls for one call after declining the incoming call, it means that the SBC or PSTN trunk provider's retry mechanism is misconfigured.</span></span> <span data-ttu-id="210e3-376">SBC を再構成して、603 応答での再試行を停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-376">The SBC must be reconfigured to stop the retry efforts on the 603 response.</span></span>

## <a name="ice-restart-media-bypass-call-transferred-to-an-endpoint-that-does-not-support-media-bypass"></a><span data-ttu-id="210e3-377">ICE の再起動: メディア バイパスをサポートしていないエンドポイントに転送されるメディア バイパス呼び出し</span><span class="sxs-lookup"><span data-stu-id="210e3-377">ICE Restart: Media bypass call transferred to an endpoint that does not support media bypass</span></span>

<span data-ttu-id="210e3-378">SBC は、RFC [5245 セクション 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1)で説明されている ICE の再起動をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="210e3-378">The SBC must support ICE restarts as described in [RFC 5245, section 9.1.1.1](https://tools.ietf.org/html/rfc5245#section-9.1.1.1).</span></span>

<span data-ttu-id="210e3-379">ダイレクト ルーティングでの再起動は、RFC の次の段落に従って実装されます。</span><span class="sxs-lookup"><span data-stu-id="210e3-379">The restart in Direct Routing is implemented according to the following paragraphs of the RFC:</span></span>

<span data-ttu-id="210e3-380">*ICE を再起動するには、エージェントはオファー内のメディア ストリームの ice-pwd と ice-ufrag の両方を変更する必要があります。 1 つのオファーでセッション レベル属性を使用できますが、後続のオファーでメディア レベルの属性として同じ ice-pwd または ice-ufrag を指定できます。 これはパスワードの変更ではなく、その表現の変更に過ぎなく、ICE の再起動を引き起こします。*</span><span class="sxs-lookup"><span data-stu-id="210e3-380">*To restart ICE, an agent MUST change both the ice-pwd and the ice-ufrag for the media stream in an offer.  Note that it is permissible to use a session-level attribute in one offer, but to provide the same ice-pwd or ice-ufrag as a media-level attribute in a subsequent offer.  This is not a change in password, just a change in its representation, and does not cause an ICE restart.*</span></span>

<span data-ttu-id="210e3-381">*エージェントは、このメディア ストリームの最初のオファーと同様に、このメディア ストリームの SDP の残りのフィールドを設定します (セクション 4.3 を参照)。 そのため、候補者のセットには、そのストリームの以前の候補の一部、なし、またはすべての候補が含まれ、セクション 4.1.1 で説明されているとおりに収集された全く新しい候補セットが含まれる場合があります。*</span><span class="sxs-lookup"><span data-stu-id="210e3-381">*An agent sets the rest of the fields in the SDP for this media stream as it would in an initial offer of this media stream (see Section 4.3).  Consequently, the set of candidates MAY include some, none, or all of the previous candidates for that stream and MAY include a totally new set of candidates gathered as described in Section 4.1.1.*</span></span>

<span data-ttu-id="210e3-382">呼び出しが最初にメディア バイパスで確立され、呼び出しが Skype for Business クライアントに転送される場合、ダイレクト ルーティングはメディア プロセッサを挿入する必要があります。これは、メディア バイパスを使用した Skype for Business クライアントではダイレクト ルーティングを使用できないためです。</span><span class="sxs-lookup"><span data-stu-id="210e3-382">If the call was initially established with media bypass, and the call is transferred to a Skype for Business client, Direct Routing needs to insert a Media Processor--this is because Direct Routing cannot be used with a Skype for Business client with media bypass.</span></span> <span data-ttu-id="210e3-383">ダイレクト ルーティングは、ice-pwd と ice-ufrag を変更し、新しいメディア候補を再び提供することで、ICE 再起動プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="210e3-383">Direct Routing starts the ICE restart process by  changing the ice-pwd and ice-ufrag and offering new media candidates in a reinvite.</span></span>
