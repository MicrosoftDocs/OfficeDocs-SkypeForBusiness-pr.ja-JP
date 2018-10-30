---
title: 仲介サーバーの移行
TOCTitle: 仲介サーバーの移行
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48273287
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 仲介サーバーの移行

 

_**トピックの最終更新日:** 2012-09-28_

仲介サーバーは、マージ ウィザードの実行時に Lync Server 2013 のパイロット トポロジにマージされます。ただし、すべてのユーザーの移行後に Lync Server 2013 仲介サーバーの構成を行います。これは、Office Communications Server 2007 R2 プールが Lync Server 2013 仲介サーバーと通信できないからです。サイド バイ サイド移行では、Lync Server 2013 プールが Office Communications Server 2007 R2 仲介サーバーと通信します。

Lync Server 2013 仲介サーバーを構成すると、Office Communications Server 2007 R2 ゲートウェイのアップグレードまたは置き換えも必要になります。Office Communications Server 2007 R2 ゲートウェイは、Lync Server 2013 仲介サーバーをサポートしていません。Lync Server 2013 向けの認定ゲートウェイを展開し、Lync Server 2013 仲介サーバーに関連付ける必要があります。Office Communications Server 2007 R2 展開を完全に廃止するには、このステップが必要です。

このセクションのトピックでは、Lync Server 2013 仲介サーバーの移行を完了した後で行う必要がある構成タスクについて説明します。併置された仲介サーバーからスタンドアロンの仲介サーバーへの移行は、オプションのタスクです。

  - [仲介サーバーを構成する](configure-mediation-server.md)

  - [新しい Lync Server 2013 仲介サーバーを使用するようにボイス ルートを変更する](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [併置された仲介サーバーをスタンドアロンの仲介サーバーに移行する (省略可能)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

