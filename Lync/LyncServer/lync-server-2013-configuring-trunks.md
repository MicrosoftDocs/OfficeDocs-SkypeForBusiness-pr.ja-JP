---
title: 'Lync Server 2013: トランクの構成'
TOCTitle: トランクの構成
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48271254
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのトランクの構成

 

_**トピックの最終更新日:** 2012-11-01_

エンタープライズ VoIP 展開の一部として、仲介サーバーと次の 1 つ以上のピアの間にトランクを構成して、エンタープライズ VoIP クライアントと組織のデバイス用に公衆交換電話網 (PSTN) 接続を提供します。

  - インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続

  - PSTN ゲートウェイ

  - 構内交換機 (PBX)

詳細については、「計画」のドキュメントの「[Lync Server 2013 での PSTN 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md)」を参照してください。


> [!IMPORTANT]
> トランク構成を開始する前に、トポロジが既に作成済みであること、および仲介サーバーとそのピアが構成され、互いに関連付けられていることを確認します。詳細については、「展開」のドキュメントの「<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 での、トポロジ ビルダーを使用したゲートウェイの定義</A>」を参照してください。



> [!NOTE]
> トランク構成の一部として、Lync Server 2013 メディア バイパス機能を有効にできます。メディア バイパスを有効にすると、メディアは仲介サーバーをバイパスできます。トランクの構成は、メディア バイパスを有効にするかどうかに関係なく実行できますが、有効にすることを強くお勧めします。詳細については、「計画」のドキュメントの「<a href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 でのメディア バイパスの計画</a>」を参照してください。


## このセクション中

  - [Lync Server 2013 での複数のトランクのサポート](lync-server-2013-multiple-trunk-support.md)

  - [Lync Server 2013 でのトランク間ルーティング](lync-server-2013-inter-trunk-routing.md)

  - [トランク構成情報の表示](lync-server-2013-view-trunk-configuration-information.md)

  - [Lync Server 2013 でメディア バイパスを有効にしてトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Lync Server 2013 でメディア バイパスを無効にしてトランクを構成する](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [トランク構成設定の新しいコレクションの作成](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [SIP トランク構成設定の既存コレクションの削除](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [SIP トランク構成設定の変更](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [SIP トランク構成設定のテスト](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [個別の SIP トランク情報の表示](lync-server-2013-view-information-about-individual-sip-trunks.md)

## 関連項目

#### タスク

[Lync Server 2013 での、トポロジ ビルダーを使用したゲートウェイの定義](lync-server-2013-define-a-gateway-in-topology-builder.md)  

#### その他のリソース

[Lync Server 2013 での PSTN 接続の計画](lync-server-2013-planning-for-pstn-connectivity.md)  
[Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)

