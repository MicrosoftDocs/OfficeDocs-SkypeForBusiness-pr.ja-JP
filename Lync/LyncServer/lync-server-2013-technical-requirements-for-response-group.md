---
title: 'Lync Server 2013: 応答グループの技術要件'
description: 'Lync Server 2013: 応答グループの技術要件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3125ed8c732960e23970229e99bf5a8487eb96a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550323"
---
# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="7751a-103">Lync Server 2013 の応答グループの技術要件</span><span class="sxs-lookup"><span data-stu-id="7751a-103">Technical requirements for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7751a-104">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="7751a-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="7751a-105">このセクションでは、応答グループアプリケーションの次の技術要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="7751a-105">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="7751a-106">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="7751a-106">Hardware requirements</span></span>

  - <span data-ttu-id="7751a-107">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="7751a-107">Software requirements</span></span>

  - <span data-ttu-id="7751a-108">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="7751a-108">Port requirements</span></span>

  - <span data-ttu-id="7751a-109">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="7751a-109">Audio file requirements</span></span>

  - <span data-ttu-id="7751a-110">応答グループ構成ツールの要件</span><span class="sxs-lookup"><span data-stu-id="7751a-110">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="7751a-111">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="7751a-111">Hardware Requirements</span></span>

<span data-ttu-id="7751a-112">応答グループアプリケーションには、フロントエンドサーバーと同じハードウェア要件があります。</span><span class="sxs-lookup"><span data-stu-id="7751a-112">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="7751a-113">ハードウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7751a-113">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="7751a-114">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="7751a-114">Software Requirements</span></span>

<span data-ttu-id="7751a-115">応答グループアプリケーションには、オペレーティングシステムの要件と、フロントエンドサーバーとしてのソフトウェア前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="7751a-115">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="7751a-116">ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7751a-116">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="7751a-117">応答グループの音楽およびアナウンスに Windows Media オーディオ (.wma) ファイルを使用する場合は、応答グループアプリケーションを実行するすべてのフロントエンドサーバーまたは Standard Edition サーバーに、windows Server 2008 R2 を実行しているサーバー、または windows server 2012 または Windows Server 2012 R2 を実行しているサーバーの Microsoft Media Foundation をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7751a-117">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="7751a-118">Windows Server 2008 R2 では、windows Media フォーマットランタイムが windows デスクトップ環境の一部としてインストールされています。</span><span class="sxs-lookup"><span data-stu-id="7751a-118">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="7751a-119">オーディオ要件の詳細については、このセクション後半の「オーディオ ファイルの要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7751a-119">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="7751a-120">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="7751a-120">Port Requirements</span></span>

<span data-ttu-id="7751a-121">応答グループアプリケーションは、次のポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="7751a-121">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="7751a-122">**ポート 5071**    SIP リッスン要求に使用</span><span class="sxs-lookup"><span data-stu-id="7751a-122">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="7751a-123">**ポート 8404**    サーバー間通信に使用</span><span class="sxs-lookup"><span data-stu-id="7751a-123">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7751a-124">このポートは、一致するサービスに使用され、複数のフロントエンドサーバーを持つプールに応答グループアプリケーションが展開されるときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="7751a-124">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="7751a-125">これらのポートは既定の設定であり、<STRONG>Set-CsApplicationServer</STRONG> コマンドレットを使用して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7751a-125">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="7751a-126">このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7751a-126">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="7751a-127">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="7751a-127">Audio File Requirements</span></span>

<span data-ttu-id="7751a-128">応答グループアプリケーションは、応答グループメッセージ、保留音、または対話型音声応答 (IVR) の質問に対して、wave (.wav) ファイル形式と Windows Media オーディオ (.wma) ファイル形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7751a-128">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="7751a-129">Windows Media オーディオファイル形式では、windows Server 2008 R2 および Windows Server 2008 を実行しているフロントエンドサーバーに Windows Media フォーマットランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7751a-129">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="7751a-130">詳細については、このセクションで前述した「ソフトウェア要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7751a-130">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="7751a-131">サポートされる WAVE ファイル形式</span><span class="sxs-lookup"><span data-stu-id="7751a-131">Supported Wave File Formats</span></span>

<span data-ttu-id="7751a-132">すべての WAVE ファイルは、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7751a-132">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="7751a-133">8 ビットまたは 16 ビット ファイル</span><span class="sxs-lookup"><span data-stu-id="7751a-133">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="7751a-134">リニア PCM (LPCM)、A-Law、または u-Law 形式</span><span class="sxs-lookup"><span data-stu-id="7751a-134">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="7751a-135">モノまたはステレオ</span><span class="sxs-lookup"><span data-stu-id="7751a-135">Mono or stereo</span></span>

  - <span data-ttu-id="7751a-136">4 MB 以下</span><span class="sxs-lookup"><span data-stu-id="7751a-136">4MB or less</span></span>

<span data-ttu-id="7751a-137">WAVE ファイルで最適なパフォーマンスを得るには、16 kHz、モノ、16 ビットの WAVE ファイルをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7751a-137">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="7751a-138">サポートされる Windows Media オーディオ ファイル形式</span><span class="sxs-lookup"><span data-stu-id="7751a-138">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="7751a-139">Windows Media オーディオ ファイルを使用する場合、低いビットレートの使用を検討し、読み込み時のシステム パフォーマンスを検証してください。</span><span class="sxs-lookup"><span data-stu-id="7751a-139">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="7751a-140">Microsoft Expression Encoder 4 を使用して、ファイルを Windows Media オーディオ形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="7751a-140">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="7751a-141">Expression Encoder 4 をダウンロードするには、「」を参照してください [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) 。</span><span class="sxs-lookup"><span data-stu-id="7751a-141">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="7751a-142">応答グループ構成ツールの要件</span><span class="sxs-lookup"><span data-stu-id="7751a-142">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="7751a-143">応答グループ構成ツールは、次の表で説明するオペレーティングシステムと web ブラウザーの組み合わせをサポートします。</span><span class="sxs-lookup"><span data-stu-id="7751a-143">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7751a-p107">32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。 32 ビット版の Internet Explorer がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7751a-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="7751a-146">サポートされているオペレーティング システムおよび Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="7751a-146">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7751a-147">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="7751a-147">Operating system</span></span></th>
<th><span data-ttu-id="7751a-148">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="7751a-148">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7751a-149">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="7751a-149">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="7751a-150">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="7751a-150">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="7751a-151">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-151">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="7751a-152">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-152">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7751a-153">Windows 7</span><span class="sxs-lookup"><span data-stu-id="7751a-153">Windows 7</span></span></p>
<p><span data-ttu-id="7751a-154">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="7751a-154">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="7751a-155">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-155">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="7751a-156">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-156">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7751a-157">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="7751a-157">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="7751a-158">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="7751a-158">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="7751a-159">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-159">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="7751a-160">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-160">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7751a-161">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7751a-161">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="7751a-162">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="7751a-162">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="7751a-163">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-163">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="7751a-164">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-164">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="7751a-165">応答グループのエージェント コンソール</span><span class="sxs-lookup"><span data-stu-id="7751a-165">Response Group Agent Console</span></span>

<span data-ttu-id="7751a-166">エージェント コンソールは、次の表に記載されているオペレーティング システムと Web ブラウザーの組み合わせをサポートします。</span><span class="sxs-lookup"><span data-stu-id="7751a-166">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7751a-p108">32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。32 ビット版の Internet Explorer がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7751a-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="7751a-169">サポートされているオペレーティング システムおよび Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="7751a-169">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7751a-170">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="7751a-170">Operating system</span></span></th>
<th><span data-ttu-id="7751a-171">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="7751a-171">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7751a-172">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="7751a-172">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="7751a-173">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="7751a-173">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="7751a-174">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-174">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="7751a-175">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-175">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7751a-176">Windows 7</span><span class="sxs-lookup"><span data-stu-id="7751a-176">Windows 7</span></span></p>
<p><span data-ttu-id="7751a-177">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="7751a-177">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="7751a-178">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-178">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="7751a-179">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-179">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="7751a-180">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="7751a-180">Firefox 10.0</span></span></p>
<p><span data-ttu-id="7751a-181">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="7751a-181">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7751a-182">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="7751a-182">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="7751a-183">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="7751a-183">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="7751a-184">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-184">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="7751a-185">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-185">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7751a-186">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="7751a-186">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="7751a-187">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="7751a-187">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="7751a-188">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-188">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="7751a-189">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="7751a-189">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="7751a-190">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="7751a-190">Firefox 10.0</span></span></p>
<p><span data-ttu-id="7751a-191">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="7751a-191">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

