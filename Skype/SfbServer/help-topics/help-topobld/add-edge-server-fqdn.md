---
title: エッジ サーバーの FQDN を追加する
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
- ms.lync.tb.AddEdgeServerFqdnsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 84a9511d-601d-4819-a30c-7b08d96e4d97
description: アクセス エッジ サービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。 [機能の選択] ページで [単一の FQDN IP アドレスを使用する] オプションを選択しなかった場合は、 &amp; Web 会議エッジサービスおよび音声ビデオエッジサービスの fqdn も指定する必要があります。
ms.openlocfilehash: d67caefe3e60d8c4e9cd398438fb7a4d93cd9d45
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219228"
---
# <a name="add-edge-server-fqdn"></a><span data-ttu-id="4e7ee-104">エッジ サーバーの FQDN を追加する</span><span class="sxs-lookup"><span data-stu-id="4e7ee-104">Add Edge Server FQDN</span></span>
 
<span data-ttu-id="4e7ee-105">アクセス エッジ サービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e7ee-105">You must specify a fully qualified domain name (FQDN) for the Access Edge service.</span></span> <span data-ttu-id="4e7ee-106">[**機能の選択**] ページで [**単一の fqdn &amp; IP アドレスを使用**する] オプションを選択しなかった場合は、Web 会議エッジサービスおよび音声ビデオエッジサービスの fqdn も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e7ee-106">If you did not select the **Use a single FQDN &amp; IP address** option on the **Select features** page, you must also specify an FQDN for the Web Conferencing Edge service and for the A/V Edge service.</span></span>
  
<span data-ttu-id="4e7ee-107">また、[ **単一の FQDN &amp; IP アドレスを使用** する] オプションを選択した場合、各エッジサービスに異なるポート番号を指定する必要があります (アクセスエッジサービスの場合は444、Web 会議エッジサービスの場合は8057、音声ビデオエッジサービスの場合は 443)。</span><span class="sxs-lookup"><span data-stu-id="4e7ee-107">Also, if you selected the **Use a single FQDN &amp; IP address** option, you must specify a different port number for each of the Edge services (recommended port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="4e7ee-108">このオプションを選択しなかった場合は、3 つすべてのサービスで同じポート番号 (443 など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e7ee-108">If you did not select the option, you can use the same port number (such as 443) for all three services.</span></span>
  

