---
title: 'Lync Server 2013: アナウンス アプリケーションの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec0da862ce2032f5a659c9e9b7bd3b437349a3cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="81f8a-102">Lync Server 2013 のアナウンス アプリケーションの技術要件</span><span class="sxs-lookup"><span data-stu-id="81f8a-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81f8a-103">_**最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="81f8a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="81f8a-104">このセクションでは、アナウンスメントアプリケーションの次の技術上の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="81f8a-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="81f8a-105">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="81f8a-105">Hardware requirements</span></span>

  - <span data-ttu-id="81f8a-106">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="81f8a-106">Software requirements</span></span>

  - <span data-ttu-id="81f8a-107">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="81f8a-107">Port requirements</span></span>

  - <span data-ttu-id="81f8a-108">オーディオファイルの要件</span><span class="sxs-lookup"><span data-stu-id="81f8a-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="81f8a-109">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="81f8a-109">Hardware Requirements</span></span>

<span data-ttu-id="81f8a-110">アナウンスメントアプリケーションには、フロントエンドサーバーと同じハードウェア要件があります。</span><span class="sxs-lookup"><span data-stu-id="81f8a-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="81f8a-111">ハードウェア要件の詳細については、サポートドキュメントの「[サーバーハードウェアプラットフォーム (Lync server 2013 の場合](lync-server-2013-server-hardware-platforms.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81f8a-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="81f8a-112">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="81f8a-112">Software Requirements</span></span>

<span data-ttu-id="81f8a-113">アナウンスメントアプリケーションには、フロントエンドサーバーと同じオペレーティングシステム要件とソフトウェアの前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="81f8a-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="81f8a-114">ソフトウェア要件の詳細については、サポートドキュメントの「 [Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81f8a-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="81f8a-115">アナウンスメントアプリケーションを実行するすべてのフロントエンドサーバーまたは標準エディションのサーバーは、windows server 2008 R2 を実行しているサーバー、または Windows Server 2012 を実行しているサーバーの Microsoft メディアファンデーションに Windows Media Format ランタイムをインストールする必要があります。Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="81f8a-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="81f8a-116">Windows Server 2008 R2 の場合、windows Media 形式ランタイムは Windows デスクトップエクスペリエンスの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="81f8a-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="81f8a-117">Windows media Format Runtime または Microsoft メディアファンデーションは、アナウンスメントアプリケーションがお知らせや音楽を再生するために Windows Media オーディオ (.wma) ファイルを使用する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="81f8a-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="81f8a-118">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="81f8a-118">Port Requirements</span></span>

<span data-ttu-id="81f8a-119">アナウンスメントアプリケーションでは、次のポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="81f8a-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="81f8a-120">\*\*\*\*   SIP リスニング要求に使用されるポート5071</span><span class="sxs-lookup"><span data-stu-id="81f8a-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81f8a-121">このポートは既定の設定であり、<STRONG>Set-CsApplicationServer</STRONG> コマンドレットを使用して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="81f8a-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="81f8a-122">このコマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81f8a-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="81f8a-123">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="81f8a-123">Audio File Requirements</span></span>

<span data-ttu-id="81f8a-124">アナウンスメントアプリケーションは、音楽とお知らせのウェーブ (.wav) ファイル形式と Windows Media オーディオ (.wma) ファイル形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="81f8a-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="81f8a-125">アナウンスメントアプリケーションのオーディオファイルの要件は、応答グループアプリケーションの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="81f8a-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="81f8a-126">詳細については、「 [Lync Server 2013 の応答グループの技術要件](lync-server-2013-technical-requirements-for-response-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81f8a-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

