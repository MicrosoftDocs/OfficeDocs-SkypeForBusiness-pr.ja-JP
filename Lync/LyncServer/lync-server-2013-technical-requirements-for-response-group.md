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

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Lync Server 2013 の応答グループの技術要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-07_

このセクションでは、応答グループアプリケーションの次の技術上の要件について説明します。

  - ハードウェア要件

  - ソフトウェア要件

  - ポートの要件

  - オーディオファイルの要件

  - 応答グループ構成ツールの要件

<div>

## <a name="hardware-requirements"></a>ハードウェア要件

応答グループアプリケーションには、フロントエンドサーバーと同じハードウェア要件があります。 ハードウェア要件の詳細については、サポートドキュメントの「[サーバーハードウェアプラットフォーム (Lync server 2013 の場合](lync-server-2013-server-hardware-platforms.md))」を参照してください。

</div>

<div>

## <a name="software-requirements"></a>ソフトウェア要件

応答グループアプリケーションには、フロントエンドサーバーと同じオペレーティングシステム要件とソフトウェアの前提条件があります。 ソフトウェア要件の詳細については、サポートドキュメントの「 [Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

応答グループの音楽とお知らせに Windows Media Audio (.wma) ファイルを使用している場合は、Windows を実行しているサーバーに対して、応答グループアプリケーションを実行するすべてのフロントエンドサーバーまたは標準エディションのサーバーに Windows Media Format ランタイムがインストールされている必要があります。Windows Server 2012 または Windows Server 2012 R2 を実行しているサーバーのサーバー 2008 R2 または Microsoft メディアファンデーション。 Windows Server 2008 R2 の場合、windows Media Format Runtime は Windows デスクトップエクスペリエンスの一部としてインストールされます。

オーディオ要件の詳細については、このセクションで後述する「オーディオファイルの要件」を参照してください。

</div>

<div>

## <a name="port-requirements"></a>ポートの要件

応答グループのアプリケーションでは、次のポートが使用されます。

  - ****   SIP リスニング要求に使用されるポート5071

  - ****   サーバー間通信に使用されるポート8404
    
    <div>
    

    > [!NOTE]  
    > このポートは、対戦を行うサービスに使用され、複数のフロントエンドサーバーを持つプールに応答グループアプリケーションを展開するときに必要です。

    
    </div>

<div>


> [!NOTE]  
> これらのポートは既定の設定であり、<STRONG>Set-CsApplicationServer</STRONG> コマンドレットを使用して変更することができます。 このコマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>オーディオ ファイルの要件

応答グループのアプリケーションでは、wave (.wav) ファイル形式と Windows Media audio (.wma) ファイル形式がサポートされており、応答グループメッセージ、保留中の音楽、またはインタラクティブな音声応答 (IVR) の質問がサポートされています。

Windows Media オーディオファイル形式では、windows Server 2008 R2 と Windows Server 2008 を実行しているフロントエンドサーバーに Windows Media Format ランタイムがインストールされている必要があります。 詳細については、このセクションで前述した「ソフトウェア要件」を参照してください。

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

Microsoft Expression Encoder 4 を使用して、ファイルを Windows Media オーディオ形式に変換できます。 式エンコーダー4をダウンロードするに[http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)は、を参照してください。

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>応答グループ構成ツールの要件

応答グループ構成ツールでは、次の表に示すオペレーティングシステムと web ブラウザーの組み合わせがサポートされます。

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
<p>Internet Explorer 9 (ネイティブ モード)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (ネイティブ モード)</p>
<p>Internet Explorer 9 (ネイティブ モード)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
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
<td><p>Windows Server 2008 R2</p>
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

