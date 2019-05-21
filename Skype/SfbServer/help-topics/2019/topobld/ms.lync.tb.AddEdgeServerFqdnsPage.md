---
title: エッジ サーバーの FQDN の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerFqdnsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 84a9511d-601d-4819-a30c-7b08d96e4d97
ROBOTS: NOINDEX, NOFOLLOW
description: アクセスエッジサービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。 [機能の選択] ページで [単一の&amp; fqdn IP アドレスを使用する] オプションを選択していない場合は、Web 会議エッジサービスと a/V Edge サービスの fqdn も指定する必要があります。
ms.openlocfilehash: 39f3c1531dc20879f51ef9cfa2550e4838597ee1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303799"
---
# <a name="add-edge-server-fqdn"></a><span data-ttu-id="91adb-104">エッジ サーバーの FQDN の追加</span><span class="sxs-lookup"><span data-stu-id="91adb-104">Add Edge Server FQDN</span></span>
 
<span data-ttu-id="91adb-105">アクセスエッジサービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91adb-105">You must specify a fully qualified domain name (FQDN) for the Access Edge service.</span></span> <span data-ttu-id="91adb-106">**[機能の選択**] ページで [**単一の&amp; fqdn IP アドレスを使用**する] オプションを選択していない場合は、Web 会議エッジサービスと a/V Edge サービスの fqdn も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91adb-106">If you did not select the **Use a single FQDN &amp; IP address** option on the **Select features** page, you must also specify an FQDN for the Web Conferencing Edge service and for the A/V Edge service.</span></span>
  
<span data-ttu-id="91adb-107">また、[単一の FQDN IP アドレスを使用する] オプションを選択した場合、エッジサービスごとに異なるポート番号を指定する必要があります (推奨されるポートの設定 444: アクセスエッジサービスの場合は8057、Web 会議エッジサービスの場合は、a/V の場合は 443)エッジサービス)。</span><span class="sxs-lookup"><span data-stu-id="91adb-107">Also, if you selected the **Use a single FQDN &amp; IP address** option, you must specify a different port number for each of the Edge services (recommended port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="91adb-108">このオプションを選択しなかった場合は、3つのサービスすべてに同じポート番号 (443 など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="91adb-108">If you did not select the option, you can use the same port number (such as 443) for all three services.</span></span>
  

