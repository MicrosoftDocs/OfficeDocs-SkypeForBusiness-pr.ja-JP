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
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Lync Server 2013 のアナウンスアプリケーションの技術要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

このセクションでは、アナウンスアプリケーションの次の技術要件について説明します。

  - ハードウェア要件

  - ソフトウェア要件

  - ポートの要件

  - オーディオ ファイルの要件

<div>

## <a name="hardware-requirements"></a>ハードウェア要件

アナウンスアプリケーションには、フロントエンドサーバーと同じハードウェア要件があります。 ハードウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md) 」を参照してください。

</div>

<div>

## <a name="software-requirements"></a>ソフトウェア要件

アナウンスアプリケーションには、フロントエンドサーバーと同じオペレーティングシステム要件とソフトウェア前提条件があります。 ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md) 」を参照してください。

アナウンスアプリケーションを実行するすべてのフロントエンドサーバーまたは Standard Edition サーバーには、windows Server 2008 R2 を実行しているサーバー、または windows server 2012 または Windows Server 2012 R2 を実行しているサーバーの Microsoft Media Foundation という Windows Media Format Runtime がインストールされている必要があります。 Windows Server 2008 R2 では、windows Media フォーマットランタイムが Windows デスクトップ環境の一部としてインストールされています。 Windows media フォーマットランタイムまたは Microsoft Media Foundation は、アナウンスメントアプリケーションがアナウンスおよび音楽用に再生する Windows Media オーディオ (.wma) ファイルに必要です。

</div>

<div>

## <a name="port-requirements"></a>ポートの要件

アナウンスメントアプリケーションは、次のポートを使用します。

  - **ポート 5071**    SIP リッスン要求に使用

<div>


> [!NOTE]  
> このポートは既定の設定であり、<STRONG>Set-CsApplicationServer</STRONG> コマンドレットを使用して変更することができます。 このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>オーディオ ファイルの要件

アナウンスメントアプリケーションは、音楽とアナウンスの Wave (.wav) ファイル形式および Windows Media オーディオ (.wma) ファイル形式をサポートしています。 アナウンスメントアプリケーションのオーディオファイルの要件は、応答グループアプリケーションの場合と同じです。 詳細については、「 [Lync Server 2013 の応答グループの技術要件](lync-server-2013-technical-requirements-for-response-group.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

