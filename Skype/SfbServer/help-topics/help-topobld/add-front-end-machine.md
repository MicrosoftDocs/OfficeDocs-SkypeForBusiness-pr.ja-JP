---
title: フロントエンド コンピューターを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: このプールにフロントエンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。 一覧にコンピューターを追加した後、トポロジを公開するまでの間はいつでも、コンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。 トポロジの公開後に FQDN を変更するには、トポロジ ビルダーでサーバーを削除し、新しいサーバーを新しい FQDN でプールに追加する必要があります。 トポロジへのフロント エンド プールの追加の詳細については、「展開」のドキュメントの「Define and Configure a Front End Pool (フロント エンド プールの定義および構成)」を参照してください。
ms.openlocfilehash: 69837016022f30453a287b6264936e20ec4883ca
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218318"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="66aba-106">フロントエンド コンピューターを追加する</span><span class="sxs-lookup"><span data-stu-id="66aba-106">Add Front End Machine</span></span>

<span data-ttu-id="66aba-107">このプールにフロントエンド サーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="66aba-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="66aba-108">一覧にコンピューターを追加した後、トポロジを公開するまでの間はいつでも、コンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="66aba-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="66aba-109">トポロジの公開後に FQDN を変更するには、トポロジ ビルダーでサーバーを削除し、新しいサーバーを新しい FQDN でプールに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66aba-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="66aba-110">トポロジへのフロント エンド プールの追加の詳細については、「展開」のドキュメントの「[Define and Configure a Front End Pool (フロント エンド プールの定義および構成)](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66aba-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66aba-111">トポロジビルダーは、プール内に最大20台のフロントエンドサーバーを持つことができることを示しています。</span><span class="sxs-lookup"><span data-stu-id="66aba-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="66aba-112">サポートされているサーバーの最大数は12です。</span><span class="sxs-lookup"><span data-stu-id="66aba-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="66aba-113">ファブリックには、最大20個の statefull サーバーを定義できます。これは、1つの時点でアクティブとオンラインにすることができます。</span><span class="sxs-lookup"><span data-stu-id="66aba-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


