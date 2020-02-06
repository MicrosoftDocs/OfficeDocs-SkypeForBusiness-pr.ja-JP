---
title: プールからのフロントエンド サーバーの削除
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: フロントエンドサーバーは、スタンドアロンコンピューターとしては存在できません。 プールに1台のコンピュータしかない場合でも、フロントエンドプールとして定義する必要があります。
ms.openlocfilehash: 93df9e293f7a1876d4a8b1f172472f708556f67f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813035"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="fc662-104">プールからのフロントエンド サーバーの削除</span><span class="sxs-lookup"><span data-stu-id="fc662-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="fc662-105">フロントエンドサーバーは、スタンドアロンコンピューターとしては存在できません。</span><span class="sxs-lookup"><span data-stu-id="fc662-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="fc662-106">プールに1台のコンピュータしかない場合でも、フロントエンドプールとして定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc662-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="fc662-107">このトピックでは、既存のフロントエンドプールから個々のフロントエンドサーバーを削除する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc662-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="fc662-108">フロントエンドサーバーがプール内の最後のサーバーである場合、またはプールを完全に削除する場合は、「[フロントエンドプールまたは Standard Edition サーバーを削除](remove-front-end-pool-or-standard-edition-server.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc662-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="fc662-109">フロントエンドプールを削除する前に、個々のフロントエンドサーバーを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fc662-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="fc662-110">プールを削除すると、各フロントエンドサーバーが削除されます。</span><span class="sxs-lookup"><span data-stu-id="fc662-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="fc662-111">プールからフロントエンドサーバーを削除するには</span><span class="sxs-lookup"><span data-stu-id="fc662-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="fc662-112">Skype for Business Server 2019 フロントエンドサーバーで、[トポロジビルダー] を開きます。</span><span class="sxs-lookup"><span data-stu-id="fc662-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="fc662-113">従来のインストールノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="fc662-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="fc662-114">[ **Enterprise Edition のフロントエンドプール**] を展開し、削除するフロントエンドサーバーでフロントエンドプールを展開して、削除するフロントエンドサーバーを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fc662-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

