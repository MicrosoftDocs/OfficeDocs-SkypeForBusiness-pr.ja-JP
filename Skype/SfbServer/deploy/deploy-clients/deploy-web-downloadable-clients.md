---
title: Skype for Business Server 2015 で Web ダウンロード可能なクライアントを展開する
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 'ビジネス Web アプリケーションの概要: が、Skype を導入し、Skype 会議アプリケーションがビジネスの Skype を使用します。'
ms.openlocfilehash: e1cee2741e1538da1e4c5ed8e25509415cb16ac3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 で Web ダウンロード可能なクライアントを展開する
 
**の概要:**Skype のビジネス Web アプリケーションの展開し、Skype 会議アプリケーションがビジネスの Skype を使用します。
  
ビジネス Web アプリケーションの Skype は、クライアントのビジネスの Skype をまだ持っていない会議のユーザーにビジネス サーバー 2015 と配備されている既定のオン ・ デマンドで Skype を実行するサーバーでインストールされている、インターネット インフォメーション サービス (IIS) web クライアントです。 このような会議ユーザーは通常ネットワークの外部から接続します。 ユーザーは会議 URL をクリックしたが、ビジネス クライアントがインストールされている Skype がない、常にユーザーにビジネス Web アプリケーションの最新バージョンの Skype を使用してミーティングに参加するためのオプションが表示されます。
  
ビジネス Web アプリケーションは、ユーザーのブラウザーでプラグインとして使用される Microsoft ActiveX コントロールを必要とするは、Skype の機能を音声、ビデオ、および共有します。 ActiveX コントロールを事前にインストールするか、インストールするメッセージが表示されたら、初めてのビジネス Web アプリケーションの Skype を使用する場合は、ユーザーを許可するか、機能にアクセスする最初の時間が必要な ActiveX コントロールです。
  
> [!NOTE]
> ビジネス 2015 エッジ サーバー展開では Skype は、境界ネットワークでの HTTPS のリバース プロキシは、クライアント アクセスのビジネス Web アプリケーションの Skype の必要があります。 簡易 URL を発行する必要もあります。 詳細については、[リバース プロキシ サーバーを設定](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)し、[簡単な Url の計画](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx)を参照してください。 
  
## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Skype のビジネス Web アプリケーション用の多要素認証を有効にします。
<a name="MFA"> </a>

ビジネス Web アプリケーションの Skype のビジネス サーバー 2015 のバージョンの Skype では、多要素認証をサポートします。 だけでなくユーザー名とパスワード、スマート カードまたは外部ネットワークからビジネス ・ ミーティングの Skype にサインインするときに参加するユーザーを認証するために、ピンなどの追加の認証方法を要求できます。 Active Directory フェデレーション サービス (AD FS) のフェデレーション サーバーを展開して、Skype のビジネス サーバー 2015 のパッシブの認証を有効にすることによって、多要素認証を有効にできます。 AD FS を構成すると、Skype をビジネス ・ ミーティングに参加しようとする外部のユーザーが表示され、ユーザー名を格納する、AD FS の多要素認証の web ページとパスワードのこと、追加の認証方法と課題構成します。
  
> [!IMPORTANT]
> 多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。 
  
- ADFS の多要素認証は、会議の参加者と開催者がともに同じ組織内に存在しているか、AD FS フェデレーション組織からのものである場合に機能します。ADFS の多要素認証は、Lync サーバーの Web インフラストラクチャでは現在サポートされていないため、Lync のフェデレーション ユーザーに対しては機能しません。
    
- ハードウェア ロード バランサーを使用する場合、Skype のビジネス Web アプリケーション クライアントからのすべての要求は、同じフロント エンド サーバーによって処理されるよう、ロード バランサーの cookie の永続化を有効にします。
    
- Skype ビジネス サーバーおよび AD FS サーバーの間で依存元パーティ信頼関係を確立するときに、ビジネス会議のため、Skype の最大長をスパンするのに十分な長さはトークンの有効期間を割り当てます。 通常、トークンの存続期間は 240 分で十分です。
    
- この構成は、Lync モバイル クライアントには適用されません。
    
### <a name="configure-multi-factor-authentication"></a>多要素認証を構成する

1. AD FS フェデレーション サーバーの役割をインストールします。 詳細については、 [Active Directory フェデレーション サービス 2.0 展開ガイド 』](https://go.microsoft.com/fwlink/p/?linkid=267511)を参照してください。
    
2. AD FS の証明書を作成します。 詳細についてを参照してください[「フェデレーション サーバーの証明書」](https://go.microsoft.com/fwlink/p/?LinkId=285376)のセクションのプランのシングル サインオンのトピックで使用するための AD FS の展開とします。
    
3. Windows PowerShell コマンドライン インターフェイスは、次のコマンドを実行します。
    
    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. 次のコマンドを実行し、パートナーシップを確立します。
    
    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. 以下の証明書利用者のルールを設定します。
    
    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   ```
 
   ```
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   ```

   ```
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>BranchCache を無効にする 
<a name="MFA"> </a>

BranchCache 機能は、Windows 7 および Windows Server 2008 R2 は、ビジネス Web アプリケーションの web コンポーネントの Skype に干渉することができます。 Skype の問題を防ぐため、ビジネス Web アプリケーションのユーザーに対して、BranchCache が有効になっていないことを確認します。 
  
、Branchcache を使用を無効にする方法の詳細は、Microsoft ダウンロード センターでの word 文書形式で使用可能な BranchCache の展開ガイドを参照してください[http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?LinkId=268788)と Windows Server 2008 R2 テクニカル ライブラリ内に HTML 形式の[https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?LinkId=268789)。
  
## <a name="verifying-skype-for-business-web-app-deployment"></a>Skype のビジネス Web アプリケーションの配置の確認
<a name="MFA"> </a>

Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して電話会議に参加できることを検証できます。 詳細については、このコマンドレットは、サーバー管理シェルのビジネス ドキュメントの Skype で[テスト CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)を参照してください。
  
## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Windows Server 2008 R2 上のプラグインのインストールのトラブルシューティング
<a name="MFA"> </a>

Windows Server 2008 R2 を実行しているコンピューター上のプラグインのインストールが失敗した場合は、Internet Explorer のセキュリティの設定または DisableMSI レジストリ キーの設定を変更する必要があります。
  
### <a name="modify-the-security-setting-in-internet-explorer"></a>Internet Explorer のセキュリティ設定を変更する

1. Internet Explorer を開きます。
    
2. [**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。
    
3. [**セキュリティ**] セクションまで下にスクロールします。
    
4. [**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにして、[**OK**] をクリックします。
    
    > [!NOTE]
    > 選択した場合、この設定もエラーが発生ビジネス Web アプリケーションの Skype から添付ファイルをダウンロードしようとしています。 
  
5. 会議にもう一度参加します。エラーが発生することなくプラグインがダウンロードされます。
    
### <a name="modify-the-disablemsi-registry-setting"></a>DisableMSI レジストリ設定を変更する

1. [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。
    
2. レジストリ エディターにアクセスするには、「**regedit**」と入力します。
    
3. HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer に移動します。
    
4. 種類 REG_DWORD の DisableMSI レジストリ キーを編集または追加し、0 に設定します。
    
5. 会議にもう一度参加します。
    
## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional"></a>Skype 会議アプリを有効にして Skype for Business Web App を置き換える (オプション)
<a name="SMA_Enable"> </a>

この手順はオプションです。 それを使用しない、外部ユーザーが引き続きビジネス Web アプリケーションの Skype を使用してミーティングに参加します。 
  
### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>簡素化された会議参加と Skype 会議アプリを有効にする

1. ユーザーが CDN オンラインに接続し、Skype の会議アプリケーションを取得することがあり、単純化を使用して、コンテンツ配信ネットワーク (CDN) へのアクセスを有効にすると、会議の参加経験します。 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. クライアント側ログ「遠隔測定」会議からを許可する web ページまたはマイクロソフトのサーバー (false コマンドの既定値) に送信する Skype 会議アプリケーションに参加します。 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    マイクロソフトに送信される情報が、 [Skype](https://support.office.com/en-us/article/Skype-for-Business-data-collection-practices-c17e8ea6-b83b-4345-9401-47a6c8b13aad?ui=en-US&amp;rs=en-US&amp;ad=US)を厳格に遵守します。
    
3. CDN を使用できない場合は、クリアテキストへのフォールバック Skype をローカルにホストされる Web アプリケーションのビジネス経験をする前にタイムアウトを設定します。 既定値は 6 秒です。 この値を 0 に設定すると、タイムアウトはなくなります。
    
   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。
<a name="SMA_Enable"> </a>

#### 

[会議クライアント (Web アプリケーションおよび会議アプリケーション) の計画します。](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
  
[会議クライアント (Web アプリケーションおよび会議アプリケーション) の計画します。](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
#### 

[会議参加ページを構成します。](http://technet.microsoft.com/library/45880423-47f4-49af-b825-cbd8e3fc1046.aspx)
  
[Microsoft Online Services のプライバシーに関する声明](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)
  
[ライセンス契約の条項とマニュアル](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)

