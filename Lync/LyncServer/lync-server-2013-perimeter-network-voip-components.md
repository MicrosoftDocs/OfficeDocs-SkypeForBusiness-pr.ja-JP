---
title: 'Lync Server 2013: 境界ネットワークの VoIP コンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb8e14228bb927f857aa5e9801f579653eb35fd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="41ecb-102">Lync Server 2013 の境界ネットワークの VoIP コンポーネント</span><span class="sxs-lookup"><span data-stu-id="41ecb-102">Perimeter network VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41ecb-103">_**最終更新日:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="41ecb-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="41ecb-104">個人または電話会議のためにユニファイドコミュニケーションクライアントを使用している外部の発信者が、同僚との音声通信を行うために、エッジサーバーに依存しています。</span><span class="sxs-lookup"><span data-stu-id="41ecb-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="41ecb-105">エッジサーバーでは、アクセスエッジサービスによって、組織のファイアウォール外の Lync ユーザーからの通話に対する SIP シグナリングが提供されます。</span><span class="sxs-lookup"><span data-stu-id="41ecb-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="41ecb-106">音声ビデオ エッジ サービスを使用すると、メディアが NAT およびファイアウォールを通過できます。</span><span class="sxs-lookup"><span data-stu-id="41ecb-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="41ecb-107">企業ファイアウォールの外部で統合コミュニケーション (UC) クライアントを使用する発信者には、個別の通話と電話会議の両方に音声ビデオ エッジ サービスが必要です。</span><span class="sxs-lookup"><span data-stu-id="41ecb-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="41ecb-p102">音声ビデオ認証サービスは音声ビデオ エッジ サービスと同じコンピューターに配置され、音声ビデオ エッジ サービスのための認証サービスを実行します。外部のユーザーが音声ビデオ エッジ サービスに接続するには、発信を行う前に、音声ビデオ認証サービスから認証トークンを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41ecb-p102">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

