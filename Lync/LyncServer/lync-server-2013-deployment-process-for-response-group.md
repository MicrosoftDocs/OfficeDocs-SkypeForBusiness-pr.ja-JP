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
ms.openlocfilehash: 2eb302f57cd335decf3523c271ff464f2954db86
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-response-group-in-lync-server-2013"></a><span data-ttu-id="7a314-102">Lync Server 2013 の応答グループの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="7a314-102">Deployment process for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a314-103">_**最終更新日:** 2012-09-27_</span><span class="sxs-lookup"><span data-stu-id="7a314-103">_**Topic Last Modified:** 2012-09-27_</span></span>

<span data-ttu-id="7a314-104">このセクションでは、応答グループアプリケーションの展開に関連するフェーズと手順の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="7a314-104">This section provides an overview of the phases and steps involved in deploying the Response Group application.</span></span>

### <a name="response-group-deployment-process"></a><span data-ttu-id="7a314-105">応答グループの展開プロセス</span><span class="sxs-lookup"><span data-stu-id="7a314-105">Response Group Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a314-106">フェーズ</span><span class="sxs-lookup"><span data-stu-id="7a314-106">Phase</span></span></th>
<th><span data-ttu-id="7a314-107">ステップ</span><span class="sxs-lookup"><span data-stu-id="7a314-107">Steps</span></span></th>
<th><span data-ttu-id="7a314-108">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="7a314-108">Permissions</span></span></th>
<th><span data-ttu-id="7a314-109">「展開」のドキュメント</span><span class="sxs-lookup"><span data-stu-id="7a314-109">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a314-110">応答グループアプリケーションをインストールする</span><span class="sxs-lookup"><span data-stu-id="7a314-110">Install the Response Group application</span></span></p></td>
<td><p><span data-ttu-id="7a314-111">応答グループアプリケーションは、エンタープライズボイスの展開時に既定でインストールされ、有効になります。</span><span class="sxs-lookup"><span data-stu-id="7a314-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="7a314-112">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7a314-112">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7a314-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013 でのエンタープライズボイスの展開</a></span><span class="sxs-lookup"><span data-stu-id="7a314-113"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a314-114">応答グループのコンポーネントをインストールする</span><span class="sxs-lookup"><span data-stu-id="7a314-114">Install components for Response Group</span></span></p></td>
<td><p><span data-ttu-id="7a314-115">Lync Server コマンドレット、Lync Server コントロールパネル、応答グループ構成ツール、エージェントのサインインとサインアウトのコンソール、応答グループのクライアント Web サービスは、Web サービスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7a314-115">Lync Server cmdlets, the Lync Server Control Panel, Response Group Configuration Tool, agents' sign-in and sign-out console, and Response Group Client Web service are installed as part of Web Services.</span></span> <span data-ttu-id="7a314-116">Enterprise Edition プールまたは Standard Edition サーバーを展開すると、Web サービスがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="7a314-116">Web Services is installed when you deploy an Enterprise Edition pool or a Standard Edition server.</span></span></p></td>
<td><p><span data-ttu-id="7a314-117">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7a314-117">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7a314-118"><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 の展開</a></span><span class="sxs-lookup"><span data-stu-id="7a314-118"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a314-119">Lync 2013 およびエンタープライズ Voip のユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="7a314-119">Enable users for Lync 2013 and for Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="7a314-120">Lync Server およびエンタープライズ Voip 用のエージェントになるユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="7a314-120">Enable users who will be agents for Lync Server and Enterprise Voice.</span></span> <span data-ttu-id="7a314-121">ユーザーをエージェント グループに追加する前に、ユーザーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7a314-121">Users must be enabled before you can add them to agent groups.</span></span> <span data-ttu-id="7a314-122">通常、ユーザーは Enterprise Edition または Standard Edition server の展開中に Lync Server に対して有効になっています。</span><span class="sxs-lookup"><span data-stu-id="7a314-122">Typically, users are enabled for Lync Server during the Enterprise Edition or Standard Edition server deployment.</span></span> <span data-ttu-id="7a314-123">エンタープライズボイスの展開中に、ユーザーはエンタープライズ Voip に対応しています。</span><span class="sxs-lookup"><span data-stu-id="7a314-123">Users are enabled for Enterprise Voice during the Enterprise Voice deployment.</span></span></p></td>
<td><p><span data-ttu-id="7a314-124">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="7a314-124">RTCUniversalUserAdmins</span></span></p>
<p><span data-ttu-id="7a314-125">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-125">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="7a314-126">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-126">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7a314-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Lync Server 2013 のユーザーアカウントを無効にするか、再び有効にする</a></span><span class="sxs-lookup"><span data-stu-id="7a314-127"><a href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">Disable or re-enable user account for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="7a314-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Lync Server 2013 でのエンタープライズ Voip のユーザーの有効化</a></span><span class="sxs-lookup"><span data-stu-id="7a314-128"><a href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a314-129">エージェント グループ、キュー、ワークフローから構成される応答グループを作成および構成する</span><span class="sxs-lookup"><span data-stu-id="7a314-129">Create and configure response groups, which consist of agent groups, queues, and workflows</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="7a314-130">Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7a314-130">Use the Lync Server Control Panel or Lync Server Management Shell to do the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="7a314-131">エージェント グループを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="7a314-131">Create and configure agent groups.</span></span></p></li>
<li><p><span data-ttu-id="7a314-132">キューを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="7a314-132">Create and configure queues.</span></span></p></li>
</ol></li>
<li><p><span data-ttu-id="7a314-133">必要に応じて、Lync Server 管理シェルを使用して、定義済みの応答グループの勤務時間および休日を作成します。</span><span class="sxs-lookup"><span data-stu-id="7a314-133">Optionally, use Lync Server Management Shell to create predefined response group business hours and holidays.</span></span></p></li>
<li><p><span data-ttu-id="7a314-134">応答グループの構成ツールまたは Lync Server 管理シェルを使用して、カスタム応答グループの営業時間や休日などのワークフロー (ハントグループまたはインタラクティブな音声応答 (IVR) 通話フロー) を作成します。</span><span class="sxs-lookup"><span data-stu-id="7a314-134">Use the Response Group Configuration Tool or Lync Server Management Shell to create workflows (hunt groups or interactive voice response (IVR) call flows), including custom response group business hours and holidays.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="7a314-135">Lync Server コントロールパネルから応答グループの構成ツールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7a314-135">You can access the Response Group Configuration Tool through Lync Server Control Panel.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="7a314-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7a314-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="7a314-137">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-137">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="7a314-138">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-138">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="7a314-139">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-139">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="7a314-140">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-140">CsAdministrator</span></span></p>
<p><span data-ttu-id="7a314-141">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="7a314-141">CsResponseGroupManager</span></span></p></td>
<td><p><span data-ttu-id="7a314-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Lync Server 2013 での応答グループのエージェント グループの作成</a></span><span class="sxs-lookup"><span data-stu-id="7a314-142"><a href="lync-server-2013-create-response-group-agent-groups.md">Create Response Group agent groups Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="7a314-143"><a href="lync-server-2013-create-response-group-queues.md">Lync Server 2013 での応答グループのキューの作成</a></span><span class="sxs-lookup"><span data-stu-id="7a314-143"><a href="lync-server-2013-create-response-group-queues.md">Create Response Group queues in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="7a314-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">省略Lync Server 2013 での応答グループの営業時間の定義</a></span><span class="sxs-lookup"><span data-stu-id="7a314-144"><a href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="7a314-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">省略Lync Server 2013 で回答グループの休日セットを定義する</a></span><span class="sxs-lookup"><span data-stu-id="7a314-145"><a href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="7a314-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Lync Server 2013 でワークフローを作成または変更する</a></span><span class="sxs-lookup"><span data-stu-id="7a314-146"><a href="lync-server-2013-create-or-modify-a-workflow.md">Create or modify a workflow in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a314-147">(オプション) アプリケーションレベルの設定をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="7a314-147">(Optional) Customize application-level settings</span></span></p></td>
<td><p><span data-ttu-id="7a314-148">Lync Server 管理シェルを使用して、既定の音楽保留の構成、既定の音楽の保留中のオーディオファイル、エージェントの ringback 猶予期間、通話コンテキストの構成をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="7a314-148">Use Lync Server Management Shell to customize the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span></p></td>
<td><p><span data-ttu-id="7a314-149">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7a314-149">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="7a314-150">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-150">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="7a314-151">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-151">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="7a314-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="7a314-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7a314-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Lync Server 2013 でのアプリケーションレベルの応答グループの設定の管理</a></span><span class="sxs-lookup"><span data-stu-id="7a314-154"><a href="lync-server-2013-managing-application-level-response-group-settings.md">Managing application-level Response Group settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a314-155">(オプション) 応答グループの管理を委任する</span><span class="sxs-lookup"><span data-stu-id="7a314-155">(Optional) Delegate management of response groups</span></span></p></td>
<td><p><span data-ttu-id="7a314-156">ユーザーに CsResponseGroupManager ロールを割り当て、応答グループの構成を委任します。</span><span class="sxs-lookup"><span data-stu-id="7a314-156">Assign users the CsResponseGroupManager role to delegate configuration of response groups.</span></span> <span data-ttu-id="7a314-157">応答グループマネージャーは、それらに割り当てられた応答グループを構成できます。</span><span class="sxs-lookup"><span data-stu-id="7a314-157">Response Group Managers can then configure the response groups assigned to them.</span></span></p></td>
<td><p><span data-ttu-id="7a314-158">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7a314-158">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="7a314-159">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-159">CsResponseGroupAdministrator</span></span></p>
<p><span data-ttu-id="7a314-160">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-160">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="7a314-161">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-161">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="7a314-162">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7a314-162">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="7a314-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</a></span><span class="sxs-lookup"><span data-stu-id="7a314-163"><a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a314-164">応答グループ展開を検証する</span><span class="sxs-lookup"><span data-stu-id="7a314-164">Verify your Response Group deployment</span></span></p></td>
<td><p><span data-ttu-id="7a314-165">ハント グループ ワークフローおよび対話型音声応答ワークフローに対する通話への応答をテストして、構成が正常に機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7a314-165">Test answering calls to your hunt group and interactive voice response workflows to ensure that your configuration works as expected.</span></span></p></td>
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

