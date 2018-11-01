---
title: 標準移行シナリオ - 概要
TOCTitle: 標準移行シナリオ - 概要
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48274008
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 標準移行シナリオ - 概要

 

_**トピックの最終更新日:** 2013-01-30_

Lync Server 2010、グループ チャットまたは Office Communications Server 2007 R2グループ チャットを Lync Server 2013常設チャット サーバー に移行するときは、次の項目を出発点として使用してください。標準の Lync Server 2013 移行パスは次のとおりです。

  - 組織が Lync Server 2010、グループ チャットまたは Office Communications Server 2007 R2グループ チャットを以前に展開しており、 Lync Server 2013常設チャット サーバーを展開する必要があります。

  - Lync Server 2013 を展開してから、 常設チャット サーバー プールを展開します。

  - 常設チャット ルームの移行を準備および計画し、移行のためにシステムをシャットダウンする適切な時間を決定します。

  - 移行のために Windows PowerShell コマンドレッド (**Export-CsPersistentChatData** および **Import-CsPersistentChatData**) を実行し、コンテンツを常設チャット サーバーに移動します。

  - 移行が成功したことを確認します。

  - 従来の展開を使用停止にします。

  - 従来のクライアントが Lync Server 2013常設チャット サーバー に接続できるように 常設チャット サーバー を構成します。新しいクライアントの展開には時間がかかるので、従来のクライアントのユーザーがチャット ルームに可能な限り早急にアクセスできるようにするには、この操作が必要になります。

  - 従来の グループ チャット (クライアント) を使用しているユーザーがチャット ルームにアクセスできることを引き続き保証しながら、新しいクライアントを展開します。

