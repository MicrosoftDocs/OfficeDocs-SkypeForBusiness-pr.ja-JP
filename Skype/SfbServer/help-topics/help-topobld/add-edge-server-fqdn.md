---
title: エッジ サーバーの FQDN の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerFqdnsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 84a9511d-601d-4819-a30c-7b08d96e4d97
description: アクセスエッジサービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。 [機能の選択] ページで [単一の&amp; fqdn IP アドレスを使用する] オプションを選択していない場合は、Web 会議エッジサービスと a/V Edge サービスの fqdn も指定する必要があります。
ms.openlocfilehash: 9169958646476b18f822f8c178e640c810bd28c1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685260"
---
# <a name="add-edge-server-fqdn"></a><span data-ttu-id="35b92-104">エッジ サーバーの FQDN の追加</span><span class="sxs-lookup"><span data-stu-id="35b92-104">Add Edge Server FQDN</span></span>
 
<span data-ttu-id="35b92-105">アクセスエッジサービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35b92-105">You must specify a fully qualified domain name (FQDN) for the Access Edge service.</span></span> <span data-ttu-id="35b92-106">**[機能の選択**] ページで [**単一の&amp; fqdn IP アドレスを使用**する] オプションを選択していない場合は、Web 会議エッジサービスと a/V Edge サービスの fqdn も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35b92-106">If you did not select the **Use a single FQDN &amp; IP address** option on the **Select features** page, you must also specify an FQDN for the Web Conferencing Edge service and for the A/V Edge service.</span></span>
  
<span data-ttu-id="35b92-107">また、[**単一の FQDN &amp; IP アドレスを使用**する] オプションを選択した場合は、各エッジサービス 444 (アクセスエッジサービスの場合は8057、Web 会議エッジサービスの場合は、a/V Edge サービスの場合は 443) に異なるポート番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35b92-107">Also, if you selected the **Use a single FQDN &amp; IP address** option, you must specify a different port number for each of the Edge services (recommended port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="35b92-108">このオプションを選択しなかった場合は、3つのサービスすべてに同じポート番号 (443 など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35b92-108">If you did not select the option, you can use the same port number (such as 443) for all three services.</span></span>
  

