---
title: 'Lync Server 2013: Hosted Exchange UM の統合のための展開プロセス'
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
ms.openlocfilehash: b314ea3bd7a88264a72c804c7c67ed3baa819972
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="2056f-102">Hosted Exchange UM と Lync Server 2013 の統合のための展開プロセス</span><span class="sxs-lookup"><span data-stu-id="2056f-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2056f-103">_**最終更新日:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="2056f-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="2056f-104">Lync Server 2013 とホストされた Exchange ユニファイドメッセージング (UM) との統合について効果的な計画を立てるには、次のことを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2056f-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="2056f-105">Lync Server 2013 とホストされている Exchange UM とを統合するための前提条件</span><span class="sxs-lookup"><span data-stu-id="2056f-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="2056f-106">統合プロセス中に必要な手順</span><span class="sxs-lookup"><span data-stu-id="2056f-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="2056f-107">ホストされた Exchange UM と統合するための展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="2056f-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="2056f-108">統合プロセスを始める前に、Lync Server 2013 (少なくとも、フロントエンドプールまたは Standard Edition サーバー)、エッジサーバー、2013 Lync 2010 クライアントを既に展開しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="2056f-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="2056f-109">統合プロセス</span><span class="sxs-lookup"><span data-stu-id="2056f-109">Integration Process</span></span>

<span data-ttu-id="2056f-110">次の表では、ホストされた Exchange UM の統合プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="2056f-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="2056f-111">展開手順の詳細については、展開ドキュメントの「 [Lync Server 2013 ユーザーのボイスメールをホストされた EXCHANGE UM に提供](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2056f-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2056f-112">段階</span><span class="sxs-lookup"><span data-stu-id="2056f-112">Phase</span></span></th>
<th><span data-ttu-id="2056f-113">手順</span><span class="sxs-lookup"><span data-stu-id="2056f-113">Steps</span></span></th>
<th><span data-ttu-id="2056f-114">権利と権限</span><span class="sxs-lookup"><span data-stu-id="2056f-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="2056f-115">「展開」のドキュメント</span><span class="sxs-lookup"><span data-stu-id="2056f-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2056f-116">エッジサーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2056f-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2056f-117">フェデレーションのためにエッジ サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2056f-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="2056f-118">エッジサーバーにデータを手動で複製します。</span><span class="sxs-lookup"><span data-stu-id="2056f-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="2056f-119">エッジサーバーでホスティングプロバイダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2056f-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2056f-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2056f-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="2056f-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Hosted Exchange UM との統合のためのエッジ サーバーの構成</a></span><span class="sxs-lookup"><span data-stu-id="2056f-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2056f-122">ホストされたボイスメールのポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="2056f-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2056f-123">グローバルでホストされているボイスメールポリシーを変更するか、サイトまたはユーザーごとのスコープを持つ新しいホストされたボイスメールポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2056f-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="2056f-124">ユーザーごとのスコープを持つポリシーの場合は、ユーザーまたはグループにポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2056f-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2056f-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2056f-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="2056f-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Lync Server 2013 でのホスト ボイス メール ポリシーの管理</a></span><span class="sxs-lookup"><span data-stu-id="2056f-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2056f-127">ユーザーがホストされたボイスメールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2056f-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2056f-128">メールボックスがホストされている Exchange サービス上にあるユーザーのユーザーアカウントを構成します。</span><span class="sxs-lookup"><span data-stu-id="2056f-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2056f-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2056f-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="2056f-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Lync Server 2013 でのホスト型ボイス メールに対するユーザーの有効化</a></span><span class="sxs-lookup"><span data-stu-id="2056f-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2056f-131">ホスト型連絡先オブジェクトを構成します。</span><span class="sxs-lookup"><span data-stu-id="2056f-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2056f-132">ホストされた Exchange UM 用の自動応答の連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2056f-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="2056f-133">Hosted Exchange UM 用のサブスクライバーアクセスの連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2056f-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2056f-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="2056f-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="2056f-135">連絡先オブジェクトを作成、変更、または削除するには、新しい-CsExUmContact を実行しているユーザー、Set-CsExUmContact コマンドレットを実行しているユーザー、または、新しい連絡先オブジェクトが保存されている Active Directory 組織単位への適切なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2056f-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="2056f-136">このアクセス許可は、Grant-CsOUPermission コマンドレットを実行することで付与されます。</span><span class="sxs-lookup"><span data-stu-id="2056f-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="2056f-137">詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2056f-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="2056f-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Lync Server 2013 での Hosted Exchange UM の連絡先オブジェクトの作成</a></span><span class="sxs-lookup"><span data-stu-id="2056f-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

