---
title: "Skype for Business Online サインイン エラーのトラブルシューティング"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
description: "Learn common causes for Skype for Business Online sign-errors and Work through troubleshooting these problems. "
---

# Skype for Business Online サインイン エラーのトラブルシューティング

> [!IMPORTANT]
> この記事は機械翻訳されています。機械翻訳についての「[免責事項](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#MT_Footer)」をお読みください。この記事の英語版を参照するには、[ここ](https://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1)をクリックしてください。 
  
Skype for Business Onlineサインイン エラーのトラブルシューティングを行うへのサインインに問題の一般的な原因を排除することで起動します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。
  
## 目的に合ったトピックをクリックしてください
<a name="__top"> </a>

> [Skype for Business Onlineサインイン エラーの一般的な原因をチェックします。](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc323194094)
    
> [特定のエラーの解決手順に従う (エンタープライズのみ)](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626440)
    
> [msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall)
    
> [DNS 設定を更新する](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service)
    
> [サード パーティの SSL 証明書を ADFS サーバー上にインストールします](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and)
    
> [セキュリティ資格情報を更新する](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1)
    
> [TrustModelData レジストリ キーを変更する](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry)
    
> [Active Directory のユーザー設定を更新する](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1)
    
> [Microsoft サポートのトラブルシューティング ガイドを使う](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626447)
    
> [詳細情報を収集し、ヘルプを探す](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1)
    
## Skype for Business Onlineサインイン エラーの一般的な原因をチェックします。
<a name="__toc323194094"> </a>

少数の原因が考えのほとんどのサインインに関する問題の原因し、これらの多くは簡単に修正します。 次の表は、サインイン エラーの一般的な原因とその解決するか、ユーザーがかかることがいくつかの手順を示します。
  
|**考えられる原因**|**解決法**|
|:-----|:-----|
|サインイン時にダイアログ ボックスが表示語句を含む: **が、サーバーがある、サインイン アドレスに対して信頼されていることを確認することはできません。接続しますか?** <br/> |ダイアログ ボックスに示されたドメイン名が、 **domainName.contoso.com** などのように自分の組織の信頼できるサーバーであることを確認します。[ **このサーバーを常に信頼する** ] チェック ボックスをオンにしてから [ **接続** ] をクリックするようにユーザーに依頼します。 <br/> エンタープライズのお客様は、ユーザーの各コンピューターで Windows のレジストリを変更すると、最初のサインイン時にこのメッセージが表示されないようにすることができます。詳細については、「[TrustModelData レジストリ キーを変更する](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry)」を参照してください。  <br/> |
|サインイン アドレス、ユーザー名、またはパスワードの入力が誤っています  <br/> | ユーザーのサインイン名とパスワードが正しいかどうかを確認してください。 <br/>  ユーザーのサインイン名が次のような形式になっていることを確認してください: **bobk@contoso.com**。これは、組織のネットワークにサインインする際に使用する形式とは異なる場合があります。  <br/>  もう一度サインインをユーザーに依頼します。 <br/> |
|パスワードを忘れました  <br/> |ユーザーのパスワードをリセットし、新しい一時的なパスワードをユーザーに通知します。  <br/> |
|Skype for Business Onlineを使用するライセンスがありません。  <br/> |ユーザーがSkype for Business Onlineユーザーとして登録されていることを確認します。されない場合は、ユーザーを登録し、またはをもう一度サインインします。  <br/> |
|Skype for Business Onlineがインストールされているバージョンが正しくありません。  <br/> |この問題は通常、「 **認証サービスがこのバージョンのプログラムと互換性がない可能性があります**」という語句を含むエラー メッセージに関連しています。  <br/> アンインストールして、Office 365 ポータルからSkype for Business Onlineを再インストールするユーザーに依頼します。  <br/> |
|サインインに必要な個人証明書を取得するときに問題が発生しました  <br/> |ユーザーのサインイン アドレスが最近変更された場合は、キャッシュされたサインイン用のデータを削除する必要があります。サインアウトして、サインイン情報へのサインイン画面で、リンクから、やり直しての削除] をクリックしてもらいます。  <br/> |
|カスタム ドメイン名をセットアップしていますが、変更内容がシステムに反映し終わっていない場合があります  <br/> |最初に、変更を反映するようにドメイン名サービス (DNS) レコードが変更されていることを確認します。  <br/> 既に DNS に必要な変更をした場合は、後でログインするようユーザーに通知します。DNS の変更は、システム全体に反映するため 72 時間かかる場合があります。  <br/> |
|システム クロックがサーバー クロックと同期していません  <br/> |ネットワーク ドメイン コントローラーが信頼できると外部時間ソースと同期していることを確認します。 詳細については、Microsoft サポート技術情報の記事 816042「[Windows Server で権限のあるタイム サーバーを構成する方法](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)」を参照してください。  <br/> |
   
[この記事は機械翻訳されています。機械翻訳についての「免責事項」をお読みください。この記事の英語版を参照するには、ここhttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1をクリックしてください。 Skype for Business Onlineサインイン エラーのトラブルシューティングを行うへのサインインに問題の一般的な原因を排除することで起動します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## 特定のエラーの解決手順に従う (エンタープライズのみ)
<a name="__toc325626440"> </a>

> [!IMPORTANT]
> この手順は、主に Microsoft Office 365 Plan E のお客様が対象です。Office 365 Plan P のお客様は、次のセクション「[詳細情報を収集し、ヘルプを探す](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1)」に進んでください。 
  
前のセクションでの説明を試した後でもサインインできない場合、エラーのタイプに応じてその他のトラブルシューティングを行うことができます。 次の表は、最も一般的なエラー メッセージと考えられる原因を示しています。次の表は、問題にそれぞれ対応するための詳細手順です。
  
|**エラー メッセージ**|**考えられる原因**|**解決法**|
|:-----|:-----|:-----|
|サインイン アドレスが見つかりません  <br/> |Microsoft Online Services サインイン アシスタントからのサインイン要求 (msoidsvc.exe) が、外部ファイアウォール、またはプロキシ サーバーを通っていません。  <br/> |[msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall) <br/> |
|サーバーが一時的に利用できません  <br/> |組織でカスタム ドメインを使用している場合、必要なドメイン ネーム システム (DNS:Domain Name System) が見つからない、または正しくない場合があります。  <br/> |[DNS 設定を更新する](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service) <br/> |
|サーバーが一時的に利用できません  <br/> |Active Directory フェデレーション サービス (ADFS) によるシングル サインオンを使用している組織では、サード パーティの証明機関からの証明書ではなく、自己署名された Secure Socket Layer (SSL) 証明書を使用していた可能性があります。  <br/> |[サード パーティの SSL 証明書を ADFS サーバー上にインストールします](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and) <br/> |
|サインインに必要な個人証明書を取得する際に問題があります  <br/> |既に削除した場合キャッシュされたサーバー データを使用してサインイン エラーが引き続き表示される、ユーザーのセキュリティ資格情報が破損している可能性がありますが、やユーザーのコンピューターの RSA フォルダーでは認証がブロックされていない可能性があります。  <br/> |[セキュリティ資格情報を更新する](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1) <br/> |
|ユーザーが初めてサインインするときは、証明書を承認するためのダイアログ ボックスが表示されます  <br/> |Skype for Businessサーバーが **TrustModelData**レジストリ キーにまだ表示されていない場合は、このダイアログ ボックスが表示されます。  <br/> |[TrustModelData レジストリ キーを変更する](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry) <br/> |
|ユーザーに対して SIP が有効ではありません  <br/> |以前に組織で Microsoft Office Communications Server または Microsoft Lync Server 2010 をインストールしていた場合、その使用をやめる前にサーバーからユーザーを削除していなかった可能性があります。その結果、Active Directory ドメイン サービスで **msRTCSIP-UserEnabled** 属性が依然として **FALSE** に設定されています。 <br/> |[Active Directory のユーザー設定を更新する](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1) <br/> |
   
### msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します
<a name="__add_a_firewall"> </a>

この手順は、" **サインイン アドレスが見つかりませんでした**" というエラー メッセージに対して考えられる修正です。
  
 **注**: 以下の手順では、Microsoft Forefront Threat Management Gateway (TMG) 2010 を使用していることを前提としています。異なる Web ゲートウェイのソリューションがある場合は、以下の手順 4 で説明する設定を使用します。
  
Forefront TMG 2010 で Msoidsvc.exe のアプリケーション エントリを作成するには、次の手順を実行します。
  
1. Forefront の左側のウィンドウで、[ **ネットワーク**] をクリックします。
    
2. [ **ネットワーク**] タブをクリックします。右側のウィンドウの [ **タスク**] タブで、[ **Forefront TMG クライアント設定の構成**] をクリックします。
    
3. [ **Forefront TMG クライアント設定**] ダイアログ ボックスで [ **新規作成**] をクリックします。
    
4. **[アプリケーション エントリの設定**] ダイアログ ボックスで、次の規則を構成します。
    
|****アプリケーション****|****キー****|****値****|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Disable  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
詳細については、Microsoft サポート技術情報の記事 2409256「、 [、オンプレミスのファイアウォールが接続をブロックするために、Skype for Business Online に接続できない](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)を参照してください。
  
### DNS 設定を更新する
<a name="__update_dns_service"> </a>

カスタム ドメインが組織で規定されている場合、この手順は、" **サーバーが一時的に利用できません** " というエラー メッセージに対して考えられる修正です。
  
- 次の CNAME レコードをドメインに追加する方法については、ドメイン名レジストラーにお問い合わせください。
    
  - **DNS レコード タイプ**: CNAME
    
  - **名前**: sip
    
  - **値/参照先**: sipdir.online.microsoft.com
    
詳細については、「Microsoft サポート技術情報の記事 2566790「、[トラブルシューティングの Skype for Business Online DNS 構成に関する問題は、Office 365 の](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)、および Office 365 Wiki の記事、 [Skype 連携させるネットワークの使用」を参照していますください。for Business (Lync) Online](https://go.microsoft.com/fwlink/?linkid=231156)します。
  
### サード パーティの SSL 証明書を ADFS サーバー上にインストールします
<a name="__verify_upn_and"> </a>

Active Domain Federation Services (ADFS) サーバーにサード パーティの SSL 証明書をインストールするには、次の手順を実行します。
  
1. サードパーティの証明機関 (VeriSign や Thawte など) から SSL 証明書を取得します。
    
2. 証明書を ADFS サーバー上 ADFS 管理コンソールを使用してインストールします。
    
### セキュリティ資格情報を更新する
<a name="__update_security_credentials_1"> </a>

この手順は、" **サインインに必要な個人証明書を取得する際に問題があります**" というエラー メッセージに対して考えられる修正です。
  
考えられる証明書または資格情報に関する問題をなくすには、まず Windows 証明書マネージャーでユーザー証明書を更新します。これを行うには、次の手順を実行します。
  
1. Windows 証明書マネージャーを開きます。これを行うには、[ **スタート**] をクリックし、[ **ファイル名を指定して実行**] をクリックして、「 **certmgr.msc**」と入力し、[ **OK**] をクリックします。
    
2. [ **個人用**] をダブルクリックし、[ **証明書**] をダブルクリックします。
    
3. [ **発行先**] 列を基準にして並べ替えて、Communications Server が発行した証明書を確認します。
    
4. 証明書を右クリックし、[ **削除**] をクリックします。
    
次に、Windows 7 を実行している場合は、Windows 資格情報マネージャーで、格納されている資格情報を削除します。これを行うには、次の手順を実行します。
  
1. [ **スタート**] をクリックし、[ **コントロール パネル**] をクリックします。次に、[ **資格情報マネージャー**] をクリックします。
    
2. Skype for Businessオンラインへの接続に使用する資格情報のセットを見つけます。
    
3. 資格情報のセットを展開し、[ **資格情報コンテナーから削除**] をクリックします。
    
4. もう一度サインインし、ユーザーの資格情報を再入力します。
    
最後に、ユーザー資格情報を更新した後でもまだサインインできない場合は、ユーザーのコンピューターの RSA フォルダーを削除してください。ユーザーの認証プロセスの完了がブロックされている可能性があるためです。
  
1. 管理者アカウントを使用して、ユーザーのコンピューターにサインインします。
    
2. 必要に応じて、 **非表示のファイルを表示する**フォルダーの表示オプションをオンにします。
    
3. エクスプローラーのアドレス バーに次のように入力します。 **C:\\Documents and Settings\\<ユーザー名>\\Application Data\\Microsoft\\Crypto\\RSA**。 ** ** *<ユーザー名>* **** は **Windows のサインイン名** です。
    
4. **S-1-5-21-** という名前で始まり、後ろに数字のストリングが続くフォルダーを削除します。
    
### TrustModelData レジストリ キーを変更する
<a name="__modify_trustmodeldata_registry"> </a>

ユーザーが初めてサインインすると、次のようなものが含まれているダイアログ ボックスが表示があります: **が、サーバーがある、サインイン アドレスに対して信頼されていることを確認することはできません。接続しますか?**これは、セキュリティ機能、およびエラーではありません。ただし、することができます] ダイアログ ボックスが表示されないようにグループ ポリシー オブジェクト (GPO) を使用して、1 回サインインする前に、ドメイン名をユーザーのコンピューターを更新します。これを行うには、次の操作を行います。
  
- 作成し、 Skype for Businessドメイン名を付加する GPO を展開: たとえば、domainName.contoso.comto \\software\\policies\\microsoft\\communicator\\trustmodeldata の現在の値。
    
> [!IMPORTANT]
> 既存の値を単に置き換えるのではなく、既存の値にドメイン名を *追加*  する必要があります。
  
詳細については、Microsoft サポート技術情報の記事 2531068「[Skype for Business (Lync) はサインイン アドレスに対してサーバーが信頼されているかどうかを検証できません](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)」を参照してください。
  
### Active Directory のユーザー設定を更新する
<a name="__update_user_settings_1"> </a>

以前に組織で Microsoft Office Communications Server または Microsoft Lync Server 2010 をインストールしていた場合、その使用をやめる前にサーバーからユーザーを削除していなかった可能性があります。その結果、Active Directory ドメイン サービスで **msRTCSIP-UserEnabled** 属性が依然として **FALSE** に設定されています。
  
この問題を解決するには、次の手順を実行します。
  
1. 関係するすべてのユーザーの **msRTCSIP-UserEnabled** 属性を **TRUE** に更新します。
    
2. Microsoft Online Services ディレクトリ同期ツール (DirSync) を再実行します。詳細については、 [Azure Active Directory とディレクトリを社内に AIntegrate](https://technet.microsoft.com/en-us/library/hh967642.aspx)を参照してください。
    
[この記事は機械翻訳されています。機械翻訳についての「免責事項」をお読みください。この記事の英語版を参照するには、ここhttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1をクリックしてください。 Skype for Business Onlineサインイン エラーのトラブルシューティングを行うへのサインインに問題の一般的な原因を排除することで起動します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## Microsoft サポートのトラブルシューティング ガイドを使う
<a name="__toc325626447"> </a>

ユーザーのサインインの問題を解決するのにはまだできない場合は、Microsoft サポート技術情報の記事 2541980「、 [Skype for Business Online のサインインに関する問題をトラブルシューティングする方法](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)候補を確認します。
  
## 詳細情報を収集し、ヘルプを探す
<a name="__collect_more_information_1"> </a>

場合は、上記のガイダンスを実行しても、サインインに関する問題を解決できない、その他の情報を収集し、テクニカル サポートにお問い合わせください。これを行うには、次の手順に従います。
  
1. ユーザーのコンピューターから、ログ ファイルと Windows イベント ログの詳細を取得します。詳しい手順については、 [Skype for Business (Lync) のエラー ログを有効にする](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)エンド ユーザー ヘルプ トピックを参照してください。
    
2. ログ ファイル、およびエラーに関する詳細情報を Microsoft テクニカル サポートにお送りください。
    
問題のコンピューターに Microsoft Online Services Diagnostic and Logging (MOSDAL) サポート ツールキットをインストールして追加の診断情報を提供するように求められることがあります。詳細については、「[MOSDAL サポート ツールキットを使用する](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)」を参照してください。
  
[この記事は機械翻訳されています。機械翻訳についての「免責事項」をお読みください。この記事の英語版を参照するには、ここhttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1をクリックしてください。 Skype for Business Onlineサインイン エラーのトラブルシューティングを行うへのサインインに問題の一般的な原因を排除することで起動します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **機械翻訳についての免責事項**: この記事の翻訳はコンピューター システムによって行われており、人間の手は加えられていません。マイクロソフトでは、英語を話さないユーザーがマイクロソフトの製品、サービス、テクノロジに関するコンテンツを理解するのに役立てるため、こうした機械翻訳を提供しています。記事は機械翻訳されているため、用語、構文、文法などに誤りがある場合があります。 
  

