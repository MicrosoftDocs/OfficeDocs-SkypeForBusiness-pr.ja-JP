---
title: 'Lync Server 2013: アナウンスの構成の前提条件と役割'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb5f909170e1de2566e21e9305175211c306fee6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="e0663-102">Lync Server 2013 のアナウンスの構成の前提条件と役割</span><span class="sxs-lookup"><span data-stu-id="e0663-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0663-103">_**最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="e0663-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="e0663-104">"お知らせ" は、エンタープライズの音声通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="e0663-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="e0663-105">このトピックでは、アナウンスメントを構成するために必要な準備と、構成タスクを実行するために必要な役割の割り当てについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e0663-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="e0663-106">このセクションでは、お知らせに関連する計画ドキュメントを読み取っていることを前提としています (「 [Lync Server 2013 の通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e0663-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="e0663-107">アナウンスメント構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="e0663-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="e0663-108">アナウンスメントアプリケーションには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e0663-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="e0663-109">アプリケーション サービス</span><span class="sxs-lookup"><span data-stu-id="e0663-109">Application service</span></span>

  - <span data-ttu-id="e0663-110">応答グループ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="e0663-110">Response Group application</span></span>

  - <span data-ttu-id="e0663-111">ファイルストア、オーディオファイルを保持する場合</span><span class="sxs-lookup"><span data-stu-id="e0663-111">File Store, to hold audio files</span></span>

<span data-ttu-id="e0663-112">エンタープライズボイスを展開すると、これらのすべてのコンポーネントが既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e0663-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="e0663-113">アナウンスメント構成ロール</span><span class="sxs-lookup"><span data-stu-id="e0663-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="e0663-114">以下の管理ツールを使用して、お知らせを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="e0663-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="e0663-115">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="e0663-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="e0663-116">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="e0663-116">Lync Server Management Shell</span></span>

<span data-ttu-id="e0663-117">アナウンスメントアプリケーションを構成するには、次の管理者ロールのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="e0663-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="e0663-118">\*\*\*\*   この管理者の役割を CsVoiceAdministrator すると、お知らせの設定など、音声に関連するすべての設定とポリシーを作成、構成、管理できます。</span><span class="sxs-lookup"><span data-stu-id="e0663-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="e0663-119">**Csserveradministrator**   この管理者ロールは、サーバーとサービスの管理、監視、トラブルシューティング、すべてのアナウンスメント設定の構成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e0663-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="e0663-120">**Csadministrator**   この管理者ロールは、すべての管理タスクを実行し、すべての設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e0663-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="e0663-121">**Csviewonlyadministrator**   この管理者ロールは展開の正常性を監視するために展開を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e0663-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0663-122">管理ユーザー権限の詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0663-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0663-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0663-123">See Also</span></span>


[<span data-ttu-id="e0663-124">Lync Server 2013 でのエンタープライズボイスの展開</span><span class="sxs-lookup"><span data-stu-id="e0663-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="e0663-125">Lync Server 2013 の通話管理機能の計画</span><span class="sxs-lookup"><span data-stu-id="e0663-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

