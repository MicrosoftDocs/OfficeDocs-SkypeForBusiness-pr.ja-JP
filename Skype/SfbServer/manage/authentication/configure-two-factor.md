---
title: Skype のビジネス サーバーの 2 要素認証を構成します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: '概要: は、Skype のビジネス サーバーの 2 要素認証を構成します。'
ms.openlocfilehash: d9df5072e1d67e46c40e1fd82ec1d88354321577
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32210998"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Skype のビジネス サーバーの 2 要素認証を構成します。

**の概要:** Skype のビジネス サーバーの 2 要素認証を構成します。

以下のセクションでは、展開に 2 要素認証を構成するために必要な手順について説明します。 二要素認証の詳細については、[オンライン管理者のユーザーの投稿をグリッドの多要素認証を有効にすると Office 365](https://go.microsoft.com/fwlink/p/?LinkId=313332)を参照してください。

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>スマート カード認証をサポートするエンタープライズ ルート証明機関を構成する

スマート カード認証をサポートするようにエンタープライズ ルート CA を構成する方法を以下の手順で説明します。

エンタープライズのルート CA をインストールする方法については、[エンタープライズ ルート証明機関をインストール](https://go.microsoft.com/fwlink/p/?LinkID=313364)を参照してください。

1. ドメイン管理者のアカウントを使用してエンタープライズ CA コンピューターにログインします。

2. システム マネージャーを起動し、証明機関 Web 登録の役割がインストールされていることを確認します。

3. [**管理ツール**] メニューから**証明機関**管理コンソールを開きます。

4. ナビゲーション ウィンドウで、[**証明機関**] を展開します。

5. [**証明書テンプレート**] を右クリックし、[**新規作成**] をクリックして、[**発行する証明書テンプレート**] を選択します。

6. [**登録エージェント**]、[**スマート カード ユーザー**]、[**スマート カード ログオン**] の順にクリックします。

7. [**OK**] をクリックします。

8. [**証明書テンプレート**] を右クリックします。

9. [**管理**] を選択します。

10. スマート カード ユーザー テンプレートのプロパティを開きます。

11. [**セキュリティ**] タブをクリックします。

12. アクセス許可を次のように変更します。

    - 読み取り/登録 (許可) アクセス許可を指定して個別のユーザー AD アカウントを追加します。または

    - 読み取り/登録 (許可) のアクセス許可を指定してスマート カード ユーザーを含むセキュリティ グループを追加します。または

    - 読み取り/登録 (許可) のアクセス許可を指定してドメイン ユーザー グループを追加します。

## <a name="configure-windows-8-for-virtual-smart-cards"></a>仮想スマート カード用に Windows 8 を構成する

2 要素認証とスマート カード テクノロジを展開する場合に考慮する必要がある要素の 1 つは、実装コストです。 Windows 8 にいくつかの新しいセキュリティ機能が用意されていて、仮想スマート カードのサポートは、最も興味深い新機能の 1 つ。

バージョン 1.2 仕様を満たす Trusted Platform Module (TPM) チップを搭載したコンピューターでは、ハードウェアの追加費用をかけずにスマート カード ログオンを活用できるようになりました。 詳細については、 [Windows 8 での仮想スマート カードの使用](https://go.microsoft.com/fwlink/p/?LinkId=313365)を参照してください。

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Windows 8 を仮想スマート カード用に構成するには

1. ビジネスが有効なユーザーは、Skype の資格情報を使用して Windows 8 のコンピューターにログインします。

2. Windows 8 のスタート画面で、画面の右下隅にカーソルを移動します。

3. [**検索**] オプションを選択し、ラー プロンプトを検索します。

4. [**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。

5. 次のコマンドを実行して、Trusted Platform Module (TPM) 管理コンソールを開きます。

  ```
  Tpm.msc
  ```

6. TPM 管理コンソールで、TPM 仕様バージョンが 1.2 以上であることを確認します。

    > [!NOTE]
    > 相互運用性のある Trust Platform Module (TPM) が見つからないことを示すダイアログが表示された場合は、相互運用性のある TPM モジュールがコンピューターにインストールされていること、およびシステム BIOS で有効になっていることを確認します。

7. TPM 管理コンソールを閉じる

8. コマンド プロンプトで、次のコマンドを使用して新しい仮想スマート カードを作成します。

  ```
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > 仮想スマート カードを作成するときにカスタム PIN 値を指定するには、代わりに /pin プロンプトを使用します。

9. コマンド プロンプトから、次のコマンドを実行してコンピューター管理コンソールを開きます。

  ```
  CompMgmt.msc
  ```

10. コンピューター管理コンソールで、[**デバイス管理**] をクリックします。

11. [**スマート カード リーダー**] を展開します。

12. 新しい仮想スマート カード リーダーが正しく作成されていることを確認します。

## <a name="enroll-users-for-smart-card-authentication"></a>スマート カード認証にユーザーを登録する

スマート カードの認証を行うユーザーを登録する方法は、主に 2 つあります。Web 登録を使ってスマート カード認証のユーザーを直接登録する方法がより簡単で、登録エージェントを使う方法はより複雑です。このトピックでは、スマート カードの証明書を自分で登録する方法について説明します。

ユーザーに代わって登録エージェントとしての登録の詳細については、[他のユーザーに代わって証明書の登録](https://go.microsoft.com/fwlink/p/?LinkID=313367)を参照してください。

### <a name="to-enroll-users-for-smart-card-authentication"></a>スマート カードの認証を行うユーザーを登録するには、次の操作を行います。

1. ビジネスが有効なユーザーは、Skype の資格情報を使用して Windows 8 のワークステーションにログインします。

2. Internet Explorer を起動します。

3. **証明書機関の Web 登録**ページを参照 (例: https://MyCA.contoso.com/certsrv)。

    > [!NOTE]
    > Internet Explorer 10 を使っている場合は、この Web サイトを互換モードで見る必要がある場合があります。

4. Web サイトの [**ようこそ**] ページで、[**証明書の要求**] を選びます。

5. 次に、[**証明書の要求の詳細設定**] を選びます。

6. [**この CA への要求を作成し送信する。**] を選びます。

7. [**証明書のテンプレート**] セクションで [**スマート カード ユーザー**] を選び、[証明書の要求の詳細設定] を次のように入力します。

  - [**キーのオプション**] で次の設定を確認します。

    - [**新しいキー セットを作成する**] ラジオ ボタンを選ぶ

    - [**CSP**] で、[**Microsoft ベース スマート カード暗号化プロバイダー**] を選ぶ

    - [**キー使用法**] で、[**Exchange**] を選ぶ (このオプションのみ有効)

    - [**キーのサイズ**] に、2048 と入力する

    - [**自動キー コンテナー名**] が選択されている

    - その他のボックスはオフにします。

  - [**追加オプション**] で次の値を確認します。

    - [**要求の形式**] で [**CMC**] を選ぶ。

    - [**ハッシュ アルゴリズム**] で [**sha1**] を選ぶ。

    - **フレンドリ名**の enterSmardcard 証明書。

8. 物理カード リーダーを使っている場合は、デバイスにスマート カードを挿入します。

9. [**送信**] をクリックして証明書要求を送信します。

10. 入力を求められたら、仮想スマート カードを作成したときに使った PIN を入力します。

    > [!NOTE]
    > 既定の仮想スマート カード暗証番号 (pin) の値は、'12345678' です。

11. 証明書が発行されたら、[**この証明書のインストール**] をクリックして登録プロセスを完了します。

    > [!NOTE]
    >  証明書の要求は、「この Web ブラウザーは証明書の要求の生成をサポートしていません」のエラーで失敗すると場合、は、問題を解決するのには 3 つの方法があります。

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Active Directory フェデレーション サービス (AD FS 2.0) を構成する

次のセクションでは、多要素認証をサポートするように Active Directory フェデレーション サービス (AD FS 2.0) を構成する方法について説明します。 AD FS 2.0 をインストールする方法についてを参照してください[AD FS 2.0 ステップ バイ ステップとガイドにどのように](https://go.microsoft.com/fwlink/p/?LinkId=313374)。

> [!NOTE]
> AD FS 2.0 をインストールするときは、Windows Server Manager を使用して Active Directory フェデレーション サービスの役割を追加しないでください。 代わりに、ダウンロードして、 [Active Directory フェデレーション サービス 2.0 の RTW のパッケージ](https://go.microsoft.com/fwlink/p/?LinkId=313375)をインストールします。

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>2 要素認証の AD FS を構成するには

1. ドメイン管理者のアカウントを使用して AD FS 2.0 コンピューターにログインします。

2. Windows PowerShell を起動します。

3. Windows PowerShell コマンド ラインで次のコマンドを実行します。

  ```
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. 展開に固有のサーバー名を置き換えて以下のコマンドを実行することで、パッシブ認証に対して有効にされる各サーバーとのパートナーシップを確立します。

  ```
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. [管理ツール] メニューから AD FS 2.0 管理コンソールを起動します。

6. **信頼関係**を展開する > **利用者を信頼**します。

7. ビジネス サーバーは、Skype の新しい信頼関係が作成されたことを確認します。

8. Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行承認規則を作成して割り当てます。

  ```
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行変換規則を作成して割り当てます。

  ```
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. AD FS 2.0 管理コンソールで、証明書利用者の信頼を右クリックし、[**要求規則の編集**] をクリックします。

11. [**発行承認規則**] タブをクリックし、新しい承認規則が正しく作成されたことを確認します。

12. [**発行変換規則**] タブをクリックし、新しい変換規則が正しく作成されたことを確認します。

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>クライアント認証をサポートする AD FS 2.0 の構成

AD FS 2.0 でスマート カードを使用した認証をサポートできるように構成可能な認証の種類が 2 つあります。

- フォーム ベース認証 (FBA)

- トランスポート層セキュリティ クライアント認証

フォーム ベース認証を使用すると、ユーザー名/パスワードを使用した認証またはスマート カードと PIN を使用した認証をユーザーに許可できる Web ページを開発できます。 このトピックでは、AD FS 2.0 でトランスポート層セキュリティ クライアント認証を実装する方法を説明します。 AD FS 2.0 の認証の種類の詳細についてを参照してください[AD FS 2.0: ローカルの認証の種類を変更する方法](https://go.microsoft.com/fwlink/p/?LinkId=313384)。

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>クライアント認証をサポートするように AD FS 2.0 を構成するには

1. ドメイン管理者のアカウントを使用して AD FS 2.0 コンピューターにログインします。

2. エクスプローラーを起動します。

3. C:\inetpub\adfs\ls に移動します。

4. 既存の web.config ファイルのバックアップ コピーを作成します。

5. メモ帳を使用して既存の web.config ファイルを開きます。

6. メニュー バーの [**編集**] をクリックし、[**検索**] をクリックします。

7. 検索\<localAuthenticationTypes\>。

    4 つの認証の種類が 1 行に 1 つずつ表示されます。

8. TLSClient 認証の種類を含む行をセクションの一覧の一番上に移動します。

9. web.config ファイルを保存して閉じます。

10. 管理者特権でコマンド プロンプトを起動します。

11. 次のコマンドを実行して IIS を再起動します。

  ```
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Skype for Business Server のパッシブ認証の構成

次のセクションでは、パッシブ認証をサポートするためにサーバーをビジネス用の Skype を構成する方法について説明します。 有効になったら、二要素認証は有効になっているユーザーはビジネス クライアント用の Skype を使用してサインインするのには、物理または仮想スマート カードと PIN を有効なを使用する必要になります。

> [!NOTE]
> レジストラーと Web サービスのパッシブ認証はサービス レベルで有効にすることを強くお勧めします。レジストラーと Web サービスのパッシブ認証をグローバル レベルで有効にすると、サポートされるデスクトップ クライアントでサインインしていないユーザーが組織全体で認証エラーになる可能性があります。

### <a name="web-service-configuration"></a>Web サービス構成設定

次の手順では、パッシブ認証を有効にするディレクター、エンタープライズ プール、Standard Edition サーバーにカスタムの Web サービス構成設定を作成する方法について説明します。

### <a name="to-create-a-custom-web-service-configuration"></a>カスタムの Web サービス構成設定を作成するには

1. ビジネス管理者のアカウントは、Skype を使用してビジネス サーバーのフロント エンド サーバーは、Skype にログインします。

2. ビジネス サーバー管理シェルには、Skype を起動します。

3. ビジネス サーバー管理シェル コマンド ラインの Skype、ディレクター、エンタープライズ プールと Standard Edition サーバーで次のコマンドを実行しているパッシブ認証を有効にするごとに、新しい Web サービス構成を作成します。

  ```
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > WsFedPassiveMetadataUri の FQDN の値は、AD FS 2.0 サーバーのフェデレーション サービス名です。フェデレーション サービス名の値は、AD FS 2.0 管理コンソールでナビゲーション ウィンドウの [**サービス**] を右クリックし、[**Edit Federation Service Properties**] を選択すると確認できます。

4. 次のコマンドを実行して、UseWsFedPassiveAuth と WsFedPassiveMetadataUri の値が正しく設定されたことを確認します。

  ```
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. クライアントでは、パッシブ認証は WebTicket 認証の最も望ましくない方法です。 すべての取締役、エンタープライズ プール、およびパッシブ認証を有効化する Standard Edition サーバー、他のすべての認証の種類必要があります無効にする Skype のビジネス Web サービスの次のコマンドレットを実行しています。

  ```
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. 次のコマンドレットを実行して、他のすべての認証の種類が無効になっていることを確認します。

  ```
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>プロキシ構成設定

Skype のビジネス Web サービスの証明書の認証を無効にするとビジネス クライアント用の Skype はレジストラーのサービスへの認証に Kerberos または NTLM などの優先順位の低い認証の種類を使用します。 Webticket を取得するためにクライアントを許可する証明書の認証が必要、ただし、Kerberos と NTLM 必要があります無効にするレジストラーのサービスです。

次の手順では、パッシブ認証を有効にするエッジ プール、エンタープライズ プール、Standard Edition サーバーにカスタムのプロキシ構成設定を作成する方法について説明します。

### <a name="to-create-a-custom-proxy-configuration"></a>カスタムのプロキシ構成設定を作成するには

1. ビジネス サーバー管理シェル コマンド ラインの Skype から、次を実行して、パッシブ認証を有効にするビジネス サーバー エッジ プール、エンタープライズ プールと Standard Edition サーバーの各 Skype の新しいプロキシ構成を作成します。コマンド:

  ```
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. 次のコマンドを実行して、他のすべてのプロキシ認証の種類が無効になっていることを確認します。

  ```
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>関連項目

[Skype のビジネス サーバーの 2 要素による認証を管理します。](two-factor-authentication.md)

[Business Server のビジネスのクライアントと Skype の Skype で二要素認証を使用します。](use-two-factor.md)
