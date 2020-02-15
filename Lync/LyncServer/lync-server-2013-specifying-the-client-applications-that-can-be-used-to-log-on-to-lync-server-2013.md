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
ms.openlocfilehash: ea0083a28253f5b79e6124dc7733a3ea096f4509
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="acb94-102">Lync Server 2013 へのログオンに使用できるクライアントアプリケーションを指定する</span><span class="sxs-lookup"><span data-stu-id="acb94-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acb94-103">_**トピックの最終更新日:** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="acb94-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="acb94-104">Lync Server 2013 では、環境でサポートされているクライアントのバージョンを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="acb94-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="acb94-105">クライアントバージョンポリシーを使用すると、複数のクライアントバージョンをサポートするためのコストを削減できます。</span><span class="sxs-lookup"><span data-stu-id="acb94-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="acb94-106">また、クライアントの以前のバージョンとそれ以降のバージョンでは、使用可能な機能が以前のバージョンのクライアントによって制限される可能性があるため、ユーザーの全体的な操作が向上します。</span><span class="sxs-lookup"><span data-stu-id="acb94-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="acb94-107">クライアントバージョン管理には、次の3つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="acb94-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="acb94-108">クライアントバージョンの構成設定を使用して、クライアントバージョンの制御をグローバルに、または特定のサイトに対して有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="acb94-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="acb94-109">クライアントバージョンポリシーを使用して、ルールのセットをグローバルに、または特定のサイト、プール、またはユーザーのグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="acb94-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="acb94-110">クライアントバージョンポリシールールはクライアントバージョンポリシーを構成し、ユーザーが特定のクライアントおよびクライアントバージョンでログオンしようとしたときに実行するアクションを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="acb94-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="acb94-111">匿名ユーザーをユーザー、サイト、またはサービスに関連付けることはできないため、匿名ユーザーが影響を受けるのはグローバル レベルのポリシーだけです。</span><span class="sxs-lookup"><span data-stu-id="acb94-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="acb94-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="acb94-112">In This Section</span></span>

  - [<span data-ttu-id="acb94-113">Lync Server 2013 のクライアントバージョンの構成設定</span><span class="sxs-lookup"><span data-stu-id="acb94-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="acb94-114">Lync Server 2013 のクライアントバージョンポリシー</span><span class="sxs-lookup"><span data-stu-id="acb94-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="acb94-115">Lync Server 2013 のクライアントバージョンルール</span><span class="sxs-lookup"><span data-stu-id="acb94-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="acb94-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="acb94-116">See Also</span></span>


[<span data-ttu-id="acb94-117">Lync Server 2013 でのデバイス、電話、クライアントアプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="acb94-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

