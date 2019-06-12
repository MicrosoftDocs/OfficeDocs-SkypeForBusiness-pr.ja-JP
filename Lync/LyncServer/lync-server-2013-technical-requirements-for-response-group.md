---
title: 'Lync Server 2013: 応答グループの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd87cb270d527753d9c6404ded4162791b542f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="76d75-102">Lync Server 2013 の応答グループの技術要件</span><span class="sxs-lookup"><span data-stu-id="76d75-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76d75-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="76d75-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="76d75-104">このセクションでは、応答グループアプリケーションの次の技術上の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="76d75-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="76d75-105">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="76d75-105">Hardware requirements</span></span>

  - <span data-ttu-id="76d75-106">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="76d75-106">Software requirements</span></span>

  - <span data-ttu-id="76d75-107">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="76d75-107">Port requirements</span></span>

  - <span data-ttu-id="76d75-108">オーディオファイルの要件</span><span class="sxs-lookup"><span data-stu-id="76d75-108">Audio file requirements</span></span>

  - <span data-ttu-id="76d75-109">応答グループ構成ツールの要件</span><span class="sxs-lookup"><span data-stu-id="76d75-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="76d75-110">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="76d75-110">Hardware Requirements</span></span>

<span data-ttu-id="76d75-111">応答グループアプリケーションには、フロントエンドサーバーと同じハードウェア要件があります。</span><span class="sxs-lookup"><span data-stu-id="76d75-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="76d75-112">ハードウェア要件の詳細については、サポートドキュメントの「[サーバーハードウェアプラットフォーム (Lync server 2013 の場合](lync-server-2013-server-hardware-platforms.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76d75-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="76d75-113">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="76d75-113">Software Requirements</span></span>

<span data-ttu-id="76d75-114">応答グループアプリケーションには、フロントエンドサーバーと同じオペレーティングシステム要件とソフトウェアの前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="76d75-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="76d75-115">ソフトウェア要件の詳細については、サポートドキュメントの「 [Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76d75-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="76d75-116">応答グループの音楽とお知らせに Windows Media Audio (.wma) ファイルを使用している場合は、Windows を実行しているサーバーに対して、応答グループアプリケーションを実行するすべてのフロントエンドサーバーまたは標準エディションのサーバーに Windows Media Format ランタイムがインストールされている必要があります。Windows Server 2012 または Windows Server 2012 R2 を実行しているサーバーのサーバー 2008 R2 または Microsoft メディアファンデーション。</span><span class="sxs-lookup"><span data-stu-id="76d75-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="76d75-117">Windows Server 2008 R2 の場合、windows Media Format Runtime は Windows デスクトップエクスペリエンスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="76d75-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="76d75-118">オーディオ要件の詳細については、このセクションで後述する「オーディオファイルの要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76d75-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="76d75-119">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="76d75-119">Port Requirements</span></span>

<span data-ttu-id="76d75-120">応答グループのアプリケーションでは、次のポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="76d75-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="76d75-121">\*\*\*\*   SIP リスニング要求に使用されるポート5071</span><span class="sxs-lookup"><span data-stu-id="76d75-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="76d75-122">\*\*\*\*   サーバー間通信に使用されるポート8404</span><span class="sxs-lookup"><span data-stu-id="76d75-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="76d75-123">このポートは、対戦を行うサービスに使用され、複数のフロントエンドサーバーを持つプールに応答グループアプリケーションを展開するときに必要です。</span><span class="sxs-lookup"><span data-stu-id="76d75-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="76d75-124">これらのポートは既定の設定であり、<STRONG>Set-CsApplicationServer</STRONG> コマンドレットを使用して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="76d75-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="76d75-125">このコマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76d75-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="76d75-126">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="76d75-126">Audio File Requirements</span></span>

<span data-ttu-id="76d75-127">応答グループのアプリケーションでは、wave (.wav) ファイル形式と Windows Media audio (.wma) ファイル形式がサポートされており、応答グループメッセージ、保留中の音楽、またはインタラクティブな音声応答 (IVR) の質問がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="76d75-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="76d75-128">Windows Media オーディオファイル形式では、windows Server 2008 R2 と Windows Server 2008 を実行しているフロントエンドサーバーに Windows Media Format ランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="76d75-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="76d75-129">詳細については、このセクションで前述した「ソフトウェア要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76d75-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="76d75-130">サポートされる WAVE ファイル形式</span><span class="sxs-lookup"><span data-stu-id="76d75-130">Supported Wave File Formats</span></span>

<span data-ttu-id="76d75-131">すべての WAVE ファイルは、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="76d75-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="76d75-132">8 ビットまたは 16 ビット ファイル</span><span class="sxs-lookup"><span data-stu-id="76d75-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="76d75-133">リニア PCM (LPCM)、A-Law、または u-Law 形式</span><span class="sxs-lookup"><span data-stu-id="76d75-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="76d75-134">モノまたはステレオ</span><span class="sxs-lookup"><span data-stu-id="76d75-134">Mono or stereo</span></span>

  - <span data-ttu-id="76d75-135">4 MB 以下</span><span class="sxs-lookup"><span data-stu-id="76d75-135">4MB or less</span></span>

<span data-ttu-id="76d75-136">WAVE ファイルで最適なパフォーマンスを得るには、16 kHz、モノ、16 ビットの WAVE ファイルをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="76d75-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="76d75-137">サポートされる Windows Media オーディオ ファイル形式</span><span class="sxs-lookup"><span data-stu-id="76d75-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="76d75-138">Windows Media オーディオ ファイルを使用する場合、低いビットレートの使用を検討し、読み込み時のシステム パフォーマンスを検証してください。</span><span class="sxs-lookup"><span data-stu-id="76d75-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="76d75-139">Microsoft Expression Encoder 4 を使用して、ファイルを Windows Media オーディオ形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="76d75-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="76d75-140">式エンコーダー4をダウンロードするに[http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)は、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76d75-140">To download Expression Encoder 4, see [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="76d75-141">応答グループ構成ツールの要件</span><span class="sxs-lookup"><span data-stu-id="76d75-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="76d75-142">応答グループ構成ツールでは、次の表に示すオペレーティングシステムと web ブラウザーの組み合わせがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="76d75-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76d75-p107">32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。32 ビット版の Internet Explorer がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="76d75-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="76d75-145">サポートされているオペレーティング システムおよび Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="76d75-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76d75-146">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="76d75-146">Operating system</span></span></th>
<th><span data-ttu-id="76d75-147">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="76d75-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76d75-148">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="76d75-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="76d75-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="76d75-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="76d75-150">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="76d75-151">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76d75-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="76d75-152">Windows 7</span></span></p>
<p><span data-ttu-id="76d75-153">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="76d75-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="76d75-154">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="76d75-155">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76d75-156">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="76d75-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="76d75-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="76d75-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="76d75-158">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="76d75-159">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76d75-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="76d75-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="76d75-161">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="76d75-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="76d75-162">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="76d75-163">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="76d75-164">応答グループのエージェント コンソール</span><span class="sxs-lookup"><span data-stu-id="76d75-164">Response Group Agent Console</span></span>

<span data-ttu-id="76d75-165">エージェント コンソールは、次の表に記載されているオペレーティング システムと Web ブラウザーの組み合わせをサポートします。</span><span class="sxs-lookup"><span data-stu-id="76d75-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76d75-p108">32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。32 ビット版の Internet Explorer がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="76d75-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="76d75-168">サポートされているオペレーティング システムおよび Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="76d75-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76d75-169">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="76d75-169">Operating system</span></span></th>
<th><span data-ttu-id="76d75-170">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="76d75-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76d75-171">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="76d75-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="76d75-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="76d75-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="76d75-173">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="76d75-174">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76d75-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="76d75-175">Windows 7</span></span></p>
<p><span data-ttu-id="76d75-176">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="76d75-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="76d75-177">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="76d75-178">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="76d75-179">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="76d75-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="76d75-180">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="76d75-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76d75-181">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="76d75-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="76d75-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="76d75-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="76d75-183">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="76d75-184">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76d75-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="76d75-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="76d75-186">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="76d75-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="76d75-187">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="76d75-188">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="76d75-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="76d75-189">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="76d75-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="76d75-190">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="76d75-190">Chrome 18.0</span></span></p></td>
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

