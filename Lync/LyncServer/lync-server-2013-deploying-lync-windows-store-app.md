---
title: 'Lync Server 2013: Lync Windows ストアアプリの展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e2abe30cd464b223523df9d5fa878607404f7a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a>Lync Server 2013 での Lync Windows ストアアプリの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-12-03_

Lync Windows ストアアプリをユーザーが使用できるようにする前に、展開が[Lync Server 2013 の Lync Windows ストアのアプリ要件](lync-server-2013-lync-windows-store-app-requirements.md)を満たしていることを確認してください。 Lync Windows ストアアプリをサポートするように Lync Server 2013 を構成する方法の詳細については、「NextHop ブログの記事、「Lync Server の[http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)自動検出と Lync Windows ストアアプリ」 () を参照してください。 サーバー環境が正しく構成された後、ユーザーは「Lync」を検索して Windows ストアから Lync アプリをダウンロードすることができます。

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a>Lync Windows ストアアプリで多要素認証を有効にする

Lync Server 2013 の累積的な更新プログラム: 2013 年6月、Lync Windows ストアアプリクライアントに対して多要素認証のサポートが追加されます。 ユーザー名とパスワードに加えて、スマートカードや Pin などの追加の認証方法を要求して、Lync 会議にサインインする際に外部ユーザーを認証することができます。 多要素認証を有効にするには、Active Directory フェデレーションサービス (AD FS) フェデレーションサーバーを展開し、Lync Server 2013 でパッシブ認証を有効にします。 AD FS を構成した後、Lync 会議に参加しようとする外部ユーザーには、ユーザー名とパスワードのチャレンジと、構成した追加の認証方法が含まれる AD FS 多要素認証 web ページが表示されます。.

<div class=" ">


> [!IMPORTANT]  
> Lync Windows ストアアプリで多要素認証を使用するように AD FS を構成する場合の重要な考慮事項は次のとおりです。 
> <UL>
> <LI>
> <P>Lync server 2013 の累積的な更新プログラム (Lync Server 2013): 少なくとも2013年6月1日 Lync 2013 デスクトップクライアントは、lync Server 2013 の累積的な更新プログラム (2013 年6月) を必要としないため、Lync 2013 クライアントは認証を行うことができるため、パッシブ認証が機能しているように見える場合があります。 ただし、Lync Windows ストアアプリクライアントの認証プロセスは完了せず、通知やエラーメッセージは表示されません。</P>
> <LI>
> <P>パッシブ認証が提供される唯一の認証の種類になるようにサーバーを構成する必要があります。</P>
> <LI>
> <P>ハードウェアロードバランサーを使用する場合は、ロードバランサーで cookie の永続性を有効にして、Lync Windows ストアアプリクライアントからのすべての要求が同じフロントエンドサーバーによって処理されるようにします。</P>
> <LI>
> <P>Lync Server と AD FS サーバー間で証明書利用者の信頼を確立するときには、Lync 会議の最大長を長くするのに十分な長さのトークンライフサイクルを割り当てます。 通常、トークンの存続期間は 240 分で十分です。</P></LI></UL>



</div>

**多要素認証を構成するには**

1.  AD FS フェデレーション サーバーの役割をインストールします。 詳細については、「Active Directory フェデレーションサービス2.0 展開<http://go.microsoft.com/fwlink/p/?linkid=267511>ガイド」を参照してください。

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

## <a name="known-issues-that-can-prevent-sign-in"></a>サインインを妨げる可能性がある既知の問題

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a>Lync Windows ストアアプリを実行しているデバイスに日付と時刻が正しく設定されていません

デバイスの時刻設定は、サーバーの時刻設定と同期されている必要があります。 これは、Microsoft Surface などのデバイス、およびドメインに参加していない Windows RT を実行しているデバイスにとって特に重要です。 これらのデバイスの時刻をタイムサーバーから自動的に設定するには、デバイス上の管理者特権でのコマンドプロンプトから次のコマンドを実行します。
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a>Lync Windows ストアアプリが Lync server またはサービスにアクセスできません

Lync Windows ストアアプリは、物理デバイスとして Windows 8 に登録されていない 4G LTE USB モデムなどのネットワークアダプターを介して Lync server またはサービスにアクセスできない場合があります。 Lync Windows ストアアプリは、デスクトップアプリとブラウザーが他のサーバーや web サイトにアクセスできる場合でも、この問題が発生することがあります。

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a>Lync Windows ストアアプリで Lync Server 2010 および Office Communications Server 2007 R2 エッジサーバーを使用してサインインできない

Office Communications Server 2007 R2 エッジサーバーを使用する Lync Server 2010 でトポロジが構成されている場合は、Lync Server 2010 の累積的な更新プログラム (7 月 2013 7 日) で使用できる、更新されたバージョンのトポロジビルダーを実行する必要があります。 以前のバージョンのトポロジビルダーでは、Office Communications Server 2007 エッジサーバーへの必要なマッピングが作成されないため、Lync Windows ストアアプリクライアントはサインインできません。 次の手順を実行する必要があります。

1.  Lync server 2010 プールおよび Lync Server の2010ディレクターの累積的な更新プログラム (2010 2013 年7月) をインストールします。

2.  次の手順を実行して、外部 SIP エントリポイントがエッジサーバーアドレスであることを示すように、Lync 自動検出構成を更新します。
    
    1.  Lync Server 管理シェルを開きます。
    
    2.  次のコマンドを実行します。
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a>証明書名の検証に失敗したため、Lync Windows ストアアプリがサインインできない

最新バージョンの Lync Windows ストアアプリを実行していない Office 365 ユーザーに対してサインインの問題が発生することがあります。 通常、この問題は複数のドメインを使用する場合に発生します (たとえば、SIP URI が**userA@domainZ.com** 、エッジサーバーが**sip.domainX.com**)。 この問題を解決するには、ユーザーは Lync Windows ストアアプリの最新バージョンをインストールする必要があります。これには、Windows 8.1 も必要です。

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a>Lync Windows ストアのアプリログを使用して問題のトラブルシューティングを行う

デバイスで生成されたログを使用して、問題のトラブルシューティングを行うことができます。 ログは次のフォルダーに格納されます。

% LocalAppData%\\\\LyncMX\_8wekyb3d8bbwe\\localappdata\\Tracing

ユーザーからログを取得する前に、ログ記録が有効になっていることを確認し、メモリに格納されているすべての情報がハードドライブ上のファイルにも保存されるように、ログを保存するようにユーザーに依頼します。

**ログ記録を有効にするには**

1.  デバイスで Lync Windows ストアアプリを開きます。

2.  画面の右端からスワイプします。 マウスを使用している場合は、画面の右上隅をポイントし、画面の下にマウスポインターを移動します。

3.  [**設定**] を選択し、[**オプション**] を選択して、**診断ログ**を **[オン**] に設定します。

4.  以前に**診断ログ**がオフになっていた場合は、Lync を再起動する必要があります。 Lync を再起動するには、次のいずれかの手順を実行します。
    
      - デバイスを再起動します。
    
      - Lync タスクを終了し、アプリをもう一度起動します。 タスクを終了するには、Windows タスクマネージャーを開き、[ **Lync**] を選択してから、[**タスクの終了**] をタップします。 Lync が表示されていない場合は、詳細**情報**をタップして、[**バックグラウンド処理**] の下で lync を探します。

**ログを保存するには**

1.  デバイスで Lync Windows ストアアプリを開きます。

2.  サインインしてください。

3.  画面の右端からスワイプします。 マウスを使用している場合は、画面の右上隅をポイントし、画面の下にマウスポインターを移動します。

4.  [**設定**] を選択し、[**バージョン情報**] を選択し、[**ログの保存**] を選択します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

