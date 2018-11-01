---
title: ドメイン ネーム システム (DNS) の要件
TOCTitle: ドメイン ネーム システム (DNS) の要件
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48272185
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ドメイン ネーム システム (DNS) の要件

 

_**トピックの最終更新日:** 2012-06-18_

Lync Server を展開するには、クライアントとサーバーの検出を可能にするドメイン ネーム システム (DNS) レコードを作成する必要があります。また、組織で必要な場合は、自動クライアント サインインもサポートする必要があります。

Lync Server では、DNS が次の方法で使用されます。

  - サーバー間通信用の内部のサーバーまたはプールを検出する。

  - クライアントによる、さまざまな SIP トランザクションに使用されるフロント エンド プールまたは Standard Edition サーバーの検出を許可する。

  - ログインされていない統合コミュニケーション (UC) デバイスによる、デバイス更新 Web サービスを実行しているフロント エンド プールまたは Standard Edition サーバーの検出、更新プログラムの取得、およびログの送信を許可する。

  - 外部のサーバーおよびクライアントによる、インスタント メッセージング (IM) または会議用のエッジ サーバーまたは HTTP リバース プロキシへの接続を許可する。

  - 外部の UC デバイスによる、エッジ サーバーまたは HTTP リバース プロキシを介したデバイス更新 Web サービスへの接続、および更新プログラムの取得を許可する。

  - モバイル クライアントによる、ユーザーがデバイスの設定で URL を手動で入力する必要がない、Web サービス リソースの自動検出を許可する。

## このセクション中

  - [Lync Server 2013 の DNS の要件を確認する](lync-server-2013-determine-dns-requirements.md)

  - [フロントエンド プールの DNS 要件](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Standard Edition サーバーの DNS 要件](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Lync Server 2013 の簡易 URL の DNS 要件](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Lync Server 2013 での自動クライアント サインインの DNS 要件](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [モビリティの DNS 要件](lync-server-2013-dns-requirements-for-mobility.md)

  - [Lync Server 2013 での DNS 負荷分散](lync-server-2013-dns-load-balancing.md)

