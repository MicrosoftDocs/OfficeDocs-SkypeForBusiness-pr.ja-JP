---
title: 'Lync Server 2013: XMPP フェデレーションに使用するエッジ プールのフェールオーバー'
TOCTitle: XMPP フェデレーションに使用するエッジ プールのフェールオーバー
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49886966
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での、XMPP フェデレーションに使用するエッジ プールのフェールオーバー

 

_**トピックの最終更新日:** 2012-10-19_

組織内に XMPP フェデレーションに使用するプールとして指定されたエッジ プールが 1 つあるとします。このプールがダウンした場合、XMPP フェデレーションを再び機能させるには、XMPP フェデレーションをフェールオーバーして別のエッジ プールを使用する必要があります。

エッジ プールを初めてインストールし、XMPP フェデレーションを有効にするときに、1 つのエッジ プールではなく、すべてのエッジ プールで XMPP フェデレーションの外部 DNS SRV レコードを設定することで障害復旧プロセスを簡素化できます。これらの SRV レコードには、それぞれ異なる優先順位が設定されている必要があります。すべての XMPP フェデレーション トラフィックは、優先順位が最も高い SRV レコードを使用してプールを通過します。XMPP フェデレーションの有効化と設定の詳細については、「[Lync Server 2013 XMPP フェデレーションのセットアップ](lync-server-2013-setting-up-xmpp-federation.md)」を参照してください。

次の手順では、EdgePool1 は XMPP フェデレーションをホストしていた元のプールを表し、EdgePool2 は XMPP フェデレーションをこれからホストするプールを表します。

## XMPP フェデレーションに使用するエッジ プールのフェールオーバー

1.  (現在ダウンしているエッジ プール以外の) 別のエッジ プールをまだ展開していない場合は、そのプールを展開します。詳細については、「[Lync Server 2013 での外部ユーザー アクセスの展開](lync-server-2013-deploying-external-user-access.md)」を参照してください。

2.  XMPP フェデレーションをホストする新しいエッジ プール (EdgePool2) の各エッジ サーバーで、次のコマンドレットを実行します。
    
        Stop-CsWindowsService

3.  XMPP フェデレーション ルートを変更して EdgePool2 を指すようにするには、次のコマンドレットを実行します。
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    この例で、Site2 は XMPP フェデレーション ルートをこれからホストするエッジ プールを含むサイトを表します。また、EdgeServer2.contoso.com はそのプール内のエッジ サーバーの FQDN です。

4.  外部 DNS サーバーで、XMPP フェデレーション用の DNS A レコードが EdgeServer2.contoso.com を指すように変更します。

5.  XMPP フェデレーションをホストするようになるエッジ プールに解決される、XMPP フェデレーション用の DNS SRV レコードがまだない場合は、以下の例のようにそれを追加する必要があります。この SRV レコードはポート値が 5269 である必要があります。
    
        _xmpp-server._tcp.contoso.com

6.  XMPP フェデレーションをホストするようになるエッジ プールがポート 5269 を外部にオープンしていることを確認します。

7.  XMPP フェデレーションをホストする新しいエッジ プール内のすべてのエッジ サーバーでサービスを開始します。
    
        Start-CsWindowsService

