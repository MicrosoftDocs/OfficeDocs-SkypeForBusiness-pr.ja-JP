---
title: 'Lync Server 2013: コール パーク構成の前提条件とユーザー権限'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 485c8ee5ba2f7d788ef2917488ebfd86607d48d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="b3cd8-102">Lync Server 2013 のコール パーク構成の前提条件とユーザー権限</span><span class="sxs-lookup"><span data-stu-id="b3cd8-102">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3cd8-103">_**最終更新日:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="b3cd8-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="b3cd8-104">コールパークは、エンタープライズボイスの展開時に既定でインストールされる通話管理機能です。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-104">Call Park is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b3cd8-105">このトピックでは、コールパークと構成タスクを実行するために必要なユーザー権利を設定する前に、準備しておく必要があることについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-105">This topic describes what you need to have in place before you can configure Call Park and the user rights that you need to perform configuration tasks.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3cd8-106">会議のカスタマイズされた保留中のファイルは Lync Server 2013 の障害回復プロセスの一部としてはバックアップされません。プールにアップロードされたファイルが破損、破損、または消去された場合、ファイルは失われます。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-106">Customized music-on-hold files for the Call Park application are not backed up as part of the Lync Server 2013 disaster recovery process, and the files will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="b3cd8-107">コール パーク用にアップロードされているカスタマイズした保留音ファイルについては、常に個別のバックアップ コピーを保持してください。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-107">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="b3cd8-108">このセクションでは、通話パークに関連する計画ドキュメントを読み取っていることを前提としています (「 [Lync Server 2013 での通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-108">This section assumes that you have read the planning documentation related to Call Park (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="call-park-configuration-prerequisites"></a><span data-ttu-id="b3cd8-109">コールパーク構成の前提条件</span><span class="sxs-lookup"><span data-stu-id="b3cd8-109">Call Park Configuration Prerequisites</span></span>

<span data-ttu-id="b3cd8-110">コールパークには、次のコンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-110">Call Park requires the following components:</span></span>

  - <span data-ttu-id="b3cd8-111">アプリケーション サービス</span><span class="sxs-lookup"><span data-stu-id="b3cd8-111">Application service</span></span>

  - <span data-ttu-id="b3cd8-112">コール パーク アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b3cd8-112">Call Park application</span></span>

<span data-ttu-id="b3cd8-113">これらのコンポーネントは、エンタープライズボイスの展開時に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-113">These components are installed automatically when you deploy Enterprise Voice.</span></span>

<span data-ttu-id="b3cd8-114">通話の保留中に発信者に音楽が聞こえるようにする場合は、音楽の保留ファイルも必要です。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-114">If you want callers to hear music while the call is parked, a music-on-hold file is also required.</span></span> <span data-ttu-id="b3cd8-115">既定の音楽の保留ファイルは、エンタープライズボイスの展開時に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-115">A default music-on-hold file is installed automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b3cd8-116">既定のファイルは、独自の音楽の保留ファイルに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-116">You can substitute the default file with your own music-on-hold file.</span></span> <span data-ttu-id="b3cd8-117">[コールパークファイルストアでは、オーディオファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-117">Call Park uses File Store to hold the audio file.</span></span>

</div>

<div>

## <a name="call-park-configuration-user-rights"></a><span data-ttu-id="b3cd8-118">コールパーク構成のユーザー権利</span><span class="sxs-lookup"><span data-stu-id="b3cd8-118">Call Park Configuration User Rights</span></span>

<span data-ttu-id="b3cd8-119">以下の管理ツールを使って、コールパークを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-119">You can use the following administrative tools to configure Call Park:</span></span>

  - <span data-ttu-id="b3cd8-120">Lync Server コントロール パネル</span><span class="sxs-lookup"><span data-stu-id="b3cd8-120">Lync Server Control Panel</span></span>

  - <span data-ttu-id="b3cd8-121">Lync Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="b3cd8-121">Lync Server Management Shell</span></span>

<span data-ttu-id="b3cd8-122">これらのツールを使って、コールパークの軌道を設定したり、コールパークで使用される他の設定を構成したりします。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-122">You use these tools to set up the Call Park orbit table and to configure other settings used by Call Park.</span></span>

<span data-ttu-id="b3cd8-123">コールパークを構成するには、タスクに応じて次の管理者ロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-123">Configuring Call Park requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="b3cd8-124">**CsVoiceAdministrator:** この管理者ロールは、音声関連のすべての設定とポリシーを作成、構成、管理できます。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-124">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="b3cd8-125">**Csuseradministrator:** この管理者の役割は、音声ポリシーでのコールパークを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-125">**CsUserAdministrator:** This administrator role can enable Call Park in voice policy.</span></span> <span data-ttu-id="b3cd8-126">この管理者ロールは、すべての音声構成に対して読み取り専用ビューでアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-126">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="b3cd8-127">**Csserveradministrator:** この管理者の役割は、サーバーとサービスの管理、監視、トラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-127">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="b3cd8-128">**Csadministrator:** この管理者ロールは、CsVoiceAdministrator、CsServerAdministrator、Csserveradministrator のすべてのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-128">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3cd8-129">管理権限の詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3cd8-129">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3cd8-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3cd8-130">See Also</span></span>


[<span data-ttu-id="b3cd8-131">Lync Server 2013 でのエンタープライズボイスの展開</span><span class="sxs-lookup"><span data-stu-id="b3cd8-131">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="b3cd8-132">Lync Server 2013 の通話管理機能の計画</span><span class="sxs-lookup"><span data-stu-id="b3cd8-132">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

