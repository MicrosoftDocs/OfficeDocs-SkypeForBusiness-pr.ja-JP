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
ms.openlocfilehash: dab3e57101efa2dd6dff1996a8f61eefc5d75021
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="47cb8-102">Lync Server 2013 の応答グループの技術要件</span><span class="sxs-lookup"><span data-stu-id="47cb8-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47cb8-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="47cb8-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="47cb8-104">このセクションでは、応答グループアプリケーションの次の技術要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="47cb8-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="47cb8-105">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="47cb8-105">Hardware requirements</span></span>

  - <span data-ttu-id="47cb8-106">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="47cb8-106">Software requirements</span></span>

  - <span data-ttu-id="47cb8-107">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="47cb8-107">Port requirements</span></span>

  - <span data-ttu-id="47cb8-108">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="47cb8-108">Audio file requirements</span></span>

  - <span data-ttu-id="47cb8-109">応答グループ構成ツールの要件</span><span class="sxs-lookup"><span data-stu-id="47cb8-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="47cb8-110">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="47cb8-110">Hardware Requirements</span></span>

<span data-ttu-id="47cb8-111">応答グループアプリケーションには、フロントエンドサーバーと同じハードウェア要件があります。</span><span class="sxs-lookup"><span data-stu-id="47cb8-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="47cb8-112">ハードウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47cb8-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="47cb8-113">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="47cb8-113">Software Requirements</span></span>

<span data-ttu-id="47cb8-114">応答グループアプリケーションには、オペレーティングシステムの要件と、フロントエンドサーバーとしてのソフトウェア前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="47cb8-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="47cb8-115">ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47cb8-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="47cb8-116">応答グループの音楽およびアナウンスに Windows Media オーディオ (.wma) ファイルを使用する場合、応答グループアプリケーションを実行するすべてのフロントエンドサーバーまたは Standard Edition サーバーに windows Media フォーマットランタイムがインストールされている必要があります。Windows Server 2012 または Windows Server 2012 R2 を実行しているサーバーのサーバー 2008 R2 または Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="47cb8-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="47cb8-117">Windows Server 2008 R2 では、windows Media フォーマットランタイムが windows デスクトップ環境の一部としてインストールされています。</span><span class="sxs-lookup"><span data-stu-id="47cb8-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="47cb8-118">オーディオ要件の詳細については、このセクション後半の「オーディオ ファイルの要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47cb8-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="47cb8-119">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="47cb8-119">Port Requirements</span></span>

<span data-ttu-id="47cb8-120">応答グループアプリケーションは、次のポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="47cb8-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="47cb8-121">**ポート 5071**   SIP リッスン要求に使用</span><span class="sxs-lookup"><span data-stu-id="47cb8-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="47cb8-122">**ポート 8404**   がサーバー間通信に使用されます。</span><span class="sxs-lookup"><span data-stu-id="47cb8-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="47cb8-123">このポートは、一致するサービスに使用され、複数のフロントエンドサーバーを持つプールに応答グループアプリケーションが展開されるときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="47cb8-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="47cb8-124">これらのポートは既定の設定であり、<STRONG>Set-CsApplicationServer</STRONG> コマンドレットを使用して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="47cb8-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="47cb8-125">このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="47cb8-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="47cb8-126">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="47cb8-126">Audio File Requirements</span></span>

<span data-ttu-id="47cb8-127">応答グループアプリケーションは、応答グループメッセージ、保留音、または対話型音声応答 (IVR) の質問に対して、wave (.wav) ファイル形式と Windows Media オーディオ (.wma) ファイル形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="47cb8-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="47cb8-128">Windows Media オーディオファイル形式では、windows Server 2008 R2 および Windows Server 2008 を実行しているフロントエンドサーバーに Windows Media フォーマットランタイムがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="47cb8-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="47cb8-129">詳細については、このセクションで前述した「ソフトウェア要件」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47cb8-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="47cb8-130">サポートされる WAVE ファイル形式</span><span class="sxs-lookup"><span data-stu-id="47cb8-130">Supported Wave File Formats</span></span>

<span data-ttu-id="47cb8-131">すべての WAVE ファイルは、次の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="47cb8-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="47cb8-132">8 ビットまたは 16 ビット ファイル</span><span class="sxs-lookup"><span data-stu-id="47cb8-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="47cb8-133">リニア PCM (LPCM)、A-Law、または u-Law 形式</span><span class="sxs-lookup"><span data-stu-id="47cb8-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="47cb8-134">モノまたはステレオ</span><span class="sxs-lookup"><span data-stu-id="47cb8-134">Mono or stereo</span></span>

  - <span data-ttu-id="47cb8-135">4 MB 以下</span><span class="sxs-lookup"><span data-stu-id="47cb8-135">4MB or less</span></span>

<span data-ttu-id="47cb8-136">WAVE ファイルで最適なパフォーマンスを得るには、16 kHz、モノ、16 ビットの WAVE ファイルをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="47cb8-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="47cb8-137">サポートされる Windows Media オーディオ ファイル形式</span><span class="sxs-lookup"><span data-stu-id="47cb8-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="47cb8-138">Windows Media オーディオ ファイルを使用する場合、低いビットレートの使用を検討し、読み込み時のシステム パフォーマンスを検証してください。</span><span class="sxs-lookup"><span data-stu-id="47cb8-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="47cb8-139">Microsoft Expression Encoder 4 を使用して、ファイルを Windows Media オーディオ形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="47cb8-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="47cb8-140">Expression Encoder 4 をダウンロードするに[https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843)は、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47cb8-140">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="47cb8-141">応答グループ構成ツールの要件</span><span class="sxs-lookup"><span data-stu-id="47cb8-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="47cb8-142">応答グループ構成ツールは、次の表で説明するオペレーティングシステムと web ブラウザーの組み合わせをサポートします。</span><span class="sxs-lookup"><span data-stu-id="47cb8-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47cb8-p107">32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。 32 ビット版の Internet Explorer がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="47cb8-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="47cb8-145">サポートされているオペレーティング システムおよび Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="47cb8-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47cb8-146">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="47cb8-146">Operating system</span></span></th>
<th><span data-ttu-id="47cb8-147">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="47cb8-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47cb8-148">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="47cb8-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="47cb8-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="47cb8-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="47cb8-150">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="47cb8-151">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47cb8-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="47cb8-152">Windows 7</span></span></p>
<p><span data-ttu-id="47cb8-153">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="47cb8-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="47cb8-154">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="47cb8-155">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47cb8-156">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="47cb8-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="47cb8-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="47cb8-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="47cb8-158">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="47cb8-159">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47cb8-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="47cb8-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="47cb8-161">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="47cb8-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="47cb8-162">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="47cb8-163">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="47cb8-164">応答グループのエージェント コンソール</span><span class="sxs-lookup"><span data-stu-id="47cb8-164">Response Group Agent Console</span></span>

<span data-ttu-id="47cb8-165">エージェント コンソールは、次の表に記載されているオペレーティング システムと Web ブラウザーの組み合わせをサポートします。</span><span class="sxs-lookup"><span data-stu-id="47cb8-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47cb8-p108">32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。32 ビット版の Internet Explorer がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="47cb8-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="47cb8-168">サポートされているオペレーティング システムおよび Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="47cb8-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47cb8-169">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="47cb8-169">Operating system</span></span></th>
<th><span data-ttu-id="47cb8-170">Web ブラウザー</span><span class="sxs-lookup"><span data-stu-id="47cb8-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47cb8-171">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="47cb8-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="47cb8-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="47cb8-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="47cb8-173">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="47cb8-174">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47cb8-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="47cb8-175">Windows 7</span></span></p>
<p><span data-ttu-id="47cb8-176">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="47cb8-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="47cb8-177">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="47cb8-178">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="47cb8-179">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="47cb8-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="47cb8-180">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="47cb8-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47cb8-181">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="47cb8-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="47cb8-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="47cb8-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="47cb8-183">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="47cb8-184">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47cb8-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="47cb8-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="47cb8-186">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="47cb8-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="47cb8-187">Internet Explorer 8 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="47cb8-188">Internet Explorer 9 (ネイティブ モード)</span><span class="sxs-lookup"><span data-stu-id="47cb8-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="47cb8-189">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="47cb8-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="47cb8-190">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="47cb8-190">Chrome 18.0</span></span></p></td>
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

