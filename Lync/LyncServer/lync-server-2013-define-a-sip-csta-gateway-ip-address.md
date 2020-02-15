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
ms.openlocfilehash: 60541799a66365275207ea998fa2d4dd218a7bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a>Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

伝送制御プロトコル (TCP) 接続を使用して、リモート通話コントロール用に展開した SIP/CSTA ゲートウェイに Lync Server が接続する場合は、トポロジビルダーでゲートウェイの IP アドレスを定義する必要があります。 トランスポート層セキュリティ (TLS) 接続をサポートするゲートウェイの場合、このステップは必要ありません。 TLS 接続をサポートするすべてのゲートウェイについては、この手順を省略して、「 [lync ユーザーのリモート通話コントロールでの Lync Server 2013 の有効化](lync-server-2013-enable-lync-users-for-remote-call-control.md)」の手順に従って、リモート通話コントロールの展開を続行できます。

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a>トポロジ ビルダーを使用して SIP/CSTA ゲートウェイの IP アドレスを定義するには

1.  トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。

2.  トポロジ ビルダーを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

3.  既存のトポロジをダウンロードするオプションを選択します。

4.  [**信頼されたアプリケーション サーバー**] ノードを展開します。

5.  「 [Lync Server 2013 のリモート通話コントロールの信頼済みアプリケーションエントリを構成](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)する」の説明に従って、作成した信頼されたアプリケーションプールを右クリックし、[**プロパティの編集**] をクリックします。

6.  [**このプールへの構成データのレプリケーションを有効にする**] チェック ボックスをオフにします。

7.  [**サービスの使用を選択した IP アドレスに限定する**] をクリックします。 既定の設定は [**すべての構成済み IP アドレスの使用**] です。

8.  [**プライマリ IP アドレス**] テキスト ボックスに、SIP/CSTA ゲートウェイの IP アドレスを入力します。

9.  中央管理ストアでトポロジを更新するには、コンソール ツリーの [**Lync Server**] をクリックし、[**操作**] ウィンドウで [**公開**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でリモート通話コントロールの静的ルートを構成する](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Lync Server 2013 でのリモート通話コントロールの信頼済みアプリケーションエントリを構成する](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

