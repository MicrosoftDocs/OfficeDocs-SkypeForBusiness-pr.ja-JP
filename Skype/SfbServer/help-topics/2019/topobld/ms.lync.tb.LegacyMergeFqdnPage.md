---
title: 従来版のマージ FQDN
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
ROBOTS: NOINDEX, NOFOLLOW
description: アクセス エッジ プールの内部 FQDN は、フェデレーション、リモート ユーザー アクセス、およびパブリック IM 接続の外部ユーザーと内部ユーザーの通信、さまざまなシナリオに使用されます。 レガシ環境で負荷分散されたエッジ サーバーが配置された場合は、内部ロード バランサー機器の完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: df1def59a082942554e46bc7de75474c3df5aa23
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220559"
---
# <a name="legacy-merge-fqdn"></a><span data-ttu-id="c1f21-104">従来版のマージ FQDN</span><span class="sxs-lookup"><span data-stu-id="c1f21-104">Legacy Merge FQDN</span></span>
 
<span data-ttu-id="c1f21-105">**アクセス エッジ プールの内部 FQDN**は、フェデレーション、リモート ユーザー アクセス、およびパブリック IM 接続の外部ユーザーと内部ユーザーの通信、さまざまなシナリオに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c1f21-105">The **Access Edge Pool internal FQDN** is used for a variety of scenarios where internal users communicate with external users for federation, remote user access, and public IM connectivity.</span></span> <span data-ttu-id="c1f21-106">レガシ環境で負荷分散されたエッジ サーバーが配置された場合は、内部ロード バランサー機器の完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="c1f21-106">If a load-balanced Edge Server was deployed in your legacy environment, enter the fully qualified domain name (FQDN) of the internal load balancer.</span></span>
  
<span data-ttu-id="c1f21-107">**5061**の**内部 SIP アクセス ポート**の値は、クライアントでは、従来のフロント エンド プールおよびサーバーと通信するための既定の伝送制御プロトコル (TCP) を SIP ポートです。</span><span class="sxs-lookup"><span data-stu-id="c1f21-107">The **Internal SIP access port** value of **5061** is the default Transmission Control Protocol (TCP) SIP port for communicating with clients, legacy Front End pools and servers.</span></span> <span data-ttu-id="c1f21-108">既定値が使用できない場合は、更新、**のアクセス ポートの内部 SIP:** の値です。</span><span class="sxs-lookup"><span data-stu-id="c1f21-108">If the default value was not used, update the **Internal SIP access port:** value.</span></span>
  

