---
title: 'Lync Server 2013: コール パークの技術要件'
TOCTitle: コール パークの技術要件
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48271787
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のコール パークの技術要件

 

_**トピックの最終更新日:** 2016-12-08_

このセクションでは、コール パークの以下の技術要件について説明します。

  - ハードウェア要件

  - ソフトウェア要件

  - ポート要件   

  - オーディオ ファイルの要件

## ハードウェア要件

コール パーク アプリケーションのハードウェア要件は フロント エンド サーバーと同じです。ハードウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013　用のサーバー ハードウェア プラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

## ソフトウェア要件

コール パーク アプリケーションのオペレーティング システムの要件とソフトウェアの前提は フロント エンド サーバーと同じです。ソフトウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

コール パーク アプリケーションが展開されるすべての フロント エンド サーバーと Standard Edition サーバーでは、Windows Server 2008 R2 を実行中のサーバーに Windows Media フォーマット ランタイムがインストールされているか、Windows Server 2012 または Windows Server 2012 R2 を実行中のサーバーに Microsoft Media Foundation がインストールされている必要があります。 Windows Server 2008 R2 では、Windows Media フォーマット ランタイムが Windows デスクトップ エクスペリエンスの一部としてインストールされます。Windows Media フォーマット ランタイムまたは Microsoft Media Foundation は、保留中に コール パークが流す曲用の Windows Media オーディオ (.wma) ファイルで必要です。

## ポートの要件

コール パーク アプリケーション は次のポートを使用します。

  - **ポート 5075**   SIP リッスン要求に使用します。

> [!NOTE]
> このポートは既定の設定であり、<strong>Set-CsApplicationServer</strong> コマンドレットを使用して変更できます。このコマンドレットの詳細については、「Lync Server 管理シェル」のドキュメントを参照してください。


## オーディオ ファイルの要件

コール パーク アプリケーションでは、保留音として Windows Media Audio (.wma) ファイルのみがサポートされています。保留音のファイルをカスタマイズするには、Microsoft Expression Encoder 4 を使用できます。Expression Encoder 4 のダウンロードについては、[http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843) の "Expression Encoder 4" を参照してください。このツールを使用すると、ファイルを WMA 形式に変換できます。コール パークの保留音ファイルとしての推奨形式は Media Audio 9、44 kHz、16 ビット、モノラル、CBR、32 kbps です。

> [!NOTE]
> 変換されたファイルは、44 kHz で録音された場合でも、電話では 16 kHz でのみ再生されます。

