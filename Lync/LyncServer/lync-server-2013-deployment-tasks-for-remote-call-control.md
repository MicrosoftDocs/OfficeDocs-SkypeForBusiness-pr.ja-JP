---
title: 'Lync Server 2013: リモート通話コントロールの展開タスク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1549cb2f71e5f6f0ab1d16907d5e83765780cca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 でのリモート通話コントロールの展開タスク

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-05_

このトピックでは、Lync Server 環境でユーザーのリモート通話コントロールを有効にするために実行する必要がある展開タスクについて説明します。

<div>


> [!NOTE]  
> Microsoft Office Communicator 2007 R2 のリモート通話コントロールに対して既に有効になっているユーザーを移行する場合は、このトピックで説明されているリモート通話コントロールの展開タスクの実行を開始する前に、追加の展開タスクを実行する必要があります。 Lync Server への移行プロセスでは、必要に応じて、Office Communications Server 2007 R2 管理ツールを使用して、信頼されたアプリケーションエントリ (旧称<EM>承認済みホストエントリ</EM>) を削除する必要があります。<BR>承認済みホストの削除の詳細については、「 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Lync Server での従来の承認済みホストの削除 2013 (オプション)</A>」を参照してください。



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>ステップ 1:  PBX との通信のための、SIP/CSTA ゲートウェイのインストールおよび構成

ユーザーにリモート通話コントロール機能を提供するためには、環境内の Lync Server と既存の構内交換機 (PBX) の両方に接続できる SIP/CSTA ゲートウェイを少なくとも1つインストールする必要があります。 SIP/CSTA ゲートウェイは、SIP と CSTA (Computer Supported Telecommunications Application) の間のゲートウェイです。 複数のゲートウェイをインストールする場合も、1 つのゲートウェイをインストールする場合も、1 つのゲートウェイまたは PBX だけで各ユーザーを構成できます。 既存の PBX に SIP/CSTA のインターフェイスがない場合は、PBX ベンダー固有のシグナリング プロトコルのサポートなど、その PBX のサポートが可能なゲートウェイを展開してください。 機能の詳細については、各ベンダーに直接お問い合わせください。

リモート通話コントロール用の Lync Server と統合できる SIP/CSTA ゲートウェイを展開する準備ができたら、以下の情報について、ゲートウェイベンダーまたはベンダーのゲートウェイに関するドキュメントを参照してください。

  - ゲートウェイの回線サーバーの URI

  - ゲートウェイに割り当てられる、ユーザーのための回線 URI

ユーザーの構成時は上記の設定が必要であり、PBX へ正常にルーティングおよび接続するためには、ゲートウェイがこれらの設定を予定どおりに指定する必要があります。

Microsoft ユニファイドコミュニケーションのオープンな相互運用性プログラム web サイトのベンダーに[https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309)ついては、「」を参照してください。

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>手順 2: CSTA 要求を SIP/CSTA ゲートウェイにルーティングするように Lync Server を構成する

リモート通話コントロールの要求をルーティングする予定の、展開内のすべての SIP/CSTA ゲートウェイの宛先アドレス (サーバー URI) に対して、Lync Server プール上に静的ルートを作成する必要があります。 また、各宛先アドレスに対応する、信頼されたアプリケーション エントリも作成する必要があります。 ゲートウェイを信頼済みアプリケーションとして指定すると、サードパーティによって開発された場合でも、Lync Server 環境の一部として実行される信頼できる状態が与えられます。これは、製品の組み込みパーツではないサービスであるため、*外部サービス*と呼ばれるものとして実行されます。 最後に、Lync Server がトランスポート層セキュリティ (TLS) 接続ではなく、伝送制御プロトコル (TCP) 接続を使用して SIP/CSTA ゲートウェイに接続する場合は、トポロジビルダーを使用してゲートウェイの IP アドレスも定義する必要があります。

静的ルートの構成の詳細については、「 [Lync Server 2013 のリモート通話コントロールの静的ルートを構成する](lync-server-2013-configure-a-static-route-for-remote-call-control.md)」を参照してください。

信頼されたアプリケーションエントリの構成の詳細については、「 [Configure a trusted application entry for remote call control In Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)」を参照してください。

トポロジビルダーでの SIP/CSTA ゲートウェイの IP アドレスの定義の詳細については、「 [Define a sip/CSTA GATEWAY ip address In Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)」を参照してください。

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>手順 3: リモート通話コントロールの Lync ユーザーを構成する

ユーザーが Lync Server に対して有効になったら、Lync server コントロールパネルまたは Lync Server 管理シェルを使用して、リモート通話コントロールに対して有効にすることができます。 この展開ステップで、各ユーザーに回線サーバー URI と回線 URI を割り当てることができます。 回線サーバー URI は、ユーザーに割り当てる SIP/CSTA ゲートウェイの SIP URI です。 回線 URI は、ユーザーに割り当てられる一意の電話番号です。

リモート通話コントロールに対するユーザーの構成の詳細については、「 [Lync Server 2013 でのリモート通話コントロールの lync ユーザーの有効化](lync-server-2013-enable-lync-users-for-remote-call-control.md)」を参照してください。

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>ステップ 4:  Lync Server の電話番号正規化ルールの定義

リモート通話コントロールのシナリオでは、Lync Server は電話番号の正規化ルールを使用して、SIP/CSTA ゲートウェイから受信する電話番号を e.164 形式に変換します。 一部のリモート通話コントロール機能が正常に動作するようにするには、電話番号をこの標準形式にする必要があります。 リモート通話コントロールは、アドレス帳サービスで構成する時と同じ電話番号正規化ルールを使用しますが、これはエンタープライズ VoIP で使用する電話番号正規化ルールとは異なります。

リモート通話コントロールで電話番号の正規化ルールを使用する方法の詳細については、「 [Lync Server 2013 でのリモート通話コントロールと電話番号の正規化](lync-server-2013-remote-call-control-and-phone-number-normalization.md)」を参照してください。 アドレス帳サービスの電話番号正規化ルールの詳細については、「操作」のドキュメントの「 [Lync Server 2013 でアドレス帳サービスを管理する](lync-server-2013-administering-the-address-book-service.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

