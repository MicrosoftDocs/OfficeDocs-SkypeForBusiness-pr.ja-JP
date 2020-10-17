---
title: グループ通話ピックアップの構成の前提条件とユーザー権限
description: グループ通話ピックアップの構成の前提条件とユーザー権限。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d2a758b7199634e14ee387d2554b30bf2ae8d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554453"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="03468-103">Lync Server 2013 でのグループ通話ピックアップ構成の前提条件とユーザー権限</span><span class="sxs-lookup"><span data-stu-id="03468-103">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03468-104">_**トピックの最終更新日:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="03468-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="03468-105">グループ通話ピックアップは、エンタープライズ Voip を展開するときに既定でインストールされる通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="03468-105">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="03468-106">このトピックでは、グループ通話ピックアップおよび構成タスクを実行するために必要なユーザー権限を構成する前に行う必要のある事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="03468-106">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="03468-107">このセクションでは、グループ通話ピックアップに関連する計画のドキュメントを読んでいることを前提としています (「 [Lync Server 2013 でグループ通話ピックアップを計画](lync-server-2013-planning-for-group-call-pickup.md)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="03468-107">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="03468-108">グループ通話ピックアップの構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="03468-108">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="03468-109">グループ通話ピックアップでは、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="03468-109">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="03468-110">アプリケーション サービス</span><span class="sxs-lookup"><span data-stu-id="03468-110">Application service</span></span>

  - <span data-ttu-id="03468-111">コール パーク アプリケーション</span><span class="sxs-lookup"><span data-stu-id="03468-111">Call Park application</span></span>

<span data-ttu-id="03468-112">これらのコンポーネントは、エンタープライズ Voip を展開するときに自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="03468-112">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="03468-113">グループ通話ピックアップ構成のユーザー権限</span><span class="sxs-lookup"><span data-stu-id="03468-113">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="03468-114">グループ通話ピックアップを構成するには、次の管理ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="03468-114">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="03468-115">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="03468-115">Lync Server Management Shell</span></span>

  - <span data-ttu-id="03468-116">SEFAUtil リソースキットツール</span><span class="sxs-lookup"><span data-stu-id="03468-116">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="03468-117">Lync Server 管理シェルを使用して、コールパークオービットテーブルで通話ピックアップグループを作成および管理します。</span><span class="sxs-lookup"><span data-stu-id="03468-117">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="03468-118">SEFAUtil リソースキットツールを使用して、通話ピックアップグループを割り当て、ユーザーのグループ通話ピックアップを有効にしたり、ユーザーのグループ通話ピックアップを無効にしたりします。</span><span class="sxs-lookup"><span data-stu-id="03468-118">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="03468-119">グループ通話ピックアップを構成するには、タスクに応じて、次の管理役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="03468-119">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="03468-120">**CsVoiceAdministrator:** この管理者の役割は、音声関連のすべての設定とポリシーを作成、構成、および管理できます。</span><span class="sxs-lookup"><span data-stu-id="03468-120">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="03468-121">**Csuseradministrator:** この管理者の役割は、ユーザーのグループ通話ピックアップを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="03468-121">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="03468-122">また、すべての音声構成に対する読み取り専用の表示アクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="03468-122">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="03468-123">**Csserveradministrator:** この管理者の役割は、サーバーとサービスを管理、監視、およびトラブルシューティングできます。</span><span class="sxs-lookup"><span data-stu-id="03468-123">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="03468-124">**Csadministrator:** この管理者の役割は、CsVoiceAdministrator、CsServerAdministrator、および Csserveradministrator のすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="03468-124">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="03468-125">管理権限の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03468-125">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="03468-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="03468-126">See Also</span></span>


[<span data-ttu-id="03468-127">Lync Server 2013 でのエンタープライズ Voip の展開</span><span class="sxs-lookup"><span data-stu-id="03468-127">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="03468-128">Lync Server 2013 での通話管理機能の計画</span><span class="sxs-lookup"><span data-stu-id="03468-128">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

