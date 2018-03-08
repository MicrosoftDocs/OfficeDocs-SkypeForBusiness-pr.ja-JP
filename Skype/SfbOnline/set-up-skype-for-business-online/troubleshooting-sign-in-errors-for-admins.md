---
title: "管理者向けの Skype を Business Online サインイン エラーのトラブルシューティング"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "これらの問題のトラブルシューティングを行って Skype for Business Online のサインイン エラーと作業の一般的な原因を説明します。 "
ms.openlocfilehash: aa5069e5fd5bf40ebd460c03b72ce8d9327da6d2
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>管理者向けの Skype を Business Online サインイン エラーのトラブルシューティング

Skype for Business Online サインイン エラーのトラブルシューティングにまずへのサインインに問題の一般的な原因を除去します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。 
  
## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください
<a name="top"> </a>

> [Skype for Business Online サインイン エラーの一般的な原因をチェックします。](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
    
> [特定のエラー (エンタープライズのみ) の解決手順に従う](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
    
> [Msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します。](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
    
> [DNS の設定を更新します。](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
    
> [サード パーティの SSL 証明書を ADFS サーバー上にインストールします。](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
    
> [セキュリティ資格情報を更新します。](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
    
> [TrustModelData レジストリ キーを変更します。](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
    
> [Active Directory でユーザー設定を更新します。](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
    
> [Microsoft サポートのトラブルシューティング ガイドを使う](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
    
> [詳細情報を収集し、その他のヘルプを探す.](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)
    
## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Skype for Business Online サインイン エラーの一般的な原因をチェックします。
<a name="toc323194094"> </a>

少数の原因が考えのほとんどのサインインに関する問題の原因し、これらの多くは簡単に修正します。次の表は、サインイン エラーの一般的な原因とその解決するか、ユーザーがかかることがいくつかの手順を示します。
  
|**考えられる原因**|**解決方法**|
|:-----|:-----|
|サインイン時にダイアログ ボックスが表示語句を含む:**が、サーバーがある、サインイン アドレスに対して信頼されていることを確認することはできません。接続しますか?** <br/> |ダイアログ ボックスで、ドメイン名に、組織内の信頼されたサーバーがあることを確認、たとえば、 **domainName.contoso.com**します。**常にこのサーバーを信頼する**] チェック ボックスをオンにユーザーに確認し、[**接続**] をクリックします。 <br/> 企業のお客様は、このメッセージをされたユーザーが各ユーザーのコンピューターで Windows レジストリを編集して、1 回サインインしたときに表示されないようにします。詳細については、[変更 TrustModelData レジストリ キー](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)を参照してください。<br/> |
|サインイン アドレス、ユーザー名、またはパスワードの入力が誤っています  <br/> | ユーザーのサインイン名とパスワードが正しいことを確認します。 <br/>  ユーザーのサインイン名が次のように書式設定されたことを確認する: **bobk@contoso.com**します。組織のネットワークへのサインインに使用する書式と異なる場合があります。  <br/>  もう一度サインインをユーザーに依頼します。 <br/> |
|パスワードを忘れました  <br/> |ユーザーのパスワードを再設定し、新しい一時的なパスワードに通知します。  <br/> |
|Skype for Business Online を使用ライセンスがありません。  <br/> |ユーザーが Skype for Business Online ユーザーとして登録されていることを確認します。されない場合は、ユーザーを登録し、またはをもう一度サインインします。  <br/> |
|Skype for Business Online がインストールされているバージョンが正しくありません。  <br/> |この問題は通常、次の語句を含むエラー メッセージに関連付けられて:**認証サービスがこのバージョンのプログラムと互換性があります**。  <br/> アンインストールして、Skype を for Business Online、Office 365 ポータルから再インストールするユーザーに依頼します。  <br/> |
|サインインに必要な個人証明書を取得する際に問題があります  <br/> |ユーザーのサインイン アドレスが最近変更された場合は、キャッシュされたサインイン用のデータを削除する必要があります。サインアウトして、サインイン情報へのサインイン画面で、リンクから、やり直しての削除] をクリックしてもらいます。  <br/> |
|カスタム ドメイン名をセットアップしていますが、変更内容がシステムに反映し終わっていない場合があります  <br/> |最初に、変更を反映するようにドメイン名サービス (DNS) レコードが変更されていることを確認します。  <br/> 既に DNS に必要な変更をした場合は、後でログインするようユーザーに通知します。DNS の変更は、システム全体に反映するため 72 時間かかる場合があります。  <br/> |
|システム クロックがサーバー クロックと同期していません  <br/> |信頼性の高い外部タイム ソースと、ネットワークのドメイン コント ローラーが同期されることを確認します。詳細については、Microsoft サポート技術情報の記事 816042、 [Windows Server で時間を優先するサーバーを構成する方法](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)を参照してください。<br/> |
   
Skype for Business Online サインイン エラーのトラブルシューティングにまずへのサインインに問題の一般的な原因を除去します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。 
  
## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>特定のエラーの解決手順に従う (エンタープライズのみ)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  次の手順は、Microsoft Office 365 プラン E の顧客の主な目的としています。Office 365 プラン P 製品を使用している場合は、[詳細情報を収集しその他のヘルプを探す. ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)、次のセクションに進みます。 
  
ユーザーは、前のセクションの提案を実施した後にサインインできない場合、は、エラーの種類に基づいて、その他のトラブルシューティングを実行できます。次の表は、最も一般的なエラー メッセージと考えられる原因を示します。各問題を解決する手順の詳細については、次の表。
  
|**エラー メッセージ**|**考えられる原因**|**解決方法**|
|:-----|:-----|:-----|
|サインイン アドレスが見つかりません  <br/> |Microsoft Online Services サインイン アシスタントからのサインイン要求 (msoidsvc.exe) が、外部ファイアウォール、またはプロキシ サーバーを通っていません。  <br/> |[Msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します。](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|サーバーが一時的に利用できません  <br/> |組織でカスタム ドメインを使用している場合、必要なドメイン ネーム システム (DNS:Domain Name System) が見つからない、または正しくない場合があります。  <br/> |[DNS の設定を更新します。](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|サーバーが一時的に利用できません  <br/> |Active Directory フェデレーション サービス (ADFS) によるシングル サインオンを使用している組織では、サード パーティの証明機関からの証明書ではなく、自己署名された Secure Socket Layer (SSL) 証明書を使用していた可能性があります。  <br/> |[サード パーティの SSL 証明書を ADFS サーバー上にインストールします。](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|サインインに必要な個人証明書を取得する際に問題があります  <br/> |既に削除した場合キャッシュされたサーバー データを使用してサインイン エラーが引き続き表示される、ユーザーのセキュリティ資格情報が破損している可能性がありますが、やユーザーのコンピューターの RSA フォルダーでは認証がブロックされていない可能性があります。  <br/> |[セキュリティ資格情報を更新します。](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|ユーザーが初めてサインインするときは、証明書を承認するためのダイアログ ボックスが表示されます  <br/> |Skype for Business サーバーが**TrustModelData**レジストリ キーにまだ追加されていない場合は、このダイアログ ボックスが表示されます。 <br/> |[TrustModelData レジストリ キーを変更します。](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|ユーザーに対して SIP が有効ではありません  <br/> |組織には、Microsoft Office Communications Server または Microsoft Lync Server 2010 の以前のインストールがある、可能性がありますいないから削除したユーザー サーバー解除にする前にします。その結果**に UserEnabled**属性**FALSE** Active Directory ドメイン サービスの設定が。<br/> |[Active Directory でユーザー設定を更新します。](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |
   
### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します
<a name="add-a-firewall"> </a>

この手順は次のエラー メッセージに対して考えられる修正:**サインイン アドレスは見つかりませんでした**。
  
 **メモ**: 次の手順では、Microsoft Forefront 脅威 Management Gateway (TMG) 2010 を使用するいると仮定します。別の web ゲートウェイ ソリューションを使っている場合は、以下の手順 4 で説明する、設定を使います。
  
Forefront TMG 2010 で Msoidsvc.exe のアプリケーション エントリを作成するには、次の手順を実行します。
  
1. Forefront の左側のウィンドウで [**ネットワーク**] をクリックします。
    
2. [**ネットワーク**] タブをクリックします。右側のウィンドウで [**タスク**] タブで、[ **Forefront TMG クライアント設定の構成**] をクリックします。
    
3. **Forefront TMG クライアント設定**] ダイアログ ボックスで、[**新規**] をクリックします。
    
4. **アプリケーション エントリの設定**] ダイアログ ボックスで、次のルールを構成します。
    
|**アプリケーション**|**キー**|**{Value}**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Disable  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
詳細について[をオンプレミスのファイアウォールが接続をブロックするために、Skype for Business Online に接続できない](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)Microsoft サポート技術情報の記事 2409256「を参照してください。
  
### <a name="update-dns-settings"></a>DNS 設定を更新する
<a name="update-dns-service"> </a>

組織にカスタム ドメインがある場合は、この手順は、次のエラー メッセージに対して考えられる修正:**サーバーが一時的に利用できません**。
  
- 次の CNAME レコードをドメインに追加する方法については、ドメイン名レジストラーにお問い合わせください。
    
  - **DNS レコードの種類**: CNAME 
    
  - **名前**: sip
    
  - **値/先**: sipdir.online.microsoft.com
    
詳細については、Microsoft サポート技術情報の記事 2566790「 [Office 365 でビジネス Online DNS 構成の問題のトラブルシューティング Skype](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)を参照してください。
  
### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>サード パーティの SSL 証明書を ADFS サーバー上にインストールします
<a name="verify-upn-and"> </a>

Active Domain Federation Services (ADFS) サーバーにサード パーティの SSL 証明書をインストールするには、次の手順を実行します。
  
1. サードパーティの証明機関 (VeriSign や Thawte など) から SSL 証明書を取得します。
    
2. 証明書を ADFS サーバー上 ADFS 管理コンソールを使用してインストールします。 
    
### <a name="update-security-credentials"></a>セキュリティ資格情報を更新する
<a name="update-security-credentials"> </a>

この手順は、エラー メッセージ**のサインインに必要な個人証明書を取得する際に問題**の考えられる修正です。
  
証明書または資格情報の可能性のある問題を消すために最初に、ユーザーの証明書では、Windows 証明書を更新します。これを行うには、次の手順に従います。
  
1. Windows の証明書マネージャーを開きます。これを行うには、[**スタート**] ボタン**実行**] をクリックして、 **certmgr.msc**] と入力し、[ **OK**] をクリックします。 
    
2. **個人**をダブルクリックし、[**証明書**をダブルクリックします。 
    
3. **[発行先**] 列、Communications Server が発行した証明書を確認して並べ替えます。
    
4. 証明書を右クリックし、[**削除**] をクリックします。 
    
次に、Windows 7 を実行している場合は、Windows 資格情報マネージャーで、格納されている資格情報を削除します。これを行うには、次の手順を実行します。
  
1. [**スタート**] ボタン、**コントロール パネル**] をクリックし、[**資格情報マネージャー**] をクリックします。 
    
2. Skype for Business Online に接続するための資格情報のセットを見つけます。 
    
3. 資格情報のセットを展開し、**コンテナーから削除**] をクリックします。 
    
4. もう一度サインインし、ユーザーの資格情報を再入力します。
    
最後に、ユーザーもサインインできない場合、資格情報を更新した後、試してくださいユーザーのコンピューターの RSA フォルダーを削除するため、ユーザーの認証プロセスの実行がブロックされている可能性があります。
  
1. 管理者アカウントを使用して、ユーザーのコンピューターにサインインします。
    
2. 必要に応じて、**非表示のファイルを表示する**フォルダーの表示オプションをオンにします。 
    
3. 次に、アドレス バー エクスプ ローラーの入力: **c:\\ドキュメントと設定\\ユーザー名\\アプリケーション データ\\Microsoft\\暗号化\\RSA**、***ユーザー名***には、Windows のサインイン名です。
    
4. 名前で始まり、任意のフォルダーを削除する**S-1-5-21 -**数字のストリングが続きます。
    
### <a name="modify-trustmodeldata-registry-keys"></a>TrustModelData レジストリ キーを変更する
<a name="modify-trustmodeldata-registry"> </a>

ユーザーが初めてサインインすると、次のようなものが含まれているダイアログ ボックスが表示があります:**が、サーバーがある、サインイン アドレスに対して信頼されていることを確認することはできません。接続しますか?**これは、セキュリティ機能、およびエラーではありません。ただし、することができます] ダイアログ ボックスが表示されないようにグループ ポリシー オブジェクト (GPO) を使用して、1 回サインインする前に、ドメイン名をユーザーのコンピューターを更新します。これを行うには、次の操作を行います。
  
- 作成して、Skype for Business のドメイン名を付加する GPO を展開する-domainName.contoso.com—to HKEY_LOCAL_MACHINE の現在の値など、\\ソフトウェア\\ポリシー\\Microsoft\\Communicator\\TrustModelData します。
    
> [!IMPORTANT]
>  必要な*追加*既存の値にドメイン名を置き換えるだけでなくします。
  
詳細については、 [Skype for Business (Lync) のサーバーが、サインイン アドレスに対して信頼されていることを確認できない](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)Microsoft サポート技術情報の記事 2531068「、を参照してください。
  
### <a name="update-user-settings-in-active-directory"></a>Active Directory のユーザー設定を更新する
<a name="update-user-settings"> </a>

組織には、Microsoft Office Communications Server または Microsoft Lync Server 2010 の以前のインストールがある、可能性がありますいないから削除したユーザー サーバー解除にする前にします。その結果**に UserEnabled**属性**FALSE** Active Directory ドメイン サービスの設定が。
  
この問題を解決するには、次の手順を実行します。
  
1. 影響を受けるすべてのユーザー**に UserEnabled**属性を**TRUE**に更新します。
    
2. Microsoft Online Services ディレクトリ同期ツール (DirSync) を再実行します。詳細については、 [AIntegrate 社内に Azure Active Directory ディレクトリ](https://technet.microsoft.com/en-us/library/hh967642.aspx)を参照してください。 
    
Skype for Business Online サインイン エラーのトラブルシューティングにまずへのサインインに問題の一般的な原因を除去します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。 
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Microsoft サポートのトラブルシューティング ガイドを使う
<a name="toc325626447"> </a>

ユーザーのサインインの問題を解決するのにはまだできない場合は、Microsoft サポート技術情報の記事 2541980「、 [Skype for Business Online のサインインに関する問題をトラブルシューティングする方法](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)の提案を確認します。
  
## <a name="collect-more-information-and-seek-additional-help"></a>詳細情報を収集し、ヘルプを探す
<a name="collect-more-information"> </a>

場合は、上記のガイダンスを実行しても、サインインに関する問題を解決できない、その他の情報を収集し、テクニカル サポートにお問い合わせください。これを行うには、次の手順に従います。 
  
1. ユーザーのコンピューターから、ログ ファイルと Windows イベント ログの詳細を取得します。詳しい手順については、 [Lync でのエラー ログを有効にする](http://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)エンド ユーザー ヘルプ トピックを参照してください。
    
2. ログ ファイル、およびエラーに関する詳細情報を Microsoft テクニカル サポートにお送りください。
    
影響を受けるユーザーのコンピューターで、Microsoft Online Services Diagnostic and Logging (MOSDAL) サポート ツールキットをインストールして、追加の診断情報を指定するを求められる場合があります。詳細については、「 [MOSDAL サポート ツールキット](http://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)」を参照してください。
  
Skype for Business Online サインイン エラーのトラブルシューティングにまずへのサインインに問題の一般的な原因を除去します。必要に応じて、特定の解像度がエラーの種類に基づいて、手順に従って、[できます。ユーザーもサインインできない場合、追加情報を収集し、[その他のヘルプを探す. します。 
  
## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップします。](set-up-skype-for-business-online.md)

[ビジネス ユーザー向けの Skype Skype の連絡先を追加できるようにします。](let-skype-for-business-users-add-skype-contacts.md)
