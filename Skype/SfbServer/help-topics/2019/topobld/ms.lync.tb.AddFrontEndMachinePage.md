---
title: フロント エンド コンピューターを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: このプール内のフロント エンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。 一覧にコンピューターを追加した後でも、トポロジを公開するまでの間は、いつでもコンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。 トポロジ ビルダーでは、サーバーを削除し、新しい FQDN を持つプールに新しいサーバーを追加、トポロジを公開すると、FQDN を変更する必要です。 トポロジにフロント エンド プールを追加する方法の詳細を定義して構成するフロント エンド プールを展開に関するドキュメントを参照してください。
ms.openlocfilehash: e1353c84316858282d5b3a78491190f4ea611117
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23262170"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="054dd-106">フロント エンド コンピューターを追加します。</span><span class="sxs-lookup"><span data-stu-id="054dd-106">Add Front End Machine</span></span>

<span data-ttu-id="054dd-107">このプール内のフロント エンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="054dd-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="054dd-108">一覧にコンピューターを追加した後でも、トポロジを公開するまでの間は、いつでもコンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="054dd-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="054dd-109">トポロジ ビルダーでは、サーバーを削除し、新しい FQDN を持つプールに新しいサーバーを追加、トポロジを公開すると、FQDN を変更する必要です。</span><span class="sxs-lookup"><span data-stu-id="054dd-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="054dd-110">トポロジにフロント エンド プールを追加する方法の詳細は、展開に関するドキュメントの[定義およびフロント エンド プールを構成する](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="054dd-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="054dd-111">トポロジ ビルダーがプール内に最大 20 個のフロント エンド サーバーを持つことができることを示しているに注意してください。</span><span class="sxs-lookup"><span data-stu-id="054dd-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="054dd-112">サーバーの最大許容数は 12 です。</span><span class="sxs-lookup"><span data-stu-id="054dd-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="054dd-113">うち 12 でき、アクティブなオンライン同時に、ファブリック内で定義されている最大 20 個のステートフル サーバーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="054dd-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


