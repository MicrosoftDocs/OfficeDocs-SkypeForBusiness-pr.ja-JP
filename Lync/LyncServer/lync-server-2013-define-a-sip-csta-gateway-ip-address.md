---
title: 'Lync Server 2013: SIP/CSTA ゲートウェイの IP アドレスの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c50958f2c7c44045e25ff4ac9619f3ad73a5f302
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

Lync Server が伝送制御プロトコル (TCP) 接続を使ってリモート通話コントロール用に展開した SIP/CSTA ゲートウェイに接続する場合は、トポロジビルダーでゲートウェイの IP アドレスを定義する必要があります。 トランスポート層セキュリティ (TLS) 接続をサポートするゲートウェイの場合、この手順は必要ありません。 TLS 接続をサポートしているすべてのゲートウェイについては、この手順をスキップして、「lync[ユーザーが Lync Server 2013 のリモート通話制御を有効にする](lync-server-2013-enable-lync-users-for-remote-call-control.md)」の手順に従って、リモート通話コントロールの展開を継続できます。

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>Topology Builder を使用して SIP/CSTA ゲートウェイの IP アドレスを定義するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジビルダーを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server Topology Builder**] の順にクリックします。

3.  既存のトポロジをダウンロードするためのオプションを選択します。

4.  [信頼されている**アプリケーションサーバー** ] ノードを展開します。

5.  「 [Lync Server 2013 のリモート通話コントロールに対して信頼されているアプリケーションエントリを構成](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)する」の説明に従って、作成した信頼できるアプリケーションプールを右クリックし、[**プロパティの編集**] をクリックします。

6.  [**このプールへの構成データのレプリケーションを有効に**する] チェックボックスをオフにします。

7.  [**サービスの利用制限を選択した IP アドレスに制限] を**クリックします。 既定の設定では、[構成され**た IP アドレスをすべて使用する**] を選びます。

8.  [**プライマリ IP アドレス**] テキストボックスに、SIP/csta ゲートウェイの IP アドレスを入力します。

9.  サーバーの全体管理ストアでトポロジを更新するには、コンソールツリーで [ **Lync Server**] をクリックし、[**操作**] ウィンドウで [**発行**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのリモート通話コントロールの静的ルートの構成](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Lync Server 2013 でリモート通話コントロールの信頼済みアプリケーション エントリを構成する](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

