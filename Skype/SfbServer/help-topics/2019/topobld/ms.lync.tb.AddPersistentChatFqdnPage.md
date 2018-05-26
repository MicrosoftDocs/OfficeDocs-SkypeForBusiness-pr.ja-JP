---
title: 常設チャットの FQDN の定義
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: 新しい永続的なチャットのサーバーまたは新しい永続的なチャット プールの定義ウィザードを使用して永続的なチャット サーバー プールを作成するとします。 複数コンピューターのプール] または [単一コンピューターのプールを選択します。 単一コンピューター プールを選択し、後で複数コンピューター プールが必要になった場合は、その単一コンピューター プールを削除してから複数コンピューター プールを定義する必要があります。
ms.openlocfilehash: 419eab5bb6f92c3b0859214042e59378b5d8c601
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2018
---
# <a name="define-persistent-chat-fqdn"></a><span data-ttu-id="93abd-105">常設チャットの FQDN の定義</span><span class="sxs-lookup"><span data-stu-id="93abd-105">Define Persistent Chat FQDN</span></span>
 
<span data-ttu-id="93abd-106">新しい永続的なチャットのサーバーまたは**新しい永続的なチャット プールの定義**ウィザードを使用して永続的なチャット サーバー プールを作成するとします。</span><span class="sxs-lookup"><span data-stu-id="93abd-106">You create a new Persistent Chat Server or Persistent Chat Server pool using the **Define New Persistent Chat Pool** wizard.</span></span> <span data-ttu-id="93abd-107">**複数コンピューター プール**または**単一コンピューター プール**を選択してください。</span><span class="sxs-lookup"><span data-stu-id="93abd-107">Select either a **Multiple computer pool** or a **Single computer pool**.</span></span> <span data-ttu-id="93abd-108">単一コンピューター プールを選択し、後で複数コンピューター プールが必要になった場合は、その単一コンピューター プールを削除してから複数コンピューター プールを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93abd-108">If you select a single computer pool and later need a multiple computer pool, you will need to remove the single computer pool and then define a multiple computer pool.</span></span>
  
<span data-ttu-id="93abd-109">永続的なチャット サーバーまたは永続的なチャット サーバー プールの**プールの FQDN**を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93abd-109">You must also define a **Pool FQDN** for the Persistent Chat Server or Persistent Chat Server pool.</span></span> <span data-ttu-id="93abd-110">単一コンピューター プールのプール完全修飾ドメイン名 (FQDN) は、その単一サーバー プールを形成するコンピューターの FQDN と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="93abd-110">The pool fully qualified domain name (FQDN) for a single computer pool must be the same as the FQDN of the computer that makes up the single server pool.</span></span> <span data-ttu-id="93abd-111">複数コンピューター プールの場合、FQDN はその複数コンピューター プールを表すために選択した名前であることが必要で、これは DNS でホスト A (および IPv6 を使用する場合は AAAA) レコードによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="93abd-111">For a multiple computer pool, the FQDN must be the name you choose to represent this multiple computer pool and is defined in DNS by a host A (and AAAA if IPv6 is being used) record.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="93abd-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="93abd-112">See also</span></span>

#### 

[<span data-ttu-id="93abd-113">ビジネス サーバー 2015 の Skype での永続的なチャット サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="93abd-113">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="93abd-114">ビジネス サーバー 2015 トポロジの場合、Skype に永続的なチャット サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="93abd-114">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

