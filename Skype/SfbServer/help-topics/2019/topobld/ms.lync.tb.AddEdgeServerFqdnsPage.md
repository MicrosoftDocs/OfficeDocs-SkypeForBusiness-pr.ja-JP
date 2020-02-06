---
title: エッジ サーバーの FQDN の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerFqdnsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 84a9511d-601d-4819-a30c-7b08d96e4d97
ROBOTS: NOINDEX, NOFOLLOW
description: アクセスエッジサービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。 [機能の選択] ページで [単一の&amp; fqdn IP アドレスを使用する] オプションを選択していない場合は、Web 会議エッジサービスと a/V Edge サービスの fqdn も指定する必要があります。
ms.openlocfilehash: 2c7434331185006dd0c3b146872634ee7b9a40d8
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798214"
---
# <a name="add-edge-server-fqdn"></a><span data-ttu-id="516b6-104">エッジ サーバーの FQDN の追加</span><span class="sxs-lookup"><span data-stu-id="516b6-104">Add Edge Server FQDN</span></span>
 
<span data-ttu-id="516b6-105">アクセスエッジサービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="516b6-105">You must specify a fully qualified domain name (FQDN) for the Access Edge service.</span></span> <span data-ttu-id="516b6-106">**[機能の選択**] ページで [**単一の&amp; fqdn IP アドレスを使用**する] オプションを選択していない場合は、Web 会議エッジサービスと a/V Edge サービスの fqdn も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="516b6-106">If you did not select the **Use a single FQDN &amp; IP address** option on the **Select features** page, you must also specify an FQDN for the Web Conferencing Edge service and for the A/V Edge service.</span></span>
  
<span data-ttu-id="516b6-107">また、[**単一の FQDN &amp; IP アドレスを使用**する] オプションを選択した場合は、各エッジサービス 444 (アクセスエッジサービスの場合は8057、Web 会議エッジサービスの場合は、a/V Edge サービスの場合は 443) に異なるポート番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="516b6-107">Also, if you selected the **Use a single FQDN &amp; IP address** option, you must specify a different port number for each of the Edge services (recommended port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="516b6-108">このオプションを選択しなかった場合は、3つのサービスすべてに同じポート番号 (443 など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="516b6-108">If you did not select the option, you can use the same port number (such as 443) for all three services.</span></span>
  

