---
title: 発信通話でのトランクのフェイルオーバー
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: このトピックでは、Teams からセッションボーダーコントローラー (SBC) への発信通話に対するトランクのフェイルオーバーを処理する方法について説明します。
ms.openlocfilehash: a5462de971fed32a0618800b257b9c6e37b462af
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572126"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="feca9-103">発信通話でのトランクのフェイルオーバー</span><span class="sxs-lookup"><span data-stu-id="feca9-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="feca9-104">このトピックでは、チームからセッションボーダーコントローラー (SBC) への、トランクのフェイルオーバーを回避する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="feca9-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="feca9-105">ネットワークエラーへのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="feca9-105">Failover on network errors</span></span>

<span data-ttu-id="feca9-106">何らかの理由でトランクが接続できない場合、同じトランクへの接続は、別の Microsoft データセンターから試みられます。</span><span class="sxs-lookup"><span data-stu-id="feca9-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="feca9-107">接続が拒否された場合や、TLS タイムアウトがある場合、または他のネットワークレベルの問題が発生した場合など、トランクが接続されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="feca9-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="feca9-108">たとえば、管理者が、既知の IP アドレスからの SBC のみへのアクセスを制限したが、SBC のアクセス制御リスト (ACL) にすべての Microsoft ダイレクトルーティングデータセンターの IP アドレスを指定していない場合、接続が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="feca9-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="feca9-109">セッションボーダーコントローラー (SBC) から受信した特定の SIP コードのフェイルオーバー</span><span class="sxs-lookup"><span data-stu-id="feca9-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="feca9-110">直接ルーティングが、発信した招待に応答して4xx または 6xx SIP のエラーコードを受信した場合、通話は既定で完了したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="feca9-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="feca9-111">[発信] は、チームクライアントから公衆交換電話網 (PSTN) への通話であり、次のトラフィックフローが含まれます。 Teams クライアント-> ダイレクトルーティング-> SBC-> テレフォニーネットワーク。</span><span class="sxs-lookup"><span data-stu-id="feca9-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="feca9-112">SIP コードの一覧は、[セッション開始プロトコル (SIP) RFC](https://tools.ietf.org/html/rfc3261)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="feca9-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="feca9-113">"408 要求がタイムアウトしました。" というコードの着信招待に対して SBC が返信した場合、サーバーはユーザーの場所を特定できなかったなど、適切な時間内に応答を作成できませんでした。</span><span class="sxs-lookup"><span data-stu-id="feca9-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="feca9-114">クライアントは、後で変更せずに要求を繰り返すことがあります。 "</span><span class="sxs-lookup"><span data-stu-id="feca9-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="feca9-115">この特定の SBC は、呼び出し元への接続で問題が発生している可能性があります。これは、ネットワークの構成の誤りやエラーなどが原因です。</span><span class="sxs-lookup"><span data-stu-id="feca9-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="feca9-116">ただし、ルートにはもう1つの SBC があります。これは、呼び出し元に連絡できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="feca9-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="feca9-117">次の図では、ユーザーが電話番号に通話を発信すると、そのルートに2つの SBCs が含まれていて、この通話が行われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="feca9-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="feca9-118">最初に、通話に SBC1.contoso.com が選択されていますが、ネットワークの問題のため、SBC1.contoso.com は PTSN ネットワークに接続できません。</span><span class="sxs-lookup"><span data-stu-id="feca9-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="feca9-119">既定では、通話は現在完了しています。</span><span class="sxs-lookup"><span data-stu-id="feca9-119">By default, the call will be completed at this moment.</span></span> 
 
![ネットワークの問題のため、SBC に接続できないことを示す図](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="feca9-121">ただし、ルートにはさらに、通話を発信できる SBC が1つ追加されています。</span><span class="sxs-lookup"><span data-stu-id="feca9-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="feca9-122">パラメーター `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`を構成する場合、2つ目の SBC は次の図の SBC2.contoso.com で試行されます。</span><span class="sxs-lookup"><span data-stu-id="feca9-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![第2の SBC へのルーティングを示す図](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="feca9-124">FailoverResponseCodes を設定してコードを指定すると、ネットワークやその他の問題が原因で、SBC が通話を発信できない場合に、ルーティングを微調整し、潜在的な問題を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="feca9-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="feca9-125">既定値: 408、503、504</span><span class="sxs-lookup"><span data-stu-id="feca9-125">Default values:  408, 503, 504</span></span>

