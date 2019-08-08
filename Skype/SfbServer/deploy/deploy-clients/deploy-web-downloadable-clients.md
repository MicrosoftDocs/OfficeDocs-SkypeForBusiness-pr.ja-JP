---
title: Skype for Business Server で Web ダウンロード可能なクライアントを展開する
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: '概要: skype for Business Web App および skype for Business で使用される Skype 会議アプリを展開します。'
ms.openlocfilehash: 8f2449fde2f270834bda50602fe163829f3b725f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234395"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Skype for Business Server で Web ダウンロード可能なクライアントを展開する

**概要:** Skype for Business 2015 Web App および skype for business Server で使用される Skype 会議アプリを展開します。

Skype for Business Web App は、Skype for Business Server を実行しているサーバーにインストールされたインターネットインフォメーションサービス (IIS) web クライアントであり、既定では、Skype for business クライアントをまだ持っていないユーザーとの会議のために、既定ではオンデマンドで展開されます。 このような会議ユーザーは通常ネットワークの外部から接続します。 ユーザーが会議 URL をクリックしたときに、Skype for business クライアントがインストールされていない場合は、最新バージョンの Skype for Business Web App、Skype 会議アプリ、または Skype for Business for Mac を使用して、会議に参加するためのオプションをユーザーに提示します。

Skype for Business Web App の音声、ビデオ、共有機能には、ユーザーのブラウザーでプラグインとして使用される Microsoft ActiveX コントロールが必要です。 事前に ActiveX コントロールをインストールするか、メッセージが表示されたときにユーザーがインストールできるようにすることができます。これは、Skype for Business Web App を初めて使用したとき、または ActiveX コントロールを必要とする機能に初めてアクセスしたときに発生します。

> [!NOTE]
> Skype for Business Server Edge Server の展開では、Skype for Business Web App クライアントアクセスには境界ネットワーク内の HTTPS 逆プロキシが必要です。 簡易 URL を発行する必要もあります。 詳細については、「 [Skype For Business Server の単純な url に対し](../../plan-your-deployment/network-requirements/simple-urls.md)て[リバースプロキシサーバー](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)と DNS 要件を設定する」を参照してください。

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Skype for Business Web App の多要素認証を有効にする
<a name="MFA"> </a>

Skype for Business Web App、Skype 会議アプリ、Skype for Business for Mac は多要素認証をサポートしています。 ユーザー名とパスワードに加えて、Skype for Business 会議にサインインしたときに外部ネットワークから参加するユーザーを認証するために、スマートカードや Pin などの追加の認証方法が必要になることがあります。 多要素認証を有効にするには、Active Directory フェデレーションサービス (AD FS) フェデレーションサーバーを展開し、Skype for Business Server でパッシブ認証を有効にします。 AD FS を構成した後、Skype for Business 会議に参加しようとしている外部ユーザーには、ユーザー名とパスワードの問題と、その他の認証方法と共にその他の認証方法が含まれた、AD FS 多要素認証の web ページが表示されます。が設定されました。

> [!IMPORTANT]
> 多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。

- ADFS の多要素認証は、会議の参加者と開催者がともに同じ組織内に存在しているか、AD FS フェデレーション組織からのものである場合に機能します。ADFS の多要素認証は、Lync サーバーの Web インフラストラクチャでは現在サポートされていないため、Lync のフェデレーション ユーザーに対しては機能しません。

- ハードウェアロードバランサーを使用している場合は、Skype for Business Web App クライアントまたは会議アプリクライアントからのすべての要求が同じフロントエンドサーバーによって処理されるように、ロードバランサーの cookie の永続化を有効にします。

- Skype for Business Server と AD FS サーバー間で証明書利用者の信頼を確立する場合は、Skype for Business 会議の最大長に収まる長さのトークン寿命を割り当てます。 通常、トークンの存続期間は 240 分で十分です。

- この構成は、Lync モバイル クライアントには適用されません。

### <a name="configure-multi-factor-authentication"></a>多要素認証を構成する

1. AD FS フェデレーション サーバーの役割をインストールします。 詳細については、 [Active Directory フェデレーションサービス2.0 展開ガイド](https://go.microsoft.com/fwlink/p/?linkid=267511)を参照してください。

2. AD FS の証明書を作成します。 詳細については、「AD FS の計画と展開」の「[フェデレーションサーバーの証明書」](https://go.microsoft.com/fwlink/p/?LinkId=285376)セクションを参照してください。シングルサインオンのトピックで使うことができます。

3. Windows PowerShell コマンドラインインターフェイスで、次のコマンドを実行します。

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
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a>BranchCache を無効にする 
<a name="MFA"> </a>

Windows 7 および Windows Server 2008 R2 の BranchCache 機能は、Skype for Business Web App web コンポーネントを干渉する可能性があります。 Skype for Business Web App ユーザーの問題を回避するには、BranchCache が有効になっていないことを確認します。

BranchCache の無効化の詳細については、「 [branchcache の展開ガイド](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)」を参照してください。

## <a name="verifying-skype-for-business-web-app-deployment"></a>Skype for Business Web App の展開を確認する
<a name="MFA"> </a>

Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して電話会議に参加できることを検証できます。 このコマンドレットの詳細については、「Skype for Business Server 管理シェルのドキュメントの[CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 」を参照してください。

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>Windows Server 2008 R2 でのプラグインのインストールのトラブルシューティング
<a name="MFA"> </a>

Windows Server 2008 R2 を実行しているコンピューターでプラグインのインストールが失敗した場合は、Internet Explorer のセキュリティ設定または DisableMSI のレジストリキー設定を変更する必要があります。

### <a name="modify-the-security-setting-in-internet-explorer"></a>Internet Explorer のセキュリティ設定を変更する

1. Internet Explorer を開きます。

2. [**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。

3. [**セキュリティ**] セクションまで下にスクロールします。

4. [**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにして、[**OK**] をクリックします。

    > [!NOTE]
    > この設定を選択すると、Skype for Business Web App から添付ファイルをダウンロードしようとしたときにもエラーが発生します。

5. 会議にもう一度参加します。エラーが発生することなくプラグインがダウンロードされます。

### <a name="modify-the-disablemsi-registry-setting"></a>DisableMSI レジストリ設定を変更する

1. [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

2. レジストリ エディターにアクセスするには、「**regedit**」と入力します。

3. HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer に移動します。

4. 種類 REG_DWORD の DisableMSI レジストリ キーを編集または追加し、0 に設定します。

5. 会議にもう一度参加します。

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Skype for Business Web App の代わりに Skype 会議アプリを有効にする (オプション、Skype for Business Server 2015 のみ)
<a name="SMA_Enable"> </a>

この手順はオプションであり、Skype for Business Server 2015 CU5 以降以降に適用されます。 このアプリを使用しない場合、外部ユーザーは Skype for Business Web App を使って会議に参加し続けることができます。

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>簡素化された会議参加と Skype 会議アプリを有効にする

1. コンテンツ配信ネットワーク (CDN) へのアクセスを有効にすると、ユーザーは CDN online に接続して、Skype 会議アプリ (Windows 上) と Skype for Business for Mac (Mac) を入手して、簡単な会議の参加エクスペリエンスを利用することができます。

   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. 会議参加 web ページまたは Skype 会議アプリからのクライアント側のログ利用統計情報を、Microsoft サーバーに送信することを許可します (コマンドは既定で false になります)。

   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Microsoft に送信される情報は、 [Skype For business のデータ収集方法](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)に厳密に準拠しています。

3. CDN が利用できない場合は、ローカルでホストされている Skype for Business Web App のエクスペリエンスに戻す前に、タイムアウトを設定します。 既定値は 6 秒です。 この値を 0 に設定すると、タイムアウトはなくなります。

   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a>関連項目
<a name="SMA_Enable"> </a>

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Skype for Business Server で会議の参加ページを構成する](../../manage/conferencing/meeting-join-page.md)

[Microsoft Online Services のプライバシーに関する声明](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)

[ライセンス条項とドキュメント](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
