---
title: "Lync Server 2013: XMPP フェデレーションの計画"
TOCTitle: "Lync Server 2013: XMPP フェデレーションの計画"
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48272921
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での XMPP (Extensible Messaging and Presence Protocol) フェデレーションの計画

 

_**トピックの最終更新日:** 2012-10-22_

以前のバージョンの Lync Server と Office Communications Server は、XMPP (Extensible Messaging and Presence Protocol) ゲートウェイを搭載し、このゲートウェイを独立したサーバーの役割として展開すると、XMPP 展開とのフェデレーションが行えました。Microsoft Lync Server 2013 では、XMPP 機能は機能として展開できます。XMPP 機能は 2 箇所にインストールされます。1 つは、エッジ サーバー上で実行される XMPP プロキシ、もう 1 つは、フロント エンド サーバー上で実行される XMPP ゲートウェイです。

XMPP の展開と構成については、「[Lync Server 2013 での外部ユーザー アクセスの展開](lync-server-2013-deploying-external-user-access.md)」に記載されています。組織で XMPP のサポートを計画するには、ファイアウォールにポートとプロトコルの規則を定義し、証明書を構成して、DNS レコードを追加します。このセクションの以降のトピックに、展開の XMPP フェデレーションを適切に計画するのに必要な情報をまとめます。


> [!IMPORTANT]
> Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。



## このセクション中

  - [証明書の概要 - XMPP (Extensible Messaging and Presence Protocol) フェデレーション](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [ポートの概要 - XMPP (Extensible Messaging and Presence Protocol) フェデレーション](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [DNS の概要 - XMPP (Extensible Messaging and Presence Protocol) フェデレーション](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

## 関連項目

#### タスク

[Lync Server 2013 XMPP フェデレーションのセットアップ](lync-server-2013-setting-up-xmpp-federation.md)  
[Lync Server 2013 での XMPP フェデレーション ユーザー アクセスを制御するポリシーの構成](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  

#### その他のリソース

[Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsXmppAllowedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppAllowedPartner)  
[Get-CsXmppGatewayConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppGatewayConfiguration)

