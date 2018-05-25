---
title: 従来のマージ
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Web 会議の外部 FQDN は、外部ユーザーがオンプレミス会議への参加を許可します。 従来のエッジ サーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: 09bba6fa5532e85572a1272fde59dc0a1f7a9c1e
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="legacy-merge"></a><span data-ttu-id="eb184-104">従来のマージ</span><span class="sxs-lookup"><span data-stu-id="eb184-104">Legacy Merge</span></span>
 
<span data-ttu-id="eb184-105">**Web カンファレンスの外部 FQDN**では、オンプレミス会議に参加する外部ユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="eb184-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="eb184-106">従来のエッジ サーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="eb184-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>
  
<span data-ttu-id="eb184-107">会議クライアント用に構成された既定の伝送制御プロトコル (TCP) セッション開始プロトコル (SIP) ポートを**443**の**外部の Web 会議の外部ポート**の値には。</span><span class="sxs-lookup"><span data-stu-id="eb184-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="eb184-108">既定値が使用できない場合は、**外部の Web 会議の外部ポート**の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="eb184-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>
  
<span data-ttu-id="eb184-109">フェデレーションのこのエッジ サーバーを使用する場合は、[**このエッジ プールがフェデレーションとパブリック IM 接続の使用**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb184-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="eb184-110">展開される複数のエッジ サーバーがあれば、フェデレーションの 1 つだけ有効にします。</span><span class="sxs-lookup"><span data-stu-id="eb184-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="eb184-111">このボックスをオンにしないし、フェデレーションを有効にすることを決定後、する必要がありますトポロジ ビルダー結合ウィザードを再度実行すると、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="eb184-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="eb184-112">詳細については、「[フェーズ 4: トポロジを結合します](http://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="eb184-112">For details, see [Phase 4: Merge Topologies](http://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>
  

