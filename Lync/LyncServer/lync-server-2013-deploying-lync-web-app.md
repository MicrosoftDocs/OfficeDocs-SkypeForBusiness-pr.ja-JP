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
ms.openlocfilehash: d4508c9c499b0219f754bf9815063f4b1210b811
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a>Lync Server 2013 での Lync Web App の展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-07-18_

Lync Web App は、Lync Server 2013 と共にインストールされるインターネットインフォメーションサービス (IIS) web クライアントで、既定では有効になっています。 サーバーで Lync Web App を有効にしたり、web クライアントをユーザーに展開したりするための追加の手順は必要ありません。 ユーザーが会議 URL をクリックしても、Lync 2013 クライアントがインストールされていない場合は、最新バージョンの Lync Web App を使用して会議に参加するためのオプションがユーザーに表示されます。

Lync Web App の音声、ビデオ、および共有機能には、Microsoft ActiveX コントロールが必要です。 ActiveX コントロールを事前にインストールするか、要求されたときにユーザーにインストールを許可することができます。これは、初めて Lync Web App を使用するとき、または ActiveX コントロールを必要とする機能に初めてアクセスしたときに発生します。

<div class=" ">


> [!NOTE]  
> Lync Server 2013 エッジサーバー展開では、Lync Web App クライアントアクセスには、境界ネットワーク内の HTTPS リバースプロキシが必要です。 また、簡易 URL も公開する必要があります。 詳細については、「lync <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">server 2013 用のリバースプロキシサーバーの設定</A>」および「 <A href="lync-server-2013-planning-for-simple-urls.md">lync server 2013 での簡単な url の計画</A>」を参照してください。



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a>Lync Web App で多要素認証を有効にする

Lync Web App の Lync Server 2013 バージョンは、多要素認証をサポートしています。 ユーザー名とパスワードに加えて、スマートカードや Pin などの追加の認証方法を要求して、Lync 会議にサインインするときに外部ネットワークから参加しているユーザーを認証することができます。 Active Directory フェデレーションサービス (AD FS) フェデレーションサーバーを展開し、Lync Server 2013 でパッシブ認証を有効にすることによって、多要素認証を有効にすることができます。 AD FS を構成した後、Lync 会議に参加しようとする外部ユーザーには、ユーザー名とパスワードのチャレンジと、構成した追加の認証方法が含まれる AD FS 多要素認証 web ページが表示されます。.

<div class=" ">


> [!IMPORTANT]  
> 多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。 
> <UL>
> <LI>
> <P>複数要素 ADFS 認証は、会議の参加者と開催者が両方とも同じ組織内にあるか、または AD FS フェデレーション組織の両方にある場合に機能します。 Lync server web インフラストラクチャでは現在サポートされていないため、Lync フェデレーションユーザーは多要素 ADFS 認証を使用できません。</P>
> <LI>
> <P>ハードウェアロードバランサーを使用する場合は、ロードバランサーで cookie の永続性を有効にして、Lync Web App クライアントからのすべての要求が同じフロントエンドサーバーによって処理されるようにします。</P>
> <LI>
> <P>Lync Server と AD FS サーバー間で証明書利用者の信頼を確立するときには、Lync 会議の最大長を長くするのに十分な長さのトークンライフサイクルを割り当てます。 通常、トークンの存続期間は 240 分で十分です。</P>
> <LI>
> <P>この構成は、Lync mobile クライアントには適用されません。</P></LI></UL>



</div>

**多要素認証を構成するには**

1.  AD FS フェデレーション サーバーの役割をインストールします。 詳細については、「Active Directory フェデレーションサービス2.0 展開ガイド」を参照してください。<http://go.microsoft.com/fwlink/p/?linkid=267511>

2.  AD FS の証明書を作成します。 詳細については、「計画と展開」の「AD FS を展開するには」の「フェデレーションサーバー証明書」セクション[http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)を参照してください。シングルサインオンについては、「」を参照してください。

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

## <a name="branchcache-configuration"></a>BranchCache 構成

Windows 7 および Windows Server 2008 R2 の BranchCache 機能は、Lync Web App web コンポーネントと競合する可能性があります。 Lync Web App ユーザーの問題が発生しないようにするには、BranchCache が有効になっていないことを確認してください。

BranchCache を無効にする方法の詳細については、「BranchCache 展開ガイド」を参照してください[http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)。このガイドは、MICROSOFT ダウンロードセンターおよび HTML 形式の Windows Server 2008 R2 Technical Library () にある word 形式で利用できます。

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a>Lync Web App の展開を確認する

Test-CsUcwaConference コマンドレットを使用すると、2 人のテスト ユーザーが統合コミュニケーション Web API (UCWA) を使用して会議に参加できることを検証できます。 このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントの「 [test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 」を参照してください。

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a>Windows Server 2008 R2 でのプラグインのインストールのトラブルシューティング

Windows Server 2008 R2 を実行しているコンピューターでプラグインのインストールが失敗した場合は、Internet Explorer のセキュリティ設定または DisableMSI レジストリキーの設定を変更する必要があります。

**Internet Explorer のセキュリティ設定を変更するには**

1.  Internet Explorer を開きます。

2.  [**ツール**]、[**インターネット オプション**]、[**詳細設定**] の順にクリックします。

3.  [**セキュリティ**] セクションまで下にスクロールします。

4.  [**暗号化されたページをディスクに保存しない**] チェック ボックスをオフにし、[**OK**] をクリックします。
    
    <div class=" ">
    

    > [!NOTE]  
    > この設定を選択すると、Lync Web App から添付ファイルをダウンロードしようとした場合にもエラーが発生します。

    
    </div>

5.  会議にもう一度参加します。 エラーが発生することなくプラグインがダウンロードされます。

**DisableMSI レジストリ設定を変更するには**

1.  [**スタート**] ボタンをクリックし、[**ファイル名を指定して実行**] をクリックします。

2.  レジストリ エディターにアクセスするには、「**regedit**」と入力します。

3.  \_[HKEY\_LOCAL MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer に移動します。

4.  REG\_DWORD 型の DisableMSI レジストリキーを編集または追加し、0に設定します。

5.  会議にもう一度参加します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での会議参加ページの構成](lync-server-2013-configuring-the-meeting-join-page.md)  
[Lync Server 2013 の lync Web App がサポートされているプラットフォーム](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

