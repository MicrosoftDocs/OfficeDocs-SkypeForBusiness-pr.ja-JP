---
title: 従来版のマージ
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Web 会議の外部 FQDN を使うと、外部ユーザーはオンプレミスの会議に参加できます。 従来のエッジサーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: 984d40f8797a974a5865cca37ba1057dc638d886
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217998"
---
# <a name="legacy-merge"></a><span data-ttu-id="8671f-104">従来版のマージ</span><span class="sxs-lookup"><span data-stu-id="8671f-104">Legacy Merge</span></span>

<span data-ttu-id="8671f-105">**Web 会議の外部 FQDN**を使うと、外部ユーザーはオンプレミスの会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="8671f-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="8671f-106">従来のエッジサーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="8671f-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="8671f-107">**外部 Web 会議の外部ポート**の値は**443**で、会議クライアントに対して構成されている既定の伝送制御プロトコル (TCP) セッション開始プロトコル (SIP) ポートです。</span><span class="sxs-lookup"><span data-stu-id="8671f-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="8671f-108">既定値が使用されていない場合は、 **外部 Web 会議の外部ポート** 値を更新します。</span><span class="sxs-lookup"><span data-stu-id="8671f-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="8671f-109">このエッジサーバーをフェデレーション用に使用する場合は、[ **このエッジプールをフェデレーションとパブリック IM 接続に使用** する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8671f-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="8671f-110">複数のエッジ サーバーを展開している場合、そのうちの 1 つだけがフェデレーションで有効になります。</span><span class="sxs-lookup"><span data-stu-id="8671f-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="8671f-111">このボックスをチェックせずに、後でフェデレーションを有効にする場合は、トポロジビルダーマージウィザードをもう一度実行して、トポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8671f-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="8671f-112">詳細については、「[フェーズ 4:Merge Topologies (トポロジの結合)](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8671f-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


