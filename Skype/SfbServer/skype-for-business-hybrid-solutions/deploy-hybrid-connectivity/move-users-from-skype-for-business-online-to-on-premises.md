---
title: ビジネス上でオンラインに設置型の Skype のユーザーの移動
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 概要では、Skype で設置型のオンラインでのビジネス サーバーのユーザー アカウントを移動する方法について説明します。
ms.openlocfilehash: 033fb0a3a2cce6c763113ca94ea8af3c652cbbf5
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374359"
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a>ビジネス上でオンラインに設置型の Skype のユーザーの移動

**の概要:** Skype で設置型のオンラインでのビジネス サーバーのユーザー アカウントを移動する方法について説明します。

ユーザーがオンライン ホームし、設置型では、互いに検出可能なことを確認するには、社内設置型のオンラインでのユーザー アカウントを移動する必要があります。 互いに発見可能な状態には、すべてのユーザーは、オンプレミスの Active Directory に存在必要があります。 詳細については、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)を参照してください。 場合など、社内のユーザーがオンラインに移動する場合。

- 設置型で作成し、クラウドへの移行が必要なユーザーは、新しいがあります。

- 組織は、Skype をビジネス サーバーに展開する前に、Skype をオンライン ビジネスの展開。 したがって、最初に、クラウドで作成されたユーザーがいるし、オンライン ビジネスの Skype を移動する前に社内に移動する必要があります。

このトピックでは、2 つのシナリオについて説明します。

- [オンラインのユーザーを移動、ユーザーが最初にオンライン-への設置型](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)

- [オンライン ユーザーの移動 (ユーザーの社内には、元々 あった) に設置型の](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)

## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a>オンラインのユーザーを移動、ユーザーが最初にオンライン-への設置型
<a name="BKMK_originallyonline"> </a>

このセクションは、ユーザーが Active Directory に施設内で、アカウントを持っていないユーザーがユーザーが作成され、オンラインで有効になっているだけに適用されます。

オンライン ユーザーをオンプレミス環境に移動する前に、次のすべての条件が満たされていることを確認します。

- オンプレミス環境は、完全に展開および検証されている必要があります。 詳細については、 [Lync Server 2013 の展開](https://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx)または[展開の Skype](../../deploy/deploy.md)ビジネス サーバー 2015 のどちらのバージョンによっては、設置型で使用しているを参照してください。

- オンライン、テナントは、PowerShell のリモート アクセス用に構成しなければなりません。

    これを行うには、ここに到達することができる Windows PowerShell の最初にコネクタ モジュールのオンライン ビジネスの Skype をインストール: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911)。

    モジュールをインストールした後は、Skype のビジネス サーバー管理シェルの次のコマンドレットを入力してリモート セッションを確立できます。

  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    PowerShell を Skype でオンライン ビジネスでの使用についての詳細については、 [Windows PowerShell には、コンピューターの設定](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)を参照してください。

- 共有 SIP アドレス スペースのオンライン、テナントを構成する必要があります。 これを行うには、まずリモート Powershell セッション Skype でのオンライン ビジネスです。 続いて、次のコマンドレットを実行します。

  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > 最終版では、オンラインに移動するまで、"True"とユーザーを維持するのには SharedSipAddressSpace 属性のニーズは、施設内に残ります。

手順が終了したら後、は、次の手順で説明したようにユーザー アカウントを移行できます。

### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a>最初の設置型の展開にオンライン有効になっているユーザー アカウントを移動します。

1. 最初に、組織がハイブリッド用に構成されていることを確認します (Azure Active Directory Connect と同期ツールを含む)。 詳細については、[サーバーのビジネスとオンライン ビジネスの Skype の Skype 間のハイブリッド接続の計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)を参照してください。

   - 設置型展開、ビジネス サーバー管理シェルには、Skype のオンライン ビジネスの Skype のホスティング プロバイダーを作成するのには、次のコマンドレットを入力します。 Identity および Name パラメーターには、必要な任意の値を使用できます。

   ```
   Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
   ```

   ```
   New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

2. 確認、設置型のエッジ トランスポート サーバー上のビジネス オンラインでは、Skype への接続を有効にする証明書チェーン、次の表に示すように。 このチェーンは、ここをダウンロードすることができます: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip)。

|**証明書**|**証明書ストア**|
|:-----|:-----|
|Baltimore CyberTrust Root  <br/> |信頼されたルート CA  <br/> |
|Microsoft Internet Authority (新しい CA 証明書)  <br/> |中間 CA  <br/> |
|MSIT Machine Auth CA2 (新規発行 CA2)  <br/> |中間 CA  <br/> |

3. オンプレミスの Active Directory では、社内のビジネス サーバー 2015 の Skype の影響を受けるユーザー アカウントを有効にします。 ユーザーごとにこの操作を行うには、次のコマンドレットを入力します。

   ```
   Enable-CsUser
   -Identity "username "
   -SipAddress "sip: username @contoso.com"
   -HostingProviderProxyFqdn "sipfed.online.lync.com"
   ```

    または、ファイルからユーザー名を読み込んで Enable-CsUser コマンドレットへの入力として与えるスクリプトを作成することもできます。

   ```
   Enable-CsUser
   -Identity $Identity
   -SipAddress $SipAddress
   -HostingProviderProxyFqdn "sipfed.online.lync.com"
   ```

4. オンプレミスで更新されたユーザーとオンラインのユーザーを同期します。 詳細については、[ディレクトリの統合ツール](https://go.microsoft.com/fwlink/p/?LinkId=530320)を参照してください。

5. 設置型展開へのすべての SIP トラフィックをダイレクトするのには次の DNS レコードを更新します。

   - オンプレミスのリバース プロキシ サーバーの FQDN を指すように **lyncdiscover.contoso.com** A レコードを更新します。

   - 更新、 ** *_sip* 。 _tls.contoso.com** Lync の設置型のアクセス エッジ サービスのパブリック IP または VIP アドレスに解決するには、SRV レコード。

   - 更新、 ** *_sipfederationtls* 。 _tcp.contoso.com**のビジネス サーバー 2015 設置、Skype のアクセス エッジ サービスのパブリック IP または VIP アドレスに解決するには、SRV レコード。

   - 組織で使用するには、DNS が (「DNS の分散管理」とも呼ばれます) を分割する場合は、内部の DNS ゾーンで名前を解決するユーザーは、フロント エンド プールに割り当て、を確認します。

6. 型、`Get-CsUser`を移動するユーザーに関するいくつかのプロパティを確認するコマンドレットです。 HostingProviderProxyFQDN が `"sipfed.online.lync.com"` に設定されていること、および SIP アドレスが適切に設定されていることを確認します。

7. 設置型のオンライン ユーザーを移動します。

    単独のユーザーを移動するには、次のように入力します。

   ```
   $cred = Get-Credential
   Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
   ```

    **Get CsUSer**コマンドレットを使用して複数のユーザーを移動することができますフィルター パラメーターを指定する特定のプロパティを使用してユーザーを選択します。 たとえば、{プロバイダーをホストしている eq"sipfed.online.lync.om"} のフィルターを使用して、オンラインのすべてのユーザーを選択できます。 コマンドレットにパイプ**移動 CsUSer**コマンドレットでは、返されるユーザーは、次のようにします。

   ```
   Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
   ```

    **HostedMigrationOverrideUrl**パラメーターは次の形式で、ホストの移行サービスが実行されているプールへの URL である必要があります用に指定された URL の形式: _Https://\<プールの FQDN\>/HostedMigration/hostedmigrationService.svc_。

    ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウント用の Lync Online コントロール パネルの URL を表示することで確認できます。

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Office 365 テナントのホスティング型移行サービスの URL を確認するには

1. 管理者として Office 365 テナントにログインします。

2. [**Skype for Business 管理センター**] を開きます。

3. [**Skype for Business 管理センター**] が表示されたら、**lync.com** の近くのアドレス バーの URL を選択してコピーします。URL は、次のような書式です。

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. URL の **webdir** を **admin** に置き換えると、次のようになります。

     `https://admin0a.online.lync.com`

5. URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**

    結果の URL は、 **HostedMigrationOverrideUrl**の値は、次のようになります。

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

    > [!NOTE]
    > rtcxds データベースのトランザクション ログ ファイルの既定の最大サイズは 16 GB です。 これがあります十分な大きさを一度に多数のユーザーを移動する場合特に有効になっているミラー化がある場合。 これに対処するには、ファイル サイズを大きくするか、ログ ファイルを定期的にバックアップします。 詳細についてを参照してください[https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725)。

6. この手順は省略可能です。 Exchange 2013 Online と統合する必要がある場合は、追加のホスティング プロバイダーが必要になります。 詳細については、[設置型の Skype ビジネス サーバー 2015 と Outlook Web App の構成の統合](../../deploy/integrate-with-exchange-server/outlook-web-app.md)を参照してください。

7. ユーザーが移動されます。次の表に示すユーザーの属性の値が適切であることを確認するために、次のコマンドレットを入力します。

   ```
   Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
   ```

| **Active Directory 属性**     | **属性名**     | **オンライン ユーザーに適切な値** | **オンプレミス ユーザーの適切な値** |
|:-----------------------------------|:-----------------------|:----------------------------------|:----------------------------------------|
| msRTCSIP DeploymentLocator  <br/>  | HostingProvider  <br/> | sipfed.online.lync.com  <br/>     | SRV  <br/>                             |
| msRTCSIP PrimaryUserAddress  <br/> | SIPAddress  <br/>      | sip:userName@contoso.com  <br/>   | sip:userName@contoso.com  <br/>         |
| msRTCSIP UserEnabled  <br/>        | Enabled  <br/>         | True  <br/>                       | True  <br/>                             |

10. 移動された各ユーザーは、いったんログアウトしてからログインし直す必要があります。ユーザーは、ログイン時に連絡先リストを確認し、必要に応じて連絡先を追加する必要があります。

    スケジュールされていた会議は、オンラインからオンプレミスに移行されないことに注意してください。ユーザーは、移動後にこれらの会議をスケジュールし直す必要があります。

    DNS レコードが更新され、すべてのユーザーは、オンプレミスに割り当て、HostingProvider 属性にログオンする SRV レコードを使用するか、問い合わせオンライン プロバイダー"sipfed.online.lync.com"にします。

## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a>オンライン ユーザーの移動 (ユーザーの社内には、元々 あった) に設置型の
<a name="BKMK_originallyonprem"> </a>

このセクションでは、作成し設置型の展開を有効にし、設置型展開からオンラインへ移動されたユーザーにのみ適用されます。

- ユーザーからに移動する Skype ビジネス オンラインの設置、お客様の環境の値を修正するのには**Id**と**ターゲット**のパラメーターの値を置き換えるには、次のコマンドレットを実行します。

  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

**HostedMigrationOverrideUrl**パラメーターに指定された URL の形式は次の形式で、ホストの移行サービスが実行されているプールへの URL である必要があります。

 _Https://\<プールの FQDN\>/HostedMigration/hostedmigrationService.svc_。 ホスティング型移行サービスへの URL は、ご使用の Office 365 テナント アカウント用の Lync Online コントロール パネルの URL を表示することで確認できます。

### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>Office 365 テナントのホスティング型移行サービスの URL を確認するには

1. 管理者として Office 365 テナントにログインします。

2. [**Skype for Business 管理センター**] を開きます。

3. [**Skype for Business 管理センター**] が表示されたら、**lync.com** の近くのアドレス バーの URL を選択してコピーします。URL は、次のような書式です。

     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`

4. URL の **webdir** を **admin** に置き換えると、次のようになります。

     `https://admin0a.online.lync.com`

5. URL に以下の文字列を付加します。**/HostedMigration/hostedmigrationservice.svc**

    結果の URL は、 **HostedMigrationOverrideUrl**の値は、次のようになります。

     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`


