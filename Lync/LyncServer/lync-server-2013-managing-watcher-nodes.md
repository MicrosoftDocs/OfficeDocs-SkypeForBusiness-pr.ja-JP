---
title: 監視ノードの管理
TOCTitle: 監視ノードの管理
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49886982
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 監視ノードの管理

 

_**トピックの最終更新日:** 2012-10-20_

監視ノードで実行される代理トランザクションの変更に加え、管理者は **Set-CsWatcherNodeConfiguration** コマンドレットを使用して、監視ノードを有効化または無効化すること、およびテストの実行時に内部 URL または外部 URL を使用するように監視ノードを構成すること、という 2 つの重要なタスクも実行できます。

既定では、監視ノードは、すべての有効な代理トランザクションを定期的に実行するように設計されています。ただし、これらのトランザクションの中断が必要な場合があります。たとえば、監視ノードを一時的にネットワークから切り離す場合は、代理トランザクションを実行する理由がありません。ネットワーク接続がなければ、これらのトランザクションは必ず失敗します。監視ノードを一時的に無効にする場合は、Lync Server 管理シェルから次のようなコマンドを実行します。

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

このコマンドは、監視ノード atl-watcher- 001.litwareinc.com での代理トランザクションの実行を無効にします。代理トランザクションの実行を再開するには、Enabled プロパティを True ($True) に戻します。

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

> [!NOTE]  
> Enabled プロパティを使用して監視ノードをオンまたはオフにできます。監視ノードを完全に削除する場合は、<strong>Remove-CsWatcherNodeConfiguration</strong> コマンドレットを使用します。<br />
> Remove-CsWatcherNodeConfiguration –Identity &quot;atl-watcher-001.litwareinc.com&quot;<br />
> このコマンドは、指定されたコンピューターからすべての監視ノード構成設定を削除します。これにより、代理トランザクションの自動的な実行が停止します。ただし、このコマンドは、System Center エージェント ファイルまたは Lync Server 2013 システム ファイルをアンインストールしません。

既定では、監視ノードは、テストを実行するときに組織の外部 URL を使用します。ただし、監視ノードは、組織の内部 URL を使用するように構成することもできます。これにより、管理者は、境界ネットワーク内に配置されたユーザーの URL アクセスを検証できます。監視ノードを外部 URL ではなく内部 URL を使用するように構成するには、UseInternalWebUrls プロパティを True ($True) に設定します。

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

このプロパティを既定値である False ($False) にリセットすると、監視ノードは外部 URL を使用します。

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

