---
title: サービスのセッションの禁止
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf8fb96fef5a01f9b25ca954dd27d1bdfd1f7055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727327"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a><span data-ttu-id="18c60-102">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="18c60-102">Prevent sessions for services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18c60-103">_**最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="18c60-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="18c60-104">Microsoft Lync Server 2010 コントロールパネルを使用すると、特定のコンピューターで実行されているすべての Lync Server 2010 サービスの新しいセッションを禁止したり、特定の Lync Server 2010 サービスの新しいセッションを禁止したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="18c60-104">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="18c60-105">コンピューター上のすべての Lync Server サービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="18c60-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="18c60-106">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="18c60-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="18c60-107">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="18c60-107">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="18c60-108">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c60-108">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="18c60-109">[**状態**] ページで、必要に応じて一覧を並べ替えます。または、新しいセッションを禁止するサービスを実行しているコンピューターを検索して、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c60-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="18c60-110">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c60-110">Click **Action**.</span></span>

6.  <span data-ttu-id="18c60-111">[**すべてのサービスに対して新規セッションを**許可しない] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c60-111">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="18c60-112">特定のサービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="18c60-112">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="18c60-113">RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="18c60-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="18c60-114">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="18c60-114">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="18c60-115">左側のナビゲーションバーで、[**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c60-115">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="18c60-116">[**状態**] ページで、必要に応じて一覧を並べ替えます。または、開始または停止するサービスを実行しているコンピューターを検索して、それをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c60-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="18c60-117">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c60-117">Click **Properties**.</span></span>

6.  <span data-ttu-id="18c60-118">必要に応じてサービスの一覧を並べ替えて、新しいセッションを禁止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c60-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="18c60-119">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c60-119">Click **Action**.</span></span>

8.  <span data-ttu-id="18c60-120">[**サービスの新規セッションを**許可しない] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c60-120">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="18c60-121">[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c60-121">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

