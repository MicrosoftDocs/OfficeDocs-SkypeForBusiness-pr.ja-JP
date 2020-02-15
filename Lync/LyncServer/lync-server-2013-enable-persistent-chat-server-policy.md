---
title: 'Lync Server 2013: 常設チャットサーバーポリシーの有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1f98275ee911d1abecbc60907653ad8de0a4222
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="62697-102">Lync Server 2013 で常設チャットサーバーポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="62697-102">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62697-103">_**トピックの最終更新日:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="62697-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="62697-104">Lync Server 2013 コントロールパネルでは、**常設チャット**グループの [**常設チャットポリシー** ] ページを使用して、グローバル、プール、サイト、またはユーザーレベルでポリシーを管理できます。これには、既定のグローバルポリシーの構成や、展開用の1つまたは複数の追加のユーザーおよびサイトポリシーの作成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="62697-104">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="62697-105">ユーザーがポリシーによって常設チャットサーバーに対して有効になっている場合、常設チャットサーバー環境が Lync 2013 クライアントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="62697-105">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62697-106">トポロジでは、常設チャットサーバーのサイトポリシーは、グローバルに、ユーザーのプールごと、またはユーザーのサイトごと、またはユーザーごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="62697-106">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="62697-107">グローバルポリシーは、常設チャットサーバーを展開するときに自動的に作成されますが、構成することはできますが、削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="62697-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="62697-108">グローバル ポリシーはすべてのユーザーに適用されるため、ユーザーごとに設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="62697-108">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="62697-109">グローバルポリシーと共に、常設チャットサーバーに対してユーザーを有効にする複数のサイトおよびユーザーポリシーを作成し、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="62697-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="62697-110">プールおよびサイト常設チャットサーバーポリシーは、そのサイトのユーザーに対してのみ、グローバル常設チャットサーバーポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="62697-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="62697-111">ユーザーポリシーは、ユーザーポリシーが割り当てられているユーザーのグローバル、プール、およびサイトポリシーの両方を上書きします。</span><span class="sxs-lookup"><span data-stu-id="62697-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62697-112">常設チャットサーバーを構成して使用するには、まず、トポロジビルダーを使用して、常設チャットサーバーのサポートをトポロジに追加してから、トポロジを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62697-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="62697-113">詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 での展開への常設チャットサーバーの追加</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62697-113">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="62697-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="62697-114">In This Section</span></span>

  - [<span data-ttu-id="62697-115">Lync Server 2013 で常設チャットのグローバルポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="62697-115">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="62697-116">Lync Server 2013 で常設チャットのサイトポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="62697-116">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="62697-117">Lync Server 2013 で常設チャット用のユーザーポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="62697-117">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="62697-118">Lync Server 2013 で常設チャットポリシーをユーザーまたはユーザーグループに適用する</span><span class="sxs-lookup"><span data-stu-id="62697-118">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

