---
title: リモート通話コントロールを有効にする
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Enable remote call control
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204664(v=OCS.15)
ms:contentKeyID: 48183380
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c32e71ddc7ef0033b6a3380d394e0fe0e559945
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-remote-call-control"></a>リモート通話コントロールを有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-02_

リモート通話コントロール Lync Server 2013 を使用して、ユーザーが自分のデスクトップ構内交換機 (PBX) 電話を制御できるようにします。 従来の環境にリモート通話コントロールを展開していて、Lync Server 2013 を移行する場合は、次のタスクを実行する必要があります。

1.  SIP/CSTA ゲートウェイをインストールし、PBX と通信するように構成します。 Lync Server 2013 パイロットプールを展開する場合は、この手順を実行する必要があります。

2.  トポロジを統合してポリシーと設定を移行した後、CSTA 要求を SIP/CSTA ゲートウェイにルーティングするように Lync Server 2013 を構成します。 この手順は、自動移行の後で行う手動手順です。 CSTA 要求のルーティングを構成するには、次の操作を行います。
    
      - 従来の承認済みホストエントリを削除します (Lync Server 2013 では、*信頼されたサーバーのエントリ*として知られています)。 従来の展開からユーザーを移行する場合は、Lync Server 2013 パイロットプールで新しい信頼済みアプリケーションエントリを構成する前に、SIP/CSTA ゲートウェイ用に作成した既存の承認済みホストエントリをすべて削除してください。 従来の承認済みホストエントリを削除する方法の詳細については、「[承認済みホストエントリを削除](remove-an-authorized-host-entry.md)する」を参照してください。
    
      - リモート通話コントロールの静的ルートを構成します。 リモート通話コントロールをサポートする個別のプールに静的ルートを構成したり、プール レベルの静的ルートが構成されていない各プールでグローバル静的ルートが使用されるようにグローバル静的ルートを構成したりできます。 静的ルートを構成する方法の詳細については、「展開」のドキュメントの「 [configure a static route for remote call control In Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md) 」を参照してください。
    
      - リモート通話コントロールをサポートする各プールで、リモート通話コントロールの信頼されたアプリケーション エントリを構成します。 信頼されたアプリケーションエントリを構成する方法の詳細については、「展開」のドキュメントの「 [configure a trusted application entry for remote call control In Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) 」を参照してください。

3.  伝送制御プロトコル (TCP) を使用して Lync Server 2013 に接続する SIP/CSTA ゲートウェイを展開した場合は、トポロジビルダーでゲートウェイの IP アドレスを定義します。 IP アドレスの定義の詳細については、「展開」のドキュメントの「 [Define a SIP/CSTA GATEWAY IP address In Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) 」を参照してください。

4.  リモート通話コントロールを有効にし、回線サーバーの URI (Uniform Resource Identifier) と行 URI を割り当てることにより、リモート通話コントロールの Lync 2013 ユーザーを構成します。 従来の展開から Lync Server 2013 にユーザーを移行すると、リモート通話コントロールの設定が他のユーザーの設定と共に移行されます。

5.  従来の展開でアドレス帳の電話番号正規化ルールをカスタマイズしてある場合は、ポリシーと設定の自動移行が完了した後でいくつかの手作業を実行し、カスタマイズした正規化ルールを移行する必要があります。 正規化ルールをカスタマイズしていない場合は、アドレス帳はトポロジの他の部分と共に移行されます。 カスタマイズした正規化ルールの手動移行の詳細については、「[Migrate Address Book](migrate-address-book_1.md)」を参照してください。

</div>

<span> </span>

</div>

</div>

</div>

