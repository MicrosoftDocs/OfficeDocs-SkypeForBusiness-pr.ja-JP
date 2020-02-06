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
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeServerFqdnsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 84a9511d-601d-4819-a30c-7b08d96e4d97
description: アクセスエッジサービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。 [機能の選択] ページで [単一の&amp; fqdn IP アドレスを使用する] オプションを選択していない場合は、Web 会議エッジサービスと a/V Edge サービスの fqdn も指定する必要があります。
ms.openlocfilehash: c3ccc2f42f090fd3d6f28d22064de98879561a01
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821059"
---
# <a name="add-edge-server-fqdn"></a><span data-ttu-id="d934e-104">エッジ サーバーの FQDN の追加</span><span class="sxs-lookup"><span data-stu-id="d934e-104">Add Edge Server FQDN</span></span>
 
<span data-ttu-id="d934e-105">アクセスエッジサービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d934e-105">You must specify a fully qualified domain name (FQDN) for the Access Edge service.</span></span> <span data-ttu-id="d934e-106">**[機能の選択**] ページで [**単一の&amp; fqdn IP アドレスを使用**する] オプションを選択していない場合は、Web 会議エッジサービスと a/V Edge サービスの fqdn も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d934e-106">If you did not select the **Use a single FQDN &amp; IP address** option on the **Select features** page, you must also specify an FQDN for the Web Conferencing Edge service and for the A/V Edge service.</span></span>
  
<span data-ttu-id="d934e-107">また、[**単一の FQDN &amp; IP アドレスを使用**する] オプションを選択した場合は、各エッジサービス 444 (アクセスエッジサービスの場合は8057、Web 会議エッジサービスの場合は、a/V Edge サービスの場合は 443) に異なるポート番号を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d934e-107">Also, if you selected the **Use a single FQDN &amp; IP address** option, you must specify a different port number for each of the Edge services (recommended port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="d934e-108">このオプションを選択しなかった場合は、3つのサービスすべてに同じポート番号 (443 など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d934e-108">If you did not select the option, you can use the same port number (such as 443) for all three services.</span></span>
  

