---
title: 従来版のマージ FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
description: Access Edge プールの内部 FQDN は、内部ユーザーがフェデレーション、リモートユーザーアクセス、パブリック IM 接続の外部ユーザーと通信するさまざまなシナリオで使用されます。 負荷分散エッジサーバーがレガシ環境に展開されていた場合は、内部ロードバランサーの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: a684ae21e693119bd6bccd1a457d42cf4b37d3a7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819759"
---
# <a name="legacy-merge-fqdn"></a><span data-ttu-id="53473-104">従来版のマージ FQDN</span><span class="sxs-lookup"><span data-stu-id="53473-104">Legacy Merge FQDN</span></span>
 
<span data-ttu-id="53473-105">**Access Edge プールの内部 FQDN**は、内部ユーザーがフェデレーション、リモートユーザーアクセス、パブリック IM 接続の外部ユーザーと通信するさまざまなシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="53473-105">The **Access Edge Pool internal FQDN** is used for a variety of scenarios where internal users communicate with external users for federation, remote user access, and public IM connectivity.</span></span> <span data-ttu-id="53473-106">負荷分散エッジサーバーがレガシ環境に展開されていた場合は、内部ロードバランサーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="53473-106">If a load-balanced Edge Server was deployed in your legacy environment, enter the fully qualified domain name (FQDN) of the internal load balancer.</span></span>
  
<span data-ttu-id="53473-107">**5061**の**内部 SIP アクセスポート**値は、クライアント、従来のフロントエンドプール、およびサーバーと通信するための既定の伝送制御プロトコル (TCP) SIP ポートです。</span><span class="sxs-lookup"><span data-stu-id="53473-107">The **Internal SIP access port** value of **5061** is the default Transmission Control Protocol (TCP) SIP port for communicating with clients, legacy Front End pools and servers.</span></span> <span data-ttu-id="53473-108">既定値が使用されなかった場合は、**内部 SIP アクセスポート:** 値を更新します。</span><span class="sxs-lookup"><span data-stu-id="53473-108">If the default value was not used, update the **Internal SIP access port:** value.</span></span>
  

