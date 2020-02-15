---
title: 'Lync Server 2013: コールパークの技術要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff91e6b458d4c86f2246cff19e72e5221728e774
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="62f34-102">Lync Server 2013 のコールパークの技術要件</span><span class="sxs-lookup"><span data-stu-id="62f34-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62f34-103">_**トピックの最終更新日:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="62f34-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="62f34-104">このセクションでは、コールパークの次の技術要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="62f34-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="62f34-105">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="62f34-105">Hardware requirements</span></span>

  - <span data-ttu-id="62f34-106">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="62f34-106">Software requirements</span></span>

  - <span data-ttu-id="62f34-107">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="62f34-107">Port requirements</span></span>

  - <span data-ttu-id="62f34-108">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="62f34-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="62f34-109">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="62f34-109">Hardware Requirements</span></span>

<span data-ttu-id="62f34-110">コールパークアプリケーションには、フロントエンドサーバーと同じハードウェア要件があります。</span><span class="sxs-lookup"><span data-stu-id="62f34-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="62f34-111">ハードウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62f34-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="62f34-112">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="62f34-112">Software Requirements</span></span>

<span data-ttu-id="62f34-113">コールパークアプリケーションには、フロントエンドサーバーと同じオペレーティングシステム要件とソフトウェア前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="62f34-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="62f34-114">ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62f34-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="62f34-115">コールパークアプリケーションが展開されているすべてのフロントエンドサーバーおよび Standard Edition サーバーには、windows Server 2008 R2 を実行しているサーバー、または Windows Server 2012 を実行しているサーバー用の Microsoft Media Foundation を実行する Windows Media フォーマットランタイムがインストールされている必要があります。Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="62f34-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="62f34-116">Windows Server 2008 R2 では、windows Media フォーマットランタイムが windows デスクトップ環境の一部としてインストールされています。</span><span class="sxs-lookup"><span data-stu-id="62f34-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="62f34-117">Windows media フォーマットランタイムまたは Microsoft Media Foundation は、コールパークが保留音に対して再生する Windows Media Audio (.wma) ファイルに必要です。</span><span class="sxs-lookup"><span data-stu-id="62f34-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="62f34-118">ポートの要件</span><span class="sxs-lookup"><span data-stu-id="62f34-118">Port Requirements</span></span>

<span data-ttu-id="62f34-119">コールパークアプリケーションは、次のポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="62f34-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="62f34-120">**ポート 5075**   SIP リッスン要求に使用されます。</span><span class="sxs-lookup"><span data-stu-id="62f34-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62f34-121">このポートは既定の設定であり、<STRONG>Set-CsApplicationServer</STRONG> コマンドレットを使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="62f34-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="62f34-122">このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="62f34-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="62f34-123">オーディオ ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="62f34-123">Audio File Requirements</span></span>

<span data-ttu-id="62f34-124">コールパークアプリケーションは、保留音に対して Windows Media オーディオ (.wma) ファイルのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="62f34-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="62f34-125">保留音のファイルをカスタマイズするには、Microsoft Expression Encoder 4 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="62f34-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="62f34-126">Expression Encoder 4 をダウンロードするには、「Expression Encoder 4 [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62f34-126">To download Expression Encoder 4, see "Expression Encoder 4" at [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="62f34-127">このツールを使用すると、ファイルを WMA 形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="62f34-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="62f34-128">コール パークの保留音ファイルとしての推奨形式は Media Audio 9、44 kHz、16 ビット、モノラル、CBR、32 kbps です。</span><span class="sxs-lookup"><span data-stu-id="62f34-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="62f34-129">変換されたファイルは、44 kHz で録音された場合でも、電話では 16 kHz でのみ再生されます。</span><span class="sxs-lookup"><span data-stu-id="62f34-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

