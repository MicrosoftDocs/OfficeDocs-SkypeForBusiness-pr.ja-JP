---
title: Skype for Business で先進認証 (ADAL) を使用する方法
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: 現代の認証 (これは、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) 2016年 3 月を参照しているを使用する方法を説明するビジネス サーバー 2015 の Skype のビジネス用の Skype 用の累積的な更新です。
ms.openlocfilehash: 70878092baaee9414c8acada21a89ceea6587658
ms.sourcegitcommit: 6251a2c659909c3972ca2ea0a2bcdab4f334df34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2018
ms.locfileid: "25692762"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>How to use Modern Authentication (ADAL) with Skype for Business
 
現代の認証 (これは、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) 2016年 3 月を参照しているを使用する方法を説明するビジネス サーバー 2015 年または最初から、Skype のビジネス用の Skype 用の累積的な更新ビジネス サーバー 2019 の Skype をリリースします。
  
## <a name="whats-in-this-article"></a>この記事の内容

[プールで ADAL を構成し、ADFS をセキュリティ トークン サーバーとして設定する](use-adal.md#BKMK_Config)
  
[ADAL サインイン有効化のその他のオプション (Office クライアント アプリケーションなど)](use-adal.md#BKMK_Options)
  
[先進認証 / ADAL がサポートされていないクライアント](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a>プールで ADAL を構成し、ADFS をセキュリティ トークン サーバーとして設定する
<a name="BKMK_Config"> </a>

このプロセスでは、ADAL 用に構成されているビジネス サーバー プールに、Skype を ad FS のインストールを接続します。
  
1. 2016年 3 月をインストール Skype ビジネス サーバー プールのため、Skype をビジネスのサーバー 2015 または Standard Edition サーバーの累積的な更新プログラムです。 に、2016 年 3 月の  の累積更新プログラムをインストールします (必要に応じて、Windows Update を自動インストールで実行するよう、メンテナンス期間をスケジューリングします)。
    
2. オンプレミス ad FS サーバーに、スクリプトのセットアップ-AdfsOAuthTrustForSfB[をダウンロードします](https://aka.ms/sfbadalscripts)。 (ADFS ファームまたは独立の ADFS サーバーごとに実行するこの必要があります。 これは、必要はありません ADFS プロキシまたはプロキシで実行する)。
    
3. 内部のメモを行い、完全修飾ドメイン名 (Fqdn) をビジネス サーバー プールまたは Standard Edition サーバーは、Skype 用に外部の Web サービスです。 この作業はすべての Skype for Business プールに必要です。
    
4. ADFS サーバーの PowerShell から、Setup-AdfsOAuthTrustForSfB を実行します。内部および外部の Web サービスの FQDN の正しい URL を入力する必要があります。以下は、実行例です。
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    任意の追加のプール、Skype をビジネス サーバー依存関係者を信頼して ADFS でのプールの Web サービスの Url を手動で追加する必要があります。
    
    > [!IMPORTANT]
    > プールにパッシブ認証を使用して、ADAL も使用することはできません。 ADAL を使用するには、パッシブ認証を無効にする必要があります。 PowerShell コマンドレットでプールに対して認証を設定する方法については、[この記事](https://technet.microsoft.com/en-us/library/gg398396.aspx)を参照してください。
  
    > [!TIP]
    > 追加のプールが存在する場合、依存する関係者を信頼する ADFS で[識別子](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)として追加する必要があります > には、ADFS サーバーと ad FS の管理] を開きます。 信頼関係を拡大\>証明書利用者の関係者の信頼関係です。 依存関係者に表示されている信頼とプロパティを右クリックして右クリックし\>識別子\>プール個の追加の URL を入力\>[追加] をクリックします。 
  
5. ビジネス サーバーのフロント エンドまたは Standard Edition サーバーに対して、Skype に戻ります。 ここから OAuth サーバーを作成し、ビジネスの Skype を操作するには、その OAuth 構成を変更するコマンドレットを実行する必要があります。 ビジネス サーバー配置の Skype に 1 回この手順を行う必要があるだけです。 以下は、実行例です。
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > このコマンドを参照してください 'Id' の URL は、実際には、ADFS フェデレーション サービス名でわかる ADFS 管理サービスを右クリックすると\>のプロパティです。 '型' は、ADFS では常に、'MetadataURL' は、常に\<、ADFS サービス名\>+"/FederationMetadata/2007-06/FederationMetadata.xml"です。 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Skype ビジネス サーバーのフロント エンドまたは Standard Edition サーバーでは、まだ上のユーザーと、プールの FQDN、SIP アドレスを入力して新しい構成をテストします。 ビジネス サーバー配置の Skype に 1 回この手順を行う必要があるだけです。 以下は、実行例です。
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. ダイアログ ボックスが表示されたら、必ずテスト ユーザーの資格情報を入力してください。 テストが正常に完了していることを確認します。
    
    > [!NOTE]
    > STS URL は、ADFS*内部的*に解決するときにプロンプトが表示されますが**Windows のセキュリティ**の確認になります。 一方、URL が外部で解決した場合は、[**Sign in**] という名前のプロンプトになります。 通常、ここで望ましいのは [**Windows Security**] プロンプトです。 この動作は、特にフォーム ベース認証 (FBA) を実装していると、一貫しません。
  
また、STS URL が内部の ADFS に対して解決し、ブラウザーで統合 Windows 認証が有効になっていると、多くのユーザーがサインインするコンピューターでは、ブラウザーが、特定のブラウザー セキュリティ ゾーンでは資格情報を入力するよう明示的に構成されていない限り、認証に失敗することがあるので注意が必要です。キオスクを例に考えてみましょう。オペレーティング システムにログインしたアカウントは、Skype for Business クライアントにログインしているユーザー アカウントとは異なる場合があります。その場合、ここに記載のエラーが発生することがあります。
    
参照してくださいし、] をクリックして Internet Explorer では、このブラウザー設定を変更することができます\>ツール (または着陸装置)\>インター ネット オプション\>[セキュリティ] タブ\>と、セキュリティ ゾーン (イントラネット)。 このダイアログで、[レベルのカスタマイズ] ボタンをクリックし、[設定] ダイアログのリストの最後までスクロールします。 [ユーザー認証] で\>ログイン\>'ユーザー名とパスワードの入力を求める] オプションが表示されます。 Skype for Business クライアントを起動したユーザーが、コンピューターにログインしているユーザーと異なる (アカウントが異なる) キオスクを使用している場合は、グループ ポリシーでこれらのマシンに対してこのオプションをオンにしてテストする必要があります。
    
最後に、重要な点ですが、セキュリティ システムが情報を収集する中で、アカウントの認証または承認を必要とする場合、視覚情報の入力を複数回求められる場合があります。
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>ADAL サインイン有効化のその他のオプション (Office クライアント アプリケーションなど)
<a name="BKMK_Options"> </a>

ADAL はビジネスのため、Skype の設定 (自動的に) およびプラットフォーム間でクライアント アプリケーションを Office 2016、Exchange オンライン (場所は 'On' 既定で)、または Office 2013 のクライアントで利用することがあります。
  
> [!IMPORTANT]
> クライアント アプリケーションからの先進認証サインインで想定されることを確認する必要がありますか? [Office 2013 および Office 2016 のクライアント アプリケーションの現在の認証のしくみ](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US)を見てください。 
  
Exchange Online の最新の認証を有効に、いくつかの PowerShell コマンドレットを実行する必要があります。 Office 2013 のクライアント アプリケーションの場合は、クライアント コンピューター上のいくつかのレジストリ キーを変更する必要があります。
  
- Exchange Online に接続し、次のコマンドレットを実行します。
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- 次のレジストリ キーを、先進認証を有効にしたいデバイスまたはコンピューターごとに設定します。 規模の大きな組織では GPO が必要になります。 GPO を作成する方法についてを参照してください、'を作成するドメインの結合されたコンピューターでレジストリを変更するグループ ポリシー オブジェクト][この](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)資料の。
    
|レジストリ キー  <br/> |型  <br/> |値  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
これらのキーを設定すると、 [Office 365 で多因子認証認証 (MFA) を使用](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US)する Office アプリケーションを設定します。
  
> [!TIP]
> Office 2013 用のデバイスに最新の認証を無効にするには、ゼロの値に HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL レジストリ キーを設定します。 ようなレジストリ キー (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) は、Office 2016 のデバイスの最新の認証を無効にするのにも使用するに注意します。
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>先進認証 / ADAL がサポートされていないクライアント
<a name="BKMK_Support"> </a>

クライアントのバージョンによっては、OAuth をサポートしていないものがあります。コントロール パネルで Office クライアントのバージョンを確認できます。[プログラムの追加と削除] でバージョン番号を確認したら、以下に記載のバージョンと突き合わせてください。
  
- Office クライアント 15.0 です。0000-4766。\*
    
- Office クライアント 16.0。0000-4293。\*
    
- Office クライアント 16.0.6001.[0000-1032]
    
- Office クライアント 16.0。6000-6224。\*
    

