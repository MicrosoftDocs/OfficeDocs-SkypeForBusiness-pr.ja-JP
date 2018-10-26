---
title: XMPP フェデレーションの移行
TOCTitle: XMPP フェデレーションの移行
ms:assetid: b8d2b4b9-d0ed-4b48-820a-2c257fbdd2fb
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721861(v=OCS.15)
ms:contentKeyID: 49887117
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# XMPP フェデレーションの移行

 

_**トピックの最終更新日:** 2012-10-19_

以前のバージョンの Lync Server と Office Communications Server は、XMPP (Extensible Messaging and Presence Protocol) ゲートウェイを搭載し、このゲートウェイを独立したサーバーの役割として展開すると、XMPP 展開とのフェデレーションが行えました。 Lync Server 2013 では、XMPP 機能は機能として展開できます。XMPP 機能は 2 箇所にインストールされます。1 つは、 Lync Server 2013 エッジ サーバー上で実行される XMPP プロキシ、もう 1 つは、 Lync Server 2013 フロントエンド サーバー上で実行される XMPP ゲートウェイです。

移行の観点から、 Lync Server ユーザー アカウントを Lync Server 2013 プールに移動し、従来の XMPP ゲートウェイを引き続き使用することができます。これは、XMPP フェデレーション パートナーが Lync Server 2013 で構成されていない場合にのみ可能です。

簡単に説明すると、 Lync Server 2010 が Office Communications Server 2007 R2 XMPP ゲートウェイと一緒に展開されていて、XMPP フェデレーションが従来の Lync Server 2010 ユーザーで有効になっている場合、XMPP フェデレーションを Lync Server 2013 に移行するには、次の手順を実行します。

1.  Lync Server 2013 プールを展開します。

2.  Lync Server 2013 エッジ サーバーを展開します。

3.  すべてのユーザーを Lync Server 2013 プールに移動します。

4.  エッジ サーバーの XMPP アクセス ポリシーおよび証明書を作成します。

5.  Lync Server 2013 で XMPP フェデレーションを有効にします。

6.  Lync Server 2013 XMPP ゲートウェイを参照するように DNS エントリを更新します。

