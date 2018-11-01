---
title: 'Lync Server 2013: エンタープライズ VoIP の展開'
TOCTitle: エンタープライズ VoIP の展開
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48273348
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのエンタープライズ VoIP の展開

 

_**トピックの最終更新日:** 2012-10-03_

Lync Server 2013エンタープライズ VoIP は、Lync Server 2013 インフラストラクチャの一部です。

エンタープライズ VoIP の展開には以下のことが必要になります。

1.  「計画の」ドキュメントの「[Lync Server 2013 でのエンタープライズ VoIP の計画](lync-server-2013-planning-for-enterprise-voice.md)」セクションを確認していること。

2.  このワークロードで展開する機能およびコンポーネントの計画が完了していること。

3.  計画ツールを実行して、展開の決定事項を反映するトポロジを設計していること。

4.  「展開」のドキュメントの「[Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」に従って、 トポロジ ビルダーでトポロジ設計を開いたこと。
    
    > [!NOTE]
    > トポロジ ビルダーのインストールは内部プールでの展開プロセスの一部として行うものです。詳細については、「展開」のドキュメントの「<a href="lync-server-2013-install-lync-server-administrative-tools.md">Lync Server 2013 管理ツールをインストールする</a>」を参照してください。


また、 Lync Server Enterprise Edition が、展開する関連トポロジに対応する中央サイトとブランチ サイトで既に展開されている必要があります。 エンタープライズ VoIP のコンポーネントは、少なくとも 1 つの内部プールのファイルを定義、公開、およびインストールするまで展開できません。また、 トポロジ ビルダーを使用して、内部プールを定義および公開する必要があります。

エンタープライズ VoIP のサーバーの役割を展開できる場所 (および相互の関連性と、他の Lync Server 2013 のサーバーの役割) の例が含まれた関連トポロジを参照する場合は、「計画」のドキュメントの「[Lync Server 2013 の関連トポロジ](lync-server-2013-reference-topologies.md)」を参照してください。

通話受付管理の展開例 (ネットワーク地域、ネットワーク サイト、およびサブネットを含む) の図および説明となる関連トポロジを参照するには、「計画」のドキュメントの「[例: Lync Server 2013 での通話受付管理の組織要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)」を参照してください。


> [!IMPORTANT]
> 中央サイトで エンタープライズ VoIP を展開する場合は、このセクションをこのままお読みください。ブランチ サイトで エンタープライズ VoIP を展開する場合は、「展開」のドキュメントの「<A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 でのブランチ サイトの展開</A>」を参照してください。



このセクションには、推奨に従って、各フロントエンド サーバーまたは各 Standard Edition サーバー上に仲介サーバーを併置する展開の手順、およびスタンドアロンの仲介サーバー プールでの展開の手順が含まれています。

トポロジ ビルダーを使用して、各フロントエンド サーバーまたは各 Standard Edition サーバー上に仲介サーバーを併置するトポロジを定義および公開した場合は、次の内容に進むことができます。これは、各フロントエンド サーバーまたは各 Standard Edition サーバー用のファイルをインストールするときに、展開ウィザードにより、仲介サーバー用のファイルが自動的にインストールされるためです。

  - [Lync Server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)

トポロジ ビルダーを使用して、スタンド アロンのプールに仲介サーバーを定義および公開した場合は、次の内容を使用できます。

  - 「[Lync Server 2013 のエンタープライズ VoIP の前提条件](lync-server-2013-enterprise-voice-prerequisites.md)」に従って、トポロジがソフトウェアおよび環境の前提条件を満たすことを確認してください。

## このセクション中

  - [Lync Server 2013 のエンタープライズ VoIP の前提条件](lync-server-2013-enterprise-voice-prerequisites.md)

  - [Lync Server 2013 での仲介サーバーの展開とピアの定義](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - [Lync Server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)

  - [Lync Server 2013 でのダイヤル プランの構成](lync-server-2013-configuring-dial-plans.md)

  - [Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイス ルートの構成](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - [Lync Server 2013 での音声ルーティング構成のエクスポートとインポート](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)

  - [Lync Server 2013 での音声ルーティング構成に対する保留中の変更の公開](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [内部設置型 Exchange UM を展開して Lync Server 2013 ボイス メールを提供する](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - [Lync Server 2013 ユーザーに Hosted Exchange UM のボイス メールを提供する](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - [社内の Lync Server 2013 と Exchange Online との統合の構成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - [Lync Server 2013 での高度なエンタープライズ VoIP 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Lync Server 2013 ネットワーク領域、サイト、およびサブネットの構成](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Lync Server 2013 でのネットワーク領域の作成または変更](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Lync Server 2013 でのネットワーク サイトの作成または変更](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Lync Server 2013 でのネットワーク サイトとサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Lync Server 2013 での通話管理受付の構成](lync-server-2013-configure-call-admission-control.md)
    
      - [Lync Server 2013 での Enhanced 9-1-1 の構成](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Lync Server 2013 メディア バイパスの構成](lync-server-2013-configure-media-bypass.md)

  - [Lync Server 2013 でのエンタープライズ VoIP に対するユーザーの有効化](lync-server-2013-enable-users-for-enterprise-voice.md)

## 関連項目

#### その他のリソース

[Lync Server 2013 でのブランチ サイトの展開](lync-server-2013-deploying-branch-sites.md)  
[Lync Server 2013 でのダイヤルイン会議の構成](lync-server-2013-configuring-dial-in-conferencing.md)  
[Lync Server 2013 でのコール パークの構成](lync-server-2013-configuring-call-park.md)  
[Lync Server 2013 での、割り当てられていない番号用のアナウンスの構成](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)

