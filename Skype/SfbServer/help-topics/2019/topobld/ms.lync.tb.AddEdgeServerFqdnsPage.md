---
title: エッジ サーバーの FQDN を追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: アクセス エッジ サービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。 [機能の選択] ページで [単一の FQDN IP アドレスを使用する] オプションを選択しなかった場合は、Web 会議エッジ サービスと音声ビデオ エッジ サービスの FQDN も指定する必要があります。 &amp;
ms.openlocfilehash: b54e496ca90372c815b850bf87800e73dd354a11
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835927"
---
# <a name="add-edge-server-fqdn"></a><span data-ttu-id="36d23-104">エッジ サーバー FQDN の追加</span><span class="sxs-lookup"><span data-stu-id="36d23-104">Add Edge Server FQDN</span></span>
 
<span data-ttu-id="36d23-105">アクセス エッジ サービスの完全修飾ドメイン名 (FQDN) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36d23-105">You must specify a fully qualified domain name (FQDN) for the Access Edge service.</span></span> <span data-ttu-id="36d23-106">[機能の選択] ページで [単一の **FQDN &amp; IP** アドレスを使用する] オプションを選択しなかった場合は、Web 会議エッジ サービスと音声ビデオ エッジ サービスの FQDN も指定する必要があります。 </span><span class="sxs-lookup"><span data-stu-id="36d23-106">If you did not select the **Use a single FQDN &amp; IP address** option on the **Select features** page, you must also specify an FQDN for the Web Conferencing Edge service and for the A/V Edge service.</span></span>
  
<span data-ttu-id="36d23-107">また、[単一 **の FQDN &amp; IP** アドレスを使用する] オプションを選択した場合は、エッジ サービスごとに異なるポート番号を指定する必要があります (推奨されるポート設定: アクセス エッジ サービスの場合は 444、Web 会議エッジ サービスの場合は 8057、音声ビデオ エッジ サービスの場合は 443)。</span><span class="sxs-lookup"><span data-stu-id="36d23-107">Also, if you selected the **Use a single FQDN &amp; IP address** option, you must specify a different port number for each of the Edge services (recommended port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="36d23-108">このオプションを選択しなかった場合は、3 つすべてのサービスで同じポート番号 (443 など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="36d23-108">If you did not select the option, you can use the same port number (such as 443) for all three services.</span></span>
  

