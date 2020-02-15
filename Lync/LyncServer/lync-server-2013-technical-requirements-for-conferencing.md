---
title: Lync Server 2013 会議の技術要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc548446120ae4088d90acb45c258f3f736063d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="6df69-102">Lync Server 2013 での会議の技術要件</span><span class="sxs-lookup"><span data-stu-id="6df69-102">Technical requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6df69-103">_**トピックの最終更新日:** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="6df69-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="6df69-104">Lync Server 2013 の場合、ダイヤルイン会議、音声ビデオ会議、インスタントメッセージング (IM) 会議、および web 会議機能は、常にフロントエンドサーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="6df69-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="6df69-105">ここでは、これらのサーバーのハードウェアおよびソフトウェア要件と、サポートされている併置について詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="6df69-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="6df69-106">ダイヤルイン会議は、さまざまなコンポーネントを含む機能です。</span><span class="sxs-lookup"><span data-stu-id="6df69-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="6df69-107">コンポーネントの中には、ダイヤルイン会議固有のものも、エンタープライズ VoIP コンポーネントもあります。</span><span class="sxs-lookup"><span data-stu-id="6df69-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="6df69-108">ここでは、ダイヤルイン会議に固有のコンポーネントの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="6df69-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="6df69-109">仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイの要件の詳細については、「計画」のドキュメントの「 [lync server 2013 の仲介サーバーコンポーネント](lync-server-2013-mediation-server-component.md)」および「 [lync Server 2013 の仲介サーバーのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-mediation-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df69-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="6df69-110">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="6df69-110">Hardware Requirements</span></span>

<span data-ttu-id="6df69-111">Web 会議と音声ビデオ会議はフロントエンドサーバーと併置されているため、サーバーハードウェア要件はフロントエンドサーバーの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="6df69-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="6df69-112">ハードウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df69-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="6df69-113">ダイヤルイン会議に必要な次のコンポーネントにも、フロントエンドサーバーと同じハードウェア要件があります。</span><span class="sxs-lookup"><span data-stu-id="6df69-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="6df69-114">アプリケーション サービス</span><span class="sxs-lookup"><span data-stu-id="6df69-114">Application service</span></span>

  - <span data-ttu-id="6df69-115">会議アテンダント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6df69-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="6df69-116">会議アナウンス アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6df69-116">Conferencing Announcement application</span></span>

<span data-ttu-id="6df69-117">フロントエンドサーバーのハードウェア要件は、Lync Server 2013 の他の多くのサーバーの役割と同じですが、次の表ではその概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="6df69-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="6df69-118">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="6df69-118">Software Requirements</span></span>

<span data-ttu-id="6df69-119">Web 会議と音声ビデオ会議はフロントエンドサーバーに併置されているため、サーバーソフトウェア要件はフロントエンドサーバーと同じです。</span><span class="sxs-lookup"><span data-stu-id="6df69-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="6df69-120">ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df69-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="6df69-121">Web 会議の場合、Lync Server 2013 には、PowerPoint プレゼンテーションを処理するために、Office Web Apps および Office Web Apps サーバー (旧称 WAC Server) が必要です。</span><span class="sxs-lookup"><span data-stu-id="6df69-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="6df69-122">詳細については、「 [Office Web Apps Server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df69-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="6df69-123">ダイヤルイン会議、アプリケーションサービス、会議アテンダントアプリケーション、および会議アナウンスアプリケーションでは、フロントエンドサーバーと同じオペレーティングシステム要件を使用します。</span><span class="sxs-lookup"><span data-stu-id="6df69-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="6df69-124">ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df69-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="6df69-125">会議アテンダントアプリケーションおよび会議アナウンスアプリケーションでは、フロントエンドサーバーに Windows Media フォーマットランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df69-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="6df69-126">Windows Media フォーマット ランタイムは、保留音、録音済みの名前、および案内で使用される Windows Media オーディオ (WMA) ファイルの再生に必要です。</span><span class="sxs-lookup"><span data-stu-id="6df69-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="6df69-127">Windows Server 2012 および Windows Server 2012 R2 を除き、windows Media フォーマットランタイムは、セットアップを実行するときに Windows デスクトップの機能の一部として自動的にインストールされますが、コンピューターを再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="6df69-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="6df69-128">したがって、セットアップの実行前に、Windows Media フォーマット ランタイムが含まれる Windows デスクトップ エクスペリエンスの一部としてインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6df69-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="6df69-129">Windows Server 2012 および Windows Server 2012 R2 には Microsoft Media Foundation が必要です。</span><span class="sxs-lookup"><span data-stu-id="6df69-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="6df69-130">ダイヤルイン会議のポート要件</span><span class="sxs-lookup"><span data-stu-id="6df69-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="6df69-p107">次の表に、ダイヤルイン会議で使用されるポートを示します。 ロード バランサーを使用する場合は、プールで実行するアプリケーションが使用するポートに合わせてロード バランサーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df69-p107">The following table describes the ports that are used by dial-in conferencing. If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="6df69-133">これらのポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6df69-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="6df69-134">このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df69-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6df69-135">1 つのプール内にある同じアプリケーションのすべてのインスタンスは、同じ SIP リッスン ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="6df69-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="6df69-136">ダイヤルイン会議で使用されるポート</span><span class="sxs-lookup"><span data-stu-id="6df69-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6df69-137">ポート番号</span><span class="sxs-lookup"><span data-stu-id="6df69-137">Port number</span></span></th>
<th><span data-ttu-id="6df69-138">説明</span><span class="sxs-lookup"><span data-stu-id="6df69-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6df69-139">5072</span><span class="sxs-lookup"><span data-stu-id="6df69-139">5072</span></span></p></td>
<td><p><span data-ttu-id="6df69-140">電話会議アテンダントアプリケーションによる SIP リスニング要求の使用</span><span class="sxs-lookup"><span data-stu-id="6df69-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6df69-141">5073</span><span class="sxs-lookup"><span data-stu-id="6df69-141">5073</span></span></p></td>
<td><p><span data-ttu-id="6df69-142">電話会議アナウンスアプリケーションが SIP リスニング要求のために使用</span><span class="sxs-lookup"><span data-stu-id="6df69-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="6df69-143">ダイヤルイン会議でサポートされるクライアント</span><span class="sxs-lookup"><span data-stu-id="6df69-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="6df69-144">次のクライアントを使用して、ダイヤルイン アクセスをサポートする社内会議をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="6df69-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="6df69-145">Lync 2013 用オンラインミーティングアドイン (Lync 2013 または出席者をインストールすると自動的にインストールされます)</span><span class="sxs-lookup"><span data-stu-id="6df69-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="6df69-146">ダイヤルイン会議の設定ページの要件</span><span class="sxs-lookup"><span data-stu-id="6df69-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="6df69-147">[ダイヤルイン会議の設定] ページでは、次の表に記載されているオペレーティングシステムと web ブラウザーの組み合わせをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6df69-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6df69-148">32 ビットおよび 64 ビット版のオペレーティング システムがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6df69-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="6df69-149">サポートされているオペレーティング システムおよび Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="6df69-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6df69-150">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="6df69-150">Operating system</span></span></th>
<th><span data-ttu-id="6df69-151">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="6df69-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6df69-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="6df69-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="6df69-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="6df69-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="6df69-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="6df69-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="6df69-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="6df69-155">Firefox</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6df69-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="6df69-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="6df69-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="6df69-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="6df69-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="6df69-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="6df69-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="6df69-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6df69-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="6df69-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="6df69-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="6df69-161">Firefox</span></span></p>
<p><span data-ttu-id="6df69-162">Safari</span><span class="sxs-lookup"><span data-stu-id="6df69-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="6df69-163">ダイヤルイン会議の音声ファイル要件</span><span class="sxs-lookup"><span data-stu-id="6df69-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="6df69-164">Lync Server 2013 では、ダイヤルイン会議の音声プロンプトおよび音楽のカスタマイズはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6df69-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="6df69-165">ただし、既定のオーディオファイルの変更を必要とする強力なビジネスニーズがある場合は、microsoft サポート技術情報の記事961177、「 [Microsoft Office Communications Server 2007 R2 でダイヤルイン電話会議の音声プロンプトまたは音楽ファイルをカスタマイズする方法](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df69-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="6df69-166">[Microsoft Lync Server 会議アテンダントのカスタム音声ガイダンス](http://go.microsoft.com/fwlink/p/?linkid=396880)管理ユーティリティを使用することもできます。これにより、電話の発信者が Lync 会議にカスタムの音声ガイダンスを参加させるときに使用する既定の音声ガイダンスを置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="6df69-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](http://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="6df69-167">カスタム音声プロンプトは、Lync Server 2010 または Lync Server 2013 (Enterprise または Standard Edition) を実行しているサーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6df69-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="6df69-168">会議アテンダントアプリケーションおよび会議アナウンスアプリケーションには、保留音、録音済みの名前、および音声ガイダンスファイルに関する次の要件があります。</span><span class="sxs-lookup"><span data-stu-id="6df69-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="6df69-169">Windows Media Audio (WMA) ファイル形式</span><span class="sxs-lookup"><span data-stu-id="6df69-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="6df69-170">16 ビット モノラル</span><span class="sxs-lookup"><span data-stu-id="6df69-170">16-bit mono</span></span>

  - <span data-ttu-id="6df69-171">48 Kbps 2-pass CBR (固定ビット レート)</span><span class="sxs-lookup"><span data-stu-id="6df69-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="6df69-172">-24DB の音声レベル</span><span class="sxs-lookup"><span data-stu-id="6df69-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="6df69-173">ダイヤルイン会議のユーザー要件</span><span class="sxs-lookup"><span data-stu-id="6df69-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="6df69-174">ダイヤルイン会議ユーザーは、そのアカウントに固有の電話番号または内線番号を割り当てておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="6df69-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="6df69-175">この要件によりダイヤルイン会議中の認証が可能になります。</span><span class="sxs-lookup"><span data-stu-id="6df69-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="6df69-176">エンタープライズユーザー (つまり、組織内の Active Directory ドメインサービス資格情報と Lync Server アカウントを持つユーザー) は、電話番号 (または内線番号) と個人識別番号 (PIN) を入力して、会議にダイヤルインします。認証されたユーザー。</span><span class="sxs-lookup"><span data-stu-id="6df69-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

