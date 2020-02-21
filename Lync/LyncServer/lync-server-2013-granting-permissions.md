---
title: 'Lync Server 2013: アクセス許可の付与'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20679f910ead1f1b7cab45fde658b38233c644f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="30461-102">Lync Server 2013 でのアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="30461-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30461-103">_**トピックの最終更新日:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="30461-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="30461-104">セットアップの場合は、特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins ユニバーサルグループに対するアクセス許可を付与して、その OU の RTCUniversalServerAdmins グループのメンバーが、指定したドメインに Lync Server 2013 をインストールできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="30461-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="30461-105">OU に対するアクセス許可を付与する場合は、次のアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="30461-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="30461-106">読み取り</span><span class="sxs-lookup"><span data-stu-id="30461-106">Read</span></span>

  - <span data-ttu-id="30461-107">書き込み</span><span class="sxs-lookup"><span data-stu-id="30461-107">Write</span></span>

  - <span data-ttu-id="30461-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="30461-108">ReadSPN</span></span>

  - <span data-ttu-id="30461-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="30461-109">WriteSPN</span></span>

<span data-ttu-id="30461-110">管理のために、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが Domain Admins グループのメンバーでなくても Ou にアクセスできるように、指定された Ou にアクセス許可を追加できます。</span><span class="sxs-lookup"><span data-stu-id="30461-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="30461-111">指定した OU に追加されるアクセス許可は、[有効にする] **-CsAdDomain**コマンドレットがコンピューターとユーザーの ou コンテナーに追加するアクセス許可と同じです。</span><span class="sxs-lookup"><span data-stu-id="30461-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="30461-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="30461-112">In This Section</span></span>

  - [<span data-ttu-id="30461-113">Lync Server 2013 でのセットアップのアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="30461-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="30461-114">Lync Server 2013 での組織単位アクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="30461-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

