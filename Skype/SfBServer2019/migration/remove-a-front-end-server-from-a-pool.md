---
title: プールからのフロントエンド サーバーの削除
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: フロントエンドサーバーは、スタンドアロンのコンピューターとしては存在できません。 プール内にコンピューターが1台しかない場合でも、フロントエンドプールとして定義する必要があります。
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752319"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="56da8-104">プールからのフロントエンド サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="56da8-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="56da8-105">フロントエンドサーバーは、スタンドアロンのコンピューターとしては存在できません。</span><span class="sxs-lookup"><span data-stu-id="56da8-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="56da8-106">プール内にコンピューターが1台しかない場合でも、フロントエンドプールとして定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56da8-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="56da8-107">このトピックでは、既存のフロントエンドプールから個々のフロントエンドサーバーを削除するプロセスについて手順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="56da8-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="56da8-108">フロントエンドサーバーがプール内の最後のサーバーである場合、またはプールを完全に削除する場合は、「 [Remove Front end pool Or Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56da8-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="56da8-109">フロントエンドプールを削除する前に、個々のフロントエンドサーバーを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="56da8-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="56da8-110">プールを削除すると、各フロントエンドサーバーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="56da8-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="56da8-111">フロントエンド サーバーをプールから削除するには</span><span class="sxs-lookup"><span data-stu-id="56da8-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="56da8-112">Skype for Business Server 2019 フロントエンドサーバーで、トポロジビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="56da8-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="56da8-113">従来のインストールノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="56da8-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="56da8-114">[ **Enterprise Edition フロントエンドプール**] を展開し、削除するフロントエンドサーバーのフロントエンドプールを展開して、削除するフロントエンドサーバーを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="56da8-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

