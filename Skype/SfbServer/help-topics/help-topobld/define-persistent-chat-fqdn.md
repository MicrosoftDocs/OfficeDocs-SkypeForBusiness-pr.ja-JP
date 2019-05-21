---
title: 常設チャットの FQDN の定義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: '[新しい常設チャットプールの定義] ウィザードを使用して、新しい常設チャットサーバーまたは常設チャットサーバープールを作成します。 複数コンピューター プールまたは単一コンピューター プールを選択してください。 単一コンピューター プールを選択し、後で複数コンピューター プールが必要になった場合は、その単一コンピューター プールを削除してから複数コンピューター プールを定義する必要があります。'
ms.openlocfilehash: 247645e5cc87d23db25784d31c2727d56fab2681
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305874"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="1a10f-105">常設チャットの FQDN の定義</span><span class="sxs-lookup"><span data-stu-id="1a10f-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="1a10f-106">[新しい常設チャット**プールの定義**] ウィザードを使用して、新しい常設チャットサーバーまたは常設チャットサーバープールを作成します。</span><span class="sxs-lookup"><span data-stu-id="1a10f-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="1a10f-107">**複数コンピューター プール**または**単一コンピューター プール**を選択してください。</span><span class="sxs-lookup"><span data-stu-id="1a10f-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="1a10f-108">単一コンピューター プールを選択し、後で複数コンピューター プールが必要になった場合は、その単一コンピューター プールを削除してから複数コンピューター プールを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a10f-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="1a10f-109">また、常設チャットサーバープールまたは常設チャットサーバープールの**プール FQDN**も定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a10f-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="1a10f-110">単一コンピューター プールのプール完全修飾ドメイン名 (FQDN) は、その単一サーバー プールを形成するコンピューターの FQDN と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a10f-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="1a10f-111">複数コンピューター プールの場合、FQDN はその複数コンピューター プールを表すために選択した名前であることが必要で、これは DNS でホスト A (および IPv6 を使用する場合は AAAA) レコードによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="1a10f-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1a10f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a10f-112">See also</span></span>

[<span data-ttu-id="1a10f-113">Skype for Business Server 2015 の常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="1a10f-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="1a10f-114">Skype for Business Server 2015 トポロジに常設チャットサーバーを追加する</span><span class="sxs-lookup"><span data-stu-id="1a10f-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
