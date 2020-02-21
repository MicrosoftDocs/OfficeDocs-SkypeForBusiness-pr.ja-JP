---
title: フロントエンドプールまたは Standard Edition サーバーを定義および構成する
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
ms.openlocfilehash: bfd8cc2b12032e1283c10e26d4a9fa879621233f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-front-end-pool-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="5c2bf-102">Lync Server 2013 でのフロントエンドプールまたは Standard Edition サーバーの定義と構成</span><span class="sxs-lookup"><span data-stu-id="5c2bf-102">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c2bf-103">_**トピックの最終更新日:** 2013-03-08_</span><span class="sxs-lookup"><span data-stu-id="5c2bf-103">_**Topic Last Modified:** 2013-03-08_</span></span>

<span data-ttu-id="5c2bf-p101">この手順では、ローカル管理者または特権が割り当てられたドメイン グループのメンバーシップは必要ありません。標準ユーザーとしてコンピューターにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="5c2bf-106">エンタープライズサーバーを展開する場合、プール内のフロントエンドサーバーの最小数は常に実行しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-106">If you are deploying an Enterprise server, a minimum number of Front End Servers in a pool must be running at all times.</span></span> <span data-ttu-id="5c2bf-107">次の表は、こうした要件をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-107">The following table summarizes these requirements.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5c2bf-108">プール内のフロントエンド サーバーの総数</span><span class="sxs-lookup"><span data-stu-id="5c2bf-108">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="5c2bf-109">プールが機能するために実行されている必要のあるサーバーの数</span><span class="sxs-lookup"><span data-stu-id="5c2bf-109">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5c2bf-110">1 ～ 2</span><span class="sxs-lookup"><span data-stu-id="5c2bf-110">1-2</span></span></p></td>
<td><p><span data-ttu-id="5c2bf-111">1-d</span><span class="sxs-lookup"><span data-stu-id="5c2bf-111">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c2bf-112">3-4</span><span class="sxs-lookup"><span data-stu-id="5c2bf-112">3-4</span></span></p></td>
<td><p><span data-ttu-id="5c2bf-113">pbm-2</span><span class="sxs-lookup"><span data-stu-id="5c2bf-113">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c2bf-114">5-6</span><span class="sxs-lookup"><span data-stu-id="5c2bf-114">5-6</span></span></p></td>
<td><p><span data-ttu-id="5c2bf-115">1/3</span><span class="sxs-lookup"><span data-stu-id="5c2bf-115">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c2bf-116">7-8</span><span class="sxs-lookup"><span data-stu-id="5c2bf-116">7-8</span></span></p></td>
<td><p><span data-ttu-id="5c2bf-117">2/4</span><span class="sxs-lookup"><span data-stu-id="5c2bf-117">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5c2bf-118">9-10</span><span class="sxs-lookup"><span data-stu-id="5c2bf-118">9-10</span></span></p></td>
<td><p><span data-ttu-id="5c2bf-119">5</span><span class="sxs-lookup"><span data-stu-id="5c2bf-119">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5c2bf-120">11-12</span><span class="sxs-lookup"><span data-stu-id="5c2bf-120">11-12</span></span></p></td>
<td><p><span data-ttu-id="5c2bf-121">6 </span><span class="sxs-lookup"><span data-stu-id="5c2bf-121">6</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]
> <span data-ttu-id="5c2bf-122">Lync Server 2013 では、フロントエンドサーバーをプールに追加または削除するときは、サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-122">For Lync Server 2013, any time you add or remove a Front End Server from the pool, you must restart services.</span></span> <span data-ttu-id="5c2bf-123">サーバーの削除と追加は別の操作として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-123">Removing and adding servers should be done as separate operations.</span></span> <span data-ttu-id="5c2bf-124">たとえば、2台のフロントエンドサーバーを追加して、2台のフロントエンドサーバーを削除する場合は、次のプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-124">For example, if you are going to add two Front End Servers and remove two Front End Servers, use the following process:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="5c2bf-125">2 台のフロントエンド サーバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-125">Remove the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="5c2bf-126">トポロジを公開し、アクティブ化し直します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-126">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="5c2bf-127">サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-127">Restart the services</span></span></P>
> <LI>
> <P><span data-ttu-id="5c2bf-128">2 台のフロントエンド サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-128">Add the two Front End Servers.</span></span></P>
> <LI>
> <P><span data-ttu-id="5c2bf-129">トポロジを公開し、アクティブ化し直します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-129">Publish and re-activate the topology.</span></span></P>
> <LI>
> <P><span data-ttu-id="5c2bf-130">サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-130">Restart the services.</span></span></P></LI></OL>



</div>

<span data-ttu-id="5c2bf-131">トポロジを定義した後、以下の手順を使用してサイトのフロントエンドプールを定義します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-131">After you have defined your topology, use the following procedure to define a Front End pool for your site.</span></span> <span data-ttu-id="5c2bf-132">トポロジの定義の詳細については、「 [Lync Server 2013 のトポロジビルダーでのトポロジの定義と構成](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-132">For details about defining the topology, see [Define and configure a topology in Topology Builder for Lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md).</span></span>

<div>

## <a name="to-define-a-front-end-pool"></a><span data-ttu-id="5c2bf-133">フロントエンドプールを定義するには</span><span class="sxs-lookup"><span data-stu-id="5c2bf-133">To define a Front End pool</span></span>

1.  <span data-ttu-id="5c2bf-134">新しいフロント エンドのプールの定義ウィザードの **[新しいフロント エンドのプールの定義]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-134">In the Define New Front End Pool Wizard, on the **Define the New Front End pool** page, click **Next**.</span></span>

2.  <span data-ttu-id="5c2bf-135">[**フロントエンドプールの fqdn の定義**] ページで、作成するプールの完全修飾ドメイン名 (fqdn) を入力し、[ **Enterprise Edition フロントエンドプール**] をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-135">On the **Define the Front End pool FQDN** page, enter a fully qualified domain name (FQDN) for the pool you are creating, click **Enterprise Edition Front End pool**, and then click **Next**.</span></span>

3.  <span data-ttu-id="5c2bf-136">[**このプール内のコンピューターの定義**] ページで、プール内の最初のフロントエンドサーバーのコンピューターの FQDN を入力し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-136">On the **Define the computers in this pool** page, enter a computer FQDN for the first Front End Server in the pool, and then click **Add**.</span></span> <span data-ttu-id="5c2bf-137">プールに追加するコンピューター (最大12台) に対してこの手順を繰り返し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-137">Repeat this step for any additional computers (up to twelve) that you want to add to the pool, and then click **Next**.</span></span>

4.  <span data-ttu-id="5c2bf-138">**[機能の選択]** ページで、このフロント エンド プールで必要な機能のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-138">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="5c2bf-139">たとえば、インスタントメッセージング (IM) とプレゼンスの機能のみを展開する場合は、[**会議**] チェックボックスをオンにして、マルチパーティ IM を許可しますが、**ダイヤルイン (PSTN) 会議**、**エンタープライズ Voip**、または**通話受付管理**の各チェックボックスは、音声、ビデオ、および共同作業の会議機能を表します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-139">For example, if you are deploying only instant messaging (IM) and presence features, you would select the **Conferencing** check box to allow multiparty IM but would not select the **Dial-in (PSTN) conferencing**, **Enterprise Voice**, or **Call Admission Control** check boxes, because they represent voice, video, and collaborative conferencing features.</span></span>
    
      - <span data-ttu-id="5c2bf-140">**会議**   このオプションを選択すると、次のような豊富な機能セットが有効になります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-140">**Conferencing**   This selection enables a rich set of features including:</span></span>
        
          - <span data-ttu-id="5c2bf-141">1 つの IM セッションに 3 人以上のユーザーが参加する IM</span><span class="sxs-lookup"><span data-stu-id="5c2bf-141">IM with more than two parties in an IM session.</span></span>
        
          - <span data-ttu-id="5c2bf-142">ドキュメントの共同作業、アプリケーション共有、およびデスクトップ共有を含む会議</span><span class="sxs-lookup"><span data-stu-id="5c2bf-142">Conferencing, which includes document collaboration, application sharing, and desktop sharing.</span></span>
        
          - <span data-ttu-id="5c2bf-143">音声ビデオ会議を使用すると、ユーザーは Live Meeting サービスやサードパーティの音声ブリッジのような外部サービスを必要とせずに、音声ビデオ (A/V) 会議をリアルタイムで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-143">A/V conferencing, which enables users to have real-time audio/video (A/V) conferences without the need for external services such as the Live Meeting service or a third-party audio bridge.</span></span>
    
      - <span data-ttu-id="5c2bf-144">**ダイヤルイン (pstn) 会議**   では、電話会議プロバイダーを必要とせずに公衆交換電話網 (pstn) 電話を使用して、ユーザーが Lync Server 2013 会議のオーディオ部分に参加することができます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-144">**Dial-in (PSTN) conferencing**   Allows users to join the audio portion of a Lync Server 2013 conference by using a public switched telephone network (PSTN) phone without requiring an audio conferencing provider.</span></span>
    
      - <span data-ttu-id="5c2bf-145">**エンタープライズ voip**   エンタープライズ voip は、ユーザーが通話を発信および受信できるようにする Lync Server 2013 のボイスオーバー IP (VoIP) ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-145">**Enterprise Voice**   Enterprise Voice is the Voice over IP (VoIP) solution in Lync Server 2013 that allows users to make and receive phone calls.</span></span> <span data-ttu-id="5c2bf-146">音声通話、ボイスメール、およびハードウェアデバイスまたはソフトウェアクライアントを使用するその他の機能に Lync Server 2013 を使用する場合は、この機能を展開します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-146">You would deploy this feature if you plan to use Lync Server 2013 for voice calls, voice mail, and other functions that use a hardware device or a software client.</span></span>
    
      - <span data-ttu-id="5c2bf-147">**通話受付管理 (cac)**   CAC は、使用可能なネットワーク帯域幅に基づいて、音声通話やビデオ通話などのリアルタイム通信セッションを確立できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-147">**Call admission control (CAC)**   CAC determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="5c2bf-148">IM とプレゼンスのみを展開している場合、CAC はどちらの機能でも使用されないので不要です。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-148">If you have deployed only IM and presence, CAC is not needed because neither of these two features uses CAC.</span></span>
    
      - <span data-ttu-id="5c2bf-149">**アーカイブ**   アーカイブでは、Lync Server 2013 を経由して送信される IM コンテンツ、会議 (会議) コンテンツ、またはその両方をアーカイブすることができます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-149">**Archiving**   Archiving provides a way for you to archive IM content, conferencing (meeting) content, or both that is sent through Lync Server 2013.</span></span>
    
      - <span data-ttu-id="5c2bf-150">**監視**   監視サーバーでは、ネットワークとエンドポイント上のメディア品質を示す数値データを収集できます。また、VoIP 通話、IM メッセージ、音声ビデオ会話、ミーティング、アプリケーション共有、およびファイル転送に関連する使用状況の情報、および失敗した通話に関する通話エラーとトラブルシューティングの情報も収集できます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-150">**Monitoring**   Monitoring Server enables you to collect numerical data that describes the media quality on your network and endpoints, usage information related to VoIP calls, IM messages, A/V conversations, meetings, application sharing, and file transfers, and call error and troubleshooting information for failed calls.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5c2bf-p109">展開で CAC を有効にする場合、中央サイトあたり 1 つのプールでのみ CAC を有効にする必要があります。 CAC は、音声機能または音声ビデオ会議を展開している場合に推奨されます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-p109">If you would like to enable CAC in your deployment, it is required that you enable CAC in exactly one pool per central site. CAC is recommended if you are deploying voice features or A/V conferencing.</span></span>

    
    </div>
    
    <span data-ttu-id="5c2bf-p110">次の表に、利用できる機能 (上) とユーザーに提供される機能 (左) を示します。表内の選択は、組織でこれらの機能を有効にするために選択する必要があるものです。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-p110">The following table shows the available features (top) and the functions offered to users (left). The selections in the table are what you should select to enable those features for your organization.</span></span>
    
    
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
    <th><span data-ttu-id="5c2bf-155">会議</span><span class="sxs-lookup"><span data-stu-id="5c2bf-155">Conferencing</span></span></th>
    <th><span data-ttu-id="5c2bf-156">ダイヤルイン会議</span><span class="sxs-lookup"><span data-stu-id="5c2bf-156">Dial-In Conferencing</span></span></th>
    <th><span data-ttu-id="5c2bf-157">用に構成します</span><span class="sxs-lookup"><span data-stu-id="5c2bf-157">Enterprise Voice</span></span></th>
    <th><span data-ttu-id="5c2bf-158">通話受付管理</span><span class="sxs-lookup"><span data-stu-id="5c2bf-158">Call Admission Control</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5c2bf-159">インスタント メッセージングおよびプレゼンス</span><span class="sxs-lookup"><span data-stu-id="5c2bf-159">Instant messaging and presence</span></span></p></td>
    <td><p><span data-ttu-id="5c2bf-160">X</span><span class="sxs-lookup"><span data-stu-id="5c2bf-160">X</span></span></p></td>
    <td></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5c2bf-161">会議</span><span class="sxs-lookup"><span data-stu-id="5c2bf-161">Conferencing</span></span></p></td>
    <td><p><span data-ttu-id="5c2bf-162">X</span><span class="sxs-lookup"><span data-stu-id="5c2bf-162">X</span></span></p></td>
    <td><p><span data-ttu-id="5c2bf-163">X</span><span class="sxs-lookup"><span data-stu-id="5c2bf-163">X</span></span></p></td>
    <td></td>
    <td></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5c2bf-164">音声ビデオ会議</span><span class="sxs-lookup"><span data-stu-id="5c2bf-164">A/V conferencing</span></span></p></td>
    <td><p><span data-ttu-id="5c2bf-165">X</span><span class="sxs-lookup"><span data-stu-id="5c2bf-165">X</span></span></p></td>
    <td><p><span data-ttu-id="5c2bf-166">X</span><span class="sxs-lookup"><span data-stu-id="5c2bf-166">X</span></span></p></td>
    <td></td>
    <td><p><span data-ttu-id="5c2bf-167">X</span><span class="sxs-lookup"><span data-stu-id="5c2bf-167">X</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5c2bf-168">エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="5c2bf-168">Enterprise Voice</span></span></p></td>
    <td></td>
    <td></td>
    <td><p><span data-ttu-id="5c2bf-169">X</span><span class="sxs-lookup"><span data-stu-id="5c2bf-169">X</span></span></p></td>
    <td><p><span data-ttu-id="5c2bf-170">X</span><span class="sxs-lookup"><span data-stu-id="5c2bf-170">X</span></span></p></td>
    </tr>
    </tbody>
    </table>


5.  <span data-ttu-id="5c2bf-171">[併置された**サーバーの役割の選択**] ページで、仲介サーバーをフロントエンドサーバーに併置したり、スタンドアロンサーバーとして展開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-171">On the **Select collocated server roles** page, you can to collocate the Mediation Server on the Front End Server or to deploy it as a stand-alone server.</span></span>
    
    <span data-ttu-id="5c2bf-172">仲介サーバーをフロントエンドプールに併置することができます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-172">You can collocate the Mediation Server on the Front End pool.</span></span>
    
      - <span data-ttu-id="5c2bf-173">仲介サーバーを Enterprise Edition フロントエンドプールに併置する場合は、チェックボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-173">If you intend to collocate the Mediation Server on the Enterprise Edition Front End pool, ensure the check box is selected.</span></span> <span data-ttu-id="5c2bf-174">このサーバーの役割はプール サーバー上に展開されます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-174">The server role will be deployed on the pool servers.</span></span>
    
      - <span data-ttu-id="5c2bf-175">仲介サーバーをスタンドアロンサーバーとして展開する場合は、該当するチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-175">If you intend to deploy the Mediation Server as a stand-alone server, clear the appropriate check box.</span></span> <span data-ttu-id="5c2bf-176">フロントエンドサーバーを完全に展開した後で、仲介サーバーを別の展開手順に展開します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-176">You will deploy Mediation Server in a separate deployment step after you completely deploy the Front End Server.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5c2bf-177">仲介サーバーは、できるだけ併置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-177">We recommend that you collocate the Mediation Server if possible.</span></span> <span data-ttu-id="5c2bf-178">併置された仲介サーバーまたはスタンドアロンの仲介サーバーのサポートの詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Lync server 2013 の仲介サーバーのコンポーネントとトポロジ</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-178">For details about support for collocated or stand-alone Mediation Servers, see <A href="lync-server-2013-components-and-topologies-for-mediation-server.md">Components and topologies for Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

6.  <span data-ttu-id="5c2bf-179">[**サーバーの役割とこのフロントエンドプールの関連付け**] ページでは、サーバーの役割を定義してフロントエンドプールと関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-179">The **Associate server roles with this Front End pool** page lets you define and associate server roles with the Front End pool.</span></span> <span data-ttu-id="5c2bf-180">次の役割が使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-180">The following role is available:</span></span>
    
    <span data-ttu-id="5c2bf-181">**[エッジプール**   を有効にする] 単一のエッジサーバーまたはエッジサーバーのプールを定義して関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-181">**Enable an Edge pool**   Defines and associates a single Edge Server or a pool of Edge Servers.</span></span> <span data-ttu-id="5c2bf-182">エッジサーバーは、組織内のユーザーと組織外の人々 (フェデレーションユーザーを含む) との通信とコラボレーションを容易にします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-182">An Edge Server facilitates communication and collaboration between users inside the organization and people outside the organization, including federated users.</span></span>
    
    <span data-ttu-id="5c2bf-183">次の 2 つの場合にサーバーの役割の展開および関連付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-183">There are two possible scenarios that you can use to deploy and associate the server roles:</span></span>
    
    <span data-ttu-id="5c2bf-p116">1 つ目は、新しいインストールで新しいトポロジを定義する場合です。次のいずれかの方法でインストールができます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-p116">For scenario one, you are defining a new topology for a new installation. You can approach the installation in one of two ways:</span></span>
    
      - <span data-ttu-id="5c2bf-186">チェック ボックスをオフのままにして、トポロジの定義を続行します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-186">Leave the check box clear and proceed with defining the topology.</span></span> <span data-ttu-id="5c2bf-187">フロントエンドおよびバックエンドサーバーの役割を発行、構成、およびテストした後で、トポロジビルダーを再度実行して、役割サーバーをトポロジに追加できます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-187">After you have published, configured, and tested the Front End and Back End Server roles, you can run Topology Builder again to add the role servers to the topology.</span></span> <span data-ttu-id="5c2bf-188">この方法を使用すると、追加の役割による煩雑なことなく、フロントエンドプールと SQL Server を実行しているサーバーをテストできます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-188">This strategy will enable you to test the Front End pool and the server running SQL Server without additional complications from additional roles.</span></span> <span data-ttu-id="5c2bf-189">初期テストを完了したら、もう一度トポロジビルダーを実行して、展開する必要がある役割を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-189">After you have completed your initial testing, you can run Topology Builder again to select the roles you need to deploy.</span></span>
    
      - <span data-ttu-id="5c2bf-190">インストールする必要がある役割を選択し、選択した役割に対応するハードウェアをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-190">Select roles that you need to install, and then set up the hardware to accommodate the selected roles.</span></span>
    
    <span data-ttu-id="5c2bf-191">シナリオ2では、既存の展開があり、インフラストラクチャが新しい役割に対応できる状態になっているか、既存の役割を新しいフロントエンドサーバーに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-191">For scenario two, you have an existing deployment and your infrastructure is ready for new roles or you need to associate existing roles with a new Front End Server:</span></span>
    
      - <span data-ttu-id="5c2bf-192">この場合は、新しいフロントエンドサーバーに展開または関連付ける予定の役割を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-192">In this case, you will select the roles that you intend to deploy or associate with the new Front End Server.</span></span> <span data-ttu-id="5c2bf-193">どちらの場合も、役割の定義を続行して必要なハードウェアを設定し、インストールを進めます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-193">In either case, you will proceed with the definition of the roles, set up any needed hardware, and proceed with the installation.</span></span>

7.  <span data-ttu-id="5c2bf-194">[**SQL ストアの定義**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-194">On the **Define the SQL store** page, do one of the following:</span></span>
    
      - <span data-ttu-id="5c2bf-195">トポロジで既に定義されている既存の SQL Server ストアを使用するには、[**SQL ストア**] でインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-195">To use an existing SQL Server store that has already been defined in your topology, select an instance from **SQL store**.</span></span>
    
      - <span data-ttu-id="5c2bf-196">プール情報を格納する新しい SQL Server インスタンスを定義するには、[**新規**] をクリックし、[**新しい Sql ストアの定義**] ダイアログボックスで**sql server の FQDN**を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-196">To define a new SQL Server instance to store pool information, click **New** and then specify the **SQL Server FQDN**in the **Define New SQL Store** dialog box.</span></span>
    
      - <span data-ttu-id="5c2bf-197">SQL Server インスタンスの名前を指定するには、[**名前付きインスタンス**] を選択し、インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-197">To specify the name of a SQL Server instance, select **Named Instance**, and then specify the name of the instance.</span></span>
    
      - <span data-ttu-id="5c2bf-198">既定のインスタンスを使用するには、[**既定のインスタンス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-198">To use the default instance, click **Default instance**.</span></span>
    
      - <span data-ttu-id="5c2bf-199">SQL ミラーリングを使用するには、[**SQL ミラーリングを有効にする**] を選択し、既存のインスタンスを選択するか、新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-199">To use SQL Mirroring, select **Enable SQL mirroring** and select an existing instance or create a new instance.</span></span>

8.  <span data-ttu-id="5c2bf-200">[**ファイル共有の定義**] ページで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-200">On the **Define the file share** page, do one of the following:</span></span>
    
      - <span data-ttu-id="5c2bf-201">トポロジで既に定義されているファイル共有を使用するには、[**以前に定義したファイル共有を使用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-201">To use a file share that has already been defined in your topology, select **Use a previously defined file share**.</span></span>
    
      - <span data-ttu-id="5c2bf-202">新しいファイル共有を定義するには、[**新しいファイル共有の定義**] を選択し、[**ファイル サーバー FQDN**] ボックスで、ファイル共有が存在する既存のファイル サーバーの FQDN を入力します。そして、[**ファイル共有**] ボックスでファイル共有の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-202">To define a new file share, select **Define a new file share**, in the **File Server FQDN** box, enter the FQDN of the existing file server where the file share is to reside, and then enter a name for the file share in the **File Share** box.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="5c2bf-203">Lync Server 2013 のファイル共有をフロントエンドサーバーに配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-203">The file share for Lync Server 2013 cannot be located on the Front End Server.</span></span> <span data-ttu-id="5c2bf-204">この例では、ファイル共有が SQL Server ベースのバックエンド サーバーに配置されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-204">Note that in this example, the file share has been located on the SQL Server-based Back End Server.</span></span> <span data-ttu-id="5c2bf-205">組織の要件によってはこの場所が最適でない可能性があり、ファイル サーバーのほうが適している場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-205">This might not be an optimal location for your organization’s requirements, and a file server might be a better choice.</span></span> <span data-ttu-id="5c2bf-206">ファイル共有を作成していなくてもファイル共有を定義できます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-206">You can define the file share without the file share having been created.</span></span> <span data-ttu-id="5c2bf-207">トポロジを公開する前に、定義する場所にファイル共有を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-207">You will need to create the file share in the location you define before you publish the topology.</span></span>

    
    </div>

9.  <span data-ttu-id="5c2bf-208">[**Web サービス URL の指定**] ページで、次の 1 つまたは両方の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-208">On the **Specify the Web Services URL** page, do one or both of the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="5c2bf-209">ベース URL は、https:// の部分を除いた URL の Web サービス ID です。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-209">The base URL is the Web Services identity for the URL, minus the https://.</span></span> <span data-ttu-id="5c2bf-210">たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-210">For example, if the full URL for the Web Services of the pool is https://pool01.contoso.net, the base URL is pool01.contoso.net.</span></span>

    
    </div>
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="5c2bf-211">複数のフロントエンドプールまたはフロントエンドサーバーがある場合、外部 Web サービスの FQDN は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-211">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="5c2bf-212">たとえば、フロントエンドサーバーの外部 Web サービスの FQDN を<STRONG>pool01.contoso.com</STRONG>として定義した場合、別のフロントエンドプールまたはフロントエンドサーバーに<STRONG>pool01.contoso.com</STRONG>を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-212">For example, if you define the external Web services FQDN of a Front End Server as <STRONG>pool01.contoso.com</STRONG>, you cannot use <STRONG>pool01.contoso.com</STRONG> for another Front End pool or Front End Server.</span></span>

    
    </div>
    
    1.  <span data-ttu-id="5c2bf-213">DNS 負荷分散を構成している場合は、[内部の**Web サービスプールの fqdn を上書き**する] チェックボックスをオンにし、内部ベース url (プールの fqdn とは異なる必要が\<あります。\>また、 \*\*\*\* 基本 url の場合は、ベース url) を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-213">If you are configuring DNS load balancing, select the **Override internal Web Services pool FQDN** check box, enter the internal base URL (which must be different from the pool FQDN and could be, for example, internal-\<your base URL\>) in **Internal Base URL**.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="5c2bf-214">内部 web サービスを自己定義の FQDN で上書きする場合、各 FQDN は他のフロントエンドプール、ディレクター、またはディレクタープールとは一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-214">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span> <span data-ttu-id="5c2bf-215">Url または完全修飾ドメイン名を定義するときは、<STRONG>標準文字のみ</STRONG>(a ~ z、a ~ z、0 ~ 9、およびハイフン) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-215"><STRONG>Use only standard characters</STRONG> (including A–Z, a–z, 0–9, and hyphens) when defining URLs or fully qualified domain names.</span></span> <span data-ttu-id="5c2bf-216">Unicode 文字およびアンダースコアは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-216">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="5c2bf-217">URL または FQDN の非標準文字は、多くの場合、外部 DNS およびパブリック CAs ではサポートされていません (つまり、証明書のサブジェクト名またはサブジェクトの別名に URL または FQDN を割り当てる必要がある場合)。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-217">Nonstandard characters in a URL or FQDN are often not supported by external DNS and public CAs (that is, when the URL or FQDN must be assigned to the subject name or subject alternative name in the certificate).</span></span>

        
        </div>
    
    2.  <span data-ttu-id="5c2bf-218">必要に応じて **、外部ベース**url に外部ベース url を入力します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-218">Optionally enter the external base URL in **External Base URL**.</span></span> <span data-ttu-id="5c2bf-219">外部ベースの URL を入力して、内部ドメインの名前付けと区別します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-219">You would enter the external base URL to differentiate it from your internal domain naming.</span></span> <span data-ttu-id="5c2bf-220">たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com という場合があります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-220">For example, your internal domain is contoso.net, but your external domain name is contoso.com.</span></span> <span data-ttu-id="5c2bf-221">Contoso.com ドメイン名を使用して URL を定義します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-221">You would define the URL using the contoso.com domain name.</span></span> <span data-ttu-id="5c2bf-222">これはリバースプロキシの場合にも重要です。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-222">This is also important in the case of a reverse proxy.</span></span> <span data-ttu-id="5c2bf-223">外部ベース URL のドメイン名は、リバースプロキシの FQDN のドメイン名と同じになります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-223">The external base URL domain name would be the same as the domain name of the FQDN of the reverse proxy.</span></span> <span data-ttu-id="5c2bf-224">インスタントメッセージングとプレゼンスは、フロントエンドプールへの HTTP アクセスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-224">Instant messaging and presence does require HTTP access to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5c2bf-225">DNS 負荷分散を使用するには、適切な DNS レコードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-225">To use DNS load balancing, you must create the appropriate DNS records.</span></span> <span data-ttu-id="5c2bf-226">詳細については、「 <A href="lync-server-2013-configure-dns-for-load-balancing.md">Lync Server 2013 での負荷分散の DNS の構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-226">For details, see <A href="lync-server-2013-configure-dns-for-load-balancing.md">Configure DNS for load balancing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="5c2bf-227">**[機能の選択**] ページで [**会議**] を選択した場合は、[ **Office web apps サーバーの選択**] ページで、[**プールを office web apps サーバーに関連付ける**] を選択し、[**新規**] をクリックします (または、ドロップダウンリストから既存の Office web apps サーバーを選択します)。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-227">If you selected **Conferencing** on the **Select Features** page, on the **Select an Office Web Apps Server** page select **Associate pool with an Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

11. <span data-ttu-id="5c2bf-228">[**新しい Office Web Apps サーバーの定義**] ダイアログ ボックスで、Office Web Apps サーバー コンピューターの完全修飾ドメイン名 (FQDN) を [**Office Web Apps サーバーの FQDN**] ボックスに入力します。これを行うと、Office Web Apps サーバー検出の URL が [**Office Web Apps サーバー検出の URL**] ボックスに自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-228">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="5c2bf-229">Office Web Apps サーバーがオンプレミスでインストールされており、Lync Server 2013 と同じネットワークゾーンにある場合、オプションの**Office Web Apps サーバーは外部ネットワーク (境界/インターネット) に展開**されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-229">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="5c2bf-230">Office Web Apps サーバーを内部ファイアウォールの外側に展開する場合は、[**Office Web Apps サーバーは外部ネットワークで展開 (境界ネットワークまたはインターネット)**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-230">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5c2bf-231">詳細については、「 <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Office Web Apps Server および Lync Server 2013 との統合の構成</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-231">For details, see <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Configuring integration with Office Web Apps Server and Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="5c2bf-232">[**アーカイブ SQL ストアの定義**] ページで、既存のインスタンスまたは SQL Server を選択するか、アーカイブ データに関連付けられたデータを格納するための新しいインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-232">On the **Define the Archiving SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with archiving data.</span></span>

13. <span data-ttu-id="5c2bf-233">[**監視 SQL ストアの定義**] ページで、既存のインスタンスまたは SQL Server を選択するか、監視データに関連付けられたデータを格納するための新しいインスタンスを定義します。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-233">On the **Define the Monitoring SQL store** page, select an existing instance or SQL Server, or define a new instance to store the data associated with monitoring data.</span></span>

14. <span data-ttu-id="5c2bf-234">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-234">Click **Next**.</span></span> <span data-ttu-id="5c2bf-235">[**サーバーの役割とこのフロントエンドプールの関連付け**] ページで、他の役割サーバーを定義した場合は、別の役割構成ウィザードページが開き、サーバーの役割を構成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-235">If you defined other role servers on the **Associate server roles with this Front End pool** page, separate role configuration wizard pages will open to let you configure the server roles.</span></span> <span data-ttu-id="5c2bf-236">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-236">For details, see the following:</span></span>
    
    [<span data-ttu-id="5c2bf-237">Lync Server 2013 での外部ユーザーアクセスの展開</span><span class="sxs-lookup"><span data-stu-id="5c2bf-237">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)

15. <span data-ttu-id="5c2bf-238">構成および展開する追加のサーバーの役割を選択しなかった場合、または追加の役割サーバーの構成が完了した場合は [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c2bf-238">If you did not select additional server roles to configure and deploy, or when you have finished the configuration of the additional role servers, click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

