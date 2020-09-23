---
title: 従来のマージ FQDN
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
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
description: アクセスエッジプール内部 FQDN は、内部ユーザーがフェデレーション、リモートユーザーアクセス、およびパブリック IM 接続の外部ユーザーと通信するさまざまなシナリオで使用されます。 従来の環境で負荷分散エッジ サーバーを展開した場合は、その内部ロード バランサーの完全修飾ドメイン名 (FQDN) を入力します。
ms.openlocfilehash: 7060527c513a5dd469f08f628dd9e5415bde09d4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218458"
---
# <a name="legacy-merge-fqdn"></a><span data-ttu-id="a0618-104">従来のマージ FQDN</span><span class="sxs-lookup"><span data-stu-id="a0618-104">Legacy Merge FQDN</span></span>
 
<span data-ttu-id="a0618-p102">[**アクセス エッジ プールの内部 FQDN**] は、フェデレーション、リモート ユーザー アクセス、およびパブリック IM 接続において内部ユーザーが外部ユーザーと通信するさまざまなシナリオで使用します。従来の環境で負荷分散エッジ サーバーを展開した場合は、その内部ロード バランサーの完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0618-p102">The **Access Edge Pool internal FQDN** is used for a variety of scenarios where internal users communicate with external users for federation, remote user access, and public IM connectivity. If a load-balanced Edge Server was deployed in your legacy environment, enter the fully qualified domain name (FQDN) of the internal load balancer.</span></span>
  
<span data-ttu-id="a0618-p103">[**内部 SIP アクセス ポート**] の値 [**5061**] は、クライアントおよび従来のフロントエンド プールとサーバーとの通信で使用する既定の伝送制御プロトコル (TCP) SIP ポートです。既定値を使用しなかった場合は、[**内部 SIP アクセス ポート**] の値を更新します。</span><span class="sxs-lookup"><span data-stu-id="a0618-p103">The **Internal SIP access port** value of **5061** is the default Transmission Control Protocol (TCP) SIP port for communicating with clients, legacy Front End pools and servers. If the default value was not used, update the **Internal SIP access port:** value.</span></span>
  

