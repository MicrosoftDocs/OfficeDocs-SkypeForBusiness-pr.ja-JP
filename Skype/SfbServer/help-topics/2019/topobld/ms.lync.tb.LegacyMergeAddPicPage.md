---
title: 従来版のマージ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Web 会議の外部 FQDN を使うと、外部ユーザーはオンプレミスの会議に参加できます。 従来のエッジサーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: 96b69e53b0f7538412c6bad7cebbf8e964607b48
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300155"
---
# <a name="legacy-merge"></a><span data-ttu-id="ed0e2-104">従来版のマージ</span><span class="sxs-lookup"><span data-stu-id="ed0e2-104">Legacy Merge</span></span>

<span data-ttu-id="ed0e2-105">**Web 会議の外部 FQDN**を使うと、外部ユーザーはオンプレミスの会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="ed0e2-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="ed0e2-106">従来のエッジサーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="ed0e2-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="ed0e2-107">**外部 Web 会議の外部ポート**値は、 **443**の既定の伝送制御プロトコル (TCP) セッション開始プロトコル (SIP) ポートで、会議クライアント用に構成されています。</span><span class="sxs-lookup"><span data-stu-id="ed0e2-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="ed0e2-108">既定値を使用しなかった場合は、**外部 Web 会議の外部ポート**の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="ed0e2-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="ed0e2-109">このエッジサーバーをフェデレーション用に使用する場合は、[**このエッジプールをフェデレーションとパブリック IM 接続に使用**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ed0e2-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="ed0e2-110">複数のエッジサーバーが展開されている場合は、そのうちの1つのみがフェデレーション対象として有効になります。</span><span class="sxs-lookup"><span data-stu-id="ed0e2-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="ed0e2-111">このチェックボックスをオフにして、後でフェデレーションを有効にすることにした場合は、トポロジの公開に加えて、トポロジビルダーのマージウィザードをもう一度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed0e2-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="ed0e2-112">詳しくは、「[フェーズ 4: マージトポロジ](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ed0e2-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


