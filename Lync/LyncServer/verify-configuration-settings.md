---
title: 構成設定の確認
TOCTitle: 構成設定の確認
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48272093
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 構成設定の確認

 

_**トピックの最終更新日:** 2012-09-06_

中央管理ストアが存在する内部コンピューター、または Lync Server 2013 コア コンポーネント (OcsCore.msi) がインストールされた、ドメインに参加している任意のコンピューターで Lync Server 2013 の **Get-CsManagementStoreReplicationStatus** コマンドレットを実行することで、エッジ サーバーへの構成情報のレプリケーションを検証できます。

最初のうちは、結果でレプリケーションが "True" ではなく "False" の状態であると表示される場合があります。その場合、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、時間をおいて、レプリケーションが完了してから再び **Get-CsManagementStoreReplicationStatus** コマンドレットを実行してください。

