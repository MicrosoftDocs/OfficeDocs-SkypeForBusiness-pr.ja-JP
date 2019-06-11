---
title: 'Lync Server 2013: リモート通話コントロールの展開タスク'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f63c9cba56ccedf3559b1e9f1da1ee58cc03e195
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 のリモート通話コントロールの展開タスク

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-05_

このトピックでは、Lync Server 環境のユーザーに対してリモート通話コントロールを有効にするために実行する必要がある展開タスクについて説明します。

<div>


> [!NOTE]  
> Microsoft Office Communicator 2007 R2 で、リモート通話コントロールに対して以前有効にしたユーザーを移行する場合は、このトピックで説明されているリモート通話コントロールの展開タスクを実行する前に、追加の展開タスクを実行する必要があります。 Lync Server への移行プロセスでは、必要に応じて、Office Communications Server 2007 R2 管理ツールを使用して、信頼済みアプリケーションエントリ (以前は<EM>承認済みホストエントリ</EM>) を削除する必要があります。<BR>承認済みホストの削除の詳細については、「 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Lync Server 2013 で従来の承認済みホストを削除する (オプション)</A>」を参照してください。



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>手順 1: PBX と通信するために SIP/CSTA ゲートウェイをインストールして構成する

ユーザーにリモート通話コントロール機能を提供するには、環境内の Lync Server と既存の構内交換機 (PBX) の両方に接続できる SIP/CSTA ゲートウェイを少なくとも1つインストールする必要があります。 SIP/CSTA ゲートウェイは、SIP とコンピュータでサポートされている通信アプリケーション (CSTA) の間のゲートウェイです。 複数のゲートウェイをインストールする場合でも、1つだけの場合でも、各ユーザーを1つのゲートウェイまたは PBX で構成できます。 既存の PBX に SIP/CSTA のインタフェースがない場合は、pbx をサポートできる SIP/CSTA ゲートウェイ (pbx ベンダー固有のシグナリングプロトコルのサポートを含む) を展開してください。 機能の詳細については、各ベンダーに直接お問い合わせください。

リモート通話コントロール用に Lync Server と統合できる SIP/CSTA ゲートウェイを展開する準備ができたら、ゲートウェイベンダーに問い合わせるか、ゲートウェイで必要な以下の情報については、ベンダーのゲートウェイドキュメントを参照してください。

  - ゲートウェイのラインサーバーの URI

  - ゲートウェイに割り当てるユーザーの行の URI

上記の設定は、ユーザーの構成時に必須であり、PBX のルーティングと接続が適切に行われるように、ゲートウェイで指定されている必要があります。

Microsoft ユニファイドコミュニケーションのオープンな相互運用性プログラム web サイトでベンダーを[http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)参照するには、を参照してください。

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>手順 2: CSTA 要求を SIP/CSTA ゲートウェイにルーティングするように Lync Server を構成する

リモート通話制御要求をルーティングする対象となる、展開内のすべての SIP/CSTA ゲートウェイの宛先アドレス (サーバー URI) に、Lync サーバープールで静的ルートを作成する必要があります。 また、各宛先アドレスに対応する信頼されたアプリケーションエントリも作成する必要があります。 ゲートウェイを信頼済みアプリケーションとして指定すると、サードパーティによって開発されている場合でも、Lync Server 環境の一部として実行される信頼された状態が与えられます (これは、*外部サービス*と呼ばれるものではないサービスであるためです)。製品に組み込まれている部分)。 最後に、Lync Server がトランスポート層セキュリティ (TLS) 接続ではなく、伝送制御プロトコル (TCP) 接続を使用して SIP/CSTA ゲートウェイに接続している場合は、トポロジビルダーを使用してゲートウェイの IP アドレスを定義する必要もあります。

静的ルートの構成の詳細については、「 [Lync Server 2013 でリモート通話コントロールの静的ルートを構成](lync-server-2013-configure-a-static-route-for-remote-call-control.md)する」を参照してください。

信頼されたアプリケーションエントリの構成の詳細については、「 [Lync Server 2013 で、「リモート通話コントロール用の信頼されたアプリケーションエントリを構成](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)する」を参照してください。

Topology Builder での SIP/CSTA ゲートウェイ IP アドレスの定義の詳細については、「 [Lync Server 2013 で sip/csta ゲートウェイの ip アドレスを定義する](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)」を参照してください。

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>手順 3: リモート通話コントロール用に Lync ユーザーを構成する

Lync server のユーザーを有効にした後、Lync Server コントロールパネルまたは Lync Server 管理シェルを使用して、リモートでの通話の制御を有効にすることができます。 この展開手順では、各ユーザーに行サーバーの URI と行の URI を割り当てる必要があります。 Line server URI は、ユーザーに割り当てようとして計画している SIP/CSTA ゲートウェイの SIP URI です。 ライン URI は、ユーザーに割り当てられている一意の電話番号です。

リモート通話コントロール用にユーザーを構成する方法について詳しくは、「 [Lync Server 2013 のリモート通話コントロールで lync ユーザーを有効にする](lync-server-2013-enable-lync-users-for-remote-call-control.md)」をご覧ください。

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>手順 4: Lync Server 電話番号の正規化ルールを定義する

リモート通話コントロールのシナリオでは、Lync Server は電話番号の正規化ルールを使用して、SIP/CGI ゲートウェイから取得した電話番号を E.i 形式に変換します。 特定のリモート通話コントロール機能が正しく動作するためには、この標準化された形式で電話番号を使用する必要があります。 リモート通話コントロールは、アドレス帳サービス電話番号の正規化に対して構成したものと同じ電話番号の正規化ルールを使用します。これは、エンタープライズ Voip に使われる電話番号の正規化ルールとは異なります。

リモート通話コントロールで電話番号の正規化ルールを使用する方法について詳しくは、「 [Lync Server 2013 でのリモート通話コントロールと電話番号の正規化](lync-server-2013-remote-call-control-and-phone-number-normalization.md)」をご覧ください。 アドレス帳サービスの電話番号の正規化ルールの詳細については、操作のドキュメントで「 [Lync Server 2013 のアドレス帳サービスを管理](lync-server-2013-administering-the-address-book-service.md)する」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

