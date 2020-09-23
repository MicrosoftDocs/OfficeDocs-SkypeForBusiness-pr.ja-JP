---
title: 常設チャットの FQDN の定義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: '[新しい常設チャットプールの定義] ウィザードを使用して、新しい常設チャットサーバーまたは常設チャットサーバープールを作成します。 [複数のコンピュータープール] または [単一コンピュータープール] のどちらかを選択します。 1台のコンピュータープールを選択し、後で複数のコンピュータープールが必要な場合は、1台のコンピュータープールを削除してから、複数のコンピュータープールを定義する必要があります。'
ms.openlocfilehash: 61851656b70b85db47fdad01dff0101217262dda
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217554"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="e7ded-105">常設チャットの FQDN の定義</span><span class="sxs-lookup"><span data-stu-id="e7ded-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="e7ded-106">[ **新しい常設チャットプールの定義** ] ウィザードを使用して、新しい常設チャットサーバーまたは常設チャットサーバープールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e7ded-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="e7ded-107">[複数の **コンピュータープール** ] または [ **単一コンピュータープール**] のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7ded-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="e7ded-108">1台のコンピュータープールを選択し、後で複数のコンピュータープールが必要な場合は、1台のコンピュータープールを削除してから、複数のコンピュータープールを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7ded-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="e7ded-109">また、常設チャットサーバーまたは常設チャットサーバープールの **プール FQDN** も定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7ded-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="e7ded-110">単一のコンピュータープールのプールの完全修飾ドメイン名 (FQDN) は、単一のサーバープールを構成するコンピューターの FQDN と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7ded-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="e7ded-111">複数のコンピュータープールの場合、FQDN は、この複数のコンピュータープールを表すために選択した名前であり、ホスト A (および IPv6 が使用されている場合は AAAA) によって DNS で定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7ded-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7ded-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7ded-112">See also</span></span>

[<span data-ttu-id="e7ded-113">Skype for Business Server 2015 での常設チャットサーバーの計画</span><span class="sxs-lookup"><span data-stu-id="e7ded-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="e7ded-114">常設チャットサーバーを Skype for Business Server 2015 トポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="e7ded-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
