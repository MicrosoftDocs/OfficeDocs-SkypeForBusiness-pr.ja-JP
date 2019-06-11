---
title: リモート通話コントロールの信頼済みアプリケーション エントリを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be0dda3eedc73e5c64f7c275714955f3ce92af3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 でリモート通話コントロールの信頼済みアプリケーション エントリを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-11-02_

Lync Server で着信をルーティングするために静的ルートを適用するには、SIP/CSTA ゲートウェイが信頼済みアプリケーションとして構成されている必要があります。

<div>


> [!IMPORTANT]
> 以前のバージョンの Lync Server 展開からユーザーを移行する場合は、次の手順を実行する前に、SIP/CSTA ゲートウェイ用に作成した既存の信頼済みアプリケーションエントリ (以前は承認済みのホストエントリ) をすべて削除していることを確認してください。このトピックをご覧ください。 詳細については、「 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Lync Server 2013 で従来の承認済みホストを削除する (オプション)</A>」を参照してください。<BR>伝送制御プロトコル (TCP) 接続を使用して新しいリモート通話コントロールを展開する予定がある場合は、同じように、既存の信頼できるアプリケーションとプールで [<STRONG>サービスの利用制限</STRONG>を設定する] をオンにする必要があります。新しい信頼済みアプリケーションの TCP ポート。



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a>SIP/CSTA ゲートウェイの信頼されたアプリケーションエントリを構成するには

1.  Lync Server 管理シェルが、RTCUniversalServerAdmins グループのメンバーとして、または**CsTrustedApplicationPool**コマンドレットを割り当てた役割ベースのアクセス制御 (RBAC) ロールとしてインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  信頼できるアプリケーションエントリを作成するには、次のいずれかの操作を行います。
    
      - トランスポート層セキュリティ (TLS) 接続の場合は、コマンドプロンプトで次を入力します。
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        次に例を示します。
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - 伝送制御プロトコル (TCP) 接続の場合は、コマンドプロンプトで次を入力します。
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        次に例を示します。
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  信頼できるアプリケーションをプールに追加するには、次のいずれかの操作を行います。
    
      - TLS 接続の場合は、コマンドプロンプトで次を入力します。
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        次に例を示します。
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - TCP 接続の場合は、コマンドプロンプトで次を入力します。
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        次に例を示します。
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  トポロジに加えた公開された変更を実装するには、コマンドプロンプトで次を入力します。
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのリモート通話コントロールの静的ルートの構成](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Lync Server 2013 での SIP/CSTA ゲートウェイの IP アドレスの定義](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

