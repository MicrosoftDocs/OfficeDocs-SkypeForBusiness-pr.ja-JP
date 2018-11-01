---
title: 'Lync Server 2013: メディア バイパスの構成'
TOCTitle: メディア バイパスの構成
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48274137
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 メディア バイパスの構成

 

_**トピックの最終更新日:** 2016-12-08_

このセクションでは、少なくとも 1 台または複数の仲介サーバー (「展開」のドキュメントの「[Lync Server 2013 のトポロジ ビルダーでの仲介サーバーの定義](lync-server-2013-define-a-mediation-server-in-topology-builder.md)」および「[Lync Server 2013 でトポロジを公開する](lync-server-2013-publish-the-topology.md)」または「[Lync Server 2013 でフロントエンド プールまたは Standard Edition サーバーを定義および構成する](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)」および「[Lync Server 2013 でトポロジを公開する](lync-server-2013-publish-the-topology.md)」でそれぞれ説明しています) が公開および構成されていることを前提に説明を進めます。

また、「[Lync Server 2013 での、トポロジ ビルダーを使用したゲートウェイの定義](lync-server-2013-define-a-gateway-in-topology-builder.md)」で説明するように、PSTN 接続を可能にするために少なくとも 1 つのゲートウェイ ピアが定義されていなければなりません。ここでは、この作業も完了していることを前提とします。接続するピアが SIP トランキング プロバイダーの SBC の場合は、プロバイダーが認定プロバイダーであることとプロバイダーがメディア バイパスをサポートしていることを必ず確認してください。たとえば、多くの SIP トランキング プロバイダーが、その SBC に仲介サーバーからのトラフィックを受信することだけを許可します。その場合は、当該のトランクに対してバイパスを有効にしないでください。また、組織がその内部ネットワーク IP アドレスを SIP トランキング プロバイダーに公開していなければ、メディア バイパスを有効にすることはできません。

> [!NOTE]
> メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるとは限りません。Microsoft では、認定パートナーの PSTN ゲートウェイと SBC でテストを行い、Cisco IP-PBX でも一定のテストを行いました。メディア バイパスは、「Unified Communications Open Interoperability Program - Lync Server」( <a href="http://go.microsoft.com/fwlink/?linkid=214406%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=214406&amp;clcid=0x411</a>) に記載されている製品とバージョンのみでサポートされます。


ここでは、メディア バイパスを有効にして、仲介サーバーの要求される処理量を削減する方法について説明します。メディア バイパスを有効にする前に、「計画」のドキュメントの「[Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)」の説明に従い、環境がメディア バイパス サポートの条件を満たしていることを必ず確認してください。また、「[Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)」に記載されている情報を参照して、メディア バイパスのグローバル設定を有効にして仲介サーバーを常にバイパスするか、仲介サーバーをバイパスするかどうかを決定する際にサイトおよび地域情報を使用するかのどちらかを選択してください。この作業が済んでいるかどうか必ず確認してください。

もう 1 つの高度なエンタープライズ VoIP 機能に当たる、オプションの通話受付管理 (CAC) の構成が済んでいる場合は、通話受付管理が実行する帯域幅の予約がメディア バイパスを採用する通話に適用されないようにしてください。メディア バイパスが採用されているかどうかの検証は最初に行われます。採用されている場合は、その通話に対しては通話受付管理は使用されません。通話受付管理に対するチェックは、メディア バイパスのチェックが不合格の場合にのみ行われます。このため、PSTN にルーティングされる特定の通話に対して 2 つの機能がともに適用されることはありません。メディア バイパスは、通話のメディア エンドポイント間に帯域幅の制約がないことを前提にしているため、2 つの機能が両立しないという論理的結論にたどり着きます。メディア バイパスは、帯域幅制限のあるリンク上では実行できません。このことから、PSTN の通話には次のいずれかが適用されます。a) 仲介サーバーをメディア バイパスし、通話受付管理は通話に対して帯域幅を予約しない。または b) 通話受付管理が通話に帯域幅の予約を適用し、メディアはその通話に関わる仲介サーバーで処理される。

## 次のステップ: トランク接続でのメディア バイパスの有効化

PSTN 接続の初期設定 (ダイヤル プラン、音声ポリシー、PSTN 使用法レコード、発信通話ルート、および変換ルール) の構成が完了したら、「[Lync Server 2013 でメディア バイパスを有効にしてトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)」のステップを参照してメディア バイパスの有効化処理を開始します。

## 関連項目

#### タスク

[Lync Server 2013 でメディア バイパスを有効にしてトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[メディア バイパスを構成して仲介サーバーを常にバイパスする](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[サイトおよび地域情報を使用するためのメディア バイパス グローバル設定の構成](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  

#### 概念

[Lync Server 2013 でのグローバル メディア バイパス オプション](lync-server-2013-global-media-bypass-options.md)  

#### その他のリソース

[Lync Server 2013 でのメディア バイパスの計画](lync-server-2013-planning-for-media-bypass.md)

