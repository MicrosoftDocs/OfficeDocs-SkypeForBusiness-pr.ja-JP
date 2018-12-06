---
title: 'Lync Server 2013: メディア バイパスの計画'
TOCTitle: メディア バイパスの計画
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48272814
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのメディア バイパスの計画

 

_**トピックの最終更新日:** 2012-09-21_

メディア バイパスとは、信号が仲介サーバーを通過する通話で、可能な場合にメディア パスから仲介サーバーを削除することです。

メディア バイパスにより、遅延、不要な変換、パケット損失の可能性、および潜在的な障害点の数を低減して、音声品質を向上できます。 バイパスされた通話のメディア処理がなくなり、仲介サーバーの負荷が軽減されるため、拡張性を向上できます。 この負荷の軽減により、仲介サーバーの複数のゲートウェイを制御する機能を補完します。

仲介サーバーが配置されていないブランチ サイトが帯域幅に制約のある 1 つ以上の WAN リンクによって中央サイトに接続されている場合、メディア バイパスにより、最初に中央サイトの 仲介サーバーとの間で WAN リンク経由でメディアをやり取りする必要がなくなり、ブランチ サイトのクライアントからローカルのゲートウェイにメディアを直接送信できるようになるため、帯域幅要件が低減されます。

仲介サーバーのメディア処理を軽減することで、メディア バイパスにより、エンタープライズ VoIP インフラストラクチャで必要となる 仲介サーバーの数を低減することもできます。

次の図は、メディア バイパスを使用した場合と使用しない場合の、トポロジ内のメディアと信号の基本経路を示しています。

**メディア バイパスを使用した場合と使用しない場合の、メディアと信号の経路**

![音声 CAC メディア バイパス接続の適用](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "音声 CAC メディア バイパス接続の適用")

原則として、メディア バイパスを可能な限り有効にします。

## このセクション中

  - [Lync Server 2013 のメディア バイパスの概要](lync-server-2013-overview-of-media-bypass.md)

  - [Lync Server 2013 のメディア バイパス モード](lync-server-2013-media-bypass-modes.md)

  - [Lync Server 2013 でのメディア バイパスと通話受付管理](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Lync Server 2013 メディア バイパスの技術要件](lync-server-2013-technical-requirements-for-media-bypass.md)

## 関連項目

[Lync Server 2013 での高度なエンタープライズ VoIP 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

## 関連項目

#### タスク

[Lync Server 2013 でメディア バイパスを有効にしてトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)  

#### 概念

[Lync Server 2013 でのグローバル メディア バイパス オプション](lync-server-2013-global-media-bypass-options.md)

