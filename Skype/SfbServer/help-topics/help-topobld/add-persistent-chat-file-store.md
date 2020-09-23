---
title: 常設チャットのファイル ストアの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Standard Edition サーバーまたは Enterprise Edition フロント エンドのプールのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。
ms.openlocfilehash: 76169673848d9cbace41642d5058bfb60e90508a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218678"
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="7fafa-104">常設チャットのファイル ストアの追加</span><span class="sxs-lookup"><span data-stu-id="7fafa-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="7fafa-p102">Standard Edition サーバーまたは Enterprise Edition フロント エンドのプールのファイル ストアとして使用するファイル共有を指定する必要があります。既存のファイル共有をファイル ストアに使用できます。または、ファイル共有を配置するファイル サーバーの完全修飾ドメイン名 (FQDN) と新しいファイル共有のフォルダー名を指定して、新しいファイル共有を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7fafa-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7fafa-107">Skype for Business Server のファイル共有は、Enterprise Edition フロントエンドサーバーに配置することはできませんが、Standard Edition サーバーに配置することはできます。</span><span class="sxs-lookup"><span data-stu-id="7fafa-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7fafa-108">ファイル共有を作成する前にトポロジ ビルダーでファイル共有を定義できますが、トポロジを公開する前に定義する定義済みの場所にファイル共有を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fafa-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7fafa-109">常設チャットサーバーまたは常設チャットサーバープールをトポロジに追加するには、トポロジビルダーでファイルストアをセットアップし、ファイルストアに使用するファイル共有に随意アクセス制御リスト (Dacl) を構成できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fafa-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="7fafa-110">これには、トポロジ ビルダーを実行して新しいトポロジを公開するときに、サイト共有のフル コントロール アクセス許可 (読み取り/書き込み/変更) を持つアカウントでログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fafa-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7fafa-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fafa-111">See also</span></span>

[<span data-ttu-id="7fafa-112">Skype for Business Server 2015 での常設チャットサーバーの計画</span><span class="sxs-lookup"><span data-stu-id="7fafa-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="7fafa-113">常設チャットサーバーを Skype for Business Server 2015 トポロジに追加する</span><span class="sxs-lookup"><span data-stu-id="7fafa-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="7fafa-114">Skype for Business Server 2015 の常設チャットサーバーのハードウェアおよびソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="7fafa-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="7fafa-115">Skype for Business Server 2015 のサーバー要件</span><span class="sxs-lookup"><span data-stu-id="7fafa-115">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="7fafa-116">Skype for Business Server 2015 のトポロジの基本</span><span class="sxs-lookup"><span data-stu-id="7fafa-116">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)
