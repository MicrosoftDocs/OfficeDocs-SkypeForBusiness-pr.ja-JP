---
title: Skype for Business Server で Web ダウンロード可能なクライアントを展開する
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: '概要: Skype for Business で使用する Skype for Business Web App と Skype 会議アプリを展開します。'
ms.openlocfilehash: afab5d0977adb8749fb514f946b676598d42ea32
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805927"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a>Skype for Business Server で Web ダウンロード可能なクライアントを展開する

**概要:** Skype for Business Server で使用される Skype for Business 2015 Web App および Skype 会議アプリを展開します。

Skype for Business Web App は、Skype for Business Server を実行しているサーバーにインストールされるインターネット インフォメーション サービス (IIS) Web クライアントであり、既定では、Skype for Business クライアントを持っているユーザーを満たしていないユーザーにオンデマンドで展開されます。 これらの会議ユーザーは、ネットワークの外部から接続しない場合よりも多くの場合に使用されます。 ユーザーが会議 URL をクリックしても Skype for Business クライアントがインストールされていない場合、最新バージョンの Skype for Business Web App、Skype 会議アプリ、または Skype for Business for Mac を使用して会議に参加するオプションが表示されます。

Skype for Business Web App の音声、ビデオ、および共有機能には、ユーザーのブラウザーでプラグインとして使用される Microsoft ActiveX コントロールが必要です。 ActiveX コントロールは、事前にインストールするか、ユーザーが Skype for Business Web App を初めて使用するときに実行されるか、ActiveX コントロールを必要とする機能に初めてアクセスするときにインストールを許可することができます。

> [!NOTE]
> Skype for Business Server エッジ サーバー展開では、Skype for Business Web App クライアント アクセスには境界ネットワーク内の HTTPS リバース プロキシが必要です。 また、簡易 URL も公開する必要があります。 詳細については、「Skype for Business Server [での](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) 簡易 URL のリバース プロキシ サーバーと DNS 要件の設定 [」を参照してください](../../plan-your-deployment/network-requirements/simple-urls.md)。

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a>Skype for Business Web App の多要素認証を有効にする
<a name="MFA"> </a>

Skype for Business Web App、Skype 会議アプリ、Skype for Business for Mac は多要素認証をサポートしています。 ユーザー名とパスワードに加えて、Skype for Business 会議にサインインするときに外部ネットワークから参加しているユーザーを認証するために、スマート カードや PIN などの追加の認証方法を要求できます。 多要素認証を有効にするには、Active Directory フェデレーション サービス (AD FS) フェデレーション サーバーを展開し、Skype for Business Server でパッシブ認証を有効にします。 AD FS を構成すると、Skype for Business 会議に参加しようとする外部ユーザーに、ユーザー名とパスワードのチャレンジを含む AD FS 多要素認証 Web ページと、構成した追加の認証方法が表示されます。

> [!IMPORTANT]
> 多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。

- 多要素 ADFS 認証は、会議の参加者と開催者の両方が同じ組織内にある場合、または FS フェデレーション組織の ADである場合に機能します。 多要素 ADFS 認証は、Lync サーバー Web インフラストラクチャが現在サポートしていないので、Lync フェデレーション ユーザーには機能しません。

- ハードウェア ロード バランサーを使用する場合は、ロード バランサーで Cookie の永続性を有効にして、Skype for Business Web App または Meetings App クライアントからの要求すべてが同じフロントエンド サーバーによって処理されます。

- Skype for Business Server と AD FS サーバーの間で証明書利用者信頼を確立する場合は、Skype for Business 会議の最大の長さに十分な長さのトークンの有効期限を割り当てる必要があります。 通常、トークンの存続期間は 240 分で十分です。

- この構成は、Lync モバイル クライアントには適用されません。

### <a name="configure-multi-factor-authentication"></a>多要素認証を構成する

1. AD FS フェデレーション サーバーの役割をインストールします。 詳細については、Active Directory フェデレーション サービス [2.0 展開ガイドを参照してください。](https://go.microsoft.com/fwlink/p/?linkid=267511)

2. FS の証明書をADします。 詳細については、「シングル [サインオンで](https://go.microsoft.com/fwlink/p/?LinkId=285376) 使用する AD FS の計画と展開」の「フェデレーション サーバー証明書」セクションを参照してください。

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

Windows 7 および windows 7 および Windows Server 2008 R2 BranchCache 機能は、Skype for Business Web App Web コンポーネントに干渉する可能性があります。 Skype for Business Web App ユーザーの問題を回避するには、BranchCache が有効になっていない必要があります。

BranchCache の無効化の詳細については [、BranchCache 展開ガイドを参照してください](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。

## <a name="verifying-skype-for-business-web-app-deployment"></a>Skype for Business Web App の展開の確認
<a name="MFA"> </a>

Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して会議に参加できることを検証できます。 このコマンドレットの詳細については、Skype for Business Server 管理シェル のドキュメントの [「Test-CsUcwaConference」](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) を参照してください。

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a>インストール時のプラグイン のインストールWindows Server 2008 R2
<a name="MFA"> </a>

Windows Server 2008 R2 を実行しているコンピューターでプラグインのインストールに失敗した場合は、Internet Explorer のセキュリティ設定または DisableMSI レジストリ キーの設定を変更する必要があります。

### <a name="modify-the-security-setting-in-internet-explorer"></a>グループのセキュリティ設定を変更Internet Explorer

1. Internet Explorer を開きます。

2. [**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。

3. [**セキュリティ**] セクションまで下にスクロールします。

4. [**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにし、[**OK**] をクリックします。

    > [!NOTE]
    > この設定を選択すると、Skype for Business Web App から添付ファイルをダウンロードしようとするときにもエラーが発生します。

5. 会議にもう一度参加します。 エラーが発生することなくプラグインがダウンロードされます。

### <a name="modify-the-disablemsi-registry-setting"></a>DisableMSI レジストリ設定を変更する

1. [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

2. レジストリ エディターにアクセスするには、「**regedit**」と入力します。

3. HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer に移動します。

4. 種類 REG_DWORD の DisableMSI レジストリ キーを編集または追加し、0 に設定します。

5. 会議にもう一度参加します。

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a>Skype 会議アプリを有効にして Skype for Business Web App を置き換える (オプション、Skype for Business Server 2015 のみ)
<a name="SMA_Enable"> </a>

この手順は省略可能で、Skype for Business Server 2015 CU5 以降に適用されます。 使用しない場合、外部ユーザーは引き続き Skype for Business Web App を使用して会議に参加します。

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a>簡素化された会議参加と Skype 会議アプリを有効にする

1. コンテンツ配信ネットワーク (CDN) へのアクセスを有効にした場合、ユーザーは CDN にオンラインで接続し、Skype 会議アプリ (Windows 上) と Skype for Business for Mac (Mac) を取得し、簡素化された会議参加エクスペリエンスを使用できます。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. 会議参加 Web ページまたは Skype 会議アプリからのクライアント側ログテレメトリを Microsoft サーバーに送信できます (コマンドの既定値は false です)。

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    Microsoft に送信される情報は [、Skype for Business のデータ収集プラクティスに厳密に準拠しています](https://docs.microsoft.com/skypeforbusiness/legal-and-regulatory/data-collection-practices)。

3. CDN が利用できない場合は、ローカルでホストされている Skype for Business Web App エクスペリエンスにフォールバックする前にタイムアウトを設定します。 既定値は 6 秒です。 この値が 0 に設定されている場合、タイムアウトはありません。

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> Skype for Business Server 2015 累積更新プログラム 5 の MeetingUxUseCdn では、既定値は False に設定されます。 これにより、Skype for Business 管理者が MeetingUxUseCdn を True に設定している場合でも、Skype for Business for Mac クライアントが非フェデレーション パートナーの会議にゲストとして参加できないという問題が発生します。 これを機能するには、Skype for Business Server 2015 に累積的な更新プログラム 7、6.0.9319.534 以降が必要です。 Skype [for Business Server 2015](https://support.microsoft.com/kb/4132312)で Skype for Business Web App を置き換える Skype 会議アプリを有効にするを参照してください。


## <a name="see-also"></a>関連項目
<a name="SMA_Enable"> </a>

[会議クライアント用の計画 (Web アプリおよび会議アプリ)](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[Skype for Business Server で会議参加ページを構成する](../../manage/conferencing/meeting-join-page.md)

[Microsoft のプライバシーに関する声明](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[ライセンス条項とドキュメント](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
