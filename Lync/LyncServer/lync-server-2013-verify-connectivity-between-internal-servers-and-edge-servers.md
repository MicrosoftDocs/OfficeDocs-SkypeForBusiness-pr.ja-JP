---
title: 'Lync Server 2013: 内部サーバーとエッジ サーバーの間の接続の検証'
TOCTitle: 内部サーバーとエッジ サーバーの間の接続の検証
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48271487
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での内部サーバーとエッジ サーバーの間の接続の検証

 

_**トピックの最終更新日:** 2012-09-08_

Lync Server 2013 では、エッジ サーバーと内部サーバーの間の接続を検証するために、検証ウィザードが別途用意されていました。Lync Server 2013 では、エッジ サーバーをインストールすると接続の検証が自動的に行われます。

中央管理ストアが存在する内部コンピューター (または、Lync Server 2013 コア コンポーネント (OcsCore.msi) がインストールされた任意のドメイン結合コンピューター) で、Windows PowerShell**Get-CsManagementStoreReplicationStatus** コマンドレットを実行することで、エッジ サーバーへの構成情報のレプリケーションを検証できます。最初の結果では、レプリケーションの状態が "True" ではなく "False" と表示される場合があります。その場合は、**Invoke-CsManagementStoreReplication** コマンドレットを実行し、レプリケーションが完了するまでしばらく時間を置いてから、再び **Get-CsManagementStoreReplicationStatus** コマンドレットを実行します。

リモート ユーザー接続の確認のための Office Communications Server リモート接続アナライザーの利用も含め、外部ユーザー接続を別々に確認することができます。詳細については、「[Lync Server 2013 での外部ユーザーの接続の確認](lync-server-2013-verify-connectivity-for-external-users.md)」を参照してください。

