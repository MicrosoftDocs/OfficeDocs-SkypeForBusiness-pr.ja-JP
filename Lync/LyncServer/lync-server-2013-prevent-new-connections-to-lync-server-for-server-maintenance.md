---
title: Lync Server へのサーバーメンテナンスのための新しい接続を禁止する
description: サーバーメンテナンスのための Lync Server への新しい接続を禁止します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd676467cdd6b5bb430f972e48c2f3a53f3f6f14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579833"
---
# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>サーバーメンテナンスのための Lync Server 2013 への新しい接続を禁止する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

Lync Server を使用すると、ユーザーにサービスを損失することなく、サーバーをオフラインにすることができます (たとえば、ソフトウェアまたはハードウェアのアップグレードを適用することができます)。

プール内でサーバーへの新規接続および呼び出しを禁止するオプションを指定した場合、このオプションを実装するとすぐに新規接続および呼び出しを受け付けなくなります。これら新規の接続および呼び出しは、プール内の他のサーバーを介してルーティングされます。新規接続を禁止しているサーバーでは、既存の接続上のセッションは自然に終了するまで続行することができます。既存のセッションがすべて終了すると、サーバーをオフラインにすることができます。

フロントエンドサーバーへの新しい接続を禁止する場合、一部の Lync Server の機能およびサービスは、DNS 負荷分散を使用して正しく機能することを確認します。 プール内で DNS 負荷分散を使用していない場合、サーバーが新規接続を禁止している間、これらのサービスを介する接続はその他のサーバーに再ルーティングされない可能性があり、結果、サーバーがオフラインになる時、一部のセッションおよび通話が中断される可能性があります。 このオプションを確実に正しく動作させるために DNS 負荷分散を使用する機能は、次のとおりです。

  - Attendant

  - 会議アナウンス アプリケーション

  - 応答グループ アプリケーション

  - アナウンス アプリケーション

  - コール パーク アプリケーション

DNS 負荷分散の詳細については、「計画」のドキュメントの「 [dns load balancing In Lync Server 2013](lync-server-2013-dns-load-balancing.md) 」を参照してください。

Lync Server を実行しているサーバー上のすべてのサービスの新しい接続を禁止することに加えて、個々の Lync Server サービスの新しい接続を禁止することもできます。 たとえば、このメソッドは、サーバー全体をシャットダウンする必要がない Lync Server 更新プログラムを適用する必要がある場合に役立ちます。 1 つのサービスに対して接続を禁止する場合、Windows のサービス一覧でグループ化され、表示されるサービスを選択する必要があります。 たとえば、Lync server Front-End サービスと、監視用のデータ収集エージェントは別個の Lync Server サービスですが、Windows サービスのリストでは統合され、Lync Server のフロントエンドサービスとして表示されます。 Lync Server フロントエンドサービスの新しい接続を禁止することはできますが、これら2つの基本的な Lync Server サービスの新しい接続を個別に禁止することはできません。

<div>


> [!IMPORTANT]
> 新規接続を禁止するようにサーバーを設定しても、その後にサーバーを再起動すると、既定では、起動後すぐに新規接続の受け入れが開始されます。これを回避するために、サーバーを一時停止するだけに留め、サーバーを再起動する前に手動で再開します。



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>Lync Server への新しい接続を禁止するには、次のようにします。

1.  Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2.  [サービス] スナップインコンソールを開きます。 [ **スタート**] をクリックし、[ **すべてのプログラム**] をポイントします。次に、[ **管理ツール**] をポイントし、[ **サービス**] をクリックします。

3.  一覧で、新規接続を禁止する Lync Server Windows サービスをダブルクリックします。

4.  [プロパティ] ダイアログ ボックスの [**サービスの状態: 開始**] で、[**一時停止**] をクリックします。

5.  オプションですが、[**スタートアップの種類**] の横の [**手動**] をクリックすることをお勧めします。
    
    <div>
    

    > [!IMPORTANT]
    > 新規接続を禁止するようにサーバーを設定しても、その後にサーバーを再起動すると、既定では、起動後すぐに新規接続の受け入れが開始されます。これを回避するために、サーバーを一時停止するだけに留め、サーバーを再起動する前に手動で再開します。

    
    </div>

6.  終了したら、[**OK**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

