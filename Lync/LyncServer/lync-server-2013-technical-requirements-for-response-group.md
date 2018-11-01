---
title: 'Lync Server 2013: 応答グループの技術要件'
TOCTitle: 応答グループの技術要件
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48271962
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の応答グループの技術要件

 

_**トピックの最終更新日:** 2016-12-08_

ここでは、応答グループ アプリケーション の次の技術要件について説明します。

  - ハードウェア要件

  - ソフトウェア要件

  - ポート要件   

  - オーディオ ファイルの要件

  - 応答グループ構成ツールの要件

## ハードウェア要件

応答グループ アプリケーションのハードウェア要件は フロント エンド サーバーと同じです。ハードウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013　用のサーバー ハードウェア プラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

## ソフトウェア要件

応答グループ アプリケーションのオペレーティング システムの要件とソフトウェアの前提は フロント エンド サーバーと同じです。ソフトウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

応答グループの音楽およびアナウンスに Windows Media オーディオ (.wma) ファイルを使用する場合は、応答グループ アプリケーションを実行するすべての フロント エンド サーバーまたは Standard Editions サーバーに Windows Media フォーマット ランタイム (Windows Server 2008 R2 を実行するサーバーの場合) または Microsoft Media Foundation (Windows Server 2012 または Windows Server 2012 R2 を実行するサーバーの場合) がインストールされている必要があります。 Windows Server 2008 R2 では、Windows Media フォーマット ランタイムが Windows デスクトップ エクスペリエンスの一部としてインストールされます。

オーディオ要件の詳細については、このセクション後半の「オーディオ ファイルの要件」を参照してください。

## ポートの要件

応答グループ アプリケーションは、次のポートを使用します。

  - **ポート 5071**   SIP リッスン要求のために使用

  - **ポート 8404**   サーバー間通信に使用
    
    > [!NOTE]
    > このポートはマッチ メイキング サービスに使用され、1 つ以上の フロント エンド サーバーを持つプールに 応答グループ アプリケーションが展開される時に必要になります。


> [!NOTE]
> これらのポートは既定の設定であり、<strong>Set-CsApplicationServer</strong> コマンドレットを使用して変更することができます。このコマンドレットの詳細については、「Lync Server 管理シェル」のドキュメントを参照してください。


## オーディオ ファイルの要件

応答グループ アプリケーションでは、応答グループのメッセージ、保留音、対話型音声応答 (IVR) の質問に、WAVE (.wav) ファイル形式および Windows Media オーディオ (.wma) ファイル形式を使用できます。

Windows Media オーディオ ファイル形式を使用するには、Windows Server 2008 R2 と Windows Server 2008 を実行している フロント エンド サーバーに Windows Media フォーマット ランタイムがインストールされている必要があります。詳細については、このセクションで前述した「ソフトウェア要件」を参照してください。

## サポートされる WAVE ファイル形式

すべての WAVE ファイルは、次の要件を満たしている必要があります。

  - 8 ビットまたは 16 ビット ファイル

  - リニア PCM (LPCM)、A-Law、または u-Law 形式

  - モノまたはステレオ

  - 4 MB 以下

WAVE ファイルで最適なパフォーマンスを得るには、16 kHz、モノ、16 ビットの WAVE ファイルをお勧めします。

## サポートされる Windows Media オーディオ ファイル形式

Windows Media オーディオ ファイルを使用する場合、低いビットレートの使用を検討し、読み込み時のシステム パフォーマンスを検証してください。

Microsoft Expression Encoder 4 を使用して、ファイルを Windows Media オーディオ形式に変換できます。Expression Encoder 4 のダウンロードについては、[http://go.microsoft.com/fwlink/?linkid=202843\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=202843%26clcid=0x411) を参照してください。

## 応答グループ構成ツールの要件

応答グループ構成ツールは、次の表に記載されているオペレーティング システムと Web ブラウザーの組み合わせをサポートします。

> [!NOTE]
> 32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。32 ビット版の Internet Explorer がサポートされています。


### サポートされているオペレーティング システムおよび Web ブラウザー

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
<td><p></p>
<p></p>
<p></p>
<p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 Service Pack 1</p></td>
<td><p>Internet Explorer 8 (ネイティブ モード)</p>
<p>Internet Explorer 9 (ネイティブ モード)</p></td>
</tr>
</tbody>
</table>


## 応答グループのエージェント コンソール

エージェント コンソールは、次の表に記載されているオペレーティング システムと Web ブラウザーの組み合わせをサポートします。

> [!NOTE]
> 32 ビット版または 64 ビット版のオペレーティング システムがサポートされています。32 ビット版の Internet Explorer がサポートされています。


### サポートされているオペレーティング システムおよび Web ブラウザー

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
<td><p></p></td>
<td></td>
</tr>
</tbody>
</table>

