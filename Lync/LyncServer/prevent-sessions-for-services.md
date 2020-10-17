---
title: サービスのセッションの禁止
description: サービスのセッションを禁止します。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a452f8091716daa0a15967e2a278e82c5bc8c4f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563693"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="3d188-103">サービスのセッションの禁止</span><span class="sxs-lookup"><span data-stu-id="3d188-103">Prevent sessions for services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d188-104">_**トピックの最終更新日:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="3d188-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="3d188-105">Microsoft Lync Server 2010 コントロールパネルを使用して、特定のコンピューターで実行されているすべての Lync Server 2010 サービスの新しいセッションを禁止したり、特定の Lync Server 2010 サービスの新しいセッションを禁止したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3d188-105">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="3d188-106">コンピューター上のすべての Lync Server サービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="3d188-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="3d188-107">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3d188-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="3d188-108">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="3d188-108">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="3d188-109">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d188-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="3d188-110">[ **状態** ] ページで、必要に応じてリストを並べ替えまたは検索し、新しいセッションを禁止するサービスを実行しているコンピューターを見つけてクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d188-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="3d188-111">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d188-111">Click **Action**.</span></span>

6.  <span data-ttu-id="3d188-112">[ **すべてのサービスの新しいセッションを禁止する] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="3d188-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="3d188-113">特定のサービスの新しいセッションを禁止するには</span><span class="sxs-lookup"><span data-stu-id="3d188-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="3d188-114">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3d188-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="3d188-115">[Lync Server コントロール パネル] を開きます。</span><span class="sxs-lookup"><span data-stu-id="3d188-115">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="3d188-116">左側のナビゲーション バーで [**トポロジ**] をクリックし、[**状態**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d188-116">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="3d188-117">[**状態**] ページで、必要に応じて一覧を並べ替えるかまたは検索して、開始または停止するサービスを実行しているコンピューターを確認してクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d188-117">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="3d188-118">[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d188-118">Click **Properties**.</span></span>

6.  <span data-ttu-id="3d188-119">必要に応じてサービスの一覧を並べ替え、新しいセッションを禁止するサービスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d188-119">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="3d188-120">[**アクション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d188-120">Click **Action**.</span></span>

8.  <span data-ttu-id="3d188-121">[ **サービスの新しいセッションを禁止する] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="3d188-121">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="3d188-122">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d188-122">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

