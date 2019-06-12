---
title: 'Lync Server 2013: lync Online ユーザーをオンプレミスの Lync に移行する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d33888069b00eaf8a4d743f1e6ed3937d7a442bc
ms.sourcegitcommit: 5895afd0d5752a6ea1ace68d613f86c68eae8bdb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/11/2019
ms.locfileid: "34857492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Lync Online ユーザーをオンプレミスの lync Server に移行する2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> 以下の手順は、lync をオンプレミスで展開する前に、lync Online の Lync で最初に有効になっていたユーザーアカウントを移行する場合にのみ必要です。 初めて Lync をオンプレミスで有効にしたユーザーを移動し、後で Lync Online に移行するには、「<A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">ハイブリッド Lync Server 2013 展開でユーザーを管理</A>する」を参照してください。<BR>さらに、移動対象のすべてのユーザーは、オンプレミス Active Directory にアカウントを持っている必要があります。



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>初めて Lync Online で有効化されるユーザーアカウントをオンプレミスの Lync に移行する

1.  最初に、組織がハイブリッド用に構成されていることを確認します。
    
      - Azure Active Directory 同期ツールをインストールします。 詳細については<http://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>、を参照してください。
    
      - Lync Online でユーザーがシングルサインオンを使用できるようにするには、Active Directory <http://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>フェデレーションサービスをインストールします。
    
      - オンプレミスの展開の Lync Server 管理シェルで、次のコマンドレットを入力して、Lync Online のホスティングプロバイダーを作成します。
        
           ```
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  オンプレミスエッジサーバーで、次の表に示すように、Lync Online への接続を有効にする証明書チェーンがあることを確認します。 このチェーンは次のページからダウンロードできます。https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


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

3.  オンプレミスの Active Directory で、オンプレミスの Lync の影響を受けるユーザーアカウントを有効にします。 ユーザーごとにこの操作を行うには、次のコマンドレットを入力します。
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    または、ファイルからユーザー名を読み込んで Enable-CsUser コマンドレットへの入力として与えるスクリプトを作成することもできます。
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  DirSync を実行して、Lync Online ユーザーと、更新された Lync オンプレミスユーザーを同期します。

5.  すべての SIP トラフィックがオンプレミスの Lync に転送されるように、いくつかの DNS レコードを更新します。
    
      - オンプレミスのリバース プロキシ サーバーの FQDN を指すように **lyncdiscover.contoso.com** A レコードを更新します。
    
      - ***\_Sip * を更新し\_ます。** オンプレミスの Lync のアクセスエッジサービスのパブリック IP または VIP アドレスに解決する Tls.contoso.com SRV レコード。
    
      - * Sipfederationtls * を更新して**\_ください。\_** オンプレミスの Lync のアクセスエッジサービスのパブリック IP または VIP アドレスに解決する Tcp.contoso.com SRV レコード。
    
      - 組織でスプリット DNS ("スプリットブレイン DNS" と呼ばれることもあります) を使用している場合は、社内 DNS ゾーンを介して名前が解決されるユーザーがフロント エンド プールに転送されることを確認してください。

6.  移動する`Get-CsUser`ユーザーに関する一部のプロパティを確認するコマンドレットを入力します。 HostingProviderProxyFQDN がに`"sipfed.online.lync.com"`設定されていて、SIP アドレスが正しく設定されていることを確認する必要があります。

7.  Lync Online ユーザーをオンプレミスの Lync に移動します。
    
    単独のユーザーを移動するには、次のように入力します。
    
       ```
       $cred = Get-Credential
       ```
    
       ```
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    複数のユーザーを移動するには**** 、-Filter パラメーターを指定して、特定のプロパティを持つユーザーを選択します。 たとえば、{ホスティングプロバイダー– eq "sipfed.online.lync.om"} をフィルター処理することによって、すべての Lync Online ユーザーを選ぶことができます。 次に示すように、返されたユーザーを**移動-CsUSer**コマンドレットにパイプすることができます。
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    **HostedMigrationOverrideUrl**パラメーターに指定する url の形式は、次の形式で、ホステッド移行サービスが実行されているプールへの url である必要があります。 *Https://\<pool FQDN\>/HostedMigration/hostedmigrationService*。
    
    ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウント用の Lync Online コントロール パネルの URL を表示することで確認できます。
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Office 365 テナントのホスティング型移行サービスの URL を確認するには
    
    1.  管理者として Office 365 テナントにログインします。
    
    2.  **Lync 管理センター**を開きます。
    
    3.  **Lync 管理センター**が表示されたら、アドレスバーの URL を選択して**lync.com**にコピーします。 URL は、次のような書式です。
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  URL の **webdir** を **admin** に置き換えると、次のようになります。
        
        `https://admin0a.online.lync.com`
    
    5.  URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**
        
        以上の手順によって、**HostedMigrationOverrideUrl** の値を持った URL は次のようになります。
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > rtcxds データベースのトランザクション ログ ファイルの既定の最大サイズは 16 GB です。 一度に多くのユーザーを移行する場合 (特にミラーリングを有効にしている場合) は、このサイズでは不十分な可能性があります。 これに対処するには、ファイル サイズを大きくするか、ログ ファイルを定期的にバックアップします。 詳細については<A class=uri href="http://support.microsoft.com/kb/2756725">http://support.microsoft.com/kb/2756725</A>、を参照してください。

    
    </div>

8.  この手順は省略可能です。 Exchange 2013 Online と統合する必要がある場合は、追加のホスティング プロバイダーが必要になります。 詳細については、「[オンプレミスの Lync Server 2013 と Exchange Online との統合を構成する](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)」を参照してください。

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
    <th>Lync Online ユーザーの正しい値</th>
    <th>Lync on プレミスユーザーの正しい値</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>msRTCSIP-DeploymentLocator</p></td>
    <td><p>HostingProvider</p></td>
    <td><p>sipfed.online.lync.com</p></td>
    <td><p>SRV</p></td>
    </tr>
    <tr class="even">
    <td><p>msRTCSIP-PrimaryUserAddress</p></td>
    <td><p>SIPAddress</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    <td><p>sip:userName@contoso.com</p></td>
    </tr>
    <tr class="odd">
    <td><p>Msrtcsip-userenabled true-UserEnabled</p></td>
    <td><p>Enabled</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. 移動された各ユーザーは、Lync からログアウトしてから、もう一度ログインする必要があります。 ユーザーは、ログイン時に連絡先リストを確認し、必要に応じて連絡先を追加する必要があります。
    
    スケジュールされた会議は、Lync Online からオンプレミスの Lync に移行されないことに注意してください。 ユーザーは、移動後にこれらの会議をスケジュールし直す必要があります。
    
    DNS レコードが更新され、すべてのユーザーがオンプレミスに転送されると、HostingProvider 属性によって、Lync ユーザーは SRV レコードを使用するように指示されるか、オンラインのプロバイダー "sipfed.online.lync.com" に転送されます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

