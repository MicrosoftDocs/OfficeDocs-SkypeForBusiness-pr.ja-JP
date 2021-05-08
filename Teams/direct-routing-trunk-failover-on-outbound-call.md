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
f1.keywords:
- NOCSH
description: このトピックでは、セッション ボーダー コントローラー (SBC) への Teamsのトランク フェールオーバーを処理する方法について説明します。
ms.openlocfilehash: c88394cba0a98316ac272901a6ab2972e9eaf3c8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836179"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="5fb49-103">発信通話でのトランクのフェイルオーバー</span><span class="sxs-lookup"><span data-stu-id="5fb49-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="5fb49-104">このトピックでは、発信呼び出し (セッション ボーダー コントローラー (SBC) Teamsのトランク フェールオーバーを回避する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5fb49-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="5fb49-105">ネットワーク エラーでのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="5fb49-105">Failover on network errors</span></span>

<span data-ttu-id="5fb49-106">何らかの理由でトランクを接続できない場合、同じトランクへの接続は別の Microsoft データセンターから試されます。</span><span class="sxs-lookup"><span data-stu-id="5fb49-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="5fb49-107">たとえば、接続が拒否された場合、TLS タイムアウトがある場合、その他のネットワーク レベルの問題がある場合など、トランクが接続されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5fb49-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="5fb49-108">たとえば、管理者が既知の IP アドレスからのみ SBC へのアクセスを制限し、すべての Microsoft ダイレクト ルーティング データセンターの IP アドレスを SBC のアクセス制御リスト (ACL) に配置することを忘れた場合、接続が失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="5fb49-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="5fb49-109">セッション ボーダー コントローラー (SBC) から受信した特定の SIP コードのフェールオーバー</span><span class="sxs-lookup"><span data-stu-id="5fb49-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="5fb49-110">ダイレクト ルーティングが送信招待に応答して 4xx または 6xx の SIP エラー コードを受信した場合、呼び出しは既定で完了したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="5fb49-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="5fb49-111">送信とは、Teams クライアントから公衆交換電話網 (PSTN) への通話を意味し、トラフィック フローは Teams Client -> Direct Routing -> SBC -> Telephoney ネットワークです。</span><span class="sxs-lookup"><span data-stu-id="5fb49-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="5fb49-112">SIP コードの一覧は、セッション開始プロトコル [(SIP) RFC に記載されています](https://tools.ietf.org/html/rfc3261)。</span><span class="sxs-lookup"><span data-stu-id="5fb49-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="5fb49-113">SBC が"408 Request Timeout: The server could not produce a response within a suitable of time, if it not determine the location of the user in time. (408 要求タイムアウト: サーバーが適切な時間内に応答を生成できない場合など)、受信した招待に対して SBC が応答した場合を想定します。</span><span class="sxs-lookup"><span data-stu-id="5fb49-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="5fb49-114">クライアントは、後で変更なしで要求を繰り返す場合があります。"</span><span class="sxs-lookup"><span data-stu-id="5fb49-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="5fb49-115">この特定の SBC では、ネットワークの構成ミスや他のエラーが原因で、呼び出し先への接続に問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5fb49-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="5fb49-116">ただし、呼び出し先に到達できる可能性がある SBC がルートに 1 つ追加されます。</span><span class="sxs-lookup"><span data-stu-id="5fb49-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="5fb49-117">次の図では、ユーザーが電話番号に通話を行った場合、この通話を配信できる可能性のある 2 つの SBC がルートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="5fb49-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="5fb49-118">最初に SBC1.contoso.com が選択されますが、SBC1.contoso.com の問題により、PTSN ネットワークに到達できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5fb49-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="5fb49-119">既定では、この時点で呼び出しが完了します。</span><span class="sxs-lookup"><span data-stu-id="5fb49-119">By default, the call will be completed at this moment.</span></span> 
 
![ネットワークの問題が原因で SBC が PSTN に到達できない状態を示す図](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="5fb49-121">ただし、ルートには、呼び出しを配信できる SBC がもう 1 つある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5fb49-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="5fb49-122">パラメーター を構成すると、2 つ目の SBC が試み `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"` SBC2.contoso.com 図のようになります。</span><span class="sxs-lookup"><span data-stu-id="5fb49-122">If you configure the parameter `Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -FailoverResponseCodes "408"`, the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![第 2 の SBC へのルーティングを示す図](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="5fb49-124">-FailoverResponseCodes パラメーターを設定し、コードを指定すると、ルーティングを微調整し、SBC がネットワークなどの問題のために呼び出しを行えなくなる場合の潜在的な問題を回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5fb49-124">Setting the parameter -FailoverResponseCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="5fb49-125">既定値: 408、503、504</span><span class="sxs-lookup"><span data-stu-id="5fb49-125">Default values:  408, 503, 504</span></span>

