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

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Lync Server 2013 の応答グループの技術要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

このセクションでは、応答グループアプリケーションの次の技術要件について説明します。

  - ハードウェア要件

  - ソフトウェア要件

  - ポートの要件

  - オーディオ ファイルの要件

  - 応答グループ構成ツールの要件

<div>

## <a name="hardware-requirements"></a>ハードウェア要件

応答グループアプリケーションには、フロントエンドサーバーと同じハードウェア要件があります。 ハードウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

</div>

<div>

## <a name="software-requirements"></a>ソフトウェア要件

応答グループアプリケーションには、オペレーティングシステムの要件と、フロントエンドサーバーとしてのソフトウェア前提条件があります。 ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

応答グループの音楽およびアナウンスに Windows Media オーディオ (.wma) ファイルを使用する場合、応答グループアプリケーションを実行するすべてのフロントエンドサーバーまたは Standard Edition サーバーに windows Media フォーマットランタイムがインストールされている必要があります。Windows Server 2012 または Windows Server 2012 R2 を実行しているサーバーのサーバー 2008 R2 または Microsoft Media Foundation。 Windows Server 2008 R2 では、windows Media フォーマットランタイムが windows デスクトップ環境の一部としてインストールされています。

オーディオ要件の詳細については、このセクション後半の「オーディオ ファイルの要件」を参照してください。

</div>

<div>

## <a name="port-requirements"></a>ポートの要件

応答グループアプリケーションは、次のポートを使用します。

  - **ポート 5071**   SIP リッスン要求に使用

  - **ポート 8404**   がサーバー間通信に使用されます。
    
    <div>
    

    > [!NOTE]  
    > このポートは、一致するサービスに使用され、複数のフロントエンドサーバーを持つプールに応答グループアプリケーションが展開されるときに必要になります。

    
    </div>

<div>


> [!NOTE]  
> これらのポートは既定の設定であり、<STRONG>Set-CsApplicationServer</STRONG> コマンドレットを使用して変更することができます。 このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>オーディオ ファイルの要件

応答グループアプリケーションは、応答グループメッセージ、保留音、または対話型音声応答 (IVR) の質問に対して、wave (.wav) ファイル形式と Windows Media オーディオ (.wma) ファイル形式をサポートしています。

Windows Media オーディオファイル形式では、windows Server 2008 R2 および Windows Server 2008 を実行しているフロントエンドサーバーに Windows Media フォーマットランタイムがインストールされている必要があります。 詳細については、このセクションで前述した「ソフトウェア要件」を参照してください。

<div>

## <a name="supported-wave-file-formats"></a>サポートされる WAVE ファイル形式

すべての WAVE ファイルは、次の要件を満たしている必要があります。

  - 8 ビットまたは 16 ビット ファイル

  - リニア PCM (LPCM)、A-Law、または u-Law 形式

  - モノまたはステレオ

  - 4 MB 以下

WAVE ファイルで最適なパフォーマンスを得るには、16 kHz、モノ、16 ビットの WAVE ファイルをお勧めします。

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>サポートされる Windows Media オーディオ ファイル形式

Windows Media オーディオ ファイルを使用する場合、低いビットレートの使用を検討し、読み込み時のシステム パフォーマンスを検証してください。

Microsoft Expression Encoder 4 を使用して、ファイルを Windows Media オーディオ形式に変換できます。 Expression Encoder 4 をダウンロードするに[https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843)は、「」を参照してください。

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>応答グループ構成ツールの要件

応答グループ構成ツールは、次の表で説明するオペレーティングシステムと web ブラウザーの組み合わせをサポートします。

<div>


> [!NOTE]  
> 32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。 32 ビット版の Internet Explorer がサポートされています。



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>サポートされているオペレーティング システムおよび Web ブラウザー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>オペレーティング システム</th>
<th>Web ブラウザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (ネイティブ モード)</p>
<p>Internet Explorer 9 (ネイティブ モード)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 Service Pack 1</p></td>
<td><p>Internet Explorer 8 (ネイティブ モード)</p>
<p>Internet Explorer 9 (ネイティブ モード)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (ネイティブ モード)</p>
<p>Internet Explorer 9 (ネイティブ モード)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 Service Pack 1</p></td>
<td><p>Internet Explorer 8 (ネイティブ モード)</p>
<p>Internet Explorer 9 (ネイティブ モード)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>応答グループのエージェント コンソール

エージェント コンソールは、次の表に記載されているオペレーティング システムと Web ブラウザーの組み合わせをサポートします。

<div>


> [!NOTE]  
> 32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。32 ビット版の Internet Explorer がサポートされています。



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>サポートされているオペレーティング システムおよび Web ブラウザー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>オペレーティング システム</th>
<th>Web ブラウザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (ネイティブ モード)</p>
<p>Internet Explorer 9 (ネイティブ モード)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 Service Pack 1</p></td>
<td><p>Internet Explorer 8 (ネイティブ モード)</p>
<p>Internet Explorer 9 (ネイティブ モード)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (ネイティブ モード)</p>
<p>Internet Explorer 9 (ネイティブ モード)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 Service Pack 1</p></td>
<td><p>Internet Explorer 8 (ネイティブ モード)</p>
<p>Internet Explorer 9 (ネイティブ モード)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
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

