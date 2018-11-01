---
title: 'Lync Server 2013: Lync VDI プラグインの展開'
TOCTitle: Lync VDI プラグインの展開
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48271309
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Lync VDI プラグインの展開

 

_**トピックの最終更新日:** 2012-10-03_

Lync 2013 クライアントは仮想デスクトップ インフラストラクチャ (VDI) 環境で音声とビデオをサポートします。ユーザーは音声またはビデオ デバイス (ヘッドセット、カメラなど) をローカル コンピューター (シン クライアント、異なる目的に再使用されたコンピューターなど) に接続できます。ユーザーは、仮想マシンに接続し、仮想マシンで動作している Lync 2013 クライアントにサインインして、あたかもローカルでクライアントが実行されているように、リアルタイムの音声およびビデオの会話に参加できます。

Lync VDI プラグインは、ローカル コンピューターにインストールされ、仮想マシン上で動作している Lync 2013 クライアントでローカルの音声およびビデオ デバイスを使用できるようにするスタンドアロン アプリケーションです。このプラグインを使用するには、Lync がローカル コンピューターにインストールされている必要はありません。仮想マシン上で動作している Lync 2013 クライアントにユーザーがサインインすると、ローカル コンピューター上で動作している Lync VDI プラグインと接続を確立するための資格情報の再入力を求めるメッセージが Lync によって表示されます。この接続が確立されると、ユーザーは音声通話とビデオ通話の受発信を実行できます。

## このセクション中

  - [Lync Server 2013 の Lync VDI プラグインの前提条件](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [VDI の Lync Server 2013 使用環境の準備](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [仮想マシン上の Lync 2013 へのサインインと使用](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [Lync Server 2013 での Lync VDI プラグインのトラブルシューティング](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [Lync Server 2013 でサポートされる仮想化テクノロジと既知の制限](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

