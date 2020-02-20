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
ms.openlocfilehash: e63d75bda22228ae14077a51f78150b3884e875f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Lync Server 2013 のコールパークの技術要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

このセクションでは、コールパークの次の技術要件について説明します。

  - ハードウェア要件

  - ソフトウェア要件

  - ポートの要件

  - オーディオ ファイルの要件

<div>

## <a name="hardware-requirements"></a>ハードウェア要件

コールパークアプリケーションには、フロントエンドサーバーと同じハードウェア要件があります。 ハードウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

</div>

<div>

## <a name="software-requirements"></a>ソフトウェア要件

コールパークアプリケーションには、フロントエンドサーバーと同じオペレーティングシステム要件とソフトウェア前提条件があります。 ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

コールパークアプリケーションが展開されているすべてのフロントエンドサーバーおよび Standard Edition サーバーには、windows Server 2008 R2 を実行しているサーバー、または Windows Server 2012 を実行しているサーバー用の Microsoft Media Foundation を実行する Windows Media フォーマットランタイムがインストールされている必要があります。Windows Server 2012 R2。 Windows Server 2008 R2 では、windows Media フォーマットランタイムが windows デスクトップ環境の一部としてインストールされています。 Windows media フォーマットランタイムまたは Microsoft Media Foundation は、コールパークが保留音に対して再生する Windows Media Audio (.wma) ファイルに必要です。

</div>

<div>

## <a name="port-requirements"></a>ポートの要件

コールパークアプリケーションは、次のポートを使用します。

  - **ポート 5075**   SIP リッスン要求に使用されます。

<div>


> [!NOTE]  
> このポートは既定の設定であり、<STRONG>Set-CsApplicationServer</STRONG> コマンドレットを使用して変更できます。 このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>オーディオ ファイルの要件

コールパークアプリケーションは、保留音に対して Windows Media オーディオ (.wma) ファイルのみをサポートします。 保留音のファイルをカスタマイズするには、Microsoft Expression Encoder 4 を使用できます。 Expression Encoder 4 をダウンロードするには、「Expression Encoder 4 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843)」を参照してください。 このツールを使用すると、ファイルを WMA 形式に変換できます。 コール パークの保留音ファイルとしての推奨形式は Media Audio 9、44 kHz、16 ビット、モノラル、CBR、32 kbps です。

<div>


> [!NOTE]  
> 変換されたファイルは、44 kHz で録音された場合でも、電話では 16 kHz でのみ再生されます。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

