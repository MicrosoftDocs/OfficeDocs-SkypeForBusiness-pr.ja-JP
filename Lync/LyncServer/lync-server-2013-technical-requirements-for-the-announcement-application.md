---
title: 'Lync Server 2013: アナウンス アプリケーションの技術要件'
TOCTitle: アナウンス アプリケーションの技術要件
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48274146
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のアナウンス アプリケーションの技術要件

 

_**トピックの最終更新日:** 2013-11-07_

ここでは、アナウンス アプリケーション の次の技術要件について説明します。

  - ハードウェア要件

  - ソフトウェア要件

  - ポート要件   

  - オーディオ ファイルの要件

## ハードウェア要件

アナウンス アプリケーションのハードウェア要件は フロント エンド サーバーと同じです。ハードウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013　用のサーバー ハードウェア プラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

## ソフトウェア要件

アナウンス アプリケーションのオペレーティング システムの要件とソフトウェアの前提は フロント エンド サーバーと同じです。ソフトウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

アナウンス アプリケーションを実行するすべての フロント エンド サーバーまたは Standard Edition サーバーでは、Windows Server 2008 R2 を実行するサーバーで Windows Media フォーマット ランタイムをインストールしている必要があり、Windows Server 2012 または Windows Server 2012 R2 を実行するサーバーで Microsoft Media Foundation をインストールしている必要があります。Windows Server 2008 R2 では、Windows Media フォーマット ランタイムは Windows デスクトップ エクスペリエンスの一部としてインストールされています。アナウンス アプリケーションがアナウンスや音楽として再生する Windows Media オーディオ (.wma) ファイルでは、Windows Media フォーマット ランタイムまたは Microsoft Media Foundation が必要です。

## ポートの要件

アナウンス アプリケーション は次のポートを使用します。

  - **ポート 5071**   SIP リッスン要求のために使用

> [!NOTE]
> このポートは既定の設定であり、<strong>Set-CsApplicationServer</strong> コマンドレットを使用して変更することができます。このコマンドレットの詳細については、「Lync Server 管理シェル」のドキュメントを参照してください。


## オーディオ ファイルの要件

アナウンス アプリケーションは、音楽とアナウンスのために Wave (.wav) ファイル形式と Windows Media オーディオ (.wma) ファイルをサポートしています。アナウンス アプリケーションのオーディオ ファイルの要件は 応答グループ アプリケーションと同じです。詳細は、「[Lync Server 2013 の応答グループの技術要件](lync-server-2013-technical-requirements-for-response-group.md)」を参照してください。

