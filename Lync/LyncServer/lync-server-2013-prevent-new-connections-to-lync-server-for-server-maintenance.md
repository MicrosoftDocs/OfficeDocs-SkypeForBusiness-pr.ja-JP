---
title: Lync Server への新しい接続でサーバーのメンテナンスができないようにする
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
ms.openlocfilehash: fb0e2db6eeff584c4d1ab08bdd293113f1394e4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>Lync Server 2013 への新しい接続でサーバーのメンテナンスができないようにする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

Lync Server を使用すると、サービスが失われることなくサーバーをオフラインにすることができます (たとえば、ソフトウェアまたはハードウェアのアップグレードを適用することができます)。

プール内のサーバーへの新しい接続または呼び出しを禁止するオプションを指定すると、このオプションを実装するとすぐに、新しい接続と通話の取得が停止されます。 これらの新しい接続と通話は、プール内の他のサーバーを経由してルーティングされます。 新しい接続を禁止しているサーバーでは、既存の接続に対するセッションは自然に終了するまで続行されます。 既存のすべてのセッションが終了したら、サーバーをオフラインにすることができます。

フロントエンドサーバーへの新しい接続を禁止する場合、一部の Lync Server の機能とサービスは DNS の負荷分散を利用して適切に動作することを確認します。 プールで DNS の負荷分散を使用していない場合、サーバーが新しい接続を妨害している期間中、これらのサービスからの接続が他のサーバーに再ルーティングされないことがあります。そのため、サーバーがオフラインになったときに、一部のセッションと通話がまし. このオプションが適切に動作するように、DNS の負荷分散に依存する機能は次のように動作します。

  - Attendant

  - 会議アナウンス アプリケーション

  - 応答グループ アプリケーション

  - アナウンス アプリケーション

  - コール パーク アプリケーション

DNS の負荷分散の詳細については、計画ドキュメントの「 [Lync Server 2013 での dns の負荷分散](lync-server-2013-dns-load-balancing.md)」を参照してください。

Lync Server を実行しているサーバー上のすべてのサービスの新しい接続を防止するだけでなく、個々の Lync Server サービスへの新しい接続を防ぐこともできます。 たとえば、この方法は、サーバー全体をシャットダウンする必要がない Lync Server の更新プログラムを適用する必要がある場合に役立ちます。 1つのサービスに対する接続を禁止する場合は、サービスがグループ化され、サービスの一覧に表示されるサービスを選択する必要があることに注意してください。 たとえば、Lync Server のフロントエンドサービスと監視用のデータ収集エージェントは別々の Lync Server サービスであり、Windows services のリストでは統合され、Lync Server のフロントエンドサービスとして表示されます。 Lync Server のフロントエンドサービスへの新しい接続を禁止することはできますが、この2つの基本的な Lync Server サービスへの新しい接続を個別に無効にすることはできません。

<div>


> [!IMPORTANT]
> 新しい接続を禁止するようにサーバーを設定してから、サーバーを再起動すると、既定では、サーバーは起動後に新しい接続の受け入れを直します。 これを防ぐには、サーバーを再起動する前に、手動で一時停止および再開するようにサーバーを設定します。



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>Lync Server への新しい接続を禁止するには、次の操作を行います。

1.  Administrators グループのメンバーとして、ローカル コンピューターにログオンします。

2.  [サービス] スナップインコンソールを開きます。 [**スタート**] をクリックし、[**すべてのプログラム**] をポイントして、[**管理ツール**] をポイントし、[**サービス**] をクリックします。

3.  リストで、新しい接続を禁止する Lync Server Windows サービスをダブルクリックします。

4.  [プロパティ] ダイアログボックスの [**サービスの状態: 開始**] で、[**一時停止**] をクリックします。

5.  必要に応じて、[**スタートアップの種類**] の横にある [**手動**] をクリックします。
    
    <div>
    

    > [!IMPORTANT]
    > 新しい接続を禁止するようにサーバーを設定してから、サーバーを再起動すると、既定では、サーバーは起動後に新しい接続の受け入れを直します。 これを防ぐには、サーバーを再起動する前に、手動で一時停止および再開するようにサーバーを設定します。

    
    </div>

6.  終了したら、[**OK**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

