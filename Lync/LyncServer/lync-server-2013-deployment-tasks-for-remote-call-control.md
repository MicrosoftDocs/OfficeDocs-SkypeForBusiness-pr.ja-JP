---
title: 'Lync Server 2013: リモート通話コントロールの展開タスク'
TOCTitle: リモート通話コントロールの展開タスク
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48271474
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のリモート通話コントロールの展開タスク

 

_**トピックの最終更新日:** 2016-12-08_

ここでは、Lync Server 環境内のユーザーに対して、リモート通話コントロールを有効にするために実行する必要がある展開タスクについて説明します。

> [!NOTE]
> Microsoft Office Communicator 2007 R2 で以前にリモート通話コントロールを有効にしたユーザーを移行する場合は、このトピックで説明するリモート通話コントロールの展開タスクの実行を開始する前に、追加の展開タスクを実行する必要があります。Lync Server への移行プロセスでは、必要に応じて Office Communications Server 2007 R2 管理ツールを使用して、信頼されたアプリケーション エントリ (以前は<em>承認済みホスト エントリ</em>と呼ばれていました) を削除する必要があります。<br />
> 承認済みホストの削除の詳細については、「<a href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Lync Server 2013 での従来の承認済みホストの削除 (オプション)</a>」を参照してください。


## ステップ 1: PBX との通信のための、SIP/CSTA ゲートウェイのインストールおよび構成

ユーザーへリモート通話コントロール機能を提供するために、Lync Server およびご使用の環境内にある既存の構内交換機 (PBX) の両方に接続できる、少なくとも 1 つの SIP/CSTA ゲートウェイをインストールする必要があります。SIP/CSTA ゲートウェイは、SIP と CSTA (Computer Supported Telecommunications Application) の間のゲートウェイです。 複数のゲートウェイをインストールする場合も、1 つのゲートウェイをインストールする場合も、1 つのゲートウェイまたは PBX だけで各ユーザーを構成できます。 既存の PBX に SIP/CSTA のインターフェイスがない場合は、PBX ベンダー固有のシグナリング プロトコルのサポートなど、その PBX のサポートが可能なゲートウェイを展開してください。 機能の詳細については、各ベンダーに直接お問い合わせください。

リモート通話コントロールを実現するために、Lync Server と統合できる SIP/CSTA ゲートウェイを展開する準備ができたら、ゲートウェイで必要な構文の次の情報について、ゲートウェイ ベンダーに問い合わせるか、ベンダーのゲートウェイのドキュメントも参照してください。

  - ゲートウェイの回線サーバーの URI

  - ゲートウェイに割り当てられる、ユーザーのための回線 URI

ユーザーの構成時は上記の設定が必要であり、PBX へ正常にルーティングおよび接続するためには、ゲートウェイがこれらの設定を予定どおりに指定する必要があります。

Microsoft ユニファイド コミュニケーション Open Interoperability Program の Web サイト ([http://go.microsoft.com/fwlink/?linkid=203309\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=203309%26clcid=0x411)) のベンダーにお問い合わせください。

## ステップ 2: CSTA 要求を SIP/CSTA ゲートウェイへルーティングするための Lync Server の構成

Lync Server プールから、リモート通話コントロール要求をルーティングする、展開内のすべての SIP/CSTA ゲートウェイの宛先アドレス (サーバー URI) までの静的ルートを作成する必要があります。また、各宛先アドレスに対応する、信頼されたアプリケーション エントリも作成する必要があります。ゲートウェイを信頼されたアプリケーションとして指定すると、サードパーティが開発した Lync Server 環境であってもその環境の一部として実行するために、信頼された状態が付与されます (製品に組み込まれていないサービスなので、*外部サービス*と呼ばれるサービスを実行します)。 最後に、Lync Server がトランスポート層セキュリティ (TLS) 接続ではなく伝送制御プロトコル (TCP) 接続を使用して SIP/CSTA ゲートウェイへ接続する場合は、トポロジ ビルダーを使用してゲートウェイ IP アドレスについても定義する必要があります。

静的ルートの構成の詳細については、「[Lync Server 2013 でのリモート通話コントロールの静的ルートの構成](lync-server-2013-configure-a-static-route-for-remote-call-control.md)」を参照してください。

信頼されたアプリケーション エントリの構成の詳細については、「[Lync Server 2013 でリモート通話コントロールの信頼済みアプリケーション エントリを構成する](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)」を参照してください。

トポロジ ビルダー での SIP/CSTA ゲートウェイの IP アドレスの定義の詳細については、「[Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)」を参照してください。

## ステップ 3: リモート通話コントロールの Lync ユーザーの構成

Lync Server でユーザーが有効になったら、Lync Server コントロール パネルまたは Lync Server 管理シェルを使用してリモート通話コントロールでユーザーを有効にできます。この展開ステップで、各ユーザーに回線サーバー URI と回線 URI を割り当てることができます。回線サーバー URI は、ユーザーに割り当てる SIP/CSTA ゲートウェイの SIP URI です。回線 URI は、ユーザーに割り当てられる一意の電話番号です。

リモート通話コントロール ユーザーの構成の詳細については、「[Lync Server 2013 でのリモート通話コントロールの Lync ユーザーの有効化](lync-server-2013-enable-lync-users-for-remote-call-control.md)」を参照してください。

## ステップ 4: Lync Server の電話番号正規化ルールの定義

リモート通話コントロールを使用するシナリオでは、Lync Server は電話番号正規化ルールを使用して、SIP/CSTA ゲートウェイから受信する電話番号を E.164 形式に変換します。 一部のリモート通話コントロール機能が正常に動作するようにするには、電話番号をこの標準形式にする必要があります。 リモート通話コントロールは、アドレス帳サービスで構成する時と同じ電話番号正規化ルールを使用しますが、これはエンタープライズ VoIP で使用する電話番号正規化ルールとは異なります。

リモート通話コントロールが電話番号正規化ルールを使用する方法の詳細については、「[Lync Server 2013 でのリモート通話コントロールと電話番号正規化](lync-server-2013-remote-call-control-and-phone-number-normalization.md)」を参照してください。 アドレス帳サービスの電話番号正規化ルールの詳細については、「操作」のドキュメントの「[アドレス帳サービスの管理](lync-server-2013-administering-the-address-book-service.md)」を参照してください。

