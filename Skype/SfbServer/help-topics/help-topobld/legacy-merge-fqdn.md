---
title: FQDN レガシ データの差し込み
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
description: アクセス エッジ プールの内部 FQDN は、フェデレーション、リモート ユーザー アクセス、およびパブリック IM 接続の外部ユーザーと内部ユーザーの通信、さまざまなシナリオに使用されます。 レガシ環境で負荷分散されたエッジ サーバーが配置された場合は、内部ロード バランサー機器の完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: 86f06718e3d8a149dc93a990edbb9c0359c0d087
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987065"
---
# <a name="legacy-merge-fqdn"></a><span data-ttu-id="a3891-104">FQDN レガシ データの差し込み</span><span class="sxs-lookup"><span data-stu-id="a3891-104">Legacy Merge FQDN</span></span>
 
<span data-ttu-id="a3891-105">**アクセス エッジ プールの内部 FQDN**は、フェデレーション、リモート ユーザー アクセス、およびパブリック IM 接続の外部ユーザーと内部ユーザーの通信、さまざまなシナリオに使用されます。</span><span class="sxs-lookup"><span data-stu-id="a3891-105">The **Access Edge Pool internal FQDN** is used for a variety of scenarios where internal users communicate with external users for federation, remote user access, and public IM connectivity.</span></span> <span data-ttu-id="a3891-106">レガシ環境で負荷分散されたエッジ サーバーが配置された場合は、内部ロード バランサー機器の完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a3891-106">If a load-balanced Edge Server was deployed in your legacy environment, enter the fully qualified domain name (FQDN) of the internal load balancer.</span></span>
  
<span data-ttu-id="a3891-107">**5061**の**内部 SIP アクセス ポート**の値は、クライアントでは、従来のフロント エンド プールおよびサーバーと通信するための既定の伝送制御プロトコル (TCP) を SIP ポートです。</span><span class="sxs-lookup"><span data-stu-id="a3891-107">The **Internal SIP access port** value of **5061** is the default Transmission Control Protocol (TCP) SIP port for communicating with clients, legacy Front End pools and servers.</span></span> <span data-ttu-id="a3891-108">既定値が使用できない場合は、更新、**のアクセス ポートの内部 SIP:** の値です。</span><span class="sxs-lookup"><span data-stu-id="a3891-108">If the default value was not used, update the **Internal SIP access port:** value.</span></span>
  

