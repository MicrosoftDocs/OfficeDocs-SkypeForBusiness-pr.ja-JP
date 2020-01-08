---
title: 'Lync Server 2013: Lync Windows ストアアプリの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef2e96b1e58bb9a92b2dc9748624d38f605965f
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Lync Server 2013 での Lync Windows ストアアプリの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-12-03_

Lync Windows ストアアプリをユーザーが利用できるようにする前に、展開が[Lync Server 2013 の Lync Windows ストアアプリの要件](lync-server-2013-lync-windows-store-app-requirements.md)を満たしていることを確認してください。 Lync Windows ストアアプリをサポートするように Lync Server 2013 を構成する方法の詳細については、「NextHop のブログ記事、「Lync Server の[http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)自動検出と Lync Windows ストアアプリ (英語)」を参照してください。 サーバー環境が正しく構成された後、ユーザーは "Lync" を検索して Windows ストアから Lync アプリをダウンロードするように指示できます。

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Lync Windows ストアアプリの多要素認証を有効にする

Lync Server 2013 の累積更新プログラム: 2013 年6月は、Lync Windows ストアアプリクライアントの多要素認証のサポートを追加します。 ユーザー名とパスワードに加えて、他の認証方法 (スマートカードや Pin など) を使用して、Lync 会議にサインインするときに外部ユーザーを認証する必要があります。 多要素認証を有効にするには、Active Directory フェデレーションサービス (AD FS) フェデレーションサーバーを展開して、Lync Server 2013 でパッシブ認証を有効にします。 AD FS が構成されると、Lync 会議に参加しようとしている外部ユーザーには、ユーザー名とパスワードのチャレンジと、構成したその他の認証方法が含まれた、AD FS 多要素認証の web ページが表示されます。.

<div class=" ">


> [!IMPORTANT]  
> Lync Windows ストアアプリの多要素認証用に AD FS を構成する場合は、次の点を考慮する必要があります。 
> <UL>
> <LI>
> <P>Lync server 2013 の累積更新プログラムを含む lync Server 2013: 少なくとも、2013年6月が必要です。 Lync 2013 デスクトップクライアントでは、lync Server 2013 の累積更新プログラムは必要ありません2013。そのため、Lync 2013 クライアントは認証できるため、パッシブ認証が機能すると表示されることがあります。 ただし、Lync Windows ストアアプリクライアントの認証プロセスは完了しません。通知やエラーメッセージは表示されません。</P>
> <LI>
> <P>サーバーは、受動的認証が提供されている認証の種類のみになるように構成する必要があります。</P>
> <LI>
> <P>ハードウェアロードバランサーを使用している場合、Lync Windows ストアアプリクライアントからのすべての要求が同じフロントエンドサーバーによって処理されるように、ロードバランサーで cookie の永続性を有効にします。</P>
> <LI>
> <P>Lync Server と AD FS サーバー間で証明書利用者の信頼を確立する場合は、Lync 会議の最大の長さに収まる長さのトークンの有効期間を割り当てます。 通常、トークンの存続期間は 240 分で十分です。</P></LI></UL>



</div>

**多要素認証を構成するには**

1.  AD FS フェデレーション サーバーの役割をインストールします。 詳細については、「Active Directory フェデレーションサービス2.0 展開<http://go.microsoft.com/fwlink/p/?linkid=267511>ガイド」を参照してください。

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
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a>サインインを禁止できる既知の問題

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>Lync Windows ストアアプリが実行されているデバイスで時刻と日付が正しく設定されていない

デバイスの時刻設定がサーバーの時刻設定と同期されている必要があります。 これは、Microsoft Surface などのデバイスや、ドメインに参加していない Windows RT を実行しているその他のデバイスで特に重要です。 これらのデバイスの時刻を時刻サーバーから自動的に設定するには、デバイスの昇格されたコマンドプロンプトから次のコマンドを実行します。
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Lync Windows ストアアプリが Lync サーバーまたはサービスにアクセスできない

Lync Windows ストアアプリでは、Windows 8 に物理デバイスとして登録されないネットワークアダプター (4G LTE USB モデムなど) を介して Lync サーバーまたはサービスにアクセスできない場合があります。 デスクトップアプリやブラウザーが他のサーバーや web サイトにアクセスできる場合でも、Lync Windows ストアアプリでこの問題が発生する可能性があります。

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Lync Windows ストアアプリで Lync Server 2010 および Office Communications Server 2007 R2 Edge Server でサインインできない

使用しているトポロジが Lync Server 2010 で構成されている Office Communications Server 2007 R2 Edge サーバーの場合は、Lync Server 2010: 2013 年7月の累積更新プログラムで利用可能なトポロジビルダーの更新バージョンを実行する必要があります。 以前のバージョンのトポロジビルダーでは、Office Communications Server 2007 エッジサーバーへの必要なマッピングは作成されないため、Lync Windows ストアアプリクライアントではサインインできません。 次の手順を実行する必要があります。

1.  Lync server 2010 の累積的な更新プログラムをインストールする: Lync Server 2010 プールおよび Lync Server 2010 ディレクターの2013年7月。

2.  次の操作を行って、外部 SIP エントリポイントがエッジサーバーアドレスであることを示すために Lync 自動検出構成を更新します。
    
    1.  Lync Server 管理シェルを開きます。
    
    2.  次のコマンドを実行します。
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>証明書名の検証に失敗したため、Lync Windows ストアアプリでサインインできない

サインインの問題は、最新バージョンの Lync Windows ストアアプリを実行していない Office 365 ユーザーに対して発生する可能性があります。 この問題は通常、複数のドメインを使用している場合に発生します (たとえば、SIP URI は**userA@domainZ.com**が、エッジサーバーは**sip.domainX.com**)。 この問題を解決するには、ユーザーが最新バージョンの Lync Windows ストアアプリをインストールする必要があります。これには、Windows 8.1 が必要です。

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Lync Windows ストアアプリログを使って問題のトラブルシューティングを行う

デバイスで生成されたログを使用して、問題のトラブルシューティングを行うことができます。 ログは、次のフォルダーに保存されます。

% LocalAppData%\\\\LyncMX\_8wekyb3d8bbwe\\localappdata\\Tracing

ユーザーからログを取得する前に、ログが有効になっていることを確認してから、メモリに保存されているすべての情報がハードドライブ上のファイルにも保存されるように、ログを保存するようにユーザーに依頼します。

**ログをオンにするには**

1.  デバイスで Lync Windows ストアアプリを開きます。

2.  画面の右側からスワイプします。 マウスを使用している場合は、画面の右上隅をポイントし、マウスポインターを画面の下に移動します。

3.  [**設定**]、[**オプション**] の順に選択し、[**診断ログ**] を **[オン**] に設定します。

4.  **診断ログ**が以前にオフになっていた場合は、Lync を再起動する必要があります。 Lync を再起動するには、次のいずれかの操作を行います。
    
      - デバイスを再起動します。
    
      - Lync タスクを終了して、アプリをもう一度起動します。 タスクを終了するには、Windows タスクマネージャーを開き、[ **Lync**] を選択して、[**タスクの終了**] をタップします。 Lync が一覧に表示されていない場合は、[**詳細**] をタップして、[**バックグラウンドプロセス**] で lync を探します。

**ログを保存するには**

1.  デバイスで Lync Windows ストアアプリを開きます。

2.  サインインしてみてください。

3.  画面の右側からスワイプします。 マウスを使用している場合は、画面の右上隅をポイントし、マウスポインターを画面の下に移動します。

4.  [**設定**] を選択し、[**バージョン情報**] を選択して、[**ログの保存**] を選択します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

