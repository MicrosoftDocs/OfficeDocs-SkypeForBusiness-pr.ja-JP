---
title: 'Lync Server 2013: ホストされた Exchange UM を統合するための展開プロセス'
description: 'Lync Server 2013: ホストされた Exchange UM を統合するための展開プロセス。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83239c6534dfdaa65109c8880cc4cb4946bffab6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542613"
---
# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="d2823-103">ホストされた Exchange UM と Lync Server 2013 を統合するための展開プロセス</span><span class="sxs-lookup"><span data-stu-id="d2823-103">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2823-104">_**トピックの最終更新日:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="d2823-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="d2823-105">ホスティングされた Exchange ユニファイドメッセージング (UM) と Lync Server 2013 の統合を効果的に計画するには、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2823-105">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="d2823-106">Lync Server 2013 を hosted Exchange UM と統合するための前提条件</span><span class="sxs-lookup"><span data-stu-id="d2823-106">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="d2823-107">統合プロセス中に必要な手順</span><span class="sxs-lookup"><span data-stu-id="d2823-107">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="d2823-108">Hosted Exchange UM との統合のための展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="d2823-108">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="d2823-109">統合プロセスを開始する前に、Lync Server 2013 (少なくとも、フロントエンドプールまたは Standard Edition サーバー)、エッジサーバー、Lync 2013、Lync 2010 クライアントを展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2823-109">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="d2823-110">統合プロセス</span><span class="sxs-lookup"><span data-stu-id="d2823-110">Integration Process</span></span>

<span data-ttu-id="d2823-111">次の表は、ホストされた Exchange UM 統合プロセスの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="d2823-111">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="d2823-112">展開手順の詳細については、「展開」のドキュメントの「 [Lync Server 2013 ユーザーのボイスメールをホストされた EXCHANGE UM に提供](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2823-112">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2823-113">フェーズ</span><span class="sxs-lookup"><span data-stu-id="d2823-113">Phase</span></span></th>
<th><span data-ttu-id="d2823-114">手順</span><span class="sxs-lookup"><span data-stu-id="d2823-114">Steps</span></span></th>
<th><span data-ttu-id="d2823-115">権限とアクセス許可</span><span class="sxs-lookup"><span data-stu-id="d2823-115">Rights and permissions</span></span></th>
<th><span data-ttu-id="d2823-116">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="d2823-116">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2823-117">エッジサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d2823-117">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d2823-118">フェデレーションのためにエッジ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d2823-118">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="d2823-119">エッジサーバーにデータを手動でレプリケートします。</span><span class="sxs-lookup"><span data-stu-id="d2823-119">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="d2823-120">エッジサーバーのホスティングプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d2823-120">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d2823-121">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d2823-121">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="d2823-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">ホストされた Exchange UM との統合のためにエッジサーバーを構成する</a></span><span class="sxs-lookup"><span data-stu-id="d2823-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2823-123">ホストボイスメールポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="d2823-123">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d2823-124">グローバルホストボイスメールポリシーを変更するか、サイトまたは Per-User のスコープを使用して新しいホストボイスメールポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2823-124">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="d2823-125">Per-User スコープを持つポリシーでは、ポリシーをユーザーまたはグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d2823-125">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d2823-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d2823-126">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="d2823-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013 でホストボイスメールポリシーを管理する</a></span><span class="sxs-lookup"><span data-stu-id="d2823-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d2823-128">ホストボイスメールに対してユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d2823-128">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d2823-129">ホストされた Exchange サービス上にメールボックスがあるユーザーのユーザーアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="d2823-129">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="d2823-130">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d2823-130">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="d2823-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Lync Server 2013 でホストボイスメールに対してユーザーを有効にする</a></span><span class="sxs-lookup"><span data-stu-id="d2823-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2823-132">ホストされた連絡先オブジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="d2823-132">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d2823-133">Hosted Exchange UM の自動応答連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2823-133">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="d2823-134">Hosted Exchange UM のサブスクライバーアクセス連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d2823-134">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d2823-135">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="d2823-135">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d2823-136">連絡先オブジェクトを作成、変更、または削除するには、Set-CsExUmContact または Remove-CsExUmContact コマンドレットを実行するユーザーが、新しい連絡先オブジェクトが格納されている Active Directory 組織単位に対して適切なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2823-136">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="d2823-137">このアクセス許可は、Grant-CsOUPermission コマンドレットを実行することで付与されます。</span><span class="sxs-lookup"><span data-stu-id="d2823-137">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="d2823-138">詳細については、Lync Server 管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2823-138">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="d2823-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Lync Server 2013 で hosted Exchange UM の連絡先オブジェクトを作成する</a></span><span class="sxs-lookup"><span data-stu-id="d2823-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

