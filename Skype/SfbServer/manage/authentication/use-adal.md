---
title: Skype for Business で先進認証 (ADAL) を使用する方法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: この記事では、skype for business Server 2015 の skype for business の累積更新プログラム (Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく 2016) を使用する方法について説明します。
ms.openlocfilehash: 9fe4470e1f8f6e2cd345cd176250fb1ffb16448f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286124"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Skype for Business で先進認証 (ADAL) を使用する方法
 
この記事では、Skype for business Server 2015 の2016年3月の累積更新プログラムに含まれている先進認証 (ADAL) と OAuth 2.0 を使用する方法について説明します。Skype for Business Server 2019 のリリース。
  
## <a name="whats-in-this-article"></a>この記事の内容

[プールで ADAL を構成し、AD FS をセキュリティトークンサーバーとして設定する](use-adal.md#BKMK_Config)
  
[ADAL サインイン有効化のその他のオプション (Office クライアント アプリケーションなど)](use-adal.md#BKMK_Options)
  
[先進認証 / ADAL がサポートされていないクライアント](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a>プールで ADAL を構成し、AD FS をセキュリティトークンサーバーとして設定する
<a name="BKMK_Config"> </a>

このプロセスでは、インストールした AD FS を、ADAL 用に構成されている Skype for Business Server プールに接続します。
  
1. Skype for business server 2015 の2016年3月の累積更新プログラム (またはそれ以降) を Skype for Business Server プールまたは Standard Edition サーバーにインストールします。 に、2016 年 3 月の nm-ocs-13-se-3rd の累積更新プログラムをインストールします (必要に応じて、Windows Update を自動インストールで実行するよう、メンテナンス期間をスケジューリングします)。
    
2. オンプレミスの AD FS サーバーで、セットアップ-AdfsOAuthTrustForSfB スクリプトを[ダウンロード](https://aka.ms/sfbadalscripts)します。 (これは、AD FS ファームまたは独立した AD FS サーバーごとに実行する必要があります。 AD FS プロキシまたは Web アプリケーションプロキシで実行する必要はありません)。
    
3. Skype for Business Server プールまたは Standard Edition サーバーの内部および外部の Web サービスの完全修飾ドメイン名 (Fqdn) をメモしておきます。 この作業はすべての Skype for Business プールに必要です。
    
4. AD FS サーバー上の PowerShell から、(Windows Server 2012 `Setup-AdfsOAuthTrustForSfB.ps1` R2 の場合) または`Setup-Adfs2016OAuthTrustForSfB.ps1` (windows server 2016 以降の場合) を実行します。内部および外部の Web サービスの完全修飾ドメイン名 (Fqdn) に適切な Url を入力する必要があります。 以下は、実行例です。
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    追加のプールについては、「AD FS の Skype for Business Server の証明書利用者信頼にプール Web サービスの Url を手動で追加する必要があります。
    
    > [!IMPORTANT]
    > プールにパッシブ認証を使用して、ADAL も使用することはできません。 ADAL を使用するには、パッシブ認証を無効にする必要があります。 プールの認証を設定する方法の PowerShell コマンドレットについては、[この](https://technet.microsoft.com/en-us/library/gg398396.aspx)記事を参照してください。
  
    > [!TIP]
    > 追加のプールがある場合は、それらを > の証明書利用者信頼の[識別子](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)として追加する必要があります。その場合は、ad fs サーバーに移動して、Ad fs 管理を開きます。 信頼関係\>の証明書利用者信頼を展開します。 表示されている証明書利用者信頼を右クリックし、[プロパティ\>識別子\> ] を右クリックして、追加\>のプール URL を入力し、[追加] をクリックします。 
  
5. Skype for Business Server のフロントエンドまたは Standard Edition server サーバーに戻ります。 ここでは、OAuth サーバーを作成するコマンドレットを実行し、Skype for Business と連携するように OAuth 構成を変更する必要があります。 この手順を実行する必要があるのは、Skype for Business Server の展開ごとに1回だけです。 以下は、実行例です。
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > このコマンドに表示される "Identity" URL は、実際には、[サービス\>のプロパティ] を右クリックしたときに表示される Ad Fs フェデレーションサービスの名前です。 ' Type ' は常に ' ADFS ' であり、' MetadataURL ' は常\<に AD FS サービス名\> + "/FederationMetadata/2007-06/FederationMetadata.xml" となります。 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. 引き続き Skype for Business Server のフロントエンドサーバーまたは Standard Edition サーバーの場合は、ユーザーの SIP アドレスとプールの FQDN を入力して新しい構成をテストします。 この手順を実行する必要があるのは、Skype for Business Server の展開ごとに1回だけです。 以下は、実行例です。
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. メッセージが表示されたら、テストユーザーの資格情報を入力してください。 テストが正常に完了したことを確認します。
    
    > [!NOTE]
    > STS URL が AD FS に*内部*で解決される場合、表示されるプロンプトは**Windows セキュリティ**プロンプトになります。 一方、URL が外部で解決した場合は、[**Sign in**] という名前のプロンプトになります。 通常、ここで望ましいのは [**Windows Security**] プロンプトです。 この動作は、特にフォーム ベース認証 (FBA) を実装していると、一貫しません。
  
また、STS URL が内部の AD FS サーバーに解決され、Windows 統合認証がブラウザーで有効になっている場合は、ブラウザーが明示的に設定されている場合を除き、クライアントアプリケーションにサインインしているユーザーが多すぎると、認証が失敗する可能性があることにも注意してください。特定のブラウザーセキュリティゾーンでユーザーの資格情報を要求するように構成されている。 キオスクを例に考えてみましょう。 オペレーティング システムにログインしたアカウントは、Skype for Business クライアントにログインしているユーザー アカウントとは異なる場合があります。 その場合、ここに記載のエラーが発生することがあります。
    
Internet Explorer でこのブラウザーの設定を確認して変更する\>には、[ツール] \> (また\>は歯車\> ) の [セキュリティ] タブとセキュリティゾーン ([ローカルイントラネット] など) をクリックします。 このダイアログで、[レベルのカスタマイズ] ボタンをクリックし、[設定] ダイアログのリストの最後までスクロールします。 [ユーザー認証\>ログイン\> ] で、[ユーザー名とパスワードの入力を求める] のオプションが表示されます。 Skype for Business クライアントを起動したユーザーが、コンピューターにログインしているユーザーと異なる (アカウントが異なる) キオスクを使用している場合は、グループ ポリシーでこれらのマシンに対してこのオプションをオンにしてテストする必要があります。
    
最後に、重要な点ですが、セキュリティ システムが情報を収集する中で、アカウントの認証または承認を必要とする場合、視覚情報の入力を複数回求められる場合があります。
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>ADAL サインイン有効化のその他のオプション (Office クライアント アプリケーションなど)
<a name="BKMK_Options"> </a>

これで、すべてのプラットフォームで Office 2016 クライアントアプリ用に ADAL が Skype for Business と (自動) 構成されるようになりました。これを Exchange Online で利用することをお勧めします (既定ではオンになっていない場合)。または、Office 2013 クライアントで利用できます。
  
> [!IMPORTANT]
> クライアントアプリからの先進認証のサインインの期待について知る必要がありますか? [Office 2013 および office 2016 クライアントアプリの先進認証のしくみについて](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US)見てみます。 
  
Exchange Online の先進認証を有効にするには、いくつかの PowerShell コマンドレットを実行する必要があります。 Office 2013 クライアントアプリの場合、クライアントコンピューターの一部のレジストリキーを変更する必要があります。
  
- Exchange Online に接続して、次のコマンドレットを実行します。
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- 次のレジストリ キーを、先進認証を有効にしたいデバイスまたはコンピューターごとに設定します。 規模の大きな組織では GPO が必要になります。 GPO を作成する方法については、[この](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)記事の「ドメインに参加しているコンピューターのレジストリを変更するグループポリシーオブジェクトを作成する」を参照してください。
    
|レジストリ キー  <br/> |型  <br/> |値  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
これらのキーが設定されたら、office [365 で多要素認証 (MFA) を使用](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US)するように office アプリを設定します。
  
> [!TIP]
> Office 2013 のデバイスで先進認証を無効にするには、HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL レジストリキーの値を0に設定します。 類似したレジストリキー (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) を使って、Office 2016 のデバイスで先進認証を無効にすることもできます。
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>先進認証 / ADAL がサポートされていないクライアント
<a name="BKMK_Support"> </a>

クライアントのバージョンによっては、OAuth をサポートしていないものがあります。コントロール パネルで Office クライアントのバージョンを確認できます。[プログラムの追加と削除] でバージョン番号を確認したら、以下に記載のバージョンと突き合わせてください。
  
- Office クライアント15.0[0000-4766]。\*
    
- Office クライアント16.0[0000-4293]。\*
    
- Office クライアント 16.0.6001.[0000-1032]
    
- Office クライアント16.0[6000-6224]。\*
    
> [!NOTE]
> ハイブリッドモダン認証は、オンプレミスの Skype for Business でも利用できます。詳細については、「 [skype For business on プレミスを構成してハイブリッド先進認証を使用する方法」を](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication)参照してください。
