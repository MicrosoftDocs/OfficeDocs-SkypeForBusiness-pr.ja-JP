---
title: 'Lync Server 2013: ユーザーごとのポリシーの割り当て'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acee046ebe05d87e17cd72ef1c5d8d19830d4ee8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="4937d-102">Lync Server 2013 でのユーザー単位のポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="4937d-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4937d-103">_**トピックの最終更新日:** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="4937d-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="4937d-p101">他のユーザーに割り当てる、グローバル ポリシーなどのポリシーに定義されている設定と異なる特別な設定を指定するため、ユーザーまたはユーザー グループに特定のポリシーを割り当てることができます。 これらのポリシーは、ユーザー単位のポリシーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4937d-p101">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies. These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4937d-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4937d-106">In This Section</span></span>

  - [<span data-ttu-id="4937d-107">Lync Server 2013 でユーザー単位の会議ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4937d-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="4937d-108">Lync Server 2013 でユーザーごとのクライアントバージョンポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4937d-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="4937d-109">Lync Server 2013 でユーザー単位の PIN ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4937d-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="4937d-110">Lync Server 2013 での Lync が有効なユーザーへの外部ユーザーアクセスポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="4937d-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="4937d-111">Lync Server 2013 でユーザー単位のアーカイブポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4937d-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="4937d-112">Lync Server 2013 でユーザー単位の場所のポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4937d-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="4937d-113">Lync Server 2013 でユーザー単位のモビリティポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4937d-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="4937d-114">Lync Server 2013 でユーザー単位の常設チャットポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4937d-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="4937d-115">Lync Server 2013 でのユーザー単位のダイヤルプランポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="4937d-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="4937d-116">Lync Server 2013 でユーザーごとの音声ポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4937d-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4937d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="4937d-117">See Also</span></span>


[<span data-ttu-id="4937d-118">Lync Server 2013 でのユーザーの管理</span><span class="sxs-lookup"><span data-stu-id="4937d-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

