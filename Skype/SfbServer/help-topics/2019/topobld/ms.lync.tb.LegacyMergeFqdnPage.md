---
title: 従来版のマージ FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
ROBOTS: NOINDEX, NOFOLLOW
description: Access Edge プールの内部 FQDN は、内部ユーザーがフェデレーション、リモートユーザーアクセス、パブリック IM 接続の外部ユーザーと通信するさまざまなシナリオで使用されます。 負荷分散エッジサーバーがレガシ環境に展開されていた場合は、内部ロードバランサーの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: 324f82f31e2f0e49b77ca063f9eba162dad7e108
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688310"
---
# <a name="legacy-merge-fqdn"></a><span data-ttu-id="615e8-104">従来版のマージ FQDN</span><span class="sxs-lookup"><span data-stu-id="615e8-104">Legacy Merge FQDN</span></span>
 
<span data-ttu-id="615e8-105">**Access Edge プールの内部 FQDN**は、内部ユーザーがフェデレーション、リモートユーザーアクセス、パブリック IM 接続の外部ユーザーと通信するさまざまなシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="615e8-105">The **Access Edge Pool internal FQDN** is used for a variety of scenarios where internal users communicate with external users for federation, remote user access, and public IM connectivity.</span></span> <span data-ttu-id="615e8-106">負荷分散エッジサーバーがレガシ環境に展開されていた場合は、内部ロードバランサーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="615e8-106">If a load-balanced Edge Server was deployed in your legacy environment, enter the fully qualified domain name (FQDN) of the internal load balancer.</span></span>
  
<span data-ttu-id="615e8-107">**5061**の**内部 SIP アクセスポート**値は、クライアント、従来のフロントエンドプール、およびサーバーと通信するための既定の伝送制御プロトコル (TCP) SIP ポートです。</span><span class="sxs-lookup"><span data-stu-id="615e8-107">The **Internal SIP access port** value of **5061** is the default Transmission Control Protocol (TCP) SIP port for communicating with clients, legacy Front End pools and servers.</span></span> <span data-ttu-id="615e8-108">既定値が使用されなかった場合は、**内部 SIP アクセスポート:** 値を更新します。</span><span class="sxs-lookup"><span data-stu-id="615e8-108">If the default value was not used, update the **Internal SIP access port:** value.</span></span>
  

