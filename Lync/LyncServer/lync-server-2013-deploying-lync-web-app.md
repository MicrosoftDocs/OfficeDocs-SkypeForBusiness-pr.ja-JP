---
title: Lync Web App の展開
TOCTitle: Lync Web App の展開
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48273333
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Web App の展開

 

_**トピックの最終更新日:** 2016-12-08_

Lync Web App は、Lync Server 2013 によってインストールされるインターネット インフォメーション サービス (IIS) Web クライアントで、既定で有効になっています。サーバーでの Lync Web App の有効化またはユーザーへの Web クライアント展開のいずれを行う場合についても、これ以上のステップは必要ありません。ユーザーが会議 URL をクリックしたときに Lync 2013 クライアントがインストールされていない場合は、最新バージョンの Lync Web App を使用して会議に参加するためのオプションが表示されます。

Lync Web App の音声、ビデオ、および共有機能には、Microsoft ActiveX コントロールが必要です。ActiveX コントロールは、事前にインストールするか、プロンプトが表示されたときにユーザーがインストールすることができます。このプロンプトは、ユーザーが初めて Lync Web App を使用するときか、ActiveX コントロールを必要とする機能に初めてアクセスしたときに表示されます。

> [!NOTE]
> Lync Server 2013 エッジ サーバーの展開では、Lync Web App クライアントのアクセスには境界ネットワーク内の HTTPS リバース プロキシが必要になります。また、簡易 URL も公開する必要があります。詳細については、「<a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 のリバース プロキシ サーバーの設定</a>」および「<a href="lync-server-2013-planning-for-simple-urls.md">Lync Server 2013 での簡単な URL の計画</a>」を参照してください。


## Lync Web App での多要素認証の有効化

Lync Server 2013 バージョンの Lync Web App では多要素認証をサポートします。ユーザー名とパスワードに加え、スマート カードや PIN などの追加の認証方法を要求し、Lync 会議にサインインするときに外部ネットワークから参加しているユーザーを認証することができます。多要素認証を有効にするには、Active Directory フェデレーション サービス (AD FS) フェデレーション サーバーを展開し、Lync Server 2013 でパッシブ認証を有効にします。AD FS を構成した後、外部ユーザーが Lync 会議に参加しようとすると、AD FS 多要素認証 Web ページが表示されます。このページでは、構成した追加の認証方法と共にユーザー名とパスワードの入力が求められます。


> [!IMPORTANT]
> 多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。 
> <UL>
> <LI>
> <P>多要素 ADFS 認証は、会議の参加者と開催者の両方が同じ組織に属する場合、または両方が AS FS フェデレーション組織に属する場合に機能します。多要素 ADFS 認証は、Lync フェデレーション ユーザーに対しては機能しません (Lync サーバーの Web インフラストラクチャで現在サポートされていないため)。</P>
> <LI>
> <P>ハードウェア ロード バランサーを使用する場合、ロード バランサーで Cookie の永続性を有効にし、Lync Web App クライアントからのすべての要求が同じフロントエンド サーバーによって処理されるようにします。</P>
> <LI>
> <P>Lync Server と AD FS サーバー間で証明書利用者の信頼を確立するときは、Lync 会議の最大の長さに対して十分な長さのトークンの存続期間を割り当てます。通常、トークンの存続期間は 240 分で十分です。</P>
> <LI>
> <P>この構成は、Lync モバイル クライアントには適用されません。</P></LI></UL>



**多要素認証を構成するには**

1.  AD FS フェデレーション サーバーの役割をインストールします。詳細については、「Active Directory フェデレーション サービス 2.0 展開ガイド」([http://go.microsoft.com/fwlink/?linkid=267511\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=267511%26clcid=0x411)) を参照してください。

2.  AD FS の証明書を作成します。詳細については、「シングル サインオンで使用するために AD FS を計画して展開する」の「フェデレーション サーバーの証明書」([http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)」を参照してください。

3.  Windows PowerShell コマンドライン インターフェイスで、次のコマンドを実行します。
    
        add-pssnapin Microsoft.Adfs.powershell

4.  次のコマンドを実行し、パートナーシップを確立します。
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  以下の証明書利用者のルールを設定します。
    
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'

       &nbsp;
    
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules

       &nbsp;
    
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml

## BranchCache 構成

Windows 7 および Windows Server 2008 R2 の BranchCache 機能は、Lync Web App Web コンポーネントに干渉する可能性があります。Lync Web App ユーザーに対する問題を防ぐため、BranchCache が有効になっていないことを確認してください。

BranchCache の無効化の詳細については、「BranchCache 展開ガイド」を参照してください。Word 形式は Microsoft Download Center ([http://go.microsoft.com/fwlink/?linkid=268788\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268788%26clcid=0x411)) で、HTML 形式は Windows Server 2008 R2 テクニカル ライブラリ ([http://go.microsoft.com/fwlink/?linkid=268789\&clcid=0x411](http://go.microsoft.com/fwlink/?linkid=268789%26clcid=0x411)) で入手できます。

## Lync Web App 展開の検証

Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して会議に参加できることを検証できます。このコマンドレットの詳細については、「Lync Server 管理シェル」のドキュメントの「[Test-CsUcwaConference](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference)」を参照してください。

## Windows Server 2008 R2 でのプラグインのインストールに関するトラブルシューティング

Windows Server 2008 R2 を実行しているコンピューターでプラグインのインストールに失敗した場合、Internet Explorer のセキュリティ設定または DisableMSI レジストリ キー設定の変更が必要となる場合があります。

**Internet Explorer のセキュリティ設定を変更するには**

1.  Internet Explorer を開きます。

2.  \[**ツール**\]、\[**インターネット オプション**\]、\[**詳細設定**\] の順にクリックします。

3.  \[**セキュリティ**\] セクションまで下にスクロールします。

4.  \[**暗号化されたページをディスクに保存しない**\] チェック ボックスをオフにし、\[**OK**\] をクリックします。
    
    > [!NOTE]
    > この設定をオンにした場合、Lync Web App から添付ファイルをダウンロードしようとしたときにもエラーが発生します。


5.  会議にもう一度参加します。エラーが発生することなくプラグインがダウンロードされます。

**DisableMSI レジストリ設定を変更するには**

1.  \[**スタート**\] ボタンをクリックし、\[**ファイル名を指定して実行**\] をクリックします。

2.  レジストリ エディターにアクセスするには、「**regedit**」と入力します。

3.  HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer に移動します。

4.  種類 REG\_DWORD の DisableMSI レジストリ キーを編集または追加し、0 に設定します。

5.  会議にもう一度参加します。

## 関連項目

#### 概念

[Lync Server 2013 での会議参加ページの構成](lync-server-2013-configuring-the-meeting-join-page.md)  
[Lync Server 2013 の Lync Web App がサポートされるプラットフォーム](lync-server-2013-lync-web-app-supported-platforms.md)

