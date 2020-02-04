---
title: リモート通話コントロールの信頼済みアプリケーション エントリを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfaec78b0c7d64308b5899a6e7dc5fa95c1f53fb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757871"
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
> 以前のバージョンの Lync Server 展開からユーザーを移行する場合は、このトピックの手順を実行する前に、SIP/CGI ゲートウェイ用に作成したすべての既存の信頼済みアプリケーションエントリ (以前は承認済みホストエントリと呼ばれます) を削除してください。 詳細については、「 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Lync Server 2013 で従来の承認済みホストを削除する (オプション)</A>」を参照してください。<BR>伝送制御プロトコル (TCP) 接続を使用して新しいリモート通話コントロールを展開する予定がある場合は、新しい信頼済みアプリケーションに対して同じ TCP ポートを使う場合は、[<STRONG>サービスの利用制限</STRONG>を既存の信頼できるアプリケーションとプールに対して制限する] をオンにする必要があります。



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

