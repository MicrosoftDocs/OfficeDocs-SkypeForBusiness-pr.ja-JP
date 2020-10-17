---
title: 'Lync Server 2013: アナウンスの構成の前提条件と役割'
description: 'Lync Server 2013: アナウンスの構成の前提条件と役割。'
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
ms.openlocfilehash: a8e6e7009adc6826c255e28ddda925b0e9be5fd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561893"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="bdfc7-103">Lync Server 2013 でのアナウンスの構成の前提条件と役割</span><span class="sxs-lookup"><span data-stu-id="bdfc7-103">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdfc7-104">_**トピックの最終更新日:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="bdfc7-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="bdfc7-105">アナウンスメントは、エンタープライズ Voip の通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-105">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="bdfc7-106">このトピックでは、アナウンスを構成する前に行う必要のある内容と、構成タスクを実行するために必要な役割の割り当てについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-106">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="bdfc7-107">このセクションでは、「アナウンスに関連する計画」のドキュメントを読んでいることを前提としています (「 [Lync Server 2013 の通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-107">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="bdfc7-108">アナウンスの構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="bdfc7-108">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="bdfc7-109">アナウンスメントアプリケーションには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-109">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="bdfc7-110">アプリケーション サービス</span><span class="sxs-lookup"><span data-stu-id="bdfc7-110">Application service</span></span>

  - <span data-ttu-id="bdfc7-111">応答グループ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="bdfc7-111">Response Group application</span></span>

  - <span data-ttu-id="bdfc7-112">ファイル ストア (オーディオ ファイルを格納)</span><span class="sxs-lookup"><span data-stu-id="bdfc7-112">File Store, to hold audio files</span></span>

<span data-ttu-id="bdfc7-113">これらのコンポーネントはすべて、エンタープライズ VoIP を展開するときに既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-113">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="bdfc7-114">アナウンスの構成の役割</span><span class="sxs-lookup"><span data-stu-id="bdfc7-114">Announcement Configuration Roles</span></span>

<span data-ttu-id="bdfc7-115">以下の管理ツールを使用してアナウンスを構成できます。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-115">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="bdfc7-116">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="bdfc7-116">Lync Server Control Panel</span></span>

  - <span data-ttu-id="bdfc7-117">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="bdfc7-117">Lync Server Management Shell</span></span>

<span data-ttu-id="bdfc7-118">アナウンスアプリケーションを構成するには、次の管理役割のいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-118">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="bdfc7-119">**CsVoiceAdministrator**    この管理者の役割は、アナウンス設定を含むすべての音声関連の設定とポリシーを作成、構成、および管理できます。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-119">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="bdfc7-120">**Csserveradministrator**    この管理者の役割は、サーバーとサービスを管理、監視、およびトラブルシューティングし、すべてのアナウンス設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-120">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="bdfc7-121">**Csadministrator**    この管理者の役割は、すべての管理タスクを実行し、すべての設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-121">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="bdfc7-122">**Csviewonlyadministrator**    この管理者の役割は展開を表示して、展開の状態を監視できます。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-122">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bdfc7-123">管理ユーザー権限の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 でのロールベースのアクセス制御の計画</A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bdfc7-123">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bdfc7-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdfc7-124">See Also</span></span>


[<span data-ttu-id="bdfc7-125">Lync Server 2013 でのエンタープライズ Voip の展開</span><span class="sxs-lookup"><span data-stu-id="bdfc7-125">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="bdfc7-126">Lync Server 2013 での通話管理機能の計画</span><span class="sxs-lookup"><span data-stu-id="bdfc7-126">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

