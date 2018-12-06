---
title: 'Lync Server 2013: Hosted Exchange UM との統合のためのエッジ サーバーの構成'
TOCTitle: Hosted Exchange UM との統合のためのエッジ サーバーの構成
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48274052
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hosted Exchange UM との統合のためのエッジ サーバーの構成

 

_**トピックの最終更新日:** 2015-01-23_

Lync Server 2013 のユーザーに Hosted Exchange ユニファイド メッセージング (UM)のボイス メール機能を提供するには、エッジ サーバーで次の構成タスクを実行する必要があります。

  - フェデレーションのためにエッジ サーバーを構成します。

  - 中央管理ストアのデータをエッジ サーバーにレプリケートし、レプリケーションを確認します。

  - エッジ サーバーのホスティング プロバイダーを作成します。

詳細については、 Lync Server 管理シェルのドキュメントに記載されている次のコマンドレットを参照してください。

  - [Set-CsAccessEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAccessEdgeConfiguration)

  - [New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)


> [!IMPORTANT]
> これらの手順を実行する前に、Hosted Exchange サービス用の外部 DNS SRV レコードを作成する必要があります。詳細については、「<A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Hosted Exchange UM との統合のための DNS SRV レコードを作成する</A>」を参照してください。



## フェデレーションのためにエッジ サーバーを構成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  Set-CsAccessEdgeConfiguration コマンドレットを実行して、フェデレーションのためにサーバーを構成します。たとえば、以下を実行します。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    上述の例では、次のパラメーターが設定されます。
    
      - **UseDnsSrvRouting** は、エッジ サーバーがフェデレーション要求を送信および受信するときに、DNS SRV レコードを使用するように指定します。
    
      - **AllowFederatedUsers** は、内部ユーザーとフェデレーション ドメインからのユーザーとの通信を許可するかどうかを指定します。このプロパティは、さらに内部ユーザーが分割ドメインのシナリオでユーザーと通信できるかどうかも決定します。
    
      - **EnablePartnerDiscovery** では、 Lync Server が Active Directory の許可されたドメイン リストに記載されていないパートナー ドメインを DNS レコードを使用して検出するかどうかを指定します。False に設定されていると、 Lync Server 2013 は許可されたドメイン リストで検出されたドメインとだけフェデレーションを行います。DNS のサービス ルーティングを使用する場合、このパラメーターは必須です。ほとんどの展開環境では、すべてのパートナーに対してフェデレーションが開かれることのないように、この値を False に設定します。

## データをエッジ サーバーにレプリケートし、レプリケーションを確認するには

  - エッジ サーバーへのレプリケーションが完了したことを確認します。手順については、「[Lync Server 2013 での内部サーバーとエッジ サーバーの間の接続の検証](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)」を参照してください。

## エッジ サーバーのホスティング プロバイダーを作成するには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  **New-CsHostingProvider** コマンドレットを実行して、ホスティング プロバイダーを構成します。たとえば、以下を実行します。
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    上述の例では、次のパラメーターが設定されます。
    
      - **Identity** では、作成するホスティング プロバイダーの文字列値から成る一意識別子を指定します。この例では **Fabrikam.com** です。既存のプロバイダーがその ID で既に構成されている場合には、このコマンドは失敗することに注意してください。
    
      - **Enabled** は、ドメインとホスティング プロバイダー間のネットワーク接続が有効になっているかどうかを示します。この値を **True** に設定しないと、2 つの組織間でメッセージを交換することはできません。
    
      - **EnabledSharedAddressSpace** では、共有 SIP アドレス スペース (分割ドメイン) シナリオで、ホスティング プロバイダーが使用されているかどうかを指定します。
        
        > [!NOTE]  
        > <code>EnableSharedAddressSpace</code> を True に設定する前に、フェデレーション SRV レコードを内部で解決してください。このレコードを内部で解決できない場合は、内部 DNS で records, _sipfederationtls._tcp.&lt;domain&gt; と _sip._tls.&lt;domain&gt; を作成する必要があります。これらのレコードは Edge Server のアクセス インターフェイスの外部 IP アドレスをポイントする必要があります。
    
      - **HostsOCSUsers** は、ホスティング プロバイダーが Lync Server 2013 アカウントをホストするために使用されているかどうかを示します。 **False** は、プロバイダーが Microsoft Exchange アカウントなど、別の種類のアカウントをホストしていることを示します。
    
      - **ProxyFQDN** では、ホスティング プロバイダーで使用されているプロキシ サーバーの完全修飾ドメイン名 (FQDN) を指定します。この例では **proxyserver.fabrikam.com** です。この値は変更できません。ホスティング プロバイダーがプロキシ サーバーを変更すると、そのプロバイダーのエントリを削除して再作成する必要があります。
    
      - **IsLocal** は、ホスティング プロバイダーによって使用されるプロキシ サーバーが Lync Server 2013 トポロジ内にあるかどうかを示します。
    
      - **VerficationLevel** は、ホスティング プロバイダーとのメッセージ送受信に対して許可された確認レベルを示します。ホスティング プロバイダーから送信されたメッセージに含まれる確認レベルを信頼する **UseSourceVerification** を指定します。このレベルが指定されない場合は、メッセージは確認できないため拒否されます。

## 関連項目

#### タスク

[エッジ インストール用の Lync Server 2013 のトポロジをエクスポートして外部メディアにコピーする](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  

#### 概念

[Lync Server 2013 での内部サーバーとエッジ サーバーの間の接続の検証](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  

#### その他のリソース

[New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)

