---
title: 'Lync Server 2013: 外部ユーザー アクセスの展開'
TOCTitle: 外部ユーザー アクセスの展開
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48273722
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での外部ユーザー アクセスの展開

 

_**トピックの最終更新日:** 2013-09-23_

Microsoft Lync Server 2013 のエッジ コンポーネントを展開すると、組織の内部ネットワークにログインしていない外部ユーザー (認証されたリモート ユーザーおよび匿名のリモート ユーザー、フェデレーション パートナー (XMPP パートナーを含みます)、モバイル クライアント、パブリック インスタント メッセージング (IM) サービスのユーザーなど) でも、 Lync Server を使用して組織内の他のユーザーと通信できます。 Lync Server 2013 の展開および構成のプロセスは、 Lync Server 2010 とそれほど異なってはいません。インストールと管理のためのツールは、 Lync Server 2010 とほとんど同じです。


> [!IMPORTANT]
> Microsoft Lync Server 2013エッジ サーバーのインストールと構成は、計画に長い時間がかかり、セキュリティ、ネットワーク、ファイアウォール、ドメイン ネーム システム (DNS)、負荷分散、公開キー基盤 (PKI) などの内部チームとの調整が必要な、複雑なプロセスになる場合があります。外部アクセス コンポーネントを展開する前に、提供されている計画プロセスおよびドキュメントを検討して使用することを強くお勧めします。これにより、展開プロセスの過程で、予期しない変更および問題の数や頻度を抑えることができます。外部ユーザー アクセスの計画については、「<A href="lync-server-2013-planning-for-external-user-access.md">Lync Server 2013 の外部ユーザー アクセスの計画</A>」を参照してください。



## このセクション中

  - [Lync Server 2013 の外部ユーザー アクセスの展開チェックリスト](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [Lync Server 2013 の外部ユーザー アクセス コンポーネントのシステム要件](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013 の境界ネットワークへのサーバーのインストールの準備](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [Lync Server 2013 でのエッジおよびディレクターのトポロジの作成](lync-server-2013-building-an-edge-and-director-topology.md)

  - [Lync Server 2013 でのディレクターの設定](lync-server-2013-setting-up-the-director.md) (省略可能)

  - [Lync Server 2013 でのエッジ サーバーの設定](lync-server-2013-setting-up-edge-servers.md)

  - [Lync Server 2013 のリバース プロキシ サーバーの設定](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [Lync Server 2013 での外部ユーザー アクセスのサポートの構成](lync-server-2013-configuring-support-for-external-user-access.md)

  - [Lync Server 2013 での Lync と Skype の接続のプロビジョニング ガイド](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [Lync Server 2013 での SIP フェデレーション、XMPP フェデレーションおよびパブリック インスタント メッセージングの構成](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [Lync Server 2013 でのモビリティの展開](lync-server-2013-deploying-mobility.md)

  - [Lync Server 2013 でのエッジの展開の検証](lync-server-2013-verifying-your-edge-deployment.md)

