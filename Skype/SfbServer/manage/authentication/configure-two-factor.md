---
title: Skype for Business Server で2要素認証を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: '概要: Skype for Business Server で2要素認証を構成します。'
ms.openlocfilehash: 768ee9c2697523eff6922f20fd610554e32c1f7c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992334"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Skype for Business Server で2要素認証を構成する

**概要:** Skype for Business Server で2要素認証を構成します。

以下のセクションでは、展開に 2 要素認証を構成するために必要な手順について説明します。 2段階認証について詳しくは、「 [Office 365 の多要素認証を有効にする](https://go.microsoft.com/fwlink/p/?LinkId=313332)」をご覧ください。 Grid ユーザー投稿

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>スマート カード認証をサポートするエンタープライズ ルート証明機関を構成する

スマート カード認証をサポートするようにエンタープライズ ルート CA を構成する方法を以下の手順で説明します。

エンタープライズルート CA をインストールする方法については、「[エンタープライズルート証明機関をインストール](https://go.microsoft.com/fwlink/p/?LinkID=313364)する」を参照してください。

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

2 要素認証とスマート カード テクノロジを展開する場合に考慮する必要がある要素の 1 つは、実装コストです。 Windows 8 には新しいセキュリティ機能が数多く用意されています。また、最も重要な新機能の1つは仮想スマートカードをサポートしています。

バージョン 1.2 仕様を満たす Trusted Platform Module (TPM) チップを搭載したコンピューターでは、ハードウェアの追加費用をかけずにスマート カード ログオンを活用できるようになりました。 詳細については、「 [Windows 8 で仮想スマートカードを使用する](https://go.microsoft.com/fwlink/p/?LinkId=313365)」を参照してください。

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>Windows 8 を仮想スマート カード用に構成するには

1. Skype for Business が有効になっているユーザーの資格情報を使用して、Windows 8 コンピューターにログインします。

2. Windows 8 のスタート画面で、画面の右下隅にカーソルを移動します。

3. [**検索**] オプションを選択し、[コマンドプロンプト] を検索します。

4. [**コマンド プロンプト**] を右クリックし、[**管理者として実行**] をクリックします。

5. 次のコマンドを実行して、Trusted Platform Module (TPM) 管理コンソールを開きます。

  ```console
  Tpm.msc
  ```

6. TPM 管理コンソールで、TPM 仕様バージョンが 1.2 以上であることを確認します。

    > [!NOTE]
    > 相互運用性のある Trust Platform Module (TPM) が見つからないことを示すダイアログが表示された場合は、相互運用性のある TPM モジュールがコンピューターにインストールされていること、およびシステム BIOS で有効になっていることを確認します。

7. TPM 管理コンソールを閉じる

8. コマンド プロンプトで、次のコマンドを使用して新しい仮想スマート カードを作成します。

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > 仮想スマート カードを作成するときにカスタム PIN 値を指定するには、代わりに /pin プロンプトを使用します。

9. コマンド プロンプトから、次のコマンドを実行してコンピューター管理コンソールを開きます。

  ```console
  CompMgmt.msc
  ```

10. コンピューター管理コンソールで、[**デバイス管理**] をクリックします。

11. [**スマート カード リーダー**] を展開します。

12. 新しい仮想スマート カード リーダーが正しく作成されていることを確認します。

## <a name="enroll-users-for-smart-card-authentication"></a>スマート カード認証にユーザーを登録する

スマート カードの認証を行うユーザーを登録する方法は、主に 2 つあります。Web 登録を使ってスマート カード認証のユーザーを直接登録する方法がより簡単で、登録エージェントを使う方法はより複雑です。このトピックでは、スマート カードの証明書を自分で登録する方法について説明します。

登録エージェントとしてユーザーの代理として登録する方法について詳しくは、「[他のユーザーの代理で証明書を登録する](https://go.microsoft.com/fwlink/p/?LinkID=313367)」をご覧ください。

### <a name="to-enroll-users-for-smart-card-authentication"></a>スマート カードの認証を行うユーザーを登録するには、次の操作を行います。

1. Skype for Business が有効になっているユーザーの資格情報を使用して、Windows 8 ワークステーションにログインします。

2. Internet Explorer を起動します。

3. **証明機関の Web 登録**ページを参照しますhttps://MyCA.contoso.com/certsrv)(例:

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

    - **フレンドリ名**EnterSmardcard 証明書の場合。

8. 物理カード リーダーを使っている場合は、デバイスにスマート カードを挿入します。

9. [**送信**] をクリックして証明書要求を送信します。

10. 入力を求められたら、仮想スマート カードを作成したときに使った PIN を入力します。

    > [!NOTE]
    > 既定の仮想スマートカード PIN の値は "12345678" です。

11. 証明書が発行されたら、[**この証明書のインストール**] をクリックして登録プロセスを完了します。

    > [!NOTE]
    >  証明書の要求が、"この Web ブラウザーでは証明書要求の生成をサポートしていません" というエラーが表示される場合は、次の3つの方法で問題を解決できます。

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Active Directory フェデレーション サービス (AD FS 2.0) を構成する

次のセクションでは、多要素認証をサポートするように Active Directory フェデレーション サービス (AD FS 2.0) を構成する方法について説明します。 AD FS 2.0 をインストールする方法については、「 [AD fs 2.0 のステップバイステップとガイド](https://go.microsoft.com/fwlink/p/?LinkId=313374)」を参照してください。

> [!NOTE]
> AD FS 2.0 をインストールするときは、Windows Server Manager を使用して Active Directory フェデレーション サービスの役割を追加しないでください。 代わりに、 [Active Directory フェデレーションサービス2.0 プロフェッショナル用 rtwhttp://go.microsoft.com/fwlink/?linkid=625123 パッケージ](https://go.microsoft.com/fwlink/p/?LinkId=313375)をダウンロードしてインストールします。

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>2 要素認証の AD FS を構成するには

1. ドメイン管理者のアカウントを使用して AD FS 2.0 コンピューターにログインします。

2. Windows PowerShell を起動します。

3. Windows PowerShell コマンド ラインで次のコマンドを実行します。

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. 展開に固有のサーバー名を置き換えて以下のコマンドを実行することで、パッシブ認証に対して有効にされる各サーバーとのパートナーシップを確立します。

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. [管理ツール] メニューから AD FS 2.0 管理コンソールを起動します。

6. **信頼関係** > の**証明書利用者信頼**を展開します。

7. Skype for Business Server 用の新しい信頼が作成されていることを確認します。

8. Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行承認規則を作成して割り当てます。

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. Windows PowerShell を使用して次のコマンドを実行し、証明書利用者の信頼に関する発行変換規則を作成して割り当てます。

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. AD FS 2.0 管理コンソールで、証明書利用者の信頼を右クリックし、[**要求規則の編集**] をクリックします。

11. [**発行承認規則**] タブをクリックし、新しい承認規則が正しく作成されたことを確認します。

12. [**発行変換規則**] タブをクリックし、新しい変換規則が正しく作成されたことを確認します。

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>クライアント認証をサポートする AD FS 2.0 の構成

AD FS 2.0 でスマート カードを使用した認証をサポートできるように構成可能な認証の種類が 2 つあります。

- フォーム ベース認証 (FBA)

- トランスポート層セキュリティ クライアント認証

フォーム ベース認証を使用すると、ユーザー名/パスワードを使用した認証またはスマート カードと PIN を使用した認証をユーザーに許可できる Web ページを開発できます。 このトピックでは、AD FS 2.0 でトランスポート層セキュリティ クライアント認証を実装する方法を説明します。 AD FS 2.0 認証の種類の詳細については、「 [AD fs 2.0: ローカル認証の種類を変更する方法](https://go.microsoft.com/fwlink/p/?LinkId=313384)」を参照してください。

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>クライアント認証をサポートするように AD FS 2.0 を構成するには

1. ドメイン管理者のアカウントを使用して AD FS 2.0 コンピューターにログインします。

2. エクスプローラーを起動します。

3. C:\inetpub\adfs\ls に移動します。

4. 既存の web.config ファイルのバックアップ コピーを作成します。

5. メモ帳を使用して既存の web.config ファイルを開きます。

6. メニュー バーの [**編集**] をクリックし、[**検索**] をクリックします。

7. Localauthenticationtypes \<\>を検索します。

    4 つの認証の種類が 1 行に 1 つずつ表示されます。

8. TLSClient 認証の種類を含む行をセクションの一覧の一番上に移動します。

9. web.config ファイルを保存して閉じます。

10. 管理者特権でコマンド プロンプトを起動します。

11. 次のコマンドを実行して IIS を再起動します。

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Skype for Business Server のパッシブ認証の構成

以下のセクションでは、パッシブ認証をサポートするように Skype for Business Server を構成する方法について説明します。 有効にした場合、2要素認証が有効になっているユーザーは、物理または仮想スマートカードと有効な PIN を使用して、Skype for Business クライアントを使用してサインインする必要があります。

> [!NOTE]
> レジストラーと Web サービスのパッシブ認証はサービス レベルで有効にすることを強くお勧めします。レジストラーと Web サービスのパッシブ認証をグローバル レベルで有効にすると、サポートされるデスクトップ クライアントでサインインしていないユーザーが組織全体で認証エラーになる可能性があります。

### <a name="web-service-configuration"></a>Web サービス構成設定

次の手順では、パッシブ認証を有効にするディレクター、エンタープライズ プール、Standard Edition サーバーにカスタムの Web サービス構成設定を作成する方法について説明します。

### <a name="to-create-a-custom-web-service-configuration"></a>カスタムの Web サービス構成設定を作成するには

1. Skype for business の管理者アカウントを使用して、Skype for Business Server フロントエンドサーバーにログインします。

2. Skype for Business Server 管理シェルを起動します。

3. Skype for Business Server 管理シェルコマンドラインで、次のコマンドを実行して、各ディレクター、エンタープライズプール、および標準エディションのサーバー用の新しい Web サービス構成を作成します。これにより、パッシブ認証が有効になります。

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > WsFedPassiveMetadataUri の FQDN の値は、AD FS 2.0 サーバーのフェデレーション サービス名です。フェデレーション サービス名の値は、AD FS 2.0 管理コンソールでナビゲーション ウィンドウの [**サービス**] を右クリックし、[**Edit Federation Service Properties**] を選択すると確認できます。

4. 次のコマンドを実行して、UseWsFedPassiveAuth と WsFedPassiveMetadataUri の値が正しく設定されたことを確認します。

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. クライアントでは、パッシブ認証は WebTicket 認証の最も望ましくない方法です。 パッシブ認証を有効にするすべてのディレクター、エンタープライズプール、および標準エディションのサーバーの場合は、次のコマンドレットを実行して、Skype for Business Web サービスでその他のすべての認証の種類を無効にする必要があります。

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. 次のコマンドレットを実行して、他のすべての認証の種類が無効になっていることを確認します。

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>プロキシ構成設定

Skype for Business Web サービスの証明書認証が無効になっている場合、Skype for Business クライアントは、優先度の低い認証の種類 (Kerberos、NTLM など) を使用してレジストラーサービスを認証します。 ただし、クライアントが webticket を取得できるようにするには、証明書の認証が必要です。ただし、レジストラーサービスについては、Kerberos と NTLM を無効にする必要があります。

次の手順では、パッシブ認証を有効にするエッジ プール、エンタープライズ プール、Standard Edition サーバーにカスタムのプロキシ構成設定を作成する方法について説明します。

### <a name="to-create-a-custom-proxy-configuration"></a>カスタムのプロキシ構成設定を作成するには

1. Skype for Business Server 管理シェルのコマンドラインで、次のコマンドを実行して、各 Skype for Business Server Edge プール、エンタープライズプール、および標準エディションのサーバーに対して新しいプロキシ構成を作成します。コマンド

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. 次のコマンドを実行して、他のすべてのプロキシ認証の種類が無効になっていることを確認します。

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>関連項目

[Skype for Business Server で2要素認証を管理する](two-factor-authentication.md)

[Skype for Business クライアントと Skype for Business Server で2要素認証を使用する](use-two-factor.md)
