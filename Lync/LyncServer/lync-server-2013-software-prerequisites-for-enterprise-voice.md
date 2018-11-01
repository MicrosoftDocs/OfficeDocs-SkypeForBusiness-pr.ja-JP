---
title: 'Lync Server 2013: エンタープライズ VoIP のソフトウェア前提条件'
TOCTitle: エンタープライズ VoIP のソフトウェア前提条件
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48271894
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のエンタープライズ VoIP のソフトウェア前提条件

 

_**トピックの最終更新日:** 2012-10-03_

エンタープライズ VoIP を展開するインフラストラクチャで、次のソフトウェア前提条件が満たされることを確認します。

  - Lync Server 2013 Standard Edition または Enterprise Edition がネットワーク上にインストールされ、実行されていること。

  - 境界ネットワーク内に、すべてのエッジ サーバー (アクセス エッジ サービス、音声ビデオ エッジ サービス、Web 会議エッジ サービス、およびリバース プロキシを実行する エッジ サーバーを含む) が展開され、実行されていること。

  - Exchange ユニファイド メッセージングを Lync Server と統合し、優れた通知と通話ログ情報を Lync エンドポイントに提供できるように、Microsoft Exchange Server 2007 Service Pack 3 (SP3)、Microsoft Exchange Server 2010、または Microsoft Exchange Server 2013 のいずれかが用意されていること。

  - 1 人以上のユーザーが作成され、Lync Server に対して有効化されていること。

  - Lync のクライアントおよびデバイスが正常に展開されていること。

  - トポロジ ビルダーがネットワーク上のサーバーにインストールされていること。

## 次のステップ: セキュリティおよび構成の前提条件の確認

エンタープライズ VoIP のソフトウェア前提条件を確認したら、ドキュメントを使用してエンタープライズ VoIP 展開の準備を続行できます。

1.  「[Lync Server 2013 のエンタープライズ VoIP のセキュリティおよび構成の前提条件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)」の説明に従って、セキュリティ、ユーザー構成、およびハードウェア前提条件を確認します。

2.  「[Lync Server 2013 仲介サーバーのファイルのインストール](lync-server-2013-install-the-files-for-mediation-server.md)」の説明に従って、仲介サーバーをインストールします (ただし、併置するとフロントエンド プールまたは Standard Edition サーバー の展開プロセスの一部として仲介サーバーがインストールされるため、仲介サーバーまたはプールをスタンドアロンで展開する場合に *限ります* )。

3.  「[Lync Server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)」の説明に従って、トランク接続を構成し、ユーザーに PSTN 接続を提供します。

