---
title: 発信呼び出しのトランクのフェイル オーバー
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: セッション ボーダー コント ローラー (SBC) にチームから発信呼び出しのトランクのフェイル オーバーを処理する方法の詳細については、このトピックを参照してください。
ms.openlocfilehash: 620230ca3be07bb54386f54a983539716d07b2e9
ms.sourcegitcommit: 8279beffec35fe8a75968245c6cb09f1d622370f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2018
ms.locfileid: "27297810"
---
# <a name="trunk-failover-on-outbound-calls"></a><span data-ttu-id="a1a3c-103">発信呼び出しのトランクのフェイル オーバー</span><span class="sxs-lookup"><span data-stu-id="a1a3c-103">Trunk failover on outbound calls</span></span>

<span data-ttu-id="a1a3c-104">-セッション ボーダー コント ローラー (SBC) へのチームからの発信コールのトランクのフェイル オーバーを回避する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-104">This topic describes how to avoid trunk failovers on outbound calls--from Teams to the Session Border Controller (SBC).</span></span>

## <a name="failover-on-network-errors"></a><span data-ttu-id="a1a3c-105">ネットワーク エラーでフェイル オーバー</span><span class="sxs-lookup"><span data-stu-id="a1a3c-105">Failover on network errors</span></span>

<span data-ttu-id="a1a3c-106">トランクは、何らかの理由で接続することはできません、別の Microsoft データ センターから同じトランクへの接続が試行されます。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-106">If a trunk cannot be connected for any reason, the connection to the same trunk will be tried from a different Microsoft Datacenter.</span></span> <span data-ttu-id="a1a3c-107">トランクが接続されていないなどの場合は、TLS のタイムアウトがある場合、接続が拒否、またはその他のネットワーク レベルの問題がある場合。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-107">A trunk might not be connected, for example, if a connection is refused, if there is a TLS timeout, or if there are any other network level issues.</span></span>
<span data-ttu-id="a1a3c-108">などの接続は失敗する場合、管理者のアクセスを制限、SBC を既知の IP アドレスからのみですが、SBC のアクセス制御リスト (ACL) に直接ルーティングの Microsoft データ センターのすべての IP アドレスを配置するを忘れた場合します。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-108">For example, a connection might fail if an administrator limits access to the SBC only from well-known IP addresses, but forgets to put the IP addresses of all Microsoft Direct Routing datacenters on the Access Control List (ACL) of the SBC.</span></span> 

## <a name="failover-of-specific-sip-codes-received-from-the-session-border-controller-sbc"></a><span data-ttu-id="a1a3c-109">セッション ボーダー コント ローラー (SBC) からの受信 SIP コードの特定のフェイル オーバー</span><span class="sxs-lookup"><span data-stu-id="a1a3c-109">Failover of specific SIP codes received from the Session Border Controller (SBC)</span></span>

<span data-ttu-id="a1a3c-110">送信招待への応答での 4 xx または 6 xx SIP のエラー コードを受け取ると直接ルーティングでは、呼び出し既定で完了したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-110">If Direct Routing receives any 4xx or 6xx SIP error codes in response to an outgoing Invite, the call is considered completed by default.</span></span> <span data-ttu-id="a1a3c-111">チーム クライアントからの呼び出しに、パブリック交換電話網 (PSTN) 次のトラフィック フローには、出力方向の: チームのクライアントは、直接ルーティング-> SBC] メニューのメニューの [テレフォニー ネットワークです。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-111">Outgoing means a call from a Teams client to the Public Switched Telephone Network (PSTN) with the following traffic flow: Teams Client -> Direct Routing -> SBC -> Telephony network.</span></span>

<span data-ttu-id="a1a3c-112">SIP のコードの一覧については、[セッション開始プロトコル (SIP) の RFC](https://tools.ietf.org/html/rfc3261)を参照しています。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-112">The list of SIP Codes can be found in [Session Initiation Protocol (SIP) RFC](https://tools.ietf.org/html/rfc3261).</span></span>

<span data-ttu-id="a1a3c-113">SBC がコードを使用して受信した招待に返信した場合を想定しています"408 要求のタイムアウト: サーバーを作成できませんでした、応答、適切な時間内などの場合は時間内のユーザーの場所を特定できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-113">Assume a situation where an SBC replied on an incoming invite with the code "408 Request Timeout: The server could not produce a response within a suitable amount of time, for example, if it could not determine the location of the user in time.</span></span> <span data-ttu-id="a1a3c-114">クライアントは、可能性があります繰り返し変更することがなく要求後にいつでもします。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-114">The client MAY repeat the request without modifications at any later time."</span></span>

<span data-ttu-id="a1a3c-115">この特定の SBC には、ネットワーク設定ミスやその他のエラーが発生したため、呼び出し先 - への接続に関する問題が発生可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-115">This particular SBC might be having difficulties connecting to the callee--perhaps because of a network misconfiguration or other error.</span></span> <span data-ttu-id="a1a3c-116">しかし、1 つ以上の SBC では、ルート、呼び出し先に到達できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-116">However, there is one more SBC in the route which might be able to reach the callee.</span></span>

<span data-ttu-id="a1a3c-117">次の図では、ユーザーが電話番号への呼び出しと 2 つの半角にはこの呼び出しを提供できる可能性のあるルート。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-117">In the following diagram, when a user makes a call to a phone number, there are two SBCs in the route that can potentially deliver this call.</span></span> <span data-ttu-id="a1a3c-118">最初に、呼び出しの SBC1.contoso.com が選択されているが、SBC1.contoso.com はネットワークの問題のための PTSN ネットワークに到達することはありません。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-118">Initially, SBC1.contoso.com is selected for the call, but SBC1.contoso.com isn't able to reach a PTSN network due to a network issue.</span></span>
<span data-ttu-id="a1a3c-119">既定では、この時点で呼び出しが完了します。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-119">By default, the call will be completed at this moment.</span></span> 
 
![PSTN ネットワーク上の問題のために到達できない SBC を示しています。](media/direct-routing-failover-response-codes1.png)

<span data-ttu-id="a1a3c-121">ですが、1 つ以上の SBC で可能性のある呼び出しを提供するルート。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-121">But there is one more SBC in the route which potentially can deliver the call.</span></span>
<span data-ttu-id="a1a3c-122">セット CSOnlinePSTNGateway のパラメーターを設定する場合-の Id sbc1.contoso.com - ReinviteResponceCode「408」、2 つ目の SBC となる試行--次の図の SBC2.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="a1a3c-122">If you configure the parameter Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com -ReinviteResponceCode "408", the second SBC will be tried-- SBC2.contoso.com in the following diagram:</span></span>

![2 つ目の SBC へのルーティングを示しています](media/direct-routing-failover-response-codes2.png)

<span data-ttu-id="a1a3c-124">-FailoverResponceCodes コードでは、問題を指定する、ルーティングのチューニングし、を避けるために、パラメーターを設定することが潜在的な場合、SBC は、ネットワークまたはその他の問題のための呼び出しをすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a1a3c-124">Setting the parameter -FailoverResponceCodes and specifying the codes helps you fine tune your routing and avoid potential issues when an SBC cannot make a call due to network or other issues.</span></span>

<span data-ttu-id="a1a3c-125">既定値: 408, 503, 504</span><span class="sxs-lookup"><span data-stu-id="a1a3c-125">Default values:  408, 503, 504</span></span>

