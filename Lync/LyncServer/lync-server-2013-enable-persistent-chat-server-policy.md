---
title: 'Lync Server 2013: 常設チャット サーバー ポリシーを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58e71cd92182fc9f68d272ba23079677983b399
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="fdee1-102">Lync Server 2013 で常設チャット サーバー ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="fdee1-102">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdee1-103">_**最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="fdee1-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="fdee1-104">Lync Server 2013 コントロールパネルでは、**常設チャット**グループの**常設チャットのポリシー**ページを使用して、既定のグローバルポリシーの構成と1つ以上のユーザーレベルでポリシーを管理できます。展開用の追加のユーザーとサイトポリシー。</span><span class="sxs-lookup"><span data-stu-id="fdee1-104">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="fdee1-105">ユーザーが、ポリシーによって常設チャットサーバーを有効にしている場合は、常設チャットサーバー環境が Lync 2013 クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdee1-105">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fdee1-106">トポロジでは、常設チャットサーバーのサイトポリシーは、ユーザーのプールごと、またはユーザーごとのサイトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="fdee1-106">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="fdee1-107">グローバルポリシーは、常設チャットサーバーの展開時に自動的に作成され、構成はできますが、削除はできません。</span><span class="sxs-lookup"><span data-stu-id="fdee1-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="fdee1-108">グローバル ポリシーはすべてのユーザーに適用されるため、ユーザーごとに設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fdee1-108">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="fdee1-109">グローバルポリシーと共に、常設チャットサーバーのユーザーを有効にする、複数のサイトとユーザーのポリシーを作成して構成することができます。</span><span class="sxs-lookup"><span data-stu-id="fdee1-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="fdee1-110">プールとサイトの常設チャットサーバーポリシーは、そのサイトのユーザーに対してのみ、グローバル常設チャットサーバーポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="fdee1-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="fdee1-111">ユーザーポリシーは、ユーザーポリシーが割り当てられているユーザーのグローバル、プール、サイトの各ポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="fdee1-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fdee1-112">常設チャットサーバーを構成して使用するには、最初にトポロジビルダーを使用して、トポロジに常設チャットサーバーサポートを追加してから、トポロジを発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdee1-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="fdee1-113">詳細については、展開ドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdee1-113">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fdee1-114">このセクション中</span><span class="sxs-lookup"><span data-stu-id="fdee1-114">In This Section</span></span>

  - [<span data-ttu-id="fdee1-115">Lync Server 2013 で常設チャットのグローバル ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="fdee1-115">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="fdee1-116">Lync Server 2013 で常設チャットのサイト ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="fdee1-116">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="fdee1-117">Lync Server 2013 で常設チャット用のユーザー ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="fdee1-117">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="fdee1-118">Lync Server 2013 で常設チャット ポリシーをユーザーまたはユーザー グループに適用する</span><span class="sxs-lookup"><span data-stu-id="fdee1-118">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

