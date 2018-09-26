---
title: プールからフロント エンド サーバーを削除します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: フロント エンド サーバーは、スタンドアロンのコンピューターとして存在できません。 プール内に 1 台のコンピューターだけがある場合でも、フロント エンド プールとして定義しなければなりません。
ms.openlocfilehash: a9f0adc991355b6f79b20365795ffaf92fa230e2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028944"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="637c4-104">プールからフロント エンド サーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="637c4-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="637c4-105">フロント エンド サーバーは、スタンドアロンのコンピューターとして存在できません。</span><span class="sxs-lookup"><span data-stu-id="637c4-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="637c4-106">プール内に 1 台のコンピューターだけがある場合でも、フロント エンド プールとして定義しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="637c4-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="637c4-107">このトピックでは、既存のフロント エンド プールから個々 のフロント エンド サーバーを削除するプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="637c4-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="637c4-108">フロント エンド サーバーは、プール内の最後のサーバーまたはプールを完全に削除する場合は、[削除のフロント エンド プールまたは Standard Edition サーバー](remove-front-end-pool-or-standard-edition-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="637c4-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="637c4-109">フロント エンド プールを削除する前に、個々 のフロント エンド サーバーを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="637c4-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="637c4-110">プールを削除すると、各フロント エンド サーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="637c4-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="637c4-111">プールからフロント エンド サーバーを削除するのには</span><span class="sxs-lookup"><span data-stu-id="637c4-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="637c4-112">ビジネス 2019 フロント エンド サーバーの Skype、トポロジ ビルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="637c4-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="637c4-113">従来のインストール] ノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="637c4-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="637c4-114">**エンタープライズ エディションのフロント エンド プール**を展開し、削除を削除するには、フロント エンド サーバーを右クリックし、[**削除**] をクリックするとフロント エンド サーバーとフロント エンド プールを展開します。</span><span class="sxs-lookup"><span data-stu-id="637c4-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

