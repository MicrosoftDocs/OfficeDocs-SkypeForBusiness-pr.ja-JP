---
title: フロントエンド コンピューターを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: このプールにフロントエンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。 一覧にコンピューターを追加した後、トポロジを公開するまでの間はいつでも、コンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。 トポロジの公開後に FQDN を変更するには、トポロジ ビルダーでサーバーを削除し、新しいサーバーを新しい FQDN でプールに追加する必要があります。 トポロジへのフロント エンド プールの追加の詳細については、「展開」のドキュメントの「Define and Configure a Front End Pool (フロント エンド プールの定義および構成)」を参照してください。
ms.openlocfilehash: f962c41de50bad710edb80422911cb0c3f59943e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118686"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="1b7f9-106">フロント エンド コンピューターの追加</span><span class="sxs-lookup"><span data-stu-id="1b7f9-106">Add Front End Machine</span></span>

<span data-ttu-id="1b7f9-107">このプールにフロントエンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b7f9-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="1b7f9-108">一覧にコンピューターを追加した後、トポロジを公開するまでの間はいつでも、コンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="1b7f9-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="1b7f9-109">トポロジの公開後に FQDN を変更するには、トポロジ ビルダーでサーバーを削除し、新しいサーバーを新しい FQDN でプールに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b7f9-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="1b7f9-110">トポロジへのフロント エンド プールの追加の詳細については、「展開」のドキュメントの「[Define and Configure a Front End Pool (フロント エンド プールの定義および構成)](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b7f9-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b7f9-111">トポロジ ビルダーは、プール内に最大 20 台のフロント エンド サーバーを含め可能な点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="1b7f9-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="1b7f9-112">サポートされるサーバーの最大数は 12 です。</span><span class="sxs-lookup"><span data-stu-id="1b7f9-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="1b7f9-113">ファブリックで定義できるステートフル サーバーは最大 20 台で、そのうち 12 台は一度にアクティブおよびオンラインにできます。</span><span class="sxs-lookup"><span data-stu-id="1b7f9-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>