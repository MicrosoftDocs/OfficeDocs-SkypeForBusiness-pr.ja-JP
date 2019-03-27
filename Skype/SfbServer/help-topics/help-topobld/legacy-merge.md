---
title: 従来版のマージ
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Web 会議の外部 FQDN は、外部ユーザーがオンプレミス会議への参加を許可します。 従来のエッジ サーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: a6bb1ee83496e98f6097905fdf24c62d20d657ae
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897179"
---
# <a name="legacy-merge"></a><span data-ttu-id="a7537-104">従来版のマージ</span><span class="sxs-lookup"><span data-stu-id="a7537-104">Legacy Merge</span></span>

<span data-ttu-id="a7537-105">**Web カンファレンスの外部 FQDN**では、オンプレミス会議に参加する外部ユーザーを許可します。</span><span class="sxs-lookup"><span data-stu-id="a7537-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="a7537-106">従来のエッジ サーバーの web 会議の外部インターフェイスの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7537-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="a7537-107">会議クライアント用に構成された既定の伝送制御プロトコル (TCP) セッション開始プロトコル (SIP) ポートを**443**の**外部の Web 会議の外部ポート**の値には。</span><span class="sxs-lookup"><span data-stu-id="a7537-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="a7537-108">既定値が使用できない場合は、**外部の Web 会議の外部ポート**の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="a7537-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="a7537-109">フェデレーションのこのエッジ サーバーを使用する場合は、[**このエッジ プールがフェデレーションとパブリック IM 接続の使用**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7537-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="a7537-110">展開される複数のエッジ サーバーがあれば、フェデレーションの 1 つだけ有効にします。</span><span class="sxs-lookup"><span data-stu-id="a7537-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="a7537-111">このボックスをオンにしないし、フェデレーションを有効にすることを決定後、する必要がありますトポロジ ビルダー結合ウィザードを再度実行すると、トポロジを公開します。</span><span class="sxs-lookup"><span data-stu-id="a7537-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="a7537-112">詳細については、「[フェーズ 4: トポロジを結合します](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span><span class="sxs-lookup"><span data-stu-id="a7537-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


