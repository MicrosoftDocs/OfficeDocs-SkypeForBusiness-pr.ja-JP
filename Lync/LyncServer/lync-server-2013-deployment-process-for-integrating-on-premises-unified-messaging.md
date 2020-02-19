---
title: オンプレミスのユニファイドメッセージングを統合するための展開プロセス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6d60b120db57ad73c33e682fa8150e99f5606e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="939f6-102">オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するための展開プロセス</span><span class="sxs-lookup"><span data-stu-id="939f6-102">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="939f6-103">_**トピックの最終更新日:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="939f6-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="939f6-104">Exchange ユニファイドメッセージング (UM) と Lync Server 2013 を統合する場合は、このトピックで説明するタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="939f6-104">If you want to integrate Exchange Unified Messaging (UM) with Lync Server 2013, you must perform the tasks described in this topic.</span></span> <span data-ttu-id="939f6-105">また、「[オンプレミスのユニファイドメッセージングと Lync Server 2013 を統合するためのガイドライン](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)」に記載されている計画および展開のベストプラクティスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-105">Also be sure that you review the planning and deployment best practices described in [Guidelines for integrating on-premises Unified Messaging and Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md).</span></span> <span data-ttu-id="939f6-106">このトピックでは、Lync server 2013 を併置された仲介2013サーバーと共に展開し、「展開」のドキュメントの「 [Lync server 2013 でのエンタープライズ voip の展開](lync-server-2013-deploying-enterprise-voice.md)」で説明するように、エンタープライズ voip を有効にするための展開と構成の手順をすべて実行したことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="939f6-106">This topic assumes that you have deployed Lync Server 2013 with a collocated Mediation Server and that you have enabled users for Lync Server 2013, but not necessarily that you have performed all deployment and configuration steps to enable Enterprise Voice, as described in [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="unified-messaging-integration-process"></a><span data-ttu-id="939f6-107">ユニファイド メッセージング統合プロセス</span><span class="sxs-lookup"><span data-stu-id="939f6-107">Unified Messaging Integration Process</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="939f6-108">円滑で成功した統合を確実にするために、組織の Exchange 管理者と協力して、各ユーザーが実行するタスクを確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="939f6-108">It is important that you coordinate with your organization’s Exchange administrators to confirm the tasks that each of you will perform to help ensure a smooth, successful integration.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="939f6-109">フェーズ</span><span class="sxs-lookup"><span data-stu-id="939f6-109">Phase</span></span></th>
<th><span data-ttu-id="939f6-110">手順</span><span class="sxs-lookup"><span data-stu-id="939f6-110">Steps</span></span></th>
<th><span data-ttu-id="939f6-111">必要なグループおよび役割</span><span class="sxs-lookup"><span data-stu-id="939f6-111">Required groups and roles</span></span></th>
<th><span data-ttu-id="939f6-112">展開のドキュメント</span><span class="sxs-lookup"><span data-stu-id="939f6-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="939f6-113">次のいずれかを展開します。</span><span class="sxs-lookup"><span data-stu-id="939f6-113">Deploy one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="939f6-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) または最新のサービスパック</span><span class="sxs-lookup"><span data-stu-id="939f6-114">Microsoft Exchange Server 2007 Service Pack 1 (SP2) or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="939f6-115">Microsoft Exchange Server 2010 または最新のサービスパック</span><span class="sxs-lookup"><span data-stu-id="939f6-115">Microsoft Exchange Server 2010 or latest service pack</span></span></p></li>
<li><p><span data-ttu-id="939f6-116">Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="939f6-116">Microsoft Exchange Server 2013</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="939f6-117">Microsoft Exchange Server 2013 を使用している場合は、次の Exchange サーバーの役割を同じフォレストまたは別のフォレストの Lync Server 2013 としてインストールします。</span><span class="sxs-lookup"><span data-stu-id="939f6-117">If you are using Microsoft Exchange Server 2013, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="939f6-118">クライアント アクセス</span><span class="sxs-lookup"><span data-stu-id="939f6-118">Client Access</span></span></p></li>
<li><p><span data-ttu-id="939f6-119">メールボックス</span><span class="sxs-lookup"><span data-stu-id="939f6-119">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="939f6-120">Microsoft Exchange Server 2013 と Exchange ユニファイドメッセージング (UM) が異なるフォレストにインストールされている場合は、Lync Server 2013 フォレストを信頼するように各 Exchange フォレストを構成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-120">If Microsoft Exchange Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p>
<p><span data-ttu-id="939f6-121">Exchange 2010 を使用している場合は、Lync Server 2013 と同じフォレストまたは別のフォレストに、次の Exchange サーバーの役割をインストールします。</span><span class="sxs-lookup"><span data-stu-id="939f6-121">If you are using Exchange 2010, install the following Exchange Server roles in either the same forest or a different forest as Lync Server 2013:</span></span></p>
<ul>
<li><p><span data-ttu-id="939f6-122">ユニファイド メッセージング</span><span class="sxs-lookup"><span data-stu-id="939f6-122">Unified Messaging</span></span></p></li>
<li><p><span data-ttu-id="939f6-123">ハブ トランスポート</span><span class="sxs-lookup"><span data-stu-id="939f6-123">Hub Transport</span></span></p></li>
<li><p><span data-ttu-id="939f6-124">クライアント アクセス</span><span class="sxs-lookup"><span data-stu-id="939f6-124">Client Access</span></span></p></li>
<li><p><span data-ttu-id="939f6-125">メールボックス</span><span class="sxs-lookup"><span data-stu-id="939f6-125">Mailbox</span></span></p></li>
</ul>
<p><span data-ttu-id="939f6-126">Lync Server 2013 と Exchange ユニファイドメッセージング (UM) が異なるフォレストにインストールされている場合は、Lync Server 2013 フォレストを信頼するように各 Exchange フォレストを構成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-126">If Lync Server 2013 and Exchange Unified Messaging (UM) are installed in different forests, configure each Exchange forest to trust the Lync Server 2013 forest.</span></span></p></td>
<td><p><span data-ttu-id="939f6-127">エンタープライズ管理者 (これが組織内で最初の Exchange Server である場合)</span><span class="sxs-lookup"><span data-stu-id="939f6-127">Enterprise administrators (if this is the first Exchange Server in the organization)</span></span></p>
<p><span data-ttu-id="939f6-128">または -</span><span class="sxs-lookup"><span data-stu-id="939f6-128">-OR-</span></span></p>
<p><span data-ttu-id="939f6-129">Exchange 組織管理者 (これが組織内で最初の Exchange Server ではない場合)</span><span class="sxs-lookup"><span data-stu-id="939f6-129">Exchange Organization administrator (if this is not the first Exchange Server in the organization)</span></span></p></td>
<td><p><span data-ttu-id="939f6-130">お使いの Exchange Server のバージョンに適したドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-130">See the appropriate documentation for your version of Exchange Server:</span></span></p>
<dl>
<dt><span></span></dt>
<dd><p><span data-ttu-id="939f6-131">Exchange Server 2007 の展開に<a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="939f6-131">Exchange Server 2007 deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="939f6-132">Exchange Server 2010 または最新の service pack の<a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>展開に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="939f6-132">Exchange Server 2010 or latest service pack deployment documentation at <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a>.</span></span></p>
</dd>
<dt><span></span></dt>
<dd><p><span data-ttu-id="939f6-133">Microsoft Exchange Server 2013 の計画と展開<a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>」</span><span class="sxs-lookup"><span data-stu-id="939f6-133">Microsoft Exchange Server 2013 Planning and Deployment at <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</span></span></p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939f6-134">証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="939f6-134">Install certificates.</span></span></p></td>
<td><p><span data-ttu-id="939f6-135">信頼されたルート証明機関 (CA) から、各 Exchange UM サーバーの証明書をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="939f6-135">Download and install certificates for each Exchange UM server from a trusted root certificate authority (CA).</span></span> <span data-ttu-id="939f6-136">この証明書は、Exchange UM と Lync Server 2013 を実行しているサーバー間の相互トランスポートレベルのセキュリティ (MTLS) に必要です。</span><span class="sxs-lookup"><span data-stu-id="939f6-136">The certificates are required for mutual Transport Level Security (MTLS) between the servers running Exchange UM and Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="939f6-137">管理者</span><span class="sxs-lookup"><span data-stu-id="939f6-137">Administrators</span></span></p></td>
<td><p><span data-ttu-id="939f6-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する</a></span><span class="sxs-lookup"><span data-stu-id="939f6-138"><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939f6-139">新しい Exchange UM SIP ダイヤルプランを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-139">Create and configure a new Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="939f6-140">Exchange UM サーバーで、組織の特定の展開要件に基づいて SIP ダイヤルプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-140">On the Exchange UM server, create a SIP dial plan based on your organization’s specific deployment requirements.</span></span></p></td>
<td><p><span data-ttu-id="939f6-141">Exchange 組織管理者</span><span class="sxs-lookup"><span data-stu-id="939f6-141">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="939f6-142">Exchange 2007 SP1 または最新のサービスパックに&quot;ついては、「How to Create a ユニファイ&quot;ド<a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>メッセージング SIP URI ダイヤルプラン」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-142">For Exchange 2007 SP1 or latest service pack, see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a>.</span></span></p>
<p><span data-ttu-id="939f6-143">Exchange 2010 または最新のサービスパックに&quot;ついては、「&quot; UM <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>ダイヤルプランを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-143">For Exchange 2010 or latest service pack, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a>.</span></span></p>
<p><span data-ttu-id="939f6-144">Exchange 2013 については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>ユニファイドメッセージング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-144">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939f6-145">Exchange UM SIP ダイヤルプランのセキュリティ設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-145">Configure security settings for the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="939f6-146">エンタープライズ Voip トラフィックを暗号化するには、Exchange UM SIP ダイヤルプランのセキュリティ設定を、SIP がセキュリティで<strong>保護</strong><strong>されているか、</strong>セキュリティで保護されるように構成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-146">To encrypt Enterprise Voice traffic, configure the security settings on the Exchange UM SIP dial plan as <strong>SIP Secured</strong> or <strong>Secured</strong>.</span></span> <span data-ttu-id="939f6-147">これは、お客様の環境に Lync Phone Edition デバイスを展開または展開する予定がある場合に特に重要な手順です。</span><span class="sxs-lookup"><span data-stu-id="939f6-147">This is an especially important step if you have deployed or plan to deploy Lync Phone Edition devices in your environment.</span></span> <span data-ttu-id="939f6-148">Exchange UM 統合を使用した環境で Lync Phone Edition デバイスを機能させるには、Lync Server の暗号化設定を Exchange UM ダイヤルプランのセキュリティ設定と揃える必要があります。</span><span class="sxs-lookup"><span data-stu-id="939f6-148">For Lync Phone Edition devices to function in an environment with Exchange UM integration, Lync Server encryption settings must align with the Exchange UM dial plan security settings.</span></span> <span data-ttu-id="939f6-149">詳細については、「展開」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-149">For details, refer to the Deployment documentation.</span></span></p></td>
<td><p><span data-ttu-id="939f6-150">Exchange 組織管理者</span><span class="sxs-lookup"><span data-stu-id="939f6-150">Exchange Organization administrator</span></span></p></td>
<td><p><span data-ttu-id="939f6-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 の Microsoft Exchange でのユニファイドメッセージングの構成</a></span><span class="sxs-lookup"><span data-stu-id="939f6-151"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="939f6-152">Exchange 2007 SP1 または最新の service pack の場合は、次の項目も参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-152">For Exchange 2007 SP1 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="939f6-153">&quot;ユニファイドメッセージングダイヤルプラン&quot;でセキュリティを構成する方法<a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>について説明します。</span><span class="sxs-lookup"><span data-stu-id="939f6-153">&quot;How to Configure Security on a Unified Messaging Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a>.</span></span></p>
<p><span data-ttu-id="939f6-154">Exchange 2010 または最新 Service Pack の場合は、次のドキュメントも参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-154">For Exchange 2010 or latest service pack, see also:</span></span></p>
<p><span data-ttu-id="939f6-155">&quot;UM ダイヤルプラン&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>で VoIP セキュリティを構成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-155">&quot;Configure VoIP Security on a UM Dial Plan&quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a>.</span></span></p>
<p><span data-ttu-id="939f6-156">Exchange 2013 については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>ユニファイドメッセージング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-156">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939f6-157">ユニファイドメッセージングサーバーを Exchange UM SIP ダイヤルプランに追加します。</span><span class="sxs-lookup"><span data-stu-id="939f6-157">Add Unified Messaging servers to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="939f6-158">新しくインストールされたユニファイド メッセージング サーバーを、着信通話に応答および着信通話を処理できるようにするには、ユニファイド メッセージング サーバーを UM ダイヤル プランに追加しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="939f6-158">To enable a newly installed Unified Messaging server to answer and process incoming calls, you must add the Unified Messaging server to a UM dial plan.</span></span> <span data-ttu-id="939f6-159">この場合は、Exchange UM SIP ダイヤルプランにサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="939f6-159">In this case, add the server to the Exchange UM SIP dial plan.</span></span></p></td>
<td><p><span data-ttu-id="939f6-160">管理者</span><span class="sxs-lookup"><span data-stu-id="939f6-160">Administrators</span></span></p>
<p><span data-ttu-id="939f6-161">Exchange Server 管理者</span><span class="sxs-lookup"><span data-stu-id="939f6-161">Exchange Server administrators</span></span></p></td>
<td><p><span data-ttu-id="939f6-162">Exchange 2007 SP1 または最新のサービスパックに&quot;ついては、「方法: ユニファイドメッセージング&quot;サーバー <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>をダイヤルプランに追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-162">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add Unified Messaging Server to a Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a>.</span></span></p>
<p><span data-ttu-id="939f6-163">Exchange 2010 または最新のサービスパックに&quot;ついては、「UM サーバー&quot;のプロパティを<a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>表示または構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-163">For Exchange 2010 or latest service pack, see &quot;View or Configure the Properties of a UM Server&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a>.</span></span></p>
<p><span data-ttu-id="939f6-164">Exchange 2013 については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>ユニファイドメッセージング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-164">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939f6-165">SIP アドレスでメールボックスを構成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-165">Configure mailboxes with SIP addresses.</span></span></p></td>
<td><p><span data-ttu-id="939f6-166">Exchange UM の機能を使用するエンタープライズ Voip ユーザーのメールボックスに SIP アドレスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="939f6-166">Assign SIP addresses to the mailboxes of Enterprise Voice users who will be using Exchange UM features.</span></span></p></td>
<td><p><span data-ttu-id="939f6-167">Lync Server 2013 管理者</span><span class="sxs-lookup"><span data-stu-id="939f6-167">Lync Server 2013 administrator</span></span></p>
<p><span data-ttu-id="939f6-168">Exchange 受信者管理者</span><span class="sxs-lookup"><span data-stu-id="939f6-168">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="939f6-169">Exchange 2007 SP1 または最新のサービスパックに&quot;ついては、「UM が有効なユーザー&quot;の SIP アドレスをで<a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>追加、削除、または変更する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-169">For Exchange 2007 SP1 or latest service pack, see &quot;How to Add, Remove, or Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a>.</span></span></p>
<p><span data-ttu-id="939f6-170">Exchange 2010 または最新のサービスパックに&quot;ついては、「UM が有効なユーザー&quot;の<a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>SIP アドレスを変更する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-170">For Exchange 2010 or latest service pack, see &quot;Modify a SIP Address for a UM-Enabled User&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a>.</span></span></p>
<p><span data-ttu-id="939f6-171">Exchange 2013 については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>ユニファイドメッセージング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-171">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939f6-172">exchucutil.ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="939f6-172">Run the exchucutil.ps1 script.</span></span></p></td>
<td><p><span data-ttu-id="939f6-173">Exchange UM サービスを実行しているサーバーで、Exchange 管理シェルを開き、次の処理を実行する exchucutil. ps1 スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="939f6-173">On the server running Exchange UM services, open the Exchange Management Shell and run the exchucutil.ps1 script, which does the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="939f6-174">Lync Server 2013 に、Exchange UM Active Directory ドメインサービスオブジェクト (特に、前のタスクで作成した SIP ダイヤルプラン) を読み取るためのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="939f6-174">Grants Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects, specifically, the SIP dial plans created in the previous task.</span></span></p></li>
<li><p><span data-ttu-id="939f6-175">エンタープライズ Voip が有効になっているユーザーをホストする Lync Server 2013 Enterprise Edition プールまたは Standard Edition サーバーごとに、Active Directory 内にユニファイドメッセージング IP ゲートウェイオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-175">Creates a Unified Messaging IP gateway object in Active Directory for each Lync Server 2013 Enterprise Edition pool or Standard Edition server that hosts users who are enabled for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="939f6-176">各ゲートウェイの Exchange UM ハントグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-176">Creates an Exchange UM hunt group for each gateway.</span></span> <span data-ttu-id="939f6-177">ハント グループのパイロット ID は、対応するゲートウェイに関連付けられたダイヤル プランの名前になります。</span><span class="sxs-lookup"><span data-stu-id="939f6-177">The hunt group pilot identifier will be the name of the dial plan that is associated with the corresponding gateway.</span></span> <span data-ttu-id="939f6-178">複数のダイヤル プランが存在する場合は、これらは 1 対 1 でマップされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="939f6-178">These need to be mapped 1:1 if there is more than one dial plan.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="939f6-179">Exchange 組織管理者</span><span class="sxs-lookup"><span data-stu-id="939f6-179">Exchange Organization administrator</span></span></p>
<p><span data-ttu-id="939f6-180">Exchange 受信者管理者</span><span class="sxs-lookup"><span data-stu-id="939f6-180">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="939f6-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Lync Server 2013 の Microsoft Exchange でのユニファイドメッセージングの構成</a></span><span class="sxs-lookup"><span data-stu-id="939f6-181"><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939f6-182">Lync Server 2013 ダイヤルプランを構成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-182">Configure Lync Server 2013 dial plans.</span></span></p></td>
<td><p><span data-ttu-id="939f6-183">Exchange 2007 SP1 または最新の service pack または Exchange 2010 と統合する場合は、Exchange UM ダイヤルプランの完全修飾ドメイン名 (FQDN) と一致する名前を持つ新しいエンタープライズ Voip ダイヤルプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-183">If you are integrating with Exchange 2007 SP1 or latest service pack, or Exchange 2010, create a new Enterprise Voice dial plan with a name that matches the Exchange UM dial plan fully qualified domain name (FQDN).</span></span></p>



> [!NOTE]
> <span data-ttu-id="939f6-184">UM ダイヤルプランごとにこれを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="939f6-184">You will need to do this for each UM Dial plan.</span></span>


<p><span data-ttu-id="939f6-185">Exchange 2010 SP1 と統合する場合は、適切なグローバル/サイトレベルまたはプールレベルのエンタープライズ Voip ダイヤルプランが構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-185">If you are integrating with Exchange 2010 SP1, ensure that suitable global/site-level or pool-level Enterprise Voice dial plans have been configured.</span></span></p>



> [!NOTE]
> <span data-ttu-id="939f6-186">Exchange 2010 SP1 と統合する場合は、Lync Server のダイヤルプランと Exchange UM SIP ダイヤルプランの名前を一致させる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="939f6-186">If you are integrating with Exchange 2010 SP1, the Lync Server dial plan and Exchange UM SIP dial plan names do not need to match.</span></span>

</td>
<td><p><span data-ttu-id="939f6-187">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="939f6-187">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="939f6-188"><a href="lync-server-2013-configuring-dial-plans.md">Lync Server 2013 でのダイヤルプランの構成</a></span><span class="sxs-lookup"><span data-stu-id="939f6-188"><a href="lync-server-2013-configuring-dial-plans.md">Configuring dial plans in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939f6-189">Exchange UM 統合ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="939f6-189">Run the Exchange UM Integration tool.</span></span></p></td>
<td><p><span data-ttu-id="939f6-190">Lync Server 2013 で、 <strong>ocsumutil</strong>を次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="939f6-190">On the Lync Server 2013, run <strong>ocsumutil.exe</strong>, which:</span></span></p>
<ul>
<li><p><span data-ttu-id="939f6-191">サブスクライバー アクセスおよび自動応答連絡先オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-191">Creates Subscriber Access and Auto Attendant contact objects.</span></span></p></li>
<li><p><span data-ttu-id="939f6-192">Exchange UM ダイヤルプランの FQDN と一致する名前のエンタープライズ Voip ダイヤルプランがあることを検証します。</span><span class="sxs-lookup"><span data-stu-id="939f6-192">Validates that there is an Enterprise Voice dial plan with a name that matches the Exchange UM dial plan FQDN.</span></span> <span data-ttu-id="939f6-193">Exchange 2010 SP1 以降を実行している場合は、ダイヤルプラン名を一致させる必要がないため、このツールの警告を無視することができます。</span><span class="sxs-lookup"><span data-stu-id="939f6-193">If you are running Exchange 2010 SP1 or later, the dial plan names do not need to match, and you can ignore the tool’s warning about this.</span></span></p></li>
</ul>
<p><span data-ttu-id="939f6-194">このツールは、Active Directory の Exchange UM 設定をスキャンし、Lync Server 2013 管理者が連絡先オブジェクトを表示、作成、および編集できるようにすることによって機能します。</span><span class="sxs-lookup"><span data-stu-id="939f6-194">This tool works by scanning the Active Directory for Exchange UM settings and allowing the Lync Server 2013 administrator to view, create, and edit contact objects.</span></span></p></td>
<td><p><span data-ttu-id="939f6-195">RTCUniversalServerAdmins <em>および</em> RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="939f6-195">RTCUniversalServerAdmins <em>and</em> RTCUniversalUserAdmins</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="939f6-196">ocsumutil.exe を正常に実行するため、ユーザーはこれらのグループの両方に属していなければなりません。</span><span class="sxs-lookup"><span data-stu-id="939f6-196">To run ocsumutil.exe successfully, the user must belong to both of these groups.</span></span>





> [!NOTE]
> <span data-ttu-id="939f6-197">連絡先オブジェクトを作成するには、ocsumutil.exe を実行するユーザーが、新しい連絡先オブジェクトが保存される Active Directory 組織単位 (OU) への適切なアクセス許可を持たなければなりません。</span><span class="sxs-lookup"><span data-stu-id="939f6-197">To create Contact objects, the user who runs ocsumutil.exe must have the correct permission to the Active Directory organizational unit (OU) where the new contact objects are stored.</span></span> <span data-ttu-id="939f6-198">このアクセス許可は、 <STRONG>Grant-CsOUPermission</STRONG>コマンドレットを実行することによって付与できます。</span><span class="sxs-lookup"><span data-stu-id="939f6-198">This permission can be granted by running the <STRONG>Grant-CsOUPermission</STRONG> cmdlet.</span></span> <span data-ttu-id="939f6-199">詳細については、Lync Server 管理シェルのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-199">For details, see the Lync Server Management Shell documentation.</span></span>

</td>
<td><p><span data-ttu-id="939f6-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Microsoft Exchange Server でユニファイドメッセージングを使用するように Lync Server 2013 を構成する</a></span><span class="sxs-lookup"><span data-stu-id="939f6-200"><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="939f6-201">必要に応じて、その他のエンタープライズ VoIP 構成ステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="939f6-201">If necessary, perform other Enterprise Voice configuration steps.</span></span></p></td>
<td><p><span data-ttu-id="939f6-202">サーバーまたはユーザーにエンタープライズ VoIP 設定をまだ構成していない場合、次の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="939f6-202">If you have not already configured Enterprise Voice settings on your servers or users, do one or more of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="939f6-203">展開と構成</span><span class="sxs-lookup"><span data-stu-id="939f6-203">Deploy and configure</span></span></p>
<p><span data-ttu-id="939f6-204">公衆交換電話網 (PSTN) ゲートウェイと仲介サーバー</span><span class="sxs-lookup"><span data-stu-id="939f6-204">Public switched telephone network (PSTN) gateways and Mediation Servers</span></span></p></li>
<li><p><span data-ttu-id="939f6-205">音声ポリシー、PSTN 使用法レコード、および発信通話ルートを定義します。</span><span class="sxs-lookup"><span data-stu-id="939f6-205">Define voice policies, PSTN usage records, and outbound call routes.</span></span></p></li>
<li><p><span data-ttu-id="939f6-206">エンタープライズ VoIP に対してユーザーを有効化します。</span><span class="sxs-lookup"><span data-stu-id="939f6-206">Enable users for Enterprise Voice.</span></span></p></li>
<li><p><span data-ttu-id="939f6-207">必要に応じて、特定のユーザーにダイヤル プランを構成します。</span><span class="sxs-lookup"><span data-stu-id="939f6-207">Optionally, configure specific users with dial plans.</span></span></p></li>
</ul>
<p><span data-ttu-id="939f6-208">有効にするエンタープライズ VoIP 機能によっては、その他の構成ステップが必要となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="939f6-208">Other configuration steps may be required depending on the Enterprise Voice features that you enable.</span></span></p></td>
<td><p><span data-ttu-id="939f6-209">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="939f6-209">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="939f6-210">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="939f6-210">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="939f6-211">次のセクションのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-211">See topics in the following sections:</span></span></p>
<ul>
<li><p><span data-ttu-id="939f6-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイスルートの構成</a></span><span class="sxs-lookup"><span data-stu-id="939f6-212"><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="939f6-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Lync Server 2013 でのエンタープライズ Voip の展開</a></span><span class="sxs-lookup"><span data-stu-id="939f6-213"><a href="lync-server-2013-deploying-enterprise-voice.md">Deploying Enterprise Voice in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="939f6-214">Exchange UM のエンタープライズ Voip ユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="939f6-214">Enable Enterprise Voice users for Exchange UM.</span></span></p></td>
<td><p><span data-ttu-id="939f6-215">Exchange UM サーバーで、ユニファイドメッセージングメールボックスポリシーが作成されており、各ユーザーが固有の内線番号の割り当てを持っていることを確認してから、ユーザーのユニファイドメッセージングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="939f6-215">On the Exchange UM server, ensure that a Unified Messaging mailbox policy has been created and that each user has a unique extension number assignment, and then enable the user for Unified Messaging.</span></span></p></td>
<td><p><span data-ttu-id="939f6-216">Exchange 受信者管理者</span><span class="sxs-lookup"><span data-stu-id="939f6-216">Exchange Recipient administrator</span></span></p></td>
<td><p><span data-ttu-id="939f6-217">Exchange 2007 SP1 または最新のサービスパックに&quot;ついては、「ユーザーのユニファイ&quot;ド<a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>メッセージングを有効にする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-217">For Exchange 2007 SP1 or latest service pack, see &quot;How to Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</span></span></p>
<p><span data-ttu-id="939f6-218">Exchange 2010 または最新のサービスパックに&quot;ついては、「を&quot;使用<a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>してユーザーのユニファイドメッセージングを有効にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-218">For Exchange 2010 or latest service pack, see &quot;Enable a User for Unified Messaging&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</span></span></p>
<p><span data-ttu-id="939f6-219">Exchange 2013 については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>ユニファイドメッセージング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="939f6-219">For Exchange 2013, see Unified Messaging at <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

