---
title: 'Lync Server 2013: Lync Web App の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7415be2210e6c791434ced8af8f309b49603e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Lync Server 2013 での Lync Web App の展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-07-18_

Lync Web App は、Lync Server 2013 と共にインストールされるインターネットインフォメーションサービス (IIS) web クライアントであり、既定で有効になっています。 サーバーで Lync Web App を有効にするか、web クライアントをユーザーに展開するために、追加の手順は必要ありません。 ユーザーが会議 URL をクリックしたときに、Lync 2013 クライアントがインストールされていない場合は、最新バージョンの Lync Web App を使って会議に参加するためのオプションがユーザーに表示されます。

Lync Web App の音声、ビデオ、共有機能には、Microsoft ActiveX コントロールが必要です。 事前に ActiveX コントロールをインストールするか、メッセージが表示されたときにユーザーがアプリをインストールできるようにすることができます。これは、Lync Web App を初めて使用したとき、または ActiveX コントロールを必要とする機能に初めてアクセスしたときに発生します。

<div class=" ">


> [!NOTE]  
> Lync Server 2013 Edge Server 展開では、Lync Web App クライアントへのアクセスには、境界ネットワーク内の HTTPS 逆プロキシが必要です。 簡易 URL を発行する必要もあります。 詳細については、「 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync server 2013 用のリバースプロキシサーバーをセットアップする</A>」および「 <A href="lync-server-2013-planning-for-simple-urls.md">lync server 2013 で簡単な url を計画</A>する」を参照してください。



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Lync Web App の多要素認証を有効にする

Lync Server 2013 バージョンの Lync Web App では、多要素認証がサポートされています。 ユーザー名とパスワードに加えて、他の認証方法 (スマートカード、Pin など) を使用して、Lync 会議にサインインするときに外部ネットワークから参加するユーザーを認証する必要があります。 多要素認証を有効にするには、Active Directory フェデレーションサービス (AD FS) フェデレーションサーバーを展開し、Lync Server 2013 でパッシブ認証を有効にします。 AD FS が構成されると、Lync 会議に参加しようとしている外部ユーザーには、ユーザー名とパスワードのチャレンジと、構成したその他の認証方法が含まれた、AD FS 多要素認証の web ページが表示されます。.

<div class=" ">


> [!IMPORTANT]  
> 多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。 
> <UL>
> <LI>
> <P>ADFS の多要素認証は、会議の参加者と開催者がともに同じ組織内に存在しているか、AD FS フェデレーション組織からのものである場合に機能します。ADFS の多要素認証は、Lync サーバーの Web インフラストラクチャでは現在サポートされていないため、Lync のフェデレーション ユーザーに対しては機能しません。</P>
> <LI>
> <P>ハードウェアロードバランサーを使っている場合は、すべての要求が同じフロントエンドサーバーによって処理されるように、ロードバランサーでの cookie の永続化を有効にします。</P>
> <LI>
> <P>Lync Server と AD FS サーバー間で証明書利用者の信頼を確立する場合は、Lync 会議の最大の長さに収まる長さのトークンの有効期間を割り当てます。 通常、トークンの存続期間は 240 分で十分です。</P>
> <LI>
> <P>この構成は、Lync モバイル クライアントには適用されません。</P></LI></UL>



</div>

**多要素認証を構成するには**

1.  AD FS フェデレーション サーバーの役割をインストールします。 詳細については、「Active Directory フェデレーションサービス2.0 展開ガイド」を参照してください。<http://go.microsoft.com/fwlink/p/?linkid=267511>

2.  AD FS の証明書を作成します。 詳細については、「AD FS を計画して展開する」の「フェデレーションサーバーの証明書」セクションを参照して[http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)ください。シングルサインオンのトピックで使用します。

3.  Windows PowerShell コマンドラインインターフェイスで、次のコマンドを実行します。
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  次のコマンドを実行し、パートナーシップを確立します。
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  以下の証明書利用者のルールを設定します。
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a>BranchCache の構成

Windows 7 および Windows Server 2008 R2 の BranchCache 機能は、Lync Web App web コンポーネントを干渉する可能性があります。 Lync Web App ユーザーの問題を回避するには、BranchCache が有効になっていないことを確認します。

BranchCache の無効化の詳細については、Microsoft ダウンロードセンターの Word 形式[http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788)と、Windows Server 2008 R2 テクニカルライブラリの HTML 形式で利用できる Branchcache 展開ガイドを参照して[http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)ください。

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Lync Web App の展開を確認する

Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して電話会議に参加できることを検証できます。 このコマンドレットの詳細については、「Lync Server Management Shell ドキュメントの[CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 」を参照してください。

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Windows Server 2008 R2 でのプラグインのインストールのトラブルシューティング

Windows Server 2008 R2 を実行しているコンピューターでプラグインのインストールが失敗した場合は、Internet Explorer のセキュリティ設定または DisableMSI のレジストリキー設定を変更する必要があります。

**Internet Explorer でセキュリティ設定を変更するには**

1.  Internet Explorer を開きます。

2.  [**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。

3.  [**セキュリティ**] セクションまで下にスクロールします。

4.  [**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにして、[**OK**] をクリックします。
    
    <div class=" ">
    

    > [!NOTE]  
    > この設定を選択すると、Lync Web App から添付ファイルをダウンロードしようとしたときにもエラーが発生します。

    
    </div>

5.  会議にもう一度参加します。 エラーが発生することなくプラグインがダウンロードされます。

**DisableMSI のレジストリ設定を変更するには**

1.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

2.  レジストリ エディターにアクセスするには、「**regedit**」と入力します。

3.  \_"HKEY\_LOCAL MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer" に移動します。

4.  REG\_DWORD 型の DisableMSI レジストリキーを編集または追加し、0に設定します。

5.  会議にもう一度参加します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での会議参加ページの構成](lync-server-2013-configuring-the-meeting-join-page.md)  
[Lync Web App が Lync Server 2013 用にサポートされているプラットフォーム](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

