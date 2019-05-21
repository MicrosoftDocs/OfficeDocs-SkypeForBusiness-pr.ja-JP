---
title: フロントエンド コンピューターの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: このプールでフロントエンドサーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。 一覧にコンピューターを追加した後でも、トポロジを公開するまでの間は、いつでもコンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。 トポロジを公開した後、FQDN を変更するには、トポロジビルダーでサーバーを削除してから新しい FQDN のプールに新しいサーバーを追加する必要があります。 トポロジへのフロントエンドプールの追加について詳しくは、「展開ドキュメントでフロントエンドプールを定義して構成する」をご覧ください。
ms.openlocfilehash: a97437f9775c603ca768403f44699cfffc069fbe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281480"
---
# <a name="add-front-end-machine"></a><span data-ttu-id="ceaf3-106">フロントエンド コンピューターの追加</span><span class="sxs-lookup"><span data-stu-id="ceaf3-106">Add Front End Machine</span></span>

<span data-ttu-id="ceaf3-107">このプールでフロントエンドサーバーとして追加する各コンピューターの完全修飾ドメイン名 (FQDN) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ceaf3-107">Specify the fully qualified domain name (FQDN) of each computer that you want to add as a Front End Server in this pool.</span></span> <span data-ttu-id="ceaf3-108">一覧にコンピューターを追加した後でも、トポロジを公開するまでの間は、いつでもコンピューターの FQDN を更新したり、プールからコンピューターを削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="ceaf3-108">After adding a computer to the list, you can update the FQDN of the computer or remove it from the pool at any time prior to publishing the topology.</span></span> <span data-ttu-id="ceaf3-109">トポロジを公開した後、FQDN を変更するには、トポロジビルダーでサーバーを削除してから新しい FQDN のプールに新しいサーバーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceaf3-109">After you publish the topology, changing the FQDN requires deleting the server in Topology Builder and then adding a new server to the pool with the new FQDN.</span></span> <span data-ttu-id="ceaf3-110">トポロジへのフロントエンドプールの追加について詳しくは、「展開ドキュメントで[フロントエンドプールを定義して構成](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ceaf3-110">For details about adding a Front End pool to the topology, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ceaf3-111">トポロジビルダーでは、1つのプールに最大20台のフロントエンドサーバーを含めることができることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ceaf3-111">Note that Topology Builder indicates that you can have up to 20 Front End Servers in a pool.</span></span> <span data-ttu-id="ceaf3-112">サポートされているサーバーの最大数は12です。</span><span class="sxs-lookup"><span data-stu-id="ceaf3-112">The maximum supported number of servers is 12.</span></span> <span data-ttu-id="ceaf3-113">ファブリックには最大20の statefull サーバーを定義できます。これは、どの時点でもアクティブとオンラインにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ceaf3-113">You can have up to 20 statefull servers defined in the fabric, of which 12 can be active and online at any one time.</span></span>


