---
title: 'Lync Server 2013: ブランチサイトの復元機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5787f0fd07afcf0ca70a9c3b0f7c21e3525cfae7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="78291-102">Lync Server 2013 のブランチサイトの復元機能</span><span class="sxs-lookup"><span data-stu-id="78291-102">Branch-site resiliency features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78291-103">_**トピックの最終更新日:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="78291-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="78291-104">ブランチ サイトに復元性を提供する場合、ブランチ サイトで中央サイトへの WAN 接続に障害が発生したり、中央サイトが到達不能なときに、次の音声機能を引き続き使用できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="78291-104">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="78291-105">着信と発信の公衆交換電話網 (PSTN) 通話</span><span class="sxs-lookup"><span data-stu-id="78291-105">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="78291-106">同じサイトおよび 2 つの異なるサイト間でのユーザー同士のエンタプライズ通話</span><span class="sxs-lookup"><span data-stu-id="78291-106">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="78291-107">通話の保留、取得、転送などの基本的な通話処理</span><span class="sxs-lookup"><span data-stu-id="78291-107">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="78291-108">2 者間のインスタント メッセージング</span><span class="sxs-lookup"><span data-stu-id="78291-108">Two-party instant messaging</span></span>

  - <span data-ttu-id="78291-109">着信の転送、エンドポイントの同時呼び出し、通話委任、およびチーム呼び出しサービス。ただし、委任者と代理人 (管理者と管理スタッフなど) またはすべてのチーム メンバーが同じサイトに構成されている場合のみ</span><span class="sxs-lookup"><span data-stu-id="78291-109">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="78291-110">詳細な通話の記録 (CDR)</span><span class="sxs-lookup"><span data-stu-id="78291-110">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="78291-111">自動応答アテンダントを使用した PSTN ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="78291-111">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="78291-112">ボイスメールの再ルーティング設定を構成する場合は、ボイスメール機能。</span><span class="sxs-lookup"><span data-stu-id="78291-112">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="78291-113">(詳細については、「 [Lync Server 2013 のブランチサイトの復元要件](lync-server-2013-branch-site-resiliency-requirements.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="78291-113">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="78291-114">ユーザーの認証と権限の付与</span><span class="sxs-lookup"><span data-stu-id="78291-114">User authentication and authorization</span></span>

<span data-ttu-id="78291-115">次の機能は、復元ソリューションがブランチサイトの Lync Server のフルスケール展開である場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="78291-115">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="78291-116">IM、Web、音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="78291-116">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="78291-117">プレゼンスおよび応答不可 (DND) ベースのルーティング (通話は DND がアクティブになっている内線番号で呼び出し音が鳴らない)</span><span class="sxs-lookup"><span data-stu-id="78291-117">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="78291-118">着信の転送設定の更新</span><span class="sxs-lookup"><span data-stu-id="78291-118">Updating call forwarding settings</span></span>

  - <span data-ttu-id="78291-119">応答グループアプリケーションとコールパークアプリケーション</span><span class="sxs-lookup"><span data-stu-id="78291-119">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="78291-120">新しい電話とクライアントのプロビジョニングは、ブランチサイトに Active Directory ドメインサービスが存在する場合にのみ行います。</span><span class="sxs-lookup"><span data-stu-id="78291-120">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="78291-121">Enhanced 9-1-1 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="78291-121">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="78291-122">E9-1-1 が展開されており、WAN リンクがダウンしているために中央サイトの SIP トランクが使用できない場合、存続可能ブランチアプライアンスは E9-1-1 呼び出しをローカルブランチゲートウェイにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="78291-122">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="78291-123">この機能を有効にするには、WAN に障害が発生した場合、ブランチ サイトのユーザーの音声ポリシーにより、ローカルのゲートウェイに通話をルーティングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78291-123">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="78291-124">SBA (存続可能 branch office) は XMPP ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="78291-124">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="78291-125">SBA 構成に所属するユーザーは、Im を送信したり、XMPP の連絡先でプレゼンスを表示したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="78291-125">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

