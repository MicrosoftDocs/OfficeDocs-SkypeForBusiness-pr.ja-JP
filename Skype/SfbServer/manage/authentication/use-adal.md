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
ms.openlocfilehash: 4bf802d2710c9c271c54cf2e127cf51b24875db1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966574"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Skype for Business で先進認証 (ADAL) を使用する方法
 
現代の認証 (これは、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) 2016年 3 月を参照しているを使用する方法を説明するビジネス サーバー 2015 の Skype のビジネス用の Skype 用の累積的な更新です。
  
## <a name="whats-in-this-article"></a>この記事の内容

[ADAL とは](use-adal.md#BKMK_ADAL)
  
[プールで ADAL を構成し、ADFS をセキュリティ トークン サーバーとして設定する](use-adal.md#BKMK_Config)
  
[ADAL サインイン有効化のその他のオプション (Office クライアント アプリケーションなど)](use-adal.md#BKMK_Options)
  
[先進認証 / ADAL がサポートされていないクライアント](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a>ADAL とは
<a name="BKMK_ADAL"> </a>

ADAL は、'Active Directory Authentication Library (Active Directory 認証ライブラリ)' の頭文字であり、OAuth 2.0 と共に、先進認証の基礎となるものです。 このコード ライブラリは、(ビジネス用の Skype) のようなセキュリティ トークンを使用してクライアント ・ アプリケーションに利用可能なディレクトリにセキュリティで保護されたリソースを作成するよう設計されています。 ADAL は OAuth 2.0 と連携して、多要素認証 (MFA) やさまざまな形式の SAML Auth など、多様な認証および承認シナリオを可能にします。
  
先進認証は、クライアントとして動作するさまざまなアプリがリソースのセキュリティ保護の手段として利用しています。 ビジネス サーバーの Skype は、オンプレミスのクライアントとオンプレミスのサーバー間でユーザーにリソースへの承認の適切なレベルを提供するためにこの技術を使用します。
  
先進認証の通信 (ADAL と OAuth 2.0 をベースに使用) には次のような共通要素があります。
  
- リソースの要求を行うクライアントが、この場合、クライアントは、ビジネスの Skype です。
    
- クライアントが特定のレベルのアクセスを必要とするリソースがある、ディレクトリ サービスがこのリソースがセキュリティで保護されたリソースのビジネス サーバー用の Skype はここで。
    
- OAuth の接続、つまり、他の接続がリソースにアクセスするユーザーを*承認*するのには専用です。 (OAuth は 'サーバー' への認証に、わかりやすい名前で知られています、S2S と省略は、多くの場合)。
    
ビジネス サーバー ・最新認証 (ADAL) 会話の Skype、Skype ビジネス サーバーの ADFS (Windows Server 2012 R2 の ad FS 3.0) を介して通信します。 認証は、別の ID プロバイダー (IdP) を使用して行うことも可能ですが、Skype for Business Server は、ADFS と直接通信するよう構成する必要があります。 ビジネス サーバーの Skype 上で動作する ADFS を構成していない場合は、 [ad FS のインストール](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)を完了してください。
  
ADAL は、2016年 3 月に含まれているビジネス サーバー 2015 年の Skype 用の累積的な更新および年 2016年 3 月のビジネスの**必要があります**Skype の累積的な更新プログラムをインストールし、正しい構成のために必要な。
  
> [!NOTE]
> 初期のリリースでは、オンプレミス環境での先進認証は、混成の Skype トポロジーが使用されていない場合のみのサポートとなります。 環境がビジネス サーバーの Skype では純粋である場合などです。 この記述は、変更される可能性があります。 
  
正しい構成には、.ps1 ファイルと ADAL で使用するコマンドが収録された PowerShell パッケージをインストールする必要があります。
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a>プールで ADAL を構成し、ADFS をセキュリティ トークン サーバーとして設定する
<a name="BKMK_Config"> </a>

このプロセスでは、ADAL 用に構成されているビジネス サーバー プールに、Skype を ad FS のインストールを接続します。
  
1. 2016年 3 月をインストール Skype ビジネス サーバー プールのため、Skype をビジネスのサーバー 2015 または Standard Edition サーバーの累積的な更新プログラムです。 (スケジュール メンテナンス ウィンドウでは、必要に応じて、自動インストールの Windows Update を実行する。)
    
2. オンプレミス ad FS サーバーに、スクリプトのセットアップ-AdfsOAuthTrustForSfB[をダウンロードします](https://aka.ms/sfbadalscripts)。 (ADFS ファームまたは独立の ADFS サーバーごとに実行するこの必要があります。 これは、必要はありません ADFS プロキシまたはプロキシで実行する)。
    
3. 内部のメモを行い、完全修飾ドメイン名 (Fqdn) をビジネス サーバー プールまたは Standard Edition サーバーは、Skype 用に外部の Web サービスです。 この作業はすべての Skype for Business プールに必要です。
    
4. ADFS サーバーの PowerShell から、Setup-AdfsOAuthTrustForSfB を実行します。内部および外部の Web サービスの FQDN の正しい URL を入力する必要があります。以下は、実行例です。
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    任意の追加のプール、Skype をビジネス サーバー依存関係者を信頼して ADFS でのプールの Web サービスの Url を手動で追加する必要があります。
    
    > [!IMPORTANT]
    > プールにパッシブ認証を使用して、ADAL も使用することはできません。 ADAL を使用するには、パッシブ認証を無効にする必要があります。 プールの認証を設定する方法について、PowerShell コマンドレットは、[この](https://technet.microsoft.com/en-us/library/gg398396.aspx)資料を参照してください。
  
    > [!TIP]
    > 追加のプールが存在する場合、依存する関係者を信頼する ADFS で[識別子](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)として追加する必要があります > には、ADFS サーバーと ad FS の管理] を開きます。 信頼関係を拡大\>証明書利用者の関係者の信頼関係です。 依存関係者に表示されている信頼とプロパティを右クリックして右クリックし\>識別子\>プール個の追加の URL を入力\>[追加] をクリックします。 
  
5. ビジネス サーバーのフロント エンドまたは Standard Edition サーバーに対して、Skype に戻ります。 ここから OAuth サーバーを作成し、ビジネスの Skype を操作するには、その OAuth 構成を変更するコマンドレットを実行する必要があります。 ビジネス サーバー配置の Skype に 1 回この手順を行う必要があるだけです。 以下は、実行例です。
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > このコマンドを参照してください 'Id' の URL は、実際には、ADFS フェデレーション サービス名でわかる ADFS 管理サービスを右クリックすると\>のプロパティです。 '型' は、ADFS では常に、'MetadataURL' は、常に\<、ADFS サービス名\>+"/FederationMetadata/2007-06/FederationMetadata.xml"です。 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Skype ビジネス サーバーのフロント エンドまたは Standard Edition サーバーでは、まだ上のユーザーと、プールの FQDN、SIP アドレスを入力して新しい構成をテストします。 ビジネス サーバー配置の Skype に 1 回この手順を行う必要があるだけです。 以下は、実行例です。
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. 入力を求められたら、テスト ユーザーの資格情報を入力し、テストが正常に終了することを確認します。
    
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
    
|レジストリ キー  <br/> |型   <br/> |値  <br/> |
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
    

