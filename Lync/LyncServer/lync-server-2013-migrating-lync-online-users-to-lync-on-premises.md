---
title: Lync Online ユーザーの内部設置型  Lync への移行
TOCTitle: Lync Online ユーザーの内部設置型  Lync への移行
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62247340
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Online ユーザーの内部設置型 Lync への移行

 

_**トピックの最終更新日:** 2016-12-08_


> [!IMPORTANT]
> これらの手順はもともと内部設置型 Lync を展開する前に Lync Online の Lync で有効化されていたユーザー アカウントを移行する場合にのみ実行する必要があります。もともと内部設置型 Lync 用に有効化されていて、後で Lync Online に移動されたユーザーを移動する方法については、「<A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">ハイブリッド Lync Server 2013 展開でユーザーを管理する</A>」を参照してください。<BR>さらに、移動対象のすべてのユーザーは、内部設置型 Active Directory にアカウントを持っている必要があります。



## もともと Lync Online で有効化されていたユーザー アカウントを内部設置型 Lync に移行する

1.  最初に、組織がハイブリッド用に構成されていることを確認します。
    
      - Windows Azure Active Directory 同期ツールをインストールします。詳細については、<http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx> を参照してください。
    
      - Lync Online に対してユーザーがシングル サインオンを使用できるようにするには、Active Directory フェデレーション サービス (<http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>) を使用します。
    
      - 内部設置型展開の Lync Server 管理シェルで次のコマンドレットを入力して、Lync Online のホスティング プロバイダーを作成します。
        
            Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true

           &nbsp;
        
            New-CSHostingProvider -Identity LyncOnline -Name LyncOnlin -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root

2.  内部設置型のエッジ サーバー上で、次の表に示すように、Lync Online への接続を可能にする証明書チェーンがあることを確認します。チェーンのダウンロード用リンク: [https://corp.sts.microsoft.com/Onboard/ADFS\_Onboarding\_Pack/corp\_sts\_certs.zip](https://corp.sts.microsoft.com/onboard/adfs_onboarding_pack/corp_sts_certs.zip) 。
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>証明書</th>
    <th>証明書ストア</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Baltimore CyberTrust Root</p></td>
    <td><p>信頼されたルート CA</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft Internet Authority (新しい CA 証明書)</p></td>
    <td><p>中間 CA</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine Auth CA2 (新規発行 CA2)</p></td>
    <td><p>中間 CA</p></td>
    </tr>
    </tbody>
    </table>


3.  内部設置型 Active Directory で、内部設置型 Lync 用に対象となるユーザー アカウントを有効にします。ユーザーごとにこの操作を行うには、次のコマンドレットを入力します。
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    または、ファイルからユーザー名を読み込んで Enable-CsUser コマンドレットへの入力として与えるスクリプトを作成することもできます。
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  DirSync を実行して、Lync Online ユーザーを更新された内部設置型 Lync ユーザーと同期します。

5.  すべての SIP トラフィックが内部設置型 Lync に転送されるように、いくつかの DNS レコードを更新します。
    
      - 内部設置型リバース プロキシ サーバーの FQDN を指すように **lyncdiscover.contoso.com** A レコードを更新します。
    
      - 内部設置型 Lync のアクセス エッジ サービスのパブリック IP または VIP アドレスを解決するように ***\_sip*.\_tls.contoso.com** SRV レコードを更新します。
    
      - 内部設置型 Lync のアクセス エッジ サービスのパブリック IP または VIP アドレスを解決するように ***\_sipfederationtls*.\_tcp.contoso.com** SRV レコードを更新します。
    
      - 組織でスプリット DNS ("スプリットブレイン DNS" と呼ばれることもあります) を使用している場合は、社内 DNS ゾーンを介して名前が解決されるユーザーがフロント エンド プールに転送されることを確認してください。

6.  `Get-CsUser` コマンドレットを入力して、移行するユーザーのいくつかのプロパティを調べます。HostingProviderProxyFQDN が `"sipfed.online.lync.com"` に設定されていること、および SIP アドレスが適切に設定されていることを確認します。

7.  Lync Online ユーザーを内部設置型 Lync に移動します。
    
    単独のユーザーを移動するには、次のように入力します。
    
        $cred = Get-Credential

       &nbsp;
    
        Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
    
    **Get-CsUSer** コマンドレットに –Filter パラメーターを使用して、複数のユーザーを移動することができます。このパラメーターにより、特定のプロパティを持つユーザーを選択できます。たとえば、{Hosting Provider –eq “sipfed.online.lync.om”} をフィルターに設定してすべての Lync Online ユーザーを選択します。さらに、次に示すように、返されたユーザーをパイプを使用して、**Move-CsUSer** コマンドレットに渡すことができます。
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    **HostedMigrationOverrideUrl** パラメーターの URL には、ホスティング型移行サービスが実行されているプールへの URL を次の形式で指定する必要があります。*Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*
    
    ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウントの Lync Online コントロール パネルの URL を表示することで確認できます。
    
    ## Office 365 テナントのホスティング型移行サービスの URL を確認するには
    
    1.  管理者として Office 365 テナントにログインします。
    
    2.  \[**Lync 管理センター**\] を開きます。
    
    3.  \[**Lync 管理センター**\] が表示されたら、**lync.com** の近くのアドレス バーの URL を選択してコピーします。URL は、次のような書式です。
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  URL の **webdir** を **admin** で置き換えると、次のようになります。
        
        `https://admin0a.online.lync.com`
    
    5.  URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**
        
        以上の手順によって、**HostedMigrationOverrideUrl** の値を持った URL は次のようになります。
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]
    > rtcxds データベースのトランザクション ログ ファイルの既定の最大サイズは 16 GB です。一度に多くのユーザーを移行する場合 (特にミラーリングを有効にしている場合) は、このサイズでは不十分な可能性があります。これに対処するには、ファイル サイズを大きくするか、ログ ファイルを定期的にバックアップします。詳細については、<a href="http://support.microsoft.com/kb/2756725" class="uri">http://support.microsoft.com/kb/2756725</a> を参照してください。


8.  この手順は省略可能です。Exchange 2013 Online と統合する必要がある場合は、追加のホスティング プロバイダーが必要になります。詳細については、[社内の Lync Server 2013 と Exchange Online との統合の構成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md) を参照してください。

9.  ユーザーが移動されます。次の表に示すユーザーの属性の値が適切であることを確認するために、次のコマンドレットを入力します。
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Active Directory 属性</th>
    <th>属性名</th>
    <th>Lync Online ユーザーに適切な値</th>
    <th>内部設置型 Lync ユーザーに適切な値</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV:</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>sRTCSIP-UserEnabled</p></td>
    <td><p>Enabled</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. 移動された各ユーザーは、Lync をいったんログアウトしてからログインし直す必要があります。ユーザーは、ログイン時に連絡先リストを確認し、必要に応じて連絡先を追加する必要があります。
    
    スケジュールされていた会議は、Lync Online から内部設置型 Lync に移行されないことに注意してください。ユーザーは、移動後にこれらの会議をスケジュールし直す必要があります。
    
    DNS レコードが更新され、すべてのユーザーが内部設置型 Lync に転送されるようになると、HostingProvider 属性により、Lync ユーザーは SRV レコードを使用するか、または Online プロバイダー "sipfed.online.lync.com" に転送されます。

