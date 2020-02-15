---
title: 'Lync Server 2013: 応答グループの展開プロセス'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Response Group
ms:assetid: d390c8a1-dc6e-44d8-b386-2be1fca9877c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205270(v=OCS.15)
ms:contentKeyID: 48185437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc249ec8df233e6c22c9d5c1b54b81e23c5a173
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="83d47-102">Lync Server 2013 の応答グループの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="83d47-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83d47-103">_**トピックの最終更新日:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="83d47-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="83d47-104">このセクションでは、応答グループアプリケーションの展開に必要なフェーズと手順の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="83d47-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="83d47-105">応答グループの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="83d47-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="83d47-106">フェーズ</span><span class="sxs-lookup"><span data-stu-id="83d47-106">Phase</span></span></th>
<th><span data-ttu-id="83d47-107">手順</span><span class="sxs-lookup"><span data-stu-id="83d47-107">Steps</span></span></th>
<th><span data-ttu-id="83d47-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="83d47-108">Permissions</span></span></th>
<th><span data-ttu-id="83d47-109">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="83d47-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="83d47-110">応答グループアプリケーションをインストールする</span><span class="sxs-lookup"><span data-stu-id="83d47-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="83d47-111">応答グループアプリケーションは、エンタープライズ Voip を展開するときに既定でインストールされ、アクティブ化されます。</span><span class="sxs-lookup"><span data-stu-id="83d47-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="83d47-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="83d47-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="83d47-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013 でのエンタープライズ Voip の展開</a></span><span class="sxs-lookup"><span data-stu-id="83d47-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83d47-114">応答グループ用のコンポーネントのインストール</span><span class="sxs-lookup"><span data-stu-id="83d47-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="83d47-115">Lync Server コマンドレット、Lync Server コントロールパネル、応答グループ構成ツール、エージェントのサインインとサインアウトコンソール、および応答グループクライアント Web サービスは、Web サービスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="83d47-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="83d47-116">Web サービスは、Enterprise Edition プールまたは Standard Edition サーバーの展開時にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="83d47-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="83d47-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="83d47-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="83d47-118"><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 の展開 </a></span><span class="sxs-lookup"><span data-stu-id="83d47-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83d47-119">Lync 2013 およびエンタープライズ Voip に対してユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="83d47-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="83d47-120">Lync Server およびエンタープライズ Voip のエージェントとなるユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="83d47-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="83d47-121">ユーザーをエージェント グループに追加する前に、ユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="83d47-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="83d47-122">通常、ユーザーは Enterprise Edition または Standard Edition サーバーの展開時に Lync Server に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="83d47-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="83d47-123">エンタープライズ Voip の展開時に、ユーザーがエンタープライズ Voip に対して有効になります。</span><span class="sxs-lookup"><span data-stu-id="83d47-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="83d47-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="83d47-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="83d47-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="83d47-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="83d47-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013 のユーザーアカウントを無効または再度有効にする</a></span><span class="sxs-lookup"><span data-stu-id="83d47-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="83d47-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013 のエンタープライズ Voip でユーザーを有効にする</a></span><span class="sxs-lookup"><span data-stu-id="83d47-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83d47-129">エージェント グループ、キュー、ワークフローから成る応答グループを作成および構成する</span><span class="sxs-lookup"><span data-stu-id="83d47-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="83d47-130">Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="83d47-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="83d47-131">エージェント グループを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="83d47-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="83d47-132">キューを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="83d47-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="83d47-133">必要に応じて、Lync Server 管理シェルを使用して、定義済みの応答グループの営業時間と休日を作成します。</span><span class="sxs-lookup"><span data-stu-id="83d47-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="83d47-134">応答グループ構成ツールまたは Lync Server 管理シェルを使用して、カスタムの応答グループの営業時間と休日を含むワークフロー (ハントグループまたは対話型音声応答 (IVR) 通話フロー) を作成します。</span><span class="sxs-lookup"><span data-stu-id="83d47-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="83d47-135">応答グループ構成ツールには、Lync Server コントロールパネルからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="83d47-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="83d47-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="83d47-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="83d47-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="83d47-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="83d47-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="83d47-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="83d47-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="83d47-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="83d47-142"><a href="lync-server-2013-create-response-group-agent-groups.md">応答グループエージェントグループの作成 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="83d47-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="83d47-143"><a href="lync-server-2013-create-response-group-queues.md">Lync Server 2013 で応答グループキューを作成する</a></span><span class="sxs-lookup"><span data-stu-id="83d47-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="83d47-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">オプションLync Server 2013 で応答グループの営業時間を定義する</a></span><span class="sxs-lookup"><span data-stu-id="83d47-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="83d47-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">オプションLync Server 2013 で応答グループの休日セットを定義する</a></span><span class="sxs-lookup"><span data-stu-id="83d47-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="83d47-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Lync Server 2013 でのワークフローの作成または変更</a></span><span class="sxs-lookup"><span data-stu-id="83d47-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83d47-147">(オプション) アプリケーションレベルの設定をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="83d47-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="83d47-148">Lync Server 管理シェルを使用して、既定の保留音の構成、既定の保留音のオーディオファイル、エージェントリングバックの猶予期間、呼び出しコンテキストの構成をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="83d47-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="83d47-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="83d47-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="83d47-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="83d47-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="83d47-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="83d47-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="83d47-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Lync Server 2013 でのアプリケーションレベルの応答グループ設定の管理</a></span><span class="sxs-lookup"><span data-stu-id="83d47-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="83d47-155">(オプション) 応答グループの管理を委任する</span><span class="sxs-lookup"><span data-stu-id="83d47-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="83d47-156">ユーザーに CsResponseGroupManager ロールを割り当て、応答グループの構成を委任します。</span><span class="sxs-lookup"><span data-stu-id="83d47-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="83d47-157">応答グループマネージャーは、それに割り当てられた応答グループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="83d47-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="83d47-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="83d47-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="83d47-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="83d47-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="83d47-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="83d47-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="83d47-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="83d47-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a></span><span class="sxs-lookup"><span data-stu-id="83d47-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="83d47-164">応答グループ展開の検証</span><span class="sxs-lookup"><span data-stu-id="83d47-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="83d47-165">ハント グループ ワークフローおよび対話型音声応答ワークフローに対する通話への応答をテストして、構成が予想どおりに機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="83d47-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p>-</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

