---
title: Lync Server 2013 でのグローバル メディア バイパス オプション
TOCTitle: Lync Server 2013 でのグローバル メディア バイパス オプション
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48271430
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのグローバル メディア バイパス オプション

 

_**トピックの最終更新日:** 2016-12-08_

> [!NOTE]
> このトピックは、メディアに仲介サーバーをバイパスさせたい特定のサイトまたはサービスのピア (公衆交換電話網 (PSTN) ゲートウェイ、IP-PBX、またはインターネット テレフォニー サービス プロバイダーでのセッション ボーダー コントローラー (SBC)) へのすべてのトランク接続に対して、メディア バイパスが既に構成されていることを前提にしています。


ピアに関連付けられている個々のトランク接続でメディア パイパスを有効にするほか、メディア バイパスをグローバルに有効にする必要もあります。グローバルなメディア バイパス設定では、PSTN への呼び出しで常にメディア バイパスを試行するか、ネットワーク サイトおよびネットワーク地域へのサブネットのマッピングを使用するメディア パイパスを採用するかを指定できます。後者の方法は、もう 1 つの高度な音声機能である通話受付管理での方法と似ています。メディア バイパスと通話受付管理が両方有効な場合は、ネットワーク地域、ネットワーク サイト、および通話受付管理用に指定されるサブネット情報が、メディア バイパスを使用するかどうかを決定する際に自動的に使用されます。つまり、通話受付管理が有効な場合は、PSTN の呼び出しで常にメディア バイパスを試行するよう指定することはできません。

ここでは、Lync Server コントロール パネル と Lync Server 管理シェルを一緒に使用してグローバル メディア バイパス設定を構成する方法について説明します。

> [!NOTE]
> こうした手順を使用してメディア バイパスを構成する場合は、クライアントと仲介サーバー ピア (PSTN ゲートウェイ、IP-PBX、SIP トランキング プロバイダーでの SBC など) の間の接続状態が良好であることが前提です。リンクに帯域幅制限があると、メディア バイパスを通話に適用できません。メディア バイパスは、すべての PSTN ゲートウェイ、IP-PBX、および SBC と相互運用できるわけではありません。Microsoft は、認定パートナーと共に一連の PSTN ゲートウェイおよび SBC をテストし、Cisco IP-PBX についてもいくつかのテストを完了しています。メディア バイパスは、「Unified Communications Open Interoperability Program - Lync Server」(<a href="http://go.microsoft.com/fwlink/?linkid=214406%26clcid=0x411" class="uri">http://go.microsoft.com/fwlink/?linkid=214406&amp;clcid=0x411</a>) に記載されている製品およびバージョンでのみサポートされます。


## 次のステップ: グローバル メディア バイパス設定の選択

特定のサイトまたはサービス用のピアへのトランク接続でメディア パイパスを有効にした後、次のコンテンツをどちらかに使用します。

  - 「[メディア バイパスを構成して仲介サーバーを常にバイパスする](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)」の内容に従って、メディア バイパスを常に有効にします。

  - または、「[サイトおよび地域情報を使用するためのメディア バイパス グローバル設定の構成](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)」の内容に従って、サイトと地域の情報を使用するよう、メディア バイパスを構成します。

## 関連項目

#### タスク

[Lync Server 2013 でメディア バイパスを有効にしてトランクを構成する](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Lync Server 2013 でのネットワーク サイトとサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)  

#### 概念

[Lync Server 2013 メディア バイパスの構成](lync-server-2013-configure-media-bypass.md)  
[Lync Server 2013 のメディア バイパスと仲介サーバー](lync-server-2013-media-bypass-and-mediation-server.md)

