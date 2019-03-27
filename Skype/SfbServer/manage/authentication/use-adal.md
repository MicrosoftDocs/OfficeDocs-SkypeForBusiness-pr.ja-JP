---
title: Skype for Business で先進認証 (ADAL) を使用する方法
ms.reviewer: ''
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
ms.openlocfilehash: d6e78d60371b56c3a2cc959ded0ec7d7394d82cb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894073"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Skype for Business で先進認証 (ADAL) を使用する方法
 
現代の認証 (これは、Active Directory 認証ライブラリ (ADAL) と OAuth 2.0 に基づく) 2016年 3 月を参照しているを使用する方法を説明するビジネス サーバー 2015 年または最初から、Skype のビジネス用の Skype 用の累積的な更新ビジネス サーバー 2019 の Skype をリリースします。
  
## <a name="whats-in-this-article"></a>この記事の内容

[プール内の ADAL を構成し、AD FS セキュリティ トークン サーバー設定](use-adal.md#BKMK_Config)
  
[ADAL サインイン有効化のその他のオプション (Office クライアント アプリケーションなど)](use-adal.md#BKMK_Options)
  
[先進認証 / ADAL がサポートされていないクライアント](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a>プール内の ADAL を構成し、AD FS セキュリティ トークン サーバー設定
<a name="BKMK_Config"> </a>

このプロセスでは、ADAL 用に構成されているビジネス サーバー プールに、Skype を AD FS のインストールを接続します。
  
1. 2016年 3 月をインストールする累積的な更新 (またはそれ以降) にビジネス サーバー プールのため、Skype のビジネス サーバー 2015 または Standard Edition サーバーの Skype のです。 に、2016 年 3 月の nm-ocs-13-se-3rd の累積更新プログラムをインストールします (必要に応じて、Windows Update を自動インストールで実行するよう、メンテナンス期間をスケジューリングします)。
    
2. 設置型の AD FS サーバー、スクリプトのセットアップ-AdfsOAuthTrustForSfB[をダウンロード](https://aka.ms/sfbadalscripts)します。 (これは AD FS のファームまたは独立した AD FS サーバーごとに実行する必要です。 これは、必要はありません AD FS プロキシまたは Web アプリケーションのプロキシを実行する。)
    
3. 内部のメモを行い、完全修飾ドメイン名 (Fqdn) をビジネス サーバー プールまたは Standard Edition サーバーは、Skype 用に外部の Web サービスです。 この作業はすべての Skype for Business プールに必要です。
    
4. AD FS サーバーの PowerShell 実行`Setup-AdfsOAuthTrustForSfB.ps1`(Windows Server 2012 R2) 用または`Setup-Adfs2016OAuthTrustForSfB.ps1`(Windows サーバー 2016 のまたは後で)。内部および外部 Web サービスの完全修飾ドメイン名 (Fqdn) の適切な Url を入力する必要があります。 以下は、実行例です。
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    任意の追加のプール、Skype をビジネス サーバー依存関係者を信頼して AD FS でのプールの Web サービスの Url を手動で追加する必要があります。
    
    > [!IMPORTANT]
    > プールにパッシブ認証を使用して、ADAL も使用することはできません。 ADAL を使用するには、パッシブ認証を無効にする必要があります。 プールの認証を設定する方法について、PowerShell コマンドレットは、[この](https://technet.microsoft.com/en-us/library/gg398396.aspx)資料を参照してください。
  
    > [!TIP]
    > 追加のプールを信頼するように、依存しているパーティの[識別子](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)として追加する必要がある場合、AD の FS.> で、AD FS サーバーに移動し、AD FS の管理を開きます。 信頼関係を拡大\>証明書利用者の関係者の信頼関係です。 依存関係者に表示されている信頼とプロパティを右クリックして右クリックし\>識別子\>プール個の追加の URL を入力\>[追加] をクリックします。 
  
5. ビジネス サーバーのフロント エンドまたは Standard Edition サーバーに対して、Skype に戻ります。 ここから OAuth サーバーを作成し、ビジネスの Skype を操作するには、その OAuth 構成を変更するコマンドレットを実行する必要があります。 ビジネス サーバー配置の Skype に 1 回この手順を行う必要があるだけです。 以下は、実行例です。
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > このコマンドを参照してください 'Id' の URL は、実際には、AD FS フェデレーション サービス名表示では、AD FS の管理サービスを右クリックすると\>のプロパティです。 '型' は、常に 'の ADF' と 'MetadataURL' は、常に\<、AD FS サービス名\>+"/FederationMetadata/2007-06/FederationMetadata.xml"です。 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Skype ビジネス サーバーのフロント エンドまたは Standard Edition サーバーでは、まだ上のユーザーと、プールの FQDN、SIP アドレスを入力して新しい構成をテストします。 ビジネス サーバー配置の Skype に 1 回この手順を行う必要があるだけです。 以下は、実行例です。
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. ダイアログ ボックスが表示されたら、必ずテスト ユーザーの資格情報を入力してください。 テストが正常に完了していることを確認します。
    
    > [!NOTE]
    > STS URL は、AD FS*内部的*に解決するときにプロンプトが表示されますが**Windows のセキュリティ**の確認になります。 一方、URL が外部で解決した場合は、[**Sign in**] という名前のプロンプトになります。 通常、ここで望ましいのは [**Windows Security**] プロンプトです。 この動作は、特にフォーム ベース認証 (FBA) を実装していると、一貫しません。
  
また、STS URL は、内部の AD FS サーバーに解決され、ブラウザーで Windows 統合認証が有効になっている、多数のユーザーがクライアント アプリケーションにサインインする先のコンピューターに失敗した認証のブラウザーは、明示的にしない限り、特定のブラウザーのセキュリティ ゾーンで自分の資格情報をユーザーに要求するように構成。 キオスクを例に考えてみましょう。 オペレーティング システムにログインしたアカウントは、Skype for Business クライアントにログインしているユーザー アカウントとは異なる場合があります。 その場合、ここに記載のエラーが発生することがあります。
    
参照してくださいし、] をクリックして Internet Explorer では、このブラウザー設定を変更することができます\>ツール (または着陸装置)\>インター ネット オプション\>[セキュリティ] タブ\>と、セキュリティ ゾーン (イントラネット)。 このダイアログで、[レベルのカスタマイズ] ボタンをクリックし、[設定] ダイアログのリストの最後までスクロールします。 [ユーザー認証] で\>ログイン\>'ユーザー名とパスワードの入力を求める] オプションが表示されます。 Skype for Business クライアントを起動したユーザーが、コンピューターにログインしているユーザーと異なる (アカウントが異なる) キオスクを使用している場合は、グループ ポリシーでこれらのマシンに対してこのオプションをオンにしてテストする必要があります。
    
最後に、重要な点ですが、セキュリティ システムが情報を収集する中で、アカウントの認証または承認を必要とする場合、視覚情報の入力を複数回求められる場合があります。
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>ADAL サインイン有効化のその他のオプション (Office クライアント アプリケーションなど)
<a name="BKMK_Options"> </a>

ADAL はビジネスのため、Skype の設定 (自動的に) およびプラットフォーム間でクライアント アプリケーションを Office 2016、Exchange オンライン (場所は 'On' 既定で)、または Office 2013 のクライアントで利用することがあります。
  
> [!IMPORTANT]
> 現代の認証符号をクライアント アプリケーションからの内容を把握する必要がありますか。 [Office 2013 および Office 2016 のクライアント アプリケーションの現在の認証のしくみ](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US)を見てください。 
  
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
    
> [!NOTE]
> ハイブリッド現代の認証もサポートされて Skype のビジネス設置とする場合は詳細を知り、[ビジネス用の Skype を構成する方法、設置型ハイブリッドの最新の認証を使用する](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication)を参照してください。
