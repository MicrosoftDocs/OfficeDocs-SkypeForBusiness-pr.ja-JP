---
title: 'Lync Server 2013: 応答グループの技術要件'
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
ms.openlocfilehash: 8b07ddfa11f23c7e5183c243020c441db7219660
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="49876-102">Lync Server 2013 の応答グループの技術要件</span><span class="sxs-lookup"><span data-stu-id="49876-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49876-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="49876-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="49876-104">このセクションでは、応答グループアプリケーションの次の技術要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="49876-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="49876-105">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="49876-105">Hardware requirements</span></span>

  - <span data-ttu-id="49876-106">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="49876-106">Software requirements</span></span>

  - <span data-ttu-id="49876-107">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="49876-107">Port requirements</span></span>

  - <span data-ttu-id="49876-108">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="49876-108">Audio file requirements</span></span>

  - <span data-ttu-id="49876-109">応答グループ構成ツールの要件</span><span class="sxs-lookup"><span data-stu-id="49876-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="49876-110">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="49876-110">Hardware Requirements</span></span>

<span data-ttu-id="49876-111">応答グループアプリケーションには、フロントエンドサーバーと同じハードウェア要件があります。</span><span class="sxs-lookup"><span data-stu-id="49876-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="49876-112">ハードウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49876-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="49876-113">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="49876-113">Software Requirements</span></span>

<span data-ttu-id="49876-114">応答グループアプリケーションには、オペレーティングシステムの要件と、フロントエンドサーバーとしてのソフトウェア前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="49876-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="49876-115">ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49876-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="49876-116">応答グループの音楽およびアナウンスに Windows Media オーディオ (.wma) ファイルを使用する場合、応答グループアプリケーションを実行するすべてのフロントエンドサーバーまたは Standard Edition サーバーに windows Media フォーマットランタイムがインストールされている必要があります。Windows Server 2012 または Windows Server 2012 R2 を実行しているサーバーのサーバー 2008 R2 または Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="49876-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="49876-117">Windows Server 2008 R2 では、windows Media フォーマットランタイムが windows デスクトップ環境の一部としてインストールされています。</span><span class="sxs-lookup"><span data-stu-id="49876-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="49876-118">オーディオ要件の詳細については、このセクション後半の「オーディオ ファイルの要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49876-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="49876-119">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="49876-119">Port Requirements</span></span>

<span data-ttu-id="49876-120">応答グループアプリケーションは、次のポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="49876-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="49876-121">**ポート 5071**   SIP リッスン要求に使用</span><span class="sxs-lookup"><span data-stu-id="49876-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="49876-122">**ポート 8404**   がサーバー間通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="49876-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="49876-123">このポートは、一致するサービスに使用され、複数のフロントエンドサーバーを持つプールに応答グループアプリケーションが展開されるときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="49876-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="49876-124">これらのポートは既定の設定であり、<STRONG>Set-CsApplicationServer</STRONG> コマンドレットを使用して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="49876-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="49876-125">このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49876-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="49876-126">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="49876-126">Audio File Requirements</span></span>

<span data-ttu-id="49876-127">応答グループアプリケーションは、応答グループメッセージ、保留音、または対話型音声応答 (IVR) の質問に対して、wave (.wav) ファイル形式と Windows Media オーディオ (.wma) ファイル形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="49876-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="49876-128">Windows Media オーディオファイル形式では、windows Server 2008 R2 および Windows Server 2008 を実行しているフロントエンドサーバーに Windows Media フォーマットランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="49876-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="49876-129">詳細については、このセクションで前述した「ソフトウェア要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49876-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="49876-130">サポートされる WAVE ファイル形式</span><span class="sxs-lookup"><span data-stu-id="49876-130">Supported Wave File Formats</span></span>

<span data-ttu-id="49876-131">すべての WAVE ファイルは、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="49876-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="49876-132">8 ビットまたは 16 ビット ファイル</span><span class="sxs-lookup"><span data-stu-id="49876-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="49876-133">リニア PCM (LPCM)、A-Law、または u-Law 形式</span><span class="sxs-lookup"><span data-stu-id="49876-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="49876-134">モノまたはステレオ</span><span class="sxs-lookup"><span data-stu-id="49876-134">Mono or stereo</span></span>

  - <span data-ttu-id="49876-135">4 MB 以下</span><span class="sxs-lookup"><span data-stu-id="49876-135">4MB or less</span></span>

<span data-ttu-id="49876-136">WAVE ファイルで最適なパフォーマンスを得るには、16 kHz、モノ、16 ビットの WAVE ファイルをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="49876-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="49876-137">サポートされる Windows Media オーディオ ファイル形式</span><span class="sxs-lookup"><span data-stu-id="49876-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="49876-138">Windows Media オーディオ ファイルを使用する場合、低いビットレートの使用を検討し、読み込み時のシステム パフォーマンスを検証してください。</span><span class="sxs-lookup"><span data-stu-id="49876-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="49876-139">Microsoft Expression Encoder 4 を使用して、ファイルを Windows Media オーディオ形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="49876-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="49876-140">Expression Encoder 4 をダウンロードするに[https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843)は、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49876-140">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="49876-141">応答グループ構成ツールの要件</span><span class="sxs-lookup"><span data-stu-id="49876-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="49876-142">応答グループ構成ツールは、次の表で説明するオペレーティングシステムと web ブラウザーの組み合わせをサポートします。</span><span class="sxs-lookup"><span data-stu-id="49876-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49876-p107">32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。 32 ビット版の Internet Explorer がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="49876-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="49876-145">サポートされているオペレーティング システムおよび Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="49876-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49876-146">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="49876-146">Operating system</span></span></th>
<th><span data-ttu-id="49876-147">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="49876-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49876-148">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="49876-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="49876-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="49876-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="49876-150">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="49876-151">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49876-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="49876-152">Windows 7</span></span></p>
<p><span data-ttu-id="49876-153">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="49876-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="49876-154">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="49876-155">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49876-156">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="49876-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="49876-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="49876-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="49876-158">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="49876-159">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49876-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="49876-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="49876-161">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="49876-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="49876-162">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="49876-163">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="49876-164">応答グループのエージェント コンソール</span><span class="sxs-lookup"><span data-stu-id="49876-164">Response Group Agent Console</span></span>

<span data-ttu-id="49876-165">エージェント コンソールは、次の表に記載されているオペレーティング システムと Web ブラウザーの組み合わせをサポートします。</span><span class="sxs-lookup"><span data-stu-id="49876-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49876-p108">32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。32 ビット版の Internet Explorer がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="49876-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="49876-168">サポートされているオペレーティング システムおよび Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="49876-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="49876-169">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="49876-169">Operating system</span></span></th>
<th><span data-ttu-id="49876-170">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="49876-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49876-171">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="49876-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="49876-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="49876-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="49876-173">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="49876-174">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49876-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="49876-175">Windows 7</span></span></p>
<p><span data-ttu-id="49876-176">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="49876-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="49876-177">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="49876-178">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="49876-179">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="49876-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="49876-180">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="49876-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49876-181">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="49876-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="49876-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="49876-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="49876-183">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="49876-184">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49876-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="49876-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="49876-186">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="49876-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="49876-187">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="49876-188">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="49876-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="49876-189">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="49876-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="49876-190">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="49876-190">Chrome 18.0</span></span></p></td>
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

