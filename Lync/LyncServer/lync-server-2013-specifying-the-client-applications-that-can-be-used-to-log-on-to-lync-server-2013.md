---
title: 'Lync Server 2013: Lync Server 2013 へのログオンに使用できるクライアントアプリケーションの指定'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying the client applications that can be used to log on to Lync Server 2013
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48185450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 788a0638dee6b9d52a5d954eafb7b4e33bdfd294
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="2e486-102">Lync Server 2013 へのログオンに使用できるクライアントアプリケーションの指定</span><span class="sxs-lookup"><span data-stu-id="2e486-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e486-103">_**最終更新日:** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="2e486-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="2e486-104">Lync Server 2013 では、環境でサポートされているクライアントのバージョンを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2e486-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="2e486-105">クライアントバージョンポリシーを使用すると、複数のクライアントバージョンのサポートに関連するコストを削減することができます。</span><span class="sxs-lookup"><span data-stu-id="2e486-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="2e486-106">また、以前のバージョンのクライアントが動作している場合、使用可能な機能は以前のバージョンのクライアントで制限される可能性があるため、全体的なユーザーエクスペリエンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="2e486-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="2e486-107">クライアントのバージョン管理には、次の3つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="2e486-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="2e486-108">クライアントバージョンの構成設定は、グローバルに、または特定のサイトに対して、クライアントのバージョン管理をオンまたはオフにするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2e486-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="2e486-109">クライアントバージョンポリシーは、一連のルールをグローバルに、または特定のサイト、プール、またはユーザーのグループに割り当てるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2e486-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="2e486-110">クライアントバージョンポリシールールは、クライアントバージョンポリシーを構成し、ユーザーが特定のクライアントとクライアントバージョンでログオンしようとしたときに実行するアクションを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="2e486-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2e486-111">匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="2e486-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2e486-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="2e486-112">In This Section</span></span>

  - [<span data-ttu-id="2e486-113">Lync Server 2013 のクライアントバージョンの構成設定</span><span class="sxs-lookup"><span data-stu-id="2e486-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="2e486-114">Lync Server 2013 のクライアントバージョンポリシー</span><span class="sxs-lookup"><span data-stu-id="2e486-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="2e486-115">Lync Server 2013 でのクライアントのバージョンルール</span><span class="sxs-lookup"><span data-stu-id="2e486-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2e486-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e486-116">See Also</span></span>


[<span data-ttu-id="2e486-117">Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="2e486-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

