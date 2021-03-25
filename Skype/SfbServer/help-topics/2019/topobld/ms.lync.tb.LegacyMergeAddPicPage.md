---
title: 従来版のマージ
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Web 会議外部 FQDN を使用すると、外部ユーザーはオンプレミス会議に参加できます。 従来のエッジ サーバーの Web 会議外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: 87b70bc6d577f2752c00c7f7f73577eac7e759fa
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121066"
---
# <a name="legacy-merge"></a><span data-ttu-id="011df-104">従来版のマージ</span><span class="sxs-lookup"><span data-stu-id="011df-104">Legacy Merge</span></span>

<span data-ttu-id="011df-105">**Web 会議外部 FQDN を使用すると**、外部ユーザーはオンプレミス会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="011df-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="011df-106">従来のエッジ サーバーの Web 会議外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="011df-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="011df-107">外部 **Web 会議外部** ポート値 **443** は、会議クライアント用に構成された既定の伝送制御プロトコル (TCP) セッション開始プロトコル (SIP) ポートです。</span><span class="sxs-lookup"><span data-stu-id="011df-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="011df-108">既定値が使用されていない場合は、外部 Web 会議の外部ポート **値を更新** します。</span><span class="sxs-lookup"><span data-stu-id="011df-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="011df-109">フェデレーションに **このエッジ サーバーを使用** する場合は、[このエッジ プールをフェデレーションとパブリック IM 接続に使用する] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="011df-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="011df-110">複数のエッジ サーバーを展開している場合、そのうちの 1 つだけがフェデレーションで有効になります。</span><span class="sxs-lookup"><span data-stu-id="011df-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="011df-111">このボックスをオンにしない場合、後でフェデレーションを有効にした場合は、トポロジ ビルダーのマージ ウィザードを再度実行し、トポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="011df-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="011df-112">詳細については、「[フェーズ 4:Merge Topologies (トポロジの結合)](/previous-versions/office/lync-server-2013/phase-4-merge-topologies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="011df-112">For details, see [Phase 4: Merge Topologies](/previous-versions/office/lync-server-2013/phase-4-merge-topologies).</span></span>