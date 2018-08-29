---
title: 管理者の Skype をビジネス オンラインのサインインのエラーのトラブルシューティング
ms.author: tonysmit
author: tonysmit
manager: serdars
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
description: 'これらの問題のトラブルシューティングを行って Skype のオンライン ビジネスの記号のエラーや作業の一般的な原因を説明します。 '
ms.openlocfilehash: 88ff25ab4603810d41e92e25a62bfecb3c376246
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255789"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>管理者の Skype をビジネス オンラインのサインインのエラーのトラブルシューティング

Skype ビジネス オンラインのサインインのエラーのトラブルシューティングについてには、サインインの問題の最も一般的な原因を排除することによって開始します。 必要に応じて、手順はエラーの種類に基づいて特定の解像度に従って、できます。 ユーザーがサインインできない場合、追加情報の収集し、し、追加の支援を仰ぐことです。

## <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください。
<a name="top"> </a>

> [Skype のビジネス オンラインのサインインのエラーの一般的な原因を探します。](troubleshooting-sign-in-errors-for-admins.md#toc323194094)

> [(企業の場合のみ) の特定のエラーの解決方法の手順に従います](troubleshooting-sign-in-errors-for-admins.md#toc325626440)

> [Msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します。](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)

> [DNS の設定を更新します。](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)

> [ADFS サーバー上のサード パーティの SSL 証明書をインストールします。](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)

> [セキュリティ資格情報を更新します。](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)

> [TrustModelData レジストリ キーを変更します。](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)

> [Active Directory のユーザー設定を更新する](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)

> [トラブルシューティング ・ ガイド Microsoft のサポートを使用します。](troubleshooting-sign-in-errors-for-admins.md#toc325626447)

> [詳細情報を収集し、追加の支援を仰ぐこと](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Skype のビジネス オンラインのサインインのエラーの一般的な原因を探します。
<a name="toc323194094"> </a>

ほとんどのサインインの問題が原因の原因の数が少ないと、これらの多くは簡単に修正します。 次の表は、サインインのエラーの一般的な原因と、それを解決するか、ユーザーがかかることがいくつかの手順を示します。

|**考えられる原因**|**解像度**|
|:-----|:-----|
|、サインイン中にダイアログ ボックスが表示されます次の語句が含まれています:**のサーバーは、サインイン用アドレスに対して信頼されていることを確認できません。接続しますか?** <br/> |ダイアログ ボックスでドメイン名が、組織内の信頼されたサーバーであることを確認、 **domainName.contoso.com**などです。 [**常にこのサーバーを信頼する**] チェック ボックスを選択するユーザーに確認し、し、[**接続**] をクリックします。 <br/> 企業のお客様は、ユーザーが各ユーザーのコンピューターで Windows レジストリを変更することによってを初めてにサインインするときに表示されないようにする、このメッセージを防ぐことができます。 詳細については、[レジストリ キーの変更の TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)を参照してください。<br/> |
|サインイン用アドレスの入力ミス、ユーザー名、またはパスワード  <br/> | ユーザーのサインイン名とパスワードが正しいことを確認します。 <br/>  ユーザーのサインイン名が次のようにフォーマットされていることを確認: **bobk@contoso.com**。 これは、組織のネットワークへのサインインに使用する形式とは異なる可能性があります。  <br/>  もう一度サインインするユーザーを確認します。 <br/> |
|パスワードを忘れた場合  <br/> |ユーザーのパスワードをリセットし、彼または彼女の新しい一時的なパスワードを通知します。  <br/> |
|ビジネス オンラインの Skype を使用するライセンスがありません。  <br/> |ユーザーが、Skype のオンライン ビジネスのユーザーとして登録されていることを確認します。 そうでない場合は、ユーザーを登録し、かをもう一度サインインします。  <br/> |
|インストールされているビジネス オンラインの Skype のバージョンが正しく  <br/> |この問題は通常、次の語句が含まれるエラー メッセージに関連付けられている:**認証サービスは、このバージョンのプログラムと互換性がない可能性があります**。  <br/> アンインストールし、Skype を再インストール、Office 365 ポータルからオンライン ビジネスのユーザーに問い合わせてください。  <br/> |
|サインインに必要な個人証明書を取得する問題  <br/> |ユーザーのサインイン用アドレスが最近変更された場合は、キャッシュされている記号でデータを削除する必要があります。 サインアウトして、[サインイン情報、サインイン画面で、リンクして、再度実行の削除] をクリックしてもらいます。  <br/> |
|カスタム ドメイン名を設定して、変更可能性がありますが終了しない、システム全体に適用します。  <br/> |最初に、変更を反映するようにドメイン ネーム サービス (DNS) レコードを変更していることを確認します。  <br/> 必要な DNS の変更を既に行っている場合は、後でログインするユーザーを案内します。 DNS の変更は、システム全体に反映するのには最大 72 時間かかります。  <br/> |
|サーバーのクロックとのシステム時計の同期  <br/> |ネットワーク ドメイン コント ローラーが信頼できる外部タイム ソースと同期することを確認します。 詳細については、マイクロソフト サポート技術情報の記事 816042、 [Windows サーバーで権限のあるタイム サーバーを構成する方法](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)を参照してください。<br/> |

Skype ビジネス オンラインのサインインのエラーのトラブルシューティングについてには、サインインの問題の最も一般的な原因を排除することによって開始します。 必要に応じて、手順はエラーの種類に基づいて特定の解像度に従って、できます。 ユーザーがサインインできない場合、追加情報の収集し、し、追加の支援を仰ぐことです。

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>(企業の場合のみ) の特定のエラーの解決方法の手順に従います
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  次の手順は、主に Microsoft Office 365 プラン E のお客様です。 Office 365 プラン P 製品を使用している場合、次のセクションで、[詳細情報を収集し追加の支援を仰ぐこと](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)に進みます。

ユーザーは、前のセクションの推奨事項を実施した後にサインインできない場合、は、エラーの種類に基づいて、追加のトラブルシューティングを実行できます。 次の表は、最も一般的なエラー メッセージと考えられる原因を示します。 各問題に対処する手順の詳細については、次の表。

|**エラー メッセージ**|**考えられる原因**|**解像度**|
|:-----|:-----|:-----|
|サインイン アドレスが見つかりませんでした。  <br/> |外部ファイアウォール、またはプロキシ サーバーを介して、Microsoft オンライン サービス サインイン アシスタント (msoidsvc.exe) からのサインイン要求は使用しません。  <br/> |[Msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します。](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|サーバーが一時的に利用できません。  <br/> |組織のカスタム ドメインの場合、必要なドメイン ネーム システム (DNS) 設定に存在しないか正しくない可能性があります。  <br/> |[DNS の設定を更新します。](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|サーバーが一時的に利用できません。  <br/> |組織は、Active Directory フェデレーション サービス (ADFS) とシングル サインオンが使用されている場合がありますを使用したサード パーティの証明機関からではなく、自己署名入りのセキュア ソケット レイヤー (SSL) 証明書。  <br/> |[ADFS サーバー上のサード パーティの SSL 証明書をインストールします。](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|サインインに必要な個人証明書を取得する問題  <br/> |既に削除した場合サーバーのキャッシュされたデータを使用してサインインしエラーが引き続き表示される、ユーザーのセキュリティ資格情報が壊れている、または認証ユーザーのコンピューター上の RSA フォルダーをブロックしている可能性があります。  <br/> |[セキュリティ資格情報を更新します。](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|ユーザーが初めてサインインするときに、証明書の信頼] ダイアログ ボックスが表示されます。  <br/> |ビジネス サーバーは、Skype が**TrustModelData**レジストリ キーにまだ追加されていない場合、このダイアログ ボックスが表示されます。 <br/> |[TrustModelData レジストリ キーを変更します。](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|ユーザーは、SIP が有効ではありません。  <br/> |組織に Microsoft Office Communications Server、または Microsoft Lync Server 2010 の以前のインストールがある場合いない削除したユーザー、サーバーからそれを解除する前にします。 その結果、 **msRTCSIP UserEnabled**の属性は、 **FALSE**では、Active Directory ドメイン サービスに設定されています。 <br/> |[Active Directory のユーザー設定を更新する](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Msoidsvc.exe のファイアウォールのエントリをプロキシ サーバーに追加します。
<a name="add-a-firewall"> </a>

この手順は、次のエラー メッセージの可能性のある修正プログラム:**サインイン アドレスが見つかりません**。

> [!NOTE]
> 次の手順では、Microsoft Forefront 脅威管理ゲートウェイ (TMG) 2010 を使用するいると仮定します。 別の web ゲートウェイ ・ ソリューションでは、場合によっては、以下の手順 4 で説明する設定を使用します。


Forefront TMG 2010 年に Msoidsvc.exe のアプリケーションのエントリを作成するには、次の手順を実行します。

1. Forefront 左側のウィンドウで、[**ネットワーク**] をクリックします。

2. **[ネットワーク**] タブをクリックします。右側のウィンドウで [**タスク**] タブの下には、 **Forefront TMG クライアント設定の構成**をクリックします。

3. **Forefront TMG クライアントの設定**] ダイアログ ボックスで [**新規**] をクリックします。

4. **アプリケーション エントリの設定**] ダイアログ ボックスで、次の規則を構成します。

|**アプリケーション**|**キー**|**値**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |無効にします。  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

詳細については、マイクロソフト サポート技術情報 2409256 を[オンプレミスのファイアウォールが接続をブロックするためのオンライン ビジネスの Skype に接続できない](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)を参照してください。

### <a name="update-dns-settings"></a>DNS の設定を更新します。
<a name="update-dns-service"> </a>

この手順は次のエラー メッセージの可能性のある修正プログラム、組織のカスタム ドメインの場合:**サーバーが一時的に利用できません**。

- 以下の CNAME レコードをドメインに追加する方法については、ドメイン名登録機関にお問い合わせください。

  - **DNS レコードの種類**: CNAME

  - **名前**: sip

  - **値と変換先**: sipdir.online.microsoft.com

詳細については、マイクロソフト サポート技術情報 2566790、 [Office 365 のビジネス オンラインの DNS 構成の問題の Skype のトラブルシューティング](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)を参照してください。

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>ADFS サーバー上のサード パーティの SSL 証明書をインストールします。
<a name="verify-upn-and"> </a>

アクティブなドメイン フェデレーション サービス (ADFS) サーバーに、サード パーティの SSL 証明書をインストールするには、次の手順を実行します。

1. VeriSign や Thawte などのサード パーティの証明機関から SSL 証明書を取得します。

2. ADFS の管理コンソールを使用して ADFS サーバーに証明書をインストールします。

### <a name="update-security-credentials"></a>セキュリティ資格情報を更新します。
<a name="update-security-credentials"> </a>

この手順は、**個人用証明書の取得の問題サインインする必要ある**がエラー メッセージを修正します。

可能な証明書または資格情報の問題を排除するには、最初にユーザーの証明書では、Windows 証明書マネージャーを更新します。 これを行うには、次の手順を実行します。

1. Windows 証明書マネージャーを開きます。 これを行うには、[**スタート**] ボタン**を実行**] をクリックして、 **certmgr.msc**と入力し、[ **OK**] をクリックします。

2. **個人**、し、[**証明書**] をダブルクリックします。

3. 通信サーバーによって発行された証明書を参照し**発行で**列を並べ替えます。

4. 証明書を右クリックし、し、[**削除**] をクリックします。

次に、ユーザーが Windows 7 を実行中の場合、その保存された資格情報を Windows 資格情報マネージャーで削除します。 これを行うには、次の手順を実行します。

1. [**スタート**] ボタン、**コントロール パネル**] をクリックし、[**資格情報マネージャー**] をクリックします。

2. ビジネス オンラインの Skype に接続するために使用される資格情報のセットを検索します。

3. 資格情報のセットを展開し、**ヴォールトから削除**] をクリックします。

4. もう一度サインインし、ユーザーの資格情報を再入力します。

最後に、ユーザーがサインインできない場合、資格情報を更新した後、フォルダーを削除して RSA ユーザーのコンピューターでは、ユーザー認証プロセスの完了をブロックする可能性がありますので。

1. 管理者アカウントを使用してユーザーのコンピューターにサインインします。

2. 必要に応じて、**非表示のファイルを表示する**フォルダーの [表示] オプションを入れます。

3. 次に、アドレス バーのファイル エクスプ ローラーを入力: **c:\\ドキュメントと設定\\ユーザー名\\アプリケーション データ\\Microsoft\\暗号\\RSA**、***ユーザー名***は Windows のサインイン名です。

4. 名前で始まる任意のフォルダーを削除**S-1-5-21 -** 番号の文字列の後にします。

### <a name="modify-trustmodeldata-registry-keys"></a>TrustModelData レジストリ キーを変更します。
<a name="modify-trustmodeldata-registry"> </a>

ユーザーが初めてサインインするとき、次のようなものが含まれているダイアログ ボックスが表示、ことがあります:**のサーバーは、サインイン用アドレスに対して信頼されていることを確認できません。接続しますか?** これは、セキュリティ機能、およびエラーではありません。 ただし、最初にサインインする前に、ドメイン名を持つユーザーのコンピューターを更新するグループ ポリシー オブジェクト (GPO) を使用して表示されないようにする] ダイアログ ボックスを防ぐことができます。 これを行うには、次の操作を行います。

- 作成し、Skype をビジネス ドメイン名に追加される GPO の展開: HKEY_LOCAL_MACHINE の現在の値をたとえば、domainName.contoso.com—to\\ソフトウェア\\ポリシー\\Microsoft\\Communicator\\TrustModelData。

> [!IMPORTANT]
>  必要な*追加*のドメイン名は、既存の値を単に置き換えることです。

詳細については、マイクロソフト サポート技術情報記事 2531068、 [Skype ビジネス (Lync) のサーバーは、サインイン用アドレスに対して信頼されていることを確認できない](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)を参照してください。

### <a name="update-user-settings-in-active-directory"></a>Active Directory のユーザー設定を更新する
<a name="update-user-settings"> </a>

組織に Microsoft Office Communications Server、または Microsoft Lync Server 2010 の以前のインストールがある場合いない削除したユーザー、サーバーからそれを解除する前にします。 その結果、 **msRTCSIP UserEnabled**の属性は、 **FALSE**では、Active Directory ドメイン サービスに設定されています。

この問題を解決するには、以下の手順を実行します。

1. **TRUE**にすべての影響を受けるユーザーの**msRTCSIP UserEnabled**属性を更新します。

2. Microsoft Online Services ディレクトリ同期ツール (ディレクトリ同期) を再実行します。 詳細については、 [Azure Active Directory との AIntegrate、設置ディレクトリ](https://technet.microsoft.com/en-us/library/hh967642.aspx)を参照してください。

Skype ビジネス オンラインのサインインのエラーのトラブルシューティングについてには、サインインの問題の最も一般的な原因を排除することによって開始します。 必要に応じて、手順はエラーの種類に基づいて特定の解像度に従って、できます。 ユーザーがサインインできない場合、追加情報の収集し、し、追加の支援を仰ぐことです。
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>トラブルシューティング ・ ガイド Microsoft のサポートを使用します。
<a name="toc325626447"> </a>

ユーザーのサインインの問題を解決できていない場合は、マイクロソフト サポート技術情報記事 2541980、 [Skype のビジネスをオンラインでサインインの問題をトラブルシューティングする方法](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)の推奨事項を確認します。

## <a name="collect-more-information-and-seek-additional-help"></a>詳細情報を収集し、追加の支援を仰ぐこと
<a name="collect-more-information"> </a>

上記のガイダンスに従って、まだサインインの問題を解決することはできません追加情報を収集し、テクニカル サポートに問い合わせてください。 これを行うには、次の手順を実行します。

1. ユーザーのコンピューターからログ ファイルと Windows イベント ログの詳細を取得します。 手順については、 [Lync のエラー ログを有効にする](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)エンド ・ ユーザーのヘルプ トピックを参照してください。

2. ログ ファイルおよびエラーに関する詳細な情報をマイクロソフトのテクニカル サポートに送信します。

影響を受けるユーザーのコンピューターでの診断の Microsoft Online Services とログ (MOSDAL) サポート Toolkit をインストールすることによって追加の診断情報を提供を求められる場合があります。 詳細については、 [MOSDAL サポートの Toolkit を使用して](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)参照してください。

Skype ビジネス オンラインのサインインのエラーのトラブルシューティングについてには、サインインの問題の最も一般的な原因を排除することによって開始します。 必要に応じて、手順はエラーの種類に基づいて特定の解像度に従って、できます。 ユーザーがサインインできない場合、追加情報の収集し、し、追加の支援を仰ぐことです。

## <a name="related-topics"></a>関連トピック
[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)

[Skype for Business ユーザーが Skype 連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)


