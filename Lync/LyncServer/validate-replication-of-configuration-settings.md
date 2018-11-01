---
title: 会議設定のレプリケーションを確認する
TOCTitle: 会議設定のレプリケーションを確認する
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48272686
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会議設定のレプリケーションを確認する

 

_**トピックの最終更新日:** 2012-10-19_

中央管理ストアが存在する内部コンピューター (または、Lync Server 2013 コア コンポーネントがインストールされた任意のドメイン参加コンピューター) で、Lync Server 2013 の **Get-CsManagementStoreReplicationStatus** コマンドレットを実行すると、エッジ サーバーへの構成情報のレプリケーションを検証できます。

最初の結果では、レプリケーションに関する状態が "True" ではなく "False" と示される場合があります。その場合は、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、レプリケーションが完了するのを待ってから、もう一度 **Get-CsManagementStoreReplicationStatus** コマンドレットを実行してください。

