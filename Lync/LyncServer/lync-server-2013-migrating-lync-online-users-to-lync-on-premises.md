---
title: 'Lync Server 2013: lync Online ユーザーの Lync オンプレミスへの移行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f10aedf2a183e7ad965ba36ea0610fc02b93dfce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a>Lync Online ユーザーを lync Server 2013 の Lync オンプレミスに移行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-11-13_

<div class="">


> [!IMPORTANT]  
> これらの手順は、lync オンプレミスを展開する前に lync Online の Lync で最初に有効にされたユーザーアカウントを移行する場合にのみ必要です。 最初に Lync Online が有効になっていて、後で Lync Online に移動されたユーザーを移動するには、「<A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">ハイブリッド Lync Server 2013 展開でユーザーを管理</A>する」を参照してください。<BR>さらに、移動するすべてのユーザーは、オンプレミスの Active Directory にアカウントを持っている必要があります。



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a>Lync Online で最初に有効にされるユーザーアカウントを、オンプレミスの Lync に移行する

1.  最初に、組織がハイブリッド用に構成されていることを確認します。
    
      - Azure Active Directory 同期ツールをインストールします。 詳細については、「<https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>」を参照してください。
    
      - ユーザーが Lync Online のシングルサインオンを使用できるようにするには、Active Directory <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>フェデレーションサービスをインストールします。
    
      - オンプレミス展開で、Lync Server 管理シェルの次のコマンドレットを入力して、Lync Online のホスティングプロバイダーを作成します。
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  オンプレミスのエッジサーバーに、次の表に示すように、Lync Online への接続を可能にする証明書チェーンがあることを確認します。 このチェーンは、ここからダウンロードできます。https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb


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
    <td><p>Microsoft インターネット権威 (新規 CA 証明書)</p></td>
    <td><p>中間 CA</p></td>
    </tr>
    <tr class="odd">
    <td><p>MSIT Machine Auth CA2 (新しい発行 CA2)</p></td>
    <td><p>中間 CA</p></td>
    </tr>
    </tbody>
    </table>

3.  オンプレミスの Active Directory で、該当する Lync オンプレミスのユーザーアカウントを有効にします。 この操作は、次のコマンドレットを入力することにより、個々のユーザーに対して行うことができます。
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    または、ファイルからユーザー名を読み取り、それをユーザーコマンドレットへの入力として提供するスクリプトを作成できます。
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  DirSync を実行して、Lync Online ユーザーと、更新された Lync オンプレミスユーザーを同期します。

5.  一部の DNS レコードを更新して、すべての SIP トラフィックを社内の Lync に転送します。
    
      - **Lyncdiscover.contoso.com** A レコードを更新して、オンプレミスのリバースプロキシサーバーの FQDN を指すようにします。
    
      - ***\_Sip * を更新し\_ます。** Lync オンプレミスのアクセスエッジサービスのパブリック IP または VIP アドレスに解決する Tls.contoso.com SRV レコード。
    
      - ***\_Sipfederationtls * を更新し\_ます。** Lync オンプレミスのアクセスエッジサービスのパブリック IP または VIP アドレスに解決する Tcp.contoso.com SRV レコード。
    
      - 組織で分割 DNS ("スプリットブレイン DNS" と呼ばれることもあります) を使用している場合は、内部 DNS ゾーンを使用して名前を解決するユーザーがフロントエンドプールに転送されることを確認してください。

6.  `Get-CsUser`コマンドレットを入力して、移動するユーザーに関するいくつかのプロパティを確認します。 HostingProviderProxyFQDN がに`"sipfed.online.lync.com"`設定され、SIP アドレスが正しく設定されていることを確認する必要があります。

7.  Lync Online ユーザーをオンプレミスの Lync に移動します。
    
    単一のユーザーを移動するには、次のように入力します。
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    -Filter パラメーターを指定して**Get-help ユーザー**コマンドレットを使用して、特定のプロパティを持つユーザーを選択すると、複数のユーザーを移動できます。 たとえば、{ホスティングプロバイダー– eq "sipfed.online.lync.om"} にフィルターを適用することにより、すべての Lync Online ユーザーを選択することができます。 その後、次に示すように、返されたユーザーを移動して、 **csuser**コマンドレットにパイプ処理できます。
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    **HostedMigrationOverrideUrl**パラメーターに指定する url の形式は、次の形式で、ホストされている移行サービスが実行されているプールへの url である必要があります。 *Https://\<pool FQDN\>/HostedMigration/hostedmigrationService.svc*。
    
    Office 365 テナントアカウントの Lync Online コントロールパネルの URL を表示することによって、ホストされた移行サービスへの URL を確認できます。
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Office 365 テナントのホスト型移行サービスの URL を確認するには
    
    1.  Office 365 テナントに管理者としてログインします。
    
    2.  **Lync 管理センター**を開きます。
    
    3.  **Lync 管理センター**が表示されたら、アドレスバーの URL を選択して、 **lync.com**までコピーします。 URL の例は、次のようになります。
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  URL 内の**webdir**を**管理者**に置き換えます。結果は次のようになります。
        
        `https://admin0a.online.lync.com`
    
    5.  次の文字列を URL: **/HostedMigration/hostedmigrationservice.svc**に追加します。
        
        生成される URL は**HostedMigrationOverrideUrl**の値で、次のようになります。
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > Rtcxds データベースのトランザクションログファイルの既定の最大サイズは 16 GB です。 多数のユーザーを同時に移動する場合は、特にミラーリングを有効にしている場合は、この値が十分ではない可能性があります。 これを回避するには、ファイルサイズを増やすか、またはログファイルを定期的にバックアップします。 詳細については<A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>、「」を参照してください。

    
    </div>

8.  この手順は省略可能です。 Exchange 2013 Online と統合する必要がある場合は、追加のホスティングプロバイダーを使用する必要があります。 詳細については、「[オンプレミスの Lync Server 2013 と Exchange Online との統合の構成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)」を参照してください。

9.  ユーザーが移動されました。 ユーザーが次の表に示す属性の値を正しいかどうかを確認するには、次のコマンドレットを入力します。
    
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
    <th>Lync オンプレミスユーザーの正しい値</th>
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
    <td><p>msRTCSIP-UserEnabled</p></td>
    <td><p>有効</p></td>
    <td><p>True</p></td>
    <td><p>True</p></td>
    </tr>
    </tbody>
    </table>


10. 移動した各ユーザーは、Lync からログアウトしてログインし直す必要があります。 ログインするときに、連絡先リストを確認し、必要に応じて連絡先を追加する必要があります。
    
    予約済みの会議は、Lync Online から Lync オンプレミスに移行されないことに注意してください。 ユーザーは、移動後にこれらの会議を再度スケジュールする必要があります。
    
    DNS レコードが更新され、すべてのユーザーがオンプレミスにリダイレクトされると、HostingProvider 属性によって Lync ユーザーは SRV レコードを使用するか、またはオンラインプロバイダー "sipfed.online.lync.com" に直接接続します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

