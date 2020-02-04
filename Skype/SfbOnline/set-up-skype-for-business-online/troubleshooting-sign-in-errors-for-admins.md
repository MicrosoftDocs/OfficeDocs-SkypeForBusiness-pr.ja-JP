---
title: Skype for Business Online サインイン エラーのトラブルシューティング (管理者用)
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Skype for Business Online のサインイン エラーの一般的な原因およびこれらの問題を解決する方法について説明します。 '
ms.openlocfilehash: 3315dec928ec019dc8f970171d2eb44693cdf909
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692772"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Skype for Business Online サインイン エラーのトラブルシューティング (管理者用)

Skype for Business Online のサインイン エラーのトラブルシューティングは、サインインの失敗を引き起こす最も一般的な原因を取り除くことから始めます。 必要に応じて、エラーのタイプに応じて特定の解決手順に従うことができます。 それでもサインインできない場合は、追加の情報を収集してサポートを受けるようにします。

## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください
<a name="top"> </a>

> [Skype for Business Online のサインインエラーの一般的な原因をチェックする](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
> 
> [特定のエラーの解決手順に従う (エンタープライズのみ)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
> 
> [msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加する](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
> 
> [DNS 設定を更新する](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
> 
> [サード パーティの SSL 証明書を ADFS サーバー上にインストールする](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
> 
> [セキュリティの資格情報を更新する](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
> 
> [TrustModelData レジストリ キーを変更する](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
> 
> [Active Directory のユーザー設定を更新する](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
> 
> [Microsoft サポートのトラブルシューティング ガイドを使う](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
> 
> [詳細情報を収集し、サポートを受ける](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Skype for Business Online のサインイン エラーの一般的な原因をチェックする
<a name="toc323194094"> </a>

サインインに関する問題のほとんどは、少数の原因にたどり着き、それらの多くは簡単に修正できます。 以下の表に、一般的な原因のサインイン エラー、またそれらの解決に管理者やユーザーが使用できる手順をいくつか示します。


| **考えられる原因**                                                                                                                                                    | **解決策**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| サインイン時に、次のメッセージを含むダイアログ ボックスが表示される: "** はサインイン アドレスに対してサーバーが信頼されているかどうかを検証できません。接続しますか?**" <br/> | ダイアログ ボックスに示されたドメイン名が、 **domainName.contoso.com** などのように自分の組織の信頼できるサーバーであることを確認します。 [**このサーバーを常に信頼する**] チェック ボックスをオンにしてから [**接続**] をクリックするようにユーザーに依頼します。 <br/> エンタープライズのお客様は、ユーザーの各コンピューターで Windows のレジストリを変更すると、ユーザーが最初にサインインするときにこのメッセージが表示されないようにできます。 詳細については、「[TrustModelData レジストリ キーを変更する](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) 」を参照してください。<br/> |
| サインイン アドレス、ユーザー名、またはパスワードの誤入力  <br/>                                                                                                               | ユーザーのサインイン名とパスワードが正しいことを確認します。 <br/>  ユーザーのサインイン名が次のような形式になっていることを確認します: <strong>bobk@contoso.com</strong>。 これは、組織のネットワークにサインインする際に使用する形式とは異なる場合があります。  <br/>  もう一度サインインするようユーザーに依頼します。 <br/>                                                                                                                                                                                                                             |
| パスワードを忘れた場合  <br/>                                                                                                                                             | ユーザーのパスワードをリセットし、新しい一時的なパスワードをユーザーに通知します。  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Skype for Business Online を使用するためのライセンスが割り当てられていない  <br/>                                                                                                                  | ユーザーが Skype for Business Online ユーザーとして登録されていることを確認します。 登録されていない場合は、ユーザーを登録し、もう一度サインインするようユーザーに依頼します。  <br/>                                                                                                                                                                                                                                                                                                                                                                                           |
| インストールされている Skype for Business Online のバージョンが正しくない  <br/>                                                                                                           | これは通常、次の語句を含むエラー メッセージに関連する問題です: "**認証サービスがこのバージョンのプログラムと互換性がない可能性があります**"。  <br/> Skype for Business Online をアンインストールし、Office 365 ポータルから再インストールするようユーザーに求めます。  <br/>                                                                                                                                                                                                                                                    |
| サインインに必要な個人証明書を取得できない  <br/>                                                                                           | ユーザーのサインイン アドレスが最近変更された場合は、ユーザーはキャッシュ内のサインイン データを削除する必要がある場合があります。 ユーザーに、サインアウトし、サインイン画面上の [サインイン情報を削除] をクリックし、もう一度サインインするよう依頼します。  <br/>                                                                                                                                                                                                                                                                                                                                |
| カスタム ドメイン名を設定したものの、変更内容がシステムに反映し終わっていない可能性があります。  <br/>                                                         | まず、変更内容を反映させるため、ドメイン ネーム サービス (DNS: Domain Name Service) レコードを変更していることを確認します。  <br/> DNS に必要な変更を既に行った場合は、後でログインするようユーザーに通知します。 DNS の変更は、システム全体に反映するまで 72 時間かかる場合があります。  <br/>                                                                                                                                                                                                                                                        |
| システム クロックがサーバー クロックと同期していない  <br/>                                                                                                                     | ネットワーク ドメイン コントローラーが、信頼できる外部時間ソースと同期していることを確認します。 詳細については、Microsoft サポート技術情報の記事 816042「[ Windows Server で権限のあるタイム サーバーを構成する方法](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042) 」を参照してください。<br/>                                                                                                                                                                                                                                          |

Skype for Business Online のサインイン エラーのトラブルシューティングは、サインインの失敗を引き起こす最も一般的な原因を取り除くことから始めます。 必要に応じて、エラーのタイプに応じて特定の解決手順に従うことができます。 それでもサインインできない場合は、追加の情報を収集してサポートを受けるようにします。

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>特定のエラーの解決手順に従う (エンタープライズのみ)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  この手順は、主に Microsoft Office 365 Plan E のお客様が対象です。 Office 365 Plan P のお客様は、次のセクション「[詳細情報を収集し、サポートを受ける](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)」に進んでください。

前のセクションでの提案を試した後でもユーザーがサインインできない場合は、エラーのタイプに応じてその他のトラブルシューティングを行うことができます。 次の表は、最も一般的なエラー メッセージと考えられる原因を示します。 次の表は、問題にそれぞれ対応するための詳細手順です。

|**エラー メッセージ**|**考えられる原因**|**解決策**|
|:-----|:-----|:-----|
|サインイン アドレスが見つかりません  <br/> |Microsoft Online Services サインオン アシスタント (msoidsvc.exe) からのサインイン要求が、外部ファイアウォールまたはプロキシ サーバーを経由していません。  <br/> |[msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加する](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|サーバーが一時的に利用できません  <br/> |組織でカスタム ドメインを使用している場合、必要なドメイン ネーム システム (DNS: Domain Name System) が見つからない、または正しくない場合があります。  <br/> |[DNS 設定を更新する](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|サーバーが一時的に利用できません  <br/> |Active Directory フェデレーション サービス (ADFS) によるシングル サインオンを使用している組織では、サード パーティの証明機関からの証明書ではなく、自己署名された Secure Socket Layer (SSL) 証明書を使用していた可能性があります。  <br/> |[サード パーティの SSL 証明書を ADFS サーバー上にインストールする](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|サインインに必要な個人証明書を取得できない  <br/> |サインインに使用するキャッシュされたサーバー データを削除しても引き続きエラーが発生する場合は、ユーザーのセキュリティ資格情報が破損している、またはユーザーのコンピューターの RSA フォルダーの認証がブロックされている可能性があります。  <br/> |[セキュリティの資格情報を更新する](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|ユーザーが初めてサインインするときに、証明書を承認するためのダイアログ ボックスが表示されます。  <br/> |このダイアログ ボックスは、Skype for Business サーバーが **TrustModelData** レジストリ キーの一覧に含まれていない場合に表示されます。 <br/> |[TrustModelData レジストリ キーを変更する](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|このユーザーに対して SIP が有効になっていません  <br/> |以前に組織で Microsoft Office Communications Server または Microsoft Lync Server 2010 をインストールしていた場合、その使用をやめる前にサーバーからユーザーを削除していなかった可能性があります。 その結果、Active Directory ドメイン サービスで **msRTCSIP-UserEnabled** 属性が依然として **FALSE** に設定されています。 <br/> |[Active Directory のユーザー設定を更新する](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します
<a name="add-a-firewall"> </a>

これは、次のエラー メッセージに対して有効な場合がある解決方法の手順です: "**サインイン アドレスが見つかりませんでした**"。

> [!NOTE]
> 以下の手順では、Microsoft Forefront Threat Management Gateway (TMG) 2010 を使用していることを前提としています。 異なる Web ゲートウェイのソリューションがある場合は、下記の手順 4 で説明する設定を使用してください。


Forefront TMG 2010 で Msoidsvc.exe のアプリケーション エントリを作成するには、次の手順を実行します。

1. Forefront の左側のウィンドウで、[**ネットワーキング**] をクリックします。

2. [**ネットワーク**] タブをクリックします。右側のウィンドウの [**タスク**] タブで、[**Forefront TMG クライアント設定の構成**] をクリックします。

3. [**Forefront TMG クライアント設定**] ダイアログ ボックスで [**新規作成**] をクリックします。

4. [**アプリケーション エントリの設定**] ダイアログ ボックスで、次の規則を構成します。

|**Application**|**Key**|**値**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |無効  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

詳細については、Microsoft サポート技術情報の記事 2409256「[オンプレミスのファイアウォールが接続をブロックするため、Skype for Business Online に接続できない、またはた特定の機能が動作しない](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)」を参照してください。

### <a name="update-dns-settings"></a>DNS 設定を更新する
<a name="update-dns-service"> </a>

これは、カスタム ドメインが組織で規定されている場合に、次のエラー メッセージに対して有効な場合がある解決方法の手順です: "**サーバーが一時的に利用できません**"。

- 次の CNAME レコードをドメインに追加する方法については、ドメイン名レジストラーにお問い合わせください。

  - **DNS レコード タイプ**: CNAME

  - **名前**: sip

  - **値/参照先**: sipdir.online.lync.com

詳細については、Microsoft サポート技術情報の記事 2566790「[Office 365 Skype for Business Online DNS 構成に関する問題のトラブルシューティング](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)」を参照してください。

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>サード パーティの SSL 証明書を ADFS サーバー上にインストールする
<a name="verify-upn-and"> </a>

Active Domain Federation Services (ADFS) サーバーにサード パーティの SSL 証明書をインストールするには、次の手順を実行します。

1. サードパーティの証明機関 (VeriSign や Thawte など) から SSL 証明書を取得します。

2. ADFS 管理コンソールを使用して、ADFS サーバーに証明書をインストールします。

### <a name="update-security-credentials"></a>セキュリティの資格情報を更新する
<a name="update-security-credentials"> </a>

これは、次のエラー メッセージに対して有効な場合がある解決方法の手順です: "**サインインに必要な個人証明書を取得する際に問題があります**"。

考えられる証明書または資格情報に関する問題を解決、まず Windows 証明書マネージャーでユーザーの証明書を更新します。 これを行うには、次の手順を実行します。

1. Windows 証明書マネージャーを開きます。 これを行うには、[**スタート**] をクリックし、[**ファイル名を指定して実行**] をクリックして **ertmgr.msc** と入力し、[**OK**] をクリックします。

2. [**個人用**] をダブルクリックし、[**証明書**] をダブルクリックします。

3. [**発行先**] 列を基準にして並べ替えて、Communications Server が発行した証明書を見つけます。

4. 証明書を右クリックし、[**削除**] をクリックします。

次に、ユーザーが Windows 7 を実行している場合は、Windows 資格情報マネージャーで、格納されているユーザーの資格情報を削除します。 これを行うには、次の手順を実行します。

1. [**スタート**] をクリックし、[**コントロール パネル**] をクリックします。次に、[**資格情報マネージャー**] をクリックします。

2. Skype for Business Online への接続に使用する資格情報のセットを見つけます。

3. 資格情報のセットを展開し、[**資格情報コンテナーから削除**] をクリックします。

4. もう一度サインインし、ユーザーの資格情報を再入力します。

最後に、ユーザー資格情報を更新した後でもユーザーがまだサインインできない場合は、ユーザーのコンピューターの RSA フォルダーを削除してください。ユーザーの認証プロセスの完了がブロックされている可能性があるためです。

1. 管理者アカウントを使用して、ユーザーのコンピューターにサインインします。

2. 必要に応じて、フォルダーの表示オプション [**非表示のファイルを表示する**] を有効にします。

3. エクスプローラーのアドレス バーに次のように入力します。 **C:\\Documents and Settings\\<ユーザー名>\\Application Data\\Microsoft\\Crypto\\RSA**。***<ユーザー名>*** は Windows のサインイン名です。

4. **S-1-5-21- **という名前で始まり、後ろに数字のストリングが続くフォルダーを削除します。

### <a name="modify-trustmodeldata-registry-keys"></a>TrustModelData レジストリ キーを変更する
<a name="modify-trustmodeldata-registry"> </a>

ユーザーが最初にサインインしたとき、次のようなメッセージを含むダイアログ ボックスが表示される場合があります: "** はサインイン アドレスに対してサーバーが信頼されているかどうかを検証できません。接続しますか?**" これはセキュリティ機能であり、エラーではありません。 ただし、ユーザーが初めてサインインする前にグループ ポリシー オブジェクト (GPO) を使用してユーザーのコンピューターのドメイン名を更新すると、このダイアログ ボックスが表示されないようにすることができます。 これを実行するには、次の操作を行います。

- Skype for Business のドメイン名 (例: domainName.contoso.com) を HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData の現在の値に付加する GPO を作成し、展開します。

> [!IMPORTANT]
>  既存の値を単に置き換えるのではなく、既存の値にドメイン名を*追加*する必要があります。

詳細については、Microsoft サポート技術情報の記事 2531068「[Skype for Business (Lync) Lync はサインイン アドレスに対してサーバーが信頼されているかどうかを検証できません](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)」を参照してください。

### <a name="update-user-settings-in-active-directory"></a>Active Directory のユーザー設定を更新する
<a name="update-user-settings"> </a>

以前に組織で Microsoft Office Communications Server または Microsoft Lync Server 2010 をインストールしていた場合、その使用をやめる前にサーバーからユーザーを削除していなかった可能性があります。 その結果、Active Directory ドメイン サービスで **msRTCSIP-UserEnabled** 属性が依然として **FALSE** に設定されています。

この問題を解決するには、次の手順を実行します。

1. 関係するすべてのユーザーの **msRTCSIP-UserEnabled** 属性を **TRUE** に更新します。

2. Microsoft Online Services ディレクトリ同期ツール (DirSync) を再実行します。 詳細については、「[オンプレミスのディレクトリと Azure Active Directory の統合](https://technet.microsoft.com/ja-JP/library/hh967642.aspx)」を参照してください。

Skype for Business Online のサインイン エラーのトラブルシューティングは、サインインの失敗を引き起こす最も一般的な原因を取り除くことから始めます。 必要に応じて、エラーのタイプに応じて特定の解決手順に従うことができます。 それでもサインインできない場合は、追加の情報を収集してサポートを受けるようにします。
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Microsoft サポートのトラブルシューティング ガイドを使う
<a name="toc325626447"> </a>

これでもユーザーのサインインの問題が解決されない場合は、Microsoft サポート技術情報の記事 2541980「[Skype for Business Online へのサインインに関する問題のトラブルシューティング方法](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)」の説明をご覧ください。

## <a name="collect-more-information-and-seek-additional-help"></a>詳細情報を収集し、サポートを受ける
<a name="collect-more-information"> </a>

上記のガイダンスを実行してもサインインの問題を解決できない場合、追加の情報を収集し、テクニカル サポートに問い合わせる必要があります。 これを行うには、次の手順を実行します。

1. ユーザーのコンピューターからログ ファイルおよび Windows のイベント ログを取得します。 手順ごとの操作については、エンド ユーザー向けヘルプ トピックの「[Lync のログインの詳細](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)」を参照してください。

2. ログ ファイル、およびエラーに関する詳細情報を Microsoft テクニカル サポートにお送りください。

問題のコンピューターに Microsoft Online Services Diagnostic and Logging (MOSDAL) サポート ツールキットをインストールして追加の診断情報を提供するように求められることがあります。 詳細については、「[MOSDAL サポート ツールキットを使用する](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)」を参照してください。

Skype for Business Online のサインイン エラーのトラブルシューティングは、サインインの失敗を引き起こす最も一般的な原因を取り除くことから始めます。 必要に応じて、エラーのタイプに応じて特定の解決手順に従うことができます。 それでもサインインできない場合は、追加の情報を収集してサポートを受けるようにします。

## <a name="related-topics"></a>関連トピック
[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)


