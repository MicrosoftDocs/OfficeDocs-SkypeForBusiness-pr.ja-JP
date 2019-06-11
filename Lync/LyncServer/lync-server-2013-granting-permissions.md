---
title: 'Lync Server 2013: アクセス許可の付与'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c8afde42a231124648824fbf8fbae07b0beedc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a><span data-ttu-id="f5e80-102">Lync Server 2013 でのアクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="f5e80-102">Granting permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5e80-103">_**最終更新日:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="f5e80-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="f5e80-104">セットアップの場合、特定の Active Directory 組織単位 (OU) の RTCUniversalServerAdmins ユニバーサルグループにアクセス許可を付与し、その OU の RTCUniversalServerAdmins グループのメンバーが、指定したドメインに Lync Server 2013 をインストールできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f5e80-104">For setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain.</span></span> <span data-ttu-id="f5e80-105">OU にアクセス許可を付与すると、次のアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="f5e80-105">When you grant permissions for an OU, the following permissions are granted:</span></span>

  - <span data-ttu-id="f5e80-106">モード</span><span class="sxs-lookup"><span data-stu-id="f5e80-106">Read</span></span>

  - <span data-ttu-id="f5e80-107">書き込み</span><span class="sxs-lookup"><span data-stu-id="f5e80-107">Write</span></span>

  - <span data-ttu-id="f5e80-108">ReadSPN</span><span class="sxs-lookup"><span data-stu-id="f5e80-108">ReadSPN</span></span>

  - <span data-ttu-id="f5e80-109">WriteSPN</span><span class="sxs-lookup"><span data-stu-id="f5e80-109">WriteSPN</span></span>

<span data-ttu-id="f5e80-110">管理者は、特定の Ou にアクセス許可を追加して、フォレストの準備によって作成された RTC ユニバーサルグループのメンバーが、Domain Admins グループのメンバーではなくても Ou にアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f5e80-110">For administration, you can add permissions to specified OUs so that members of the RTC universal groups created by forest preparation can access the OUs without needing to be members of the Domain Admins group.</span></span> <span data-ttu-id="f5e80-111">指定した OU に追加されたアクセス許可は、[ユーザーの**有効化**] と同じアクセス許可であり、[コンピューター] と [ユーザー] のコンテナーに追加します。</span><span class="sxs-lookup"><span data-stu-id="f5e80-111">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users OU containers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f5e80-112">このセクション中</span><span class="sxs-lookup"><span data-stu-id="f5e80-112">In This Section</span></span>

  - [<span data-ttu-id="f5e80-113">Lync Server 2013 でのセットアップ アクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="f5e80-113">Granting setup permissions in Lync Server 2013</span></span>](lync-server-2013-granting-setup-permissions.md)

  - [<span data-ttu-id="f5e80-114">Lync Server 2013 での組織単位アクセス許可の付与</span><span class="sxs-lookup"><span data-stu-id="f5e80-114">Granting organizational unit permissions in Lync Server 2013</span></span>](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

