---
title: 'Lync Server 2013: アナウンスの構成の前提条件と役割'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dde28cac806b517a410f5edfa7ecbcf19176ed4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="e897d-102">Lync Server 2013 でのアナウンスの構成の前提条件と役割</span><span class="sxs-lookup"><span data-stu-id="e897d-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e897d-103">_**トピックの最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="e897d-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="e897d-104">アナウンスメントは、エンタープライズ Voip の通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="e897d-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="e897d-105">このトピックでは、アナウンスを構成する前に行う必要のある内容と、構成タスクを実行するために必要な役割の割り当てについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e897d-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="e897d-106">このセクションでは、「アナウンスに関連する計画」のドキュメントを読んでいることを前提としています (「 [Lync Server 2013 の通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e897d-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="e897d-107">アナウンスの構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="e897d-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="e897d-108">アナウンスメントアプリケーションには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e897d-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="e897d-109">アプリケーション サービス</span><span class="sxs-lookup"><span data-stu-id="e897d-109">Application service</span></span>

  - <span data-ttu-id="e897d-110">応答グループ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="e897d-110">Response Group application</span></span>

  - <span data-ttu-id="e897d-111">ファイル ストア (オーディオ ファイルを格納)</span><span class="sxs-lookup"><span data-stu-id="e897d-111">File Store, to hold audio files</span></span>

<span data-ttu-id="e897d-112">これらのコンポーネントはすべて、エンタープライズ VoIP を展開するときに既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e897d-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="e897d-113">アナウンスの構成の役割</span><span class="sxs-lookup"><span data-stu-id="e897d-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="e897d-114">以下の管理ツールを使用してアナウンスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e897d-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="e897d-115">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="e897d-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="e897d-116">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="e897d-116">Lync Server Management Shell</span></span>

<span data-ttu-id="e897d-117">アナウンスアプリケーションを構成するには、次の管理役割のいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="e897d-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="e897d-118">**CsVoiceAdministrator**   この管理者の役割は、アナウンス設定を含むすべての音声関連の設定とポリシーを作成、構成、および管理できます。</span><span class="sxs-lookup"><span data-stu-id="e897d-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="e897d-119">**Csserveradministrator**   この管理役割は、サーバーとサービスを管理、監視、およびトラブルシューティングし、すべてのアナウンス設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e897d-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="e897d-120">**Csadministrator**   この管理者の役割は、すべての管理タスクを実行し、すべての設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e897d-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="e897d-121">**Csviewonlyadministrator**   この管理役割は展開を表示して、展開の状態を監視できます。</span><span class="sxs-lookup"><span data-stu-id="e897d-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e897d-122">管理ユーザー権限の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 でのロールベースのアクセス制御の計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e897d-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e897d-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e897d-123">See Also</span></span>


[<span data-ttu-id="e897d-124">Lync Server 2013 でのエンタープライズ Voip の展開</span><span class="sxs-lookup"><span data-stu-id="e897d-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="e897d-125">Lync Server 2013 での通話管理機能の計画</span><span class="sxs-lookup"><span data-stu-id="e897d-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

