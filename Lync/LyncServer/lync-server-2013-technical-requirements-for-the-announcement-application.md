---
title: 'Lync Server 2013: アナウンスアプリケーションの技術要件'
description: 'Lync Server 2013: アナウンスアプリケーションの技術要件。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adc5019408b79301bbcda3993ceb7d96ee4d9b7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550313"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="be2bd-103">Lync Server 2013 のアナウンスアプリケーションの技術要件</span><span class="sxs-lookup"><span data-stu-id="be2bd-103">Technical requirements for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be2bd-104">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="be2bd-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="be2bd-105">このセクションでは、アナウンスアプリケーションの次の技術要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="be2bd-105">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="be2bd-106">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="be2bd-106">Hardware requirements</span></span>

  - <span data-ttu-id="be2bd-107">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="be2bd-107">Software requirements</span></span>

  - <span data-ttu-id="be2bd-108">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="be2bd-108">Port requirements</span></span>

  - <span data-ttu-id="be2bd-109">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="be2bd-109">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="be2bd-110">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="be2bd-110">Hardware Requirements</span></span>

<span data-ttu-id="be2bd-111">アナウンスアプリケーションには、フロントエンドサーバーと同じハードウェア要件があります。</span><span class="sxs-lookup"><span data-stu-id="be2bd-111">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="be2bd-112">ハードウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be2bd-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="be2bd-113">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="be2bd-113">Software Requirements</span></span>

<span data-ttu-id="be2bd-114">アナウンスアプリケーションには、フロントエンドサーバーと同じオペレーティングシステム要件とソフトウェア前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="be2bd-114">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="be2bd-115">ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be2bd-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="be2bd-116">アナウンスアプリケーションを実行するすべてのフロントエンドサーバーまたは Standard Edition サーバーには、windows Server 2008 R2 を実行しているサーバー、または windows server 2012 または Windows Server 2012 R2 を実行しているサーバーの Microsoft Media Foundation という Windows Media Format Runtime がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="be2bd-116">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="be2bd-117">Windows Server 2008 R2 では、windows Media フォーマットランタイムが Windows デスクトップ環境の一部としてインストールされています。</span><span class="sxs-lookup"><span data-stu-id="be2bd-117">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="be2bd-118">Windows media フォーマットランタイムまたは Microsoft Media Foundation は、アナウンスメントアプリケーションがアナウンスおよび音楽用に再生する Windows Media オーディオ (.wma) ファイルに必要です。</span><span class="sxs-lookup"><span data-stu-id="be2bd-118">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="be2bd-119">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="be2bd-119">Port Requirements</span></span>

<span data-ttu-id="be2bd-120">アナウンスメントアプリケーションは、次のポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="be2bd-120">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="be2bd-121">**ポート 5071**    SIP リッスン要求に使用</span><span class="sxs-lookup"><span data-stu-id="be2bd-121">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be2bd-122">このポートは既定の設定であり、<STRONG>Set-CsApplicationServer</STRONG> コマンドレットを使用して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="be2bd-122">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="be2bd-123">このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="be2bd-123">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="be2bd-124">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="be2bd-124">Audio File Requirements</span></span>

<span data-ttu-id="be2bd-125">アナウンスメントアプリケーションは、音楽とアナウンスの Wave (.wav) ファイル形式および Windows Media オーディオ (.wma) ファイル形式をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="be2bd-125">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="be2bd-126">アナウンスメントアプリケーションのオーディオファイルの要件は、応答グループアプリケーションの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="be2bd-126">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="be2bd-127">詳細については、「 [Lync Server 2013 の応答グループの技術要件](lync-server-2013-technical-requirements-for-response-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be2bd-127">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

