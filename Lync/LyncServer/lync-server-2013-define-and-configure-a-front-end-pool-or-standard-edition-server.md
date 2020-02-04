---
title: フロントエンド プールまたは Standard Edition サーバーを定義および構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a Front End pool or Standard Edition server
ms:assetid: 713fc263-23dd-414a-b001-82932e4fe966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398538(v=OCS.15)
ms:contentKeyID: 48184457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ddc430370c59e279e0e36aa662da0f33973e0d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="b1146-102">Lync Server 2013 でフロントエンド プールまたは Standard Edition サーバーを定義および構成する</span><span class="sxs-lookup"><span data-stu-id="b1146-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1146-103">_**最終更新日:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="b1146-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="b1146-104">この手順では、ローカル管理者または特権ドメイングループのメンバーシップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b1146-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="b1146-105">コンピューターに標準ユーザーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1146-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="b1146-106">エンタープライズサーバーを展開する場合は、プール内の少なくとも1つのフロントエンドサーバーが常に実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1146-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="b1146-107">次の表は、これらの要件をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="b1146-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1146-108">プール内のフロントエンドサーバーの合計数</span><span class="sxs-lookup"><span data-stu-id="b1146-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="b1146-109">プールを機能させるために実行する必要があるサーバーの数</span><span class="sxs-lookup"><span data-stu-id="b1146-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1146-110">1-2</span><span class="sxs-lookup"><span data-stu-id="b1146-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="b1146-111">1</span><span class="sxs-lookup"><span data-stu-id="b1146-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1146-112">3 ～ 4</span><span class="sxs-lookup"><span data-stu-id="b1146-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="b1146-113">両面</span><span class="sxs-lookup"><span data-stu-id="b1146-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1146-114">5 ～ 6</span><span class="sxs-lookup"><span data-stu-id="b1146-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="b1146-115">3</span><span class="sxs-lookup"><span data-stu-id="b1146-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1146-116">7-8</span><span class="sxs-lookup"><span data-stu-id="b1146-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="b1146-117">4</span><span class="sxs-lookup"><span data-stu-id="b1146-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1146-118">9-10</span><span class="sxs-lookup"><span data-stu-id="b1146-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="b1146-119">5</span><span class="sxs-lookup"><span data-stu-id="b1146-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1146-120">11-12</span><span class="sxs-lookup"><span data-stu-id="b1146-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="b1146-121">6</span><span class="sxs-lookup"><span data-stu-id="b1146-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="b1146-122">Lync Server 2013 の場合、プールからフロントエンドサーバーを追加または削除するときは、サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1146-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="b1146-123">サーバーの削除と追加は、個別の操作として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1146-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="b1146-124">たとえば、2台のフロントエンドサーバーを追加して、2台のフロントエンドサーバーを削除する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b1146-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="b1146-125">2台のフロントエンドサーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b1146-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="b1146-126">トポロジを公開して再アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="b1146-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="b1146-127">サービスを再起動する</span><span class="sxs-lookup"><span data-stu-id="b1146-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="b1146-128">2台のフロントエンドサーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b1146-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="b1146-129">トポロジを公開して再アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="b1146-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="b1146-130">サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b1146-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="b1146-131">トポロジを定義した後、次の手順を使用して、サイトのフロントエンドプールを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1146-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="b1146-132">トポロジの定義の詳細については、「 [Lync Server 2013 のトポロジビルダーでトポロジを定義して構成](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1146-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="b1146-133">フロントエンドプールを定義するには</span><span class="sxs-lookup"><span data-stu-id="b1146-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="b1146-134">[新しいフロントエンドプールの定義] ウィザードの [**新しいフロントエンドプールの定義**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1146-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="b1146-135">[**フロントエンドプールの FQDN の定義**] ページで、作成するプールの完全修飾ドメイン名 (fqdn) を入力し、[ **Enterprise Edition のフロントエンドプール**] をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1146-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="b1146-136">[**このプールのコンピューターを定義**する] ページで、プールの最初のフロントエンドサーバーのコンピューターの FQDN を入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1146-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="b1146-137">プールに追加するその他のコンピューター (最大で12人) について、この手順を繰り返し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1146-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="b1146-138">**[機能の選択**] ページで、このフロントエンドプールに必要な機能のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b1146-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="b1146-139">たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開している場合、[**会議**] チェックボックスをオンにして、マルチパーティの IM を許可しますが、**ダイヤルイン (PSTN) 会議**、**エンタープライズボイス**、または**通話受付制御**のチェックボックスは、音声、ビデオ、共同作業の会議機能を表します。</span><span class="sxs-lookup"><span data-stu-id="b1146-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="b1146-140">**会議**   このオプションを選択すると、次のような豊富な機能セットが有効になります。</span><span class="sxs-lookup"><span data-stu-id="b1146-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="b1146-141">IM セッションでは、2人以上の相手との IM ができます。</span><span class="sxs-lookup"><span data-stu-id="b1146-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="b1146-142">会議: ドキュメントのグループ作業、アプリケーション共有、デスクトップ共有が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b1146-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="b1146-143">A/V 会議: Live Meeting サービスやサードパーティのオーディオブリッジなどの外部サービスを必要とせずに、ユーザーがリアルタイムの音声/ビデオ (A/V) 会議を利用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b1146-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="b1146-144">**ダイヤルイン (pstn) 会議**   では、電話会議プロバイダーを必要とせずに、公衆交換電話網 (pstn) を使用して、Lync Server 2013 会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="b1146-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="b1146-145">**エンタープライズ voip**   エンタープライズ voip は、ユーザーが電話をかけたり受信したりできるようにする、Lync Server 2013 のボイスオーバー IP (VoIP) ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="b1146-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="b1146-146">この機能は、音声通話、ボイスメール、ハードウェアデバイスまたはソフトウェアクライアントを使用するその他の機能に Lync Server 2013 を使用する予定がある場合に展開します。</span><span class="sxs-lookup"><span data-stu-id="b1146-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="b1146-147">**通話受付制御 (cac)**   cac は、使用可能なネットワーク帯域幅に基づいて、音声通話やビデオ通話などのリアルタイム通信セッションを許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="b1146-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="b1146-148">IM とプレゼンスのみを展開している場合、これら2つの機能のどちらも CAC を使用しているため、CAC は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b1146-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="b1146-149">**アーカイブ**   アーカイブを使用すると、IM コンテンツ、会議 (会議) コンテンツ、または Lync Server 2013 経由で送信された両方のアイテムをアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="b1146-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="b1146-150">\*\*\*\*   監視サーバーを監視すると、ネットワークとエンドポイントのメディア品質、VoIP 通話に関連する使用状況情報、IM メッセージ、A/V の会話、会議、アプリケーション共有、ファイル転送、失敗した通話のエラーとトラブルシューティングに関する情報を説明する数値データを収集できます。</span><span class="sxs-lookup"><span data-stu-id="b1146-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b1146-151">展開で CAC を有効にする場合は、セントラルサイトごとに1つのプールで CAC を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1146-151">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site.</span></span> <span data-ttu-id="b1146-152">音声機能または A/V 会議を展開する場合は、CAC をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b1146-152">CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="b1146-153">次の表は、利用可能な機能 (上) と、ユーザーに提供される関数 (左側) を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1146-153">The following table shows the available features (top) and the functions offered to users (left).</span></span> <span data-ttu-id="b1146-154">表の選択肢は、組織でこれらの機能を有効にするために選択する必要があるものです。</span><span class="sxs-lookup"><span data-stu-id="b1146-154">The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    <col style="width: 20%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th></th>
    <th><span data-ttu-id="b1146-155">会議</span><span class="sxs-lookup"><span data-stu-id="b1146-155">Conferencing</span></span></th>
    <th><span data-ttu-id="b1146-156">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="b1146-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="b1146-157">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="b1146-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="b1146-158">通話受付管理</span><span class="sxs-lookup"><span data-stu-id="b1146-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="b1146-159">インスタント メッセージングとプレゼンス</span><span class="sxs-lookup"><span data-stu-id="b1146-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="b1146-160">X</span><span class="sxs-lookup"><span data-stu-id="b1146-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b1146-161">会議</span><span class="sxs-lookup"><span data-stu-id="b1146-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="b1146-162">X</span><span class="sxs-lookup"><span data-stu-id="b1146-162">X</span></span></p></td>
    <td><p><span data-ttu-id="b1146-163">X</span><span class="sxs-lookup"><span data-stu-id="b1146-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="b1146-164">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="b1146-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="b1146-165">X</span><span class="sxs-lookup"><span data-stu-id="b1146-165">X</span></span></p></td>
    <td><p><span data-ttu-id="b1146-166">X</span><span class="sxs-lookup"><span data-stu-id="b1146-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="b1146-167">X</span><span class="sxs-lookup"><span data-stu-id="b1146-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b1146-168">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="b1146-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="b1146-169">X</span><span class="sxs-lookup"><span data-stu-id="b1146-169">X</span></span></p></td>
    <td><p><span data-ttu-id="b1146-170">X</span><span class="sxs-lookup"><span data-stu-id="b1146-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="b1146-171">**[併置**されたサーバーの役割の選択] ページでは、フロントエンドサーバーで仲介サーバーを検索するか、スタンドアロンサーバーとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="b1146-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="b1146-172">ユーザーは、フロントエンドプールで仲介サーバーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="b1146-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="b1146-173">Enterprise Edition フロントエンドプールで仲介サーバーを検索する場合は、チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b1146-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="b1146-174">サーバーの役割はプール サーバーに展開されます。</span><span class="sxs-lookup"><span data-stu-id="b1146-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="b1146-175">仲介サーバーをスタンドアロンサーバーとして展開する場合は、該当するチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="b1146-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="b1146-176">フロントエンドサーバーを完全に展開した後、別の展開手順で仲介サーバーを展開します。</span><span class="sxs-lookup"><span data-stu-id="b1146-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b1146-177">可能であれば、仲介サーバーを検索することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b1146-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="b1146-178">併置された、またはスタンドアロンの仲介サーバーのサポートの詳細については、計画ドキュメントの「 <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync server 2013 での仲介サーバーのコンポーネントとトポロジ</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1146-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="b1146-179">[**サーバーの役割をこのフロントエンドプール] ページに関連付ける**と、サーバーの役割を定義して、フロントエンドプールに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="b1146-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="b1146-180">次の役割を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1146-180">The following role is available:</span></span>
    
    <span data-ttu-id="b1146-181">**エッジプール**   を有効にする1つのエッジサーバーまたはエッジサーバーのプールを定義して関連付けます。</span><span class="sxs-lookup"><span data-stu-id="b1146-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="b1146-182">エッジ サーバーを使用すると、組織内のユーザーと組織外のユーザー (フェデレーション ユーザーなど) との間の通信および共同作業が容易になります。</span><span class="sxs-lookup"><span data-stu-id="b1146-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="b1146-183">サーバーの役割を展開して関連付けるには、次の2つのシナリオを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1146-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="b1146-184">シナリオ 1 では、新しいインストールで新しいトポロジを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1146-184">For scenario one, you are defining a new topology for a new installation.</span></span> <span data-ttu-id="b1146-185">インストールには、次の2つの方法のいずれかの方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b1146-185">You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="b1146-186">チェックボックスをオフのままにして、トポロジの定義を続行します。</span><span class="sxs-lookup"><span data-stu-id="b1146-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="b1146-187">フロントエンド サーバーとバックエンド サーバーの各役割の公開、構成、およびテストを行った後、もう一度トポロジ ビルダーを実行して、各役割のサーバーをトポロジに追加できます。</span><span class="sxs-lookup"><span data-stu-id="b1146-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="b1146-188">この戦略では、他の役割を追加しなくても、フロントエンドプールと SQL Server を実行しているサーバーをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="b1146-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="b1146-189">最初のテストが完了したら、トポロジ ビルダーを再び実行して、展開が必要な役割を選択できます。</span><span class="sxs-lookup"><span data-stu-id="b1146-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="b1146-190">インストールする必要がある役割を選択し、選択した役割に対応するハードウェアをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="b1146-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="b1146-191">シナリオ2では、既存の展開があり、インフラストラクチャで新しい役割を割り当てることができます。または、既存の役割を新しいフロントエンドサーバーに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1146-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="b1146-192">この場合は、新しいフロントエンドサーバーに展開する、または関連付けるロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1146-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="b1146-193">どちらの場合も、役割の定義を続行して必要なハードウェアを設定し、インストールを進めます。</span><span class="sxs-lookup"><span data-stu-id="b1146-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="b1146-194">[ **SQL ストアの定義**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b1146-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b1146-195">トポロジで既に定義されている既存の SQL Server ストアを使用するには、[**SQL ストア**] でインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1146-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="b1146-196">プール情報を格納するための新しい SQL Server インスタンスを定義するには、[**新規**] をクリックし、[**新しい Sql ストアの定義**] ダイアログボックスで**sql server の FQDN**を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1146-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="b1146-197">SQL Server インスタンスの名前を指定するには、[**名前付きインスタンス**] を選択し、インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1146-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="b1146-198">既定のインスタンスを使用するには、[**既定のインスタンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1146-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="b1146-199">SQL ミラーリングを使用するには、[ **sql ミラーリングを有効に**する] を選択し、既存のインスタンスを選ぶか、新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b1146-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="b1146-200">[**ファイル共有の定義**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b1146-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="b1146-201">トポロジで既に定義されているファイル共有を使用するには、[**以前に定義したファイル共有を使用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1146-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="b1146-202">新しいファイル共有を定義するには、[**新しいファイル共有の定義**] を選択し、[**ファイル サーバー FQDN**] ボックスで、ファイル共有が存在する既存のファイル サーバーの FQDN を入力します。そして、[**ファイル共有**] ボックスでファイル共有の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1146-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="b1146-203">Lync Server 2013 のファイル共有は、フロントエンドサーバー上に配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="b1146-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="b1146-204">この例では、ファイル共有が SQL Server ベースのバックエンドサーバーに配置されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b1146-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="b1146-205">これは、組織の要件に最適な場所ではない可能性があります。また、ファイルサーバーの方が適している場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b1146-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="b1146-206">ファイル共有をまだ作成していなくても、ファイル共有を定義できます。</span><span class="sxs-lookup"><span data-stu-id="b1146-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="b1146-207">その場合は、トポロジを公開する前に、定義した場所にファイル共有を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1146-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="b1146-208">[ **Web サービスの URL の指定**] ページで、次のいずれか、または両方の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b1146-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="b1146-209">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="b1146-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="b1146-210">たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。</span><span class="sxs-lookup"><span data-stu-id="b1146-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="b1146-211">フロントエンドプールまたはフロントエンドサーバーが複数ある場合は、外部 Web サービスの FQDN が一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1146-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="b1146-212">たとえば、フロントエンドサーバーの外部 Web サービス FQDN を<STRONG>pool01.contoso.com</STRONG>として定義する場合、別のフロントエンドプールまたはフロントエンドサーバーに対して<STRONG>pool01.contoso.com</STRONG>を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b1146-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="b1146-213">DNS 負荷分散を構成する場合は、[**内部 Web サービスプールの fqdn の上書き**] チェックボックスをオンにし **、内部ベース**URL (プールの fqdn とは異なる必要があります。これ\<はプールの\>fqdn とは異なる場合があります) を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1146-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="b1146-214">自動定義の FQDN を使用して内部 web サービスを上書きする場合、各 FQDN は、他のフロントエンドプール、ディレクター、またはディレクタープールから一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1146-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="b1146-215"><STRONG>URL または完全修飾ドメイン名を定義するときに使用できる文字は、標準文字のみ</STRONG> (A ～ Z、a ～ z、0 ～ 9、およびハイフン) です。</span><span class="sxs-lookup"><span data-stu-id="b1146-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="b1146-216">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="b1146-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="b1146-217">一般に、外部 DNS および公的 CA では、URL または FQDN に非標準文字はサポートされていません (証明書で URL または FQDN をサブジェクト名またはサブジェクトの別名に割り当てることが必要になります)。</span><span class="sxs-lookup"><span data-stu-id="b1146-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="b1146-218">必要に応じて、外部ベース**url**に外部ベース url を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1146-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="b1146-219">外部のベース URL を入力して、内部ドメインの名前付けと区別します。</span><span class="sxs-lookup"><span data-stu-id="b1146-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="b1146-220">たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="b1146-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="b1146-221">Contoso.com ドメイン名を使って URL を定義します。</span><span class="sxs-lookup"><span data-stu-id="b1146-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="b1146-222">これは、リバースプロキシの場合にも重要です。</span><span class="sxs-lookup"><span data-stu-id="b1146-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="b1146-223">外部ベース URL のドメイン名は、リバースプロキシの FQDN のドメイン名と同じです。</span><span class="sxs-lookup"><span data-stu-id="b1146-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="b1146-224">インスタントメッセージングとプレゼンスを使用するには、フロントエンドプールへの HTTP アクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b1146-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b1146-225">DNS の負荷分散を使用するには、適切な DNS レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1146-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="b1146-226">詳細については、「 <A href="lync-server-2013-configure-dns-for-load-balancing.md">Lync Server 2013 でのロードバランシング用に DNS を構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1146-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="b1146-227">**[機能の選択**] ページで [**会議**] を選択した場合は、[ **Office web apps**サーバーを選択してください] ページで、[**プールを office web apps サーバーに関連付け**ます] をクリックし、[**新規**] をクリックします (または、ドロップダウンリストから既存の Office web apps サーバーを選択します)。</span><span class="sxs-lookup"><span data-stu-id="b1146-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="b1146-228">[**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="b1146-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="b1146-229">Office Web Apps サーバーがオンプレミスで、Lync Server 2013 と同じネットワークゾーンにインストールされている場合は、[ **Office Web Apps サーバーを外部ネットワーク (つまり、境界/インターネット) に展開**する] オプションを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="b1146-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="b1146-230">Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b1146-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b1146-231">詳細については、「 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps サーバーおよび Lync server 2013 との統合を構成する</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1146-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="b1146-232">[**アーカイブ SQL ストアの定義**] ページで、既存のインスタンスまたは SQL Server を選ぶか、アーカイブデータに関連付けられたデータを格納するための新しいインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1146-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="b1146-233">[ **Sql ストアの監視**] ページで、既存のインスタンスまたは sql Server を選ぶか、データの監視に関連付けられたデータを格納するための新しいインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="b1146-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="b1146-234">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1146-234">Click **Next**.</span></span> <span data-ttu-id="b1146-235">[**サーバーの役割にこのフロントエンドプールを関連付け**ます] ページで他の役割サーバーを定義した場合、役割構成ウィザードページが開き、サーバーの役割を構成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b1146-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="b1146-236">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1146-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="b1146-237">Lync Server 2013 での外部ユーザー アクセスの展開</span><span class="sxs-lookup"><span data-stu-id="b1146-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="b1146-238">構成および展開のために追加のサーバーロールを選択していない場合、または追加の役割サーバーの構成を完了した場合は、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1146-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

