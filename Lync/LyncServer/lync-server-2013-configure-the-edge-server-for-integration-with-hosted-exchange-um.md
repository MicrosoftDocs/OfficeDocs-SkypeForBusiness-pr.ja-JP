---
title: ホストされた Exchange UM との統合のためにエッジサーバーを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0779612ca4ebf33757f5d392d1619211aeb4a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a>ホストされた Exchange UM との統合のためにエッジサーバーを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-01-23_

ホストされた Exchange ユニファイドメッセージング (UM) で Lync Server 2013 ユーザーにボイスメール機能を提供するには、エッジサーバーで次の構成タスクを実行する必要があります。

  - フェデレーションのためにエッジ サーバーを構成します。

  - 中央管理ストアのデータをエッジサーバーにレプリケートし、レプリケーションを確認します。

  - エッジ サーバーのホスティング プロバイダーを作成します。

詳細については、以下のコマンドレットの Lync Server 管理シェルのドキュメントを参照してください。

  - [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [新規-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

<div>


> [!IMPORTANT]
> これらの手順を実行する前に、Hosted Exchange サービス用の外部 DNS SRV レコードを作成する必要があります。 詳細については、「ホストされ<A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">た EXCHANGE UM との統合のための DNS SRV レコードを作成する</A>」を参照してください。



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a>フェデレーションのためにエッジ サーバーを構成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  Set-CsAccessEdgeConfiguration コマンドレットを実行して、フェデレーションのためにサーバーを構成します。たとえば、以下を実行します。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    上述の例では、次のパラメーターが設定されます。
    
      - **UseDnsSrvRouting** は、エッジ サーバーがフェデレーション要求を送信および受信するときに、DNS SRV レコードを使用するように指定します。
    
      - **AllowFederatedUsers** は、内部ユーザーとフェデレーション ドメインからのユーザーとの通信を許可するかどうかを指定します。 このプロパティは、さらに内部ユーザーが分割ドメインのシナリオでユーザーと通信できるかどうかも決定します。
    
      - **Enablepartnerdiscovery** Lync SERVER が DNS レコードを使用して、Active Directory 許可ドメインリストに一覧表示されていないパートナードメインの検出を試行するかどうかを指定します。 False の場合、Lync Server 2013 は、許可されたドメインリストにあるドメインとのみフェデレーションを行います。 DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。 ほとんどの展開環境では、すべてのパートナーに対してフェデレーションが開かれることのないように、この値を False に設定します。

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a>データをエッジ サーバーにレプリケートし、レプリケーションを確認するには

  - エッジ サーバーへのレプリケーションが完了したことを確認します。 手順については、「 [Lync Server 2013 の内部サーバーとエッジサーバーの間の接続を確認](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)する」を参照してください。

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a>エッジ サーバーのホスティング プロバイダーを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

2.  **New-CsHostingProvider** コマンドレットを実行して、ホスティング プロバイダーを構成します。 たとえば、以下を実行します。
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    上述の例では、次のパラメーターが設定されます。
    
      - **Identity** では、作成するホスティング プロバイダーの文字列値から成る一意識別子を指定します。この例では **Fabrikam.com** です。 既存のプロバイダーがその ID ですでに構成されている場合には、このコマンドは失敗することに注意してください。
    
      - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。 この値を **True** に設定しないと、2 つの組織間でメッセージを交換することはできません。
    
      - **EnabledSharedAddressSpace** では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。
        
        <div>
        

        > [!NOTE]
        > True に設定<CODE>EnableSharedAddressSpace</CODE>する前に、フェデレーション SRV レコードを内部で解決してください。 このレコードを内部で解決できない場合は、レコード _sipfederationtls _tcp を作成する必要があります。&lt;ドメイン&gt;および _sip _tls。&lt;内部&gt; DNS のドメイン。 これらのレコードは、エッジサーバーのアクセスインターフェイスの外部 IP アドレスを指している必要があります。

        
        </div>
    
      - **Hostているユーザー**は、ホスティングプロバイダーが Lync Server 2013 アカウントをホストするために使用されるかどうかを示します。 **False** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。
    
      - **ProxyFQDN** では、ホスティング プロバイダーで使用されているプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。この例では **proxyserver.fabrikam.com** です。 この値は変更できません。ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。
    
      - **Islocal**は、ホスティングプロバイダーによって使用されるプロキシサーバーが Lync server 2013 トポロジ内に含まれているかどうかを示します。
    
      - **VerficationLevel** は、ホスティング プロバイダーとのメッセージ送受信に対して許可された確認レベルを示します。 ホスティング プロバイダーから送信されたメッセージに含まれる確認レベルを信頼する **UseSourceVerification** を指定します。 このレベルが指定されていないと、メッセージは確認不能として拒否されます。

</div>

<div>

## <a name="see-also"></a>関連項目


[エッジインストールのために Lync Server 2013 トポロジをエクスポートして外部メディアにコピーする](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[Lync Server 2013 の内部サーバーとエッジサーバーの間の接続を確認する](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


[新規-CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

