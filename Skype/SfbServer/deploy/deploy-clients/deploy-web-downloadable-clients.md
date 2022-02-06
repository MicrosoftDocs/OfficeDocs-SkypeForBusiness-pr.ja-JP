---
title: Web ダウンロード可能なクライアントを展開Skype for Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: '概要: 会議で使用Skype for Business Web アプリおよびSkype会議アプリを展開Skype for Business。'
---

# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Web ダウンロード可能なクライアントを展開Skype for Business Server

**概要:** 2015 Skype for Business Web アプリを展開し、Skypeで使用Skype for Business Server。

Skype for Business Web アプリは インターネット インフォメーション サービス を実行しているサーバーにインストールされている インターネット インフォメーション サービス (IIS Skype for Business Server) Web クライアントであり、既定では、サーバーを既に持ってない会議ユーザーにオンデマンドで展開Skype for Business クライアント。 これらの会議ユーザーは、ネットワークの外部から接続しないよりも頻繁に使用されます。 ユーザーが会議の URL をクリックしても Skype for Business クライアントがインストールされていない場合は常に、最新バージョンの Skype for Business Web アプリ、Skype Meetings App、または Skype for Business for Mac を使用して会議に参加するオプションが表示されます。

音声、ビデオ、および共有機能Skype for Business Web アプリ、ユーザーのブラウザー ActiveXプラグインとして使用される Microsoft ActiveX コントロールが必要です。 ActiveX コントロールを事前にインストールするか、ユーザーが Skype for Business Web アプリ を初めて使用するか、ActiveX コントロールを必要とする機能に初めてアクセスするときに、ユーザーにインストールを許可することができます。

> [!NOTE]
> エッジ Skype for Business Server展開では、境界ネットワーク内の HTTPS リバース プロキシがクライアント アクセスのSkype for Business Web アプリ必要です。 また、簡易 URL も公開する必要があります。 詳細については、「リバース プロキシ [サーバー](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers)と [DNS](../../plan-your-deployment/network-requirements/simple-urls.md) 要件を設定する」を参照してください。Skype for Business Server。

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>ユーザーの多要素認証を有効Skype for Business Web アプリ
<a name="MFA"> </a>

Skype for Business Web アプリ、Skype、会議アプリ、Skype for Business for Mac多要素認証をサポートします。 ユーザー名とパスワードに加えて、スマート カードや PIN などの追加の認証方法を要求して、Skype for Business 会議にサインインするときに外部ネットワークから参加しているユーザーを認証できます。 Active Directory フェデレーション サービス (fs) フェデレーション サーバーを展開し、AD でパッシブ認証を有効にすることで、多要素認証をSkype for Business Server。 AD FS が構成された後、Skype for Business 会議に参加しようとする外部ユーザーには、ユーザー名とパスワードチャレンジを含む AD FS 多要素認証 Web ページと、構成した追加の認証方法が表示されます。

> [!IMPORTANT]
> 多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。

- 多要素 ADFS 認証は、会議参加者と開催者の両方が同じ組織内にある場合、または FS フェデレーション組織の両方AD機能します。 多要素 ADFS 認証は、Lync サーバー Web インフラストラクチャが現在サポートしていないので、Lync フェデレーション ユーザーには機能しません。

- ハードウェア ロード バランサーを使用する場合は、Skype for Business Web アプリ または Meetings App クライアントからの要求すべてが同じフロントエンド サーバーによって処理されるロード バランサーで Cookie の永続性を有効にします。

- Skype for Business Server と AD FS サーバーの間で証明書利用者信頼を確立する場合は、Skype for Business 会議の最大長にまたがる十分な長さのトークンライフを割り当てる必要があります。 通常、トークンの存続期間は 240 分で十分です。

- この構成は、Lync モバイル クライアントには適用されません。

### <a name="configure-multi-factor-authentication"></a>多要素認証の構成

1. AD FS フェデレーション サーバーの役割をインストールします。 詳細については、「 [Active Directory フェデレーション サービス 2.0 展開ガイド」を参照してください。](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))

2. FS の証明書をADします。 詳細については、「シングル サインオン [で](/previous-versions/azure/azure-services/jj205462(v=azure.100)) 使用する AD FS の計画と展開」の「フェデレーション サーバー証明書」セクションを参照してください。

3. コマンド ライン Windows PowerShellから、次のコマンドを実行します。

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. 次のコマンドを実行し、パートナーシップを確立します。

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. 以下の証明書利用者のルールを設定します。

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>BranchCache を無効にする
<a name="MFA"> </a>

サーバー 7 および Windows Server 2008 R2 Windows BranchCache 機能は、Web コンポーネントのSkype for Business Web アプリする可能性があります。 ユーザーが問題をSkype for Business Web アプリするには、BranchCache が有効になっていないか確認してください。

BranchCache の無効化の詳細については、「 [BranchCache 展開ガイド」を参照してください](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。

## <a name="verifying-skype-for-business-web-app-deployment"></a>展開Skype for Business Web アプリ確認する
<a name="MFA"> </a>

Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して会議に参加できることを検証できます。 このコマンドレットの詳細については、「管理シェル」のドキュメントの[「Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps)」を参照Skype for Business Server参照してください。

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>サーバー 2008 R2 でのWindowsインストールのトラブルシューティング
<a name="MFA"> </a>

Windows Server 2008 R2 を実行しているコンピューターでプラグインのインストールが失敗した場合は、Internet Explorer セキュリティ設定または DisableMSI レジストリ キー設定を変更する必要があります。

### <a name="modify-the-security-setting-in-internet-explorer"></a>[セキュリティ] の設定を変更Internet Explorer

1. Internet Explorer を開きます。

2. [**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。

3. [**セキュリティ**] セクションまで下にスクロールします。

4. [**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにし、[**OK**] をクリックします。

    > [!NOTE]
    > この設定を選択すると、ファイルから添付ファイルをダウンロードしようとするときにもエラー Skype for Business Web アプリ。

5. 会議にもう一度参加します。エラーが発生することなくプラグインがダウンロードされます。

### <a name="modify-the-disablemsi-registry-setting"></a>DisableMSI レジストリ設定を変更する

1. [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

2. レジストリ エディターにアクセスするには、「**regedit**」と入力します。

3. HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer に移動します。

4. 種類 REG_DWORD の DisableMSI レジストリ キーを編集または追加し、0 に設定します。

5. 会議にもう一度参加します。

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>会議Skypeを有効にして、Skype for Business Web アプリを置き換える (オプション、Skype for Business Server 2015 のみ)
<a name="SMA_Enable"> </a>

この手順は省略可能で、2015 CU5 以降Skype for Business Server適用されます。 使用しない場合、外部ユーザーは引き続き会議に参加し、Skype for Business Web アプリ。

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>会議の参加と会議アプリのSkypeを有効にする

1. Content Delivery Network (CDN) へのアクセスを有効にした場合、ユーザーは CDN にオンラインで接続し、Skype 会議アプリ (Windows) と Skype for Business for Mac (mac) を取得し、簡略化された会議参加エクスペリエンスを使用できます。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. 会議参加 Web ページまたは会議アプリからクライアント側のログテレメトリを Microsoft サーバーに送信Skype許可します (コマンドの既定値は false)。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Microsoft に送信される情報は、データ収集のプラクティスに[Skype for Business遵守しています](/skypeforbusiness/legal-and-regulatory/data-collection-practices)。

3. 使用できない場合は、ローカルでホストされているSkype for Business Web アプリエクスペリエンスにCDNタイムアウトを設定します。 既定値は 6 秒です。 この値が 0 に設定されている場合、タイムアウトはありません。

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> MeetingUxUseCdn が 2015 Skype for Business Server累積的な更新プログラム 5 の場合、既定値は False に設定されます。 これにより、Skype for Business for Mac 管理者が MeetingUxUseCdn を True に設定している場合でも、Skype for Business for Mac Skype for Business クライアントが非フェデレーション パートナーの会議にゲストとして参加できないという問題が発生します。 これを機能するには、Skype for Business Server 2015 の累積的な更新プログラム 7、6.0.9319.534 以降が必要です。 「[2015 年Skype会議アプリを有効にして、Skype for Business Web アプリをSkype for Business Serverしてください](https://support.microsoft.com/kb/4132312)。


## <a name="see-also"></a>関連項目
<a name="SMA_Enable"> </a>

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[[会議への参加] ページを [会議] で構成Skype for Business Server](../../manage/conferencing/meeting-join-page.md)

[Microsoft のプライバシーに関する声明](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[ライセンス条項とドキュメント](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)