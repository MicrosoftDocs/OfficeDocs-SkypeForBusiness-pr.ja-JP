---
title: 常設チャットの FQDN の定義
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 新しい常設チャット サーバーまたは常設チャット サーバー プールは、新しい常設チャット プールの定義ウィザードを使用して作成します。 複数コンピューター プールまたは 1 台のコンピューター プールのどちらかを選択します。 1 台のコンピューター プールを選択し、後で複数のコンピューター プールが必要な場合は、単一のコンピューター プールを削除してから、複数のコンピューター プールを定義する必要があります。
ms.openlocfilehash: e96cc1f3c71dee7bab50d3101281596c17084207
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818447"
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="190c0-105">常設チャットの FQDN の定義</span><span class="sxs-lookup"><span data-stu-id="190c0-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="190c0-106">常設チャット プールの新しい定義ウィザードを使用して、新しい常設チャット サーバーまたは常設チャット サーバー プール **を作成** します。</span><span class="sxs-lookup"><span data-stu-id="190c0-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="190c0-107">複数のコンピューター プール **または 1 台** のコンピューター **プールを選択します**。</span><span class="sxs-lookup"><span data-stu-id="190c0-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="190c0-108">1 台のコンピューター プールを選択し、後で複数のコンピューター プールが必要な場合は、単一のコンピューター プールを削除してから、複数のコンピューター プールを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="190c0-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="190c0-109">また、常設チャット サーバーまたは常設チャット サーバー プールのプール **FQDN** も定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="190c0-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="190c0-110">1 台のコンピューター プールのプール完全修飾ドメイン名 (FQDN) は、単一サーバー プールを構成するコンピューターの FQDN と同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="190c0-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="190c0-111">複数コンピューター プールの場合、FQDN は、この複数コンピューター プールを表す名前である必要があります。FQDN は、ホスト A (および IPv6 が使用されている場合は AAAA) レコードによって DNS で定義されます。</span><span class="sxs-lookup"><span data-stu-id="190c0-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="190c0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="190c0-112">See also</span></span>

[<span data-ttu-id="190c0-113">Skype for Business Server 2015 での常設チャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="190c0-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="190c0-114">Skype for Business Server 2015 トポロジへの常設チャット サーバーの追加</span><span class="sxs-lookup"><span data-stu-id="190c0-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
