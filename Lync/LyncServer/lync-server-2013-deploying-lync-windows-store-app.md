---
title: Lync Windows ストア アプリの展開
TOCTitle: Lync Windows ストア アプリの展開
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ822971(v=OCS.15)
ms:contentKeyID: 52056655
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Windows ストア アプリの展開

 

_**トピックの最終更新日:** 2016-12-08_

Lync Windows ストア アプリ をユーザーが使用できるようにするには、展開で「[Lync Windows ストア アプリの要件](lync-server-2013-lync-windows-store-app-requirements.md)」が満たされている必要があります。Lync Windows ストア アプリ をサポートするための Lync Server 2013 の構成について詳しくは、NextHop のブログ記事「Lync Server Autodiscover and the Lync Windows Store App」([http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)) をご覧ください。サーバー環境を正しく構成したら、ユーザーに対して Windows Store で "Lync" を検索して Lync アプリをダウンロードするよう指示します。

## Lync Windows ストア アプリ での多要素認証の有効化

Lync Server 2013 の累積的な更新プログラム: 2013 年 6 月 では、Lync Windows ストア アプリ クライアントの多要素認証のサポートが追加されています。Lync 会議へのサインイン時に外部ユーザーを認証するため、ユーザー名とパスワードのほか、追加の認証方法 (スマート カードや PIN など) を必須とすることができます。多要素認証を有効にするには、Active Directory フェデレーション サービス (AD FS) のフェデレーション サーバーを展開して Lync Server 2013 でパッシブ認証を有効にする必要があります。AD FS を構成した後、外部ユーザーが Lync 会議に参加しようとすると、多要素認証 Web ページが表示されます。このページでは、構成した追加の認証方法と共にユーザー名とパスワードの入力を求められます。


> [!IMPORTANT]
> Lync Windows ストア アプリ の多要素認証の AD FS を構成する場合の重要な考慮事項を次に示します。 
> <UL>
> <LI>
> <P>Lync Server 2013 の累積的な更新プログラム: 2013 年 6 月 を含む Lync Server 2013 が最小限必要です。Lync 2013 デスクトップ クライアントでは Lync Server 2013 の累積的な更新プログラム: 2013 年 6 月 が不要なため、パッシブ認証が有効です。Lync 2013 クライアントが認証できるためです。ただし、Lync Windows ストア アプリ クライアントの認証プロセスは完了に失敗し、通知やエラー メッセージは表示されません。</P>
> <LI>
> <P>パッシブ認証が提供される唯一の認証の種類となるよう、サーバーを構成する必要があります。</P>
> <LI>
> <P>ハードウェア ロード バランサーを使用する場合、ロード バランサーで Cookie の永続性を有効にし、Lync Windows ストア アプリ クライアントからのすべての要求が同じフロントエンド サーバーによって処理されるようにします。</P>
> <LI>
> <P>Lync Server と AD FS サーバー間で証明書利用者の信頼を確立するときは、Lync 会議の最大の長さに対して十分な長さのトークンの存続期間を割り当てます。通常、トークンの存続期間は 240 分で十分です。</P></LI></UL>



**多要素認証を構成するには**

1.  AD FS フェデレーション サーバーの役割をインストールします。詳しくは、「Active Directory フェデレーション サービス 2.0 展開ガイド (英語)」<http://go.microsoft.com/fwlink/p/?linkid=267511>をご覧ください。

2.  AD FS の証明書を作成します。詳しくは、「シングル サインオンで使用するために AD FS を計画して展開する」の「フェデレーション サーバーの証明書」([http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)」をご覧ください。

3.  Windows PowerShell コマンドライン インターフェイスで次のコマンドを実行します。
    
        add-pssnapin Microsoft.Adfs.powershell

4.  次のコマンドを実行し、パートナーシップを確立します。
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  以下の証明書利用者のルールを設定します。
    
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'

       &nbsp;
    
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules

       &nbsp;
    
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml

## サインインできない原因となりうる既知の問題

## Lync Windows ストア アプリ を実行しているデバイスの日時が正確に設定されていない

デバイスの時刻設定は、サーバーの時刻設定と同期される必要があります。これは、Microsoft Surface などのデバイスや、ドメインに参加していない Windows RT を実行しているその他のデバイスでは特に重要です。これらのデバイスでタイム サーバーから自動的に時刻を設定するには、デバイスで表示されるコマンド プロンプトから次のコマンドを実行します。

    w32tm /resync

## Lync Windows ストア アプリ が Lync サーバーまたはサービスにアクセスできない

Lync Windows ストア アプリ は、Windows 8 で物理デバイスとして登録されていないネットワーク アダプター (4G LTE USB モデムなど) 経由では、Lync サーバーまたはサービスにアクセスできない場合があります。Lync Windows ストア アプリ では、デスクトップのアプリやブラウザーが他のサーバーや Web サイトにアクセスできていても、この問題が発生する場合があります。

## Lync Windows ストア アプリが Lync Server 2010 や Office Communications Server 2007 R2 エッジ サーバーでサインインできない

トポロジが Office Communications Server 2007 R2 エッジ サーバーを含む Lync Server 2010 で構成されている場合、Lync Server 2010 用の累積した更新プログラム (2013 年 7 月) で入手できるトポロジ ビルダーの更新バージョンを実行する必要があります。前のバージョンのトポロジ ビルダーでは、Office Communications Server 2007 エッジ サーバーに対する必要なマッピングが作成されないため、Lync Windows ストア アプリ クライアントがサインインできません。次の手順が必要です。

1.  Lync Server 2010 用の累積した更新プログラム (2013 年 7 月) を、Lync Server 2010 プールと Lync Server 2010 ディレクターにインストールします。

2.  次の手順を実行して Lync AutoDiscover の構成を更新し、外部 SIP エントリ ポイントがエッジ サーバーのアドレスであると示すようにします。
    
    1.  Lync Server 管理シェルを開きます。
    
    2.  次のコマンドを実行します。
        
            Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443

## Lync Windows ストア アプリが証明書名の検証エラーのためにサインインできない

Office 365 ユーザーが最新バージョンでない Lync Windows ストア アプリを使用している場合、サインインの問題が起こることがあります。この問題は通常、複数ドメインを使用している場合に発生します (たとえば、SIP URI が **userA@domainZ.com** で、エッジ サーバーが **sip.domainX.com** の場合)。この問題を解決するには、最新バージョンの Lync Windows ストア アプリをインストールする必要があり、それには Windows 8.1 のインストールも必要です。

## Lync Windows ストア アプリ ログを使用して問題のトラブルシューティングを行う

デバイスで生成されるログを使用して、問題のトラブルシューティングを行うことができます。ログは次のフォルダーに保存されています。

%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing

ユーザーからログを取得する前に、ログ作成がオンになっていることを確認し、ユーザーに対してログを保存するよう指示して、メモリ内に保存されるすべての情報がハード ドライブのファイルにも保存されるようにします。

**ログ作成をオンにするには**

1.  デバイスで Lync Windows ストア アプリ を開きます。

2.  画面の右側からスワイプします。マウスをお使いの場合は、画面の右上隅をポイントし、マウス ポインターを画面の下に移動します。

3.  \[**設定**\]、\[**オプション**\] の順に選び、\[**診断ログ**\] を \[**オン**\] に設定します。

4.  \[**診断ログ**\] が前にオフであった場合は、Lync を再起動する必要があります。Lync を再起動するには、次のいずれかの操作を実行します。
    
      - デバイスを再起動します。
    
      - Lync タスクを終了し、アプリを再度起動します。タスクを終了するには、Windows タスク マネージャーを開き、\[**Lync**\] を選び、\[**タスクの終了**\] をタップします。Lync が表示されない場合は、\[**詳細**\] をタップして \[**バックグラウンド プロセス**\] で Lync を探します。

**ログを保存するには**

1.  デバイスで Lync Windows ストア アプリ を開きます。

2.  サインインします。

3.  画面の右側からスワイプします。マウスをお使いの場合は、画面の右上隅をポイントし、マウス ポインターを画面の下に移動します。

4.  \[**設定**\]、\[**バージョン情報**\]、\[**ログを保存**\] の順に選びます。

