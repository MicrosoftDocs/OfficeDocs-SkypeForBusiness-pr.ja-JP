---
title: Skype for Business Server で 2 要素認証を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: '概要: Skype for Business Server で 2 要素認証を構成します。'
ms.openlocfilehash: a7c5b4489b6b39e924a85c5e99796044d892c11f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814417"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>Skype for Business Server で 2 要素認証を構成する

**概要:** Skype for Business Server で 2 要素認証を構成します。

以下のセクションでは、展開用に 2 要素認証を構成するために必要な手順について説明します。 2 要素認証の詳細については [、「Enabling Office 365 multi-factor authentication for online administrators - Grid User Post](https://go.microsoft.com/fwlink/p/?LinkId=313332)」を参照してください。

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>スマート カード認証をサポートするためのエンタープライズ ルート証明機関の構成

次の手順では、スマート カード認証をサポートするためにエンタープライズ ルート CA を構成する方法について説明します。

エンタープライズ ルート CA をインストールする方法については、「エンタープライズ ルート証明機関のインストール」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=313364)。

1. ドメイン管理者アカウントを使用してエンタープライズ CA コンピューターにログインします。

2. システム マネージャーを起動し、証明機関 Web 登録の役割がインストールされていることを確認します。

3. [管理 **ツール] メニュー** から証明機関管理コンソール **を** 開きます。

4. ナビゲーション ウィンドウで、[証明機関] **を展開します**。

5. [証明書テンプレート] **を右クリックし、[** 新規] **を選択** し、[発行する **証明書テンプレート] を選択します**。

6. 登録 **エージェント、スマート****カード ユーザー、および****スマート カード ログオンを選択します**。

7. [**OK**] をクリックします。

8. [証明書テンプレート] **を右クリックします**。

9. [管理] **を選択します**。

10. Smartcard ユーザー テンプレートのプロパティを開きます。

11. [セキュリティ] タブ **をクリック** します。

12. アクセス許可を次のように変更します。

    - 読み取り/AD (許可) アクセス許可を持つ個々のユーザー アカウントを追加する、または

    - 読み取り/登録 (許可) アクセス許可を持つスマート カード ユーザーを含むセキュリティ グループを追加する、または

    - 読み取り/登録 (許可) アクセス許可を持つ Domain Users グループを追加する

## <a name="configure-windows-8-for-virtual-smart-cards"></a>仮想Windows 8カードの構成

2 要素認証とスマート カード テクノロジを展開する際に考慮する必要がある要素の 1 つは、実装のコストです。 Windows 8には多くの新しいセキュリティ機能が用意されています。最も興味深い新機能の 1 つは仮想スマート カードのサポートです。

仕様バージョン 1.2 を満たすトラステッド プラットフォーム モジュール (TPM) チップを搭載したコンピューターでは、ハードウェアに追加の投資を行わずにスマート カード ログオンのメリットを得る可能性があります。 詳細については、「仮想スマート カード[と仮想スマート カードの使用」をWindows 8。](https://go.microsoft.com/fwlink/p/?LinkId=313365)

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>仮想スマート カードWindows 8を構成するには

1. Skype for Business が有効Windows 8の資格情報を使用して、ユーザーのコンピューターにログインします。

2. スタートWindows 8画面で、画面の右下隅にカーソルを移動します。

3. [検索 **] オプション** を選択し、コマンド プロンプトを検索します。

4. コマンド プロンプトを右 **クリックし、[** 管理者として実行 **] を選択します**。

5. 次のコマンドを実行して、トラステッド プラットフォーム モジュール (TPM) 管理コンソールを開きます。

  ```console
  Tpm.msc
  ```

6. TPM 管理コンソールから、TPM 仕様のバージョンが 1.2 以上である必要があります。

    > [!NOTE]
    > 互換性信頼プラットフォーム モジュール (TPM) が見つからないことを示すダイアログが表示された場合は、コンピューターに互換性のある TPM モジュールがあり、システム BIOS で有効であることを確認します。

7. TPM 管理コンソールを閉じる

8. コマンド プロンプトで、次のコマンドを使用して新しい仮想スマート カードを作成します。

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

    > [!NOTE]
    > 仮想スマート カードの作成時にカスタム PIN 値を指定するには、代わりに /pin プロンプトを使用します。

9. コマンド プロンプトで、次のコマンドを実行して、コンピューターの管理コンソールを開きます。

  ```console
  CompMgmt.msc
  ```

10. コンピューターの管理コンソールで、[デバイス管理] **を選択します**。

11. [スマート **カード リーダー] を展開します**。

12. 新しい仮想スマート カード リーダーが正常に作成されたことを確認します。

## <a name="enroll-users-for-smart-card-authentication"></a>スマート カード認証用にユーザーを登録する

スマート カード認証用にユーザーを登録するには、通常 2 つの方法があります。 より簡単な方法では、ユーザーが Web 登録を使用してスマート カード認証に直接登録する方法と、登録エージェントを使用する方法が複雑になります。 このトピックでは、スマートカード証明書の自己登録について説明します。

登録エージェントとしてユーザーの代わりに登録する方法の詳細については、「他のユーザーの代わりに証明書を登録する」 [を参照してください](https://go.microsoft.com/fwlink/p/?LinkID=313367)。

### <a name="to-enroll-users-for-smart-card-authentication"></a>スマート カード認証用にユーザーを登録するには

1. Skype for Business が有効Windows 8の資格情報を使用して、Windows 8 ワークステーションにログインします。

2. 起動Internet Explorer。

3. 証明機関 Web **登録ページ** (例: https://MyCA.contoso.com/certsrv) .

    > [!NOTE]
    > Internet Explorer 10 を使用している場合は、この Web サイトを互換モードで表示する必要があります。

4. [ようこそ] **ページで** 、[証明書の要求 **] を選択します**。

5. 次に、[詳細な要求 **] を選択します**。

6. [作成 **] を選択し、この CA に要求を送信します**。

7. [ **証明書テンプレート] セクションで** **[Smartcard** ユーザー] を選択し、次の値で証明書の詳細要求を完了します。

  - **キー オプションは、** 次の設定を確認します。

    - [新しい **キー セットの作成] ラジオ ボタンを** 選択する

    - **CSP の場合** は **、Microsoft Base スマート カード暗号化プロバイダーを選択します。**

    - キー **使用法の場合は****、[Exchange]** を選択します (これが唯一のオプションです)。

    - キー **サイズの場合は**、「2048」と入力します。

    - [自動キー **コンテナー名] が選択** されているのを確認する

    - 他のボックスはオフのままにします。

  - [その **他のオプション] で** 、次の値を確認します。

    - 要求 **形式の場合は****、CMC を選択します**。

    - ハッシュ **アルゴリズムの場合は****、sha1 を選択します**。

    - [Friendly **Name]** に「Smardcard Certificate」と入力します。

8. 物理スマートカード リーダーを使用している場合は、スマート カードをデバイスに挿入します。

9. [送信 **] を** クリックして証明書要求を送信します。

10. メッセージが表示されたら、仮想スマート カードの作成に使用した PIN を入力します。

    > [!NOTE]
    > 既定の仮想スマート カード PIN 値は '12345678' です。

11. 証明書が発行された後、[この証明書のインストール] をクリックして登録プロセスを完了します。

    > [!NOTE]
    >  「この Web ブラウザーは証明書要求の生成をサポートしません」というエラーで証明書要求が失敗した場合、次の 3 つの方法で問題を解決できます。

        a. Enable Compatibility View in Internet Explorer
        b. Enable the Turn on Intranet settings option in Internet Explorer
        c. Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Active Directory フェデレーション サービスを構成する (AD FS 2.0)

次のセクションでは、多要素認証をサポートするために Active Directory フェデレーション サービス (AD FS 2.0) を構成する方法について説明します。 AD FS 2.0 のインストール方法については、「AD [FS 2.0 Step-by-Step and How To Guides](https://go.microsoft.com/fwlink/p/?LinkId=313374)」を参照してください。

> [!NOTE]
> FS 2.0 ADインストールする場合は、Windows Server Manager を使用して Active Directory フェデレーション サービスの役割を追加しません。 代わりに、Active Directory フェデレーション サービス [2.0 RTW パッケージをダウンロードしてインストールします](https://go.microsoft.com/fwlink/p/?LinkId=313375)。

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>2 要素認証AD FS を構成するには

1. ドメイン管理者アカウントをAD FS 2.0 コンピューターにログインします。

2. Windows PowerShell を起動します。

3. コマンド ラインWindows PowerShell次のコマンドを実行します。

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. 次のコマンドを実行して、展開に固有のサーバー名を置き換え、パッシブ認証が有効になる各サーバーとのパートナーシップを確立します。

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. [管理ツール] メニューから、AD FS 2.0 管理コンソールを起動します。

6. [**信頼関係証明書利用者**  >  **信頼] を展開します**。

7. Skype for Business Server に対して新しい信頼が作成されたのを確認します。

8. 次のコマンドを実行して、証明書利用者信頼の発行承認Windows PowerShellを作成して割り当てる。

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. 次のコマンドを実行して、証明書利用者信頼の発行変換Windows PowerShell作成して割り当てる。

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. AD FS 2.0 管理コンソールで、証明書利用者信頼を右クリックし、[要求規則の編集] **を選択します**。

11. [発行 **承認規則]** タブを選択し、新しい承認ルールが正常に作成されたことを確認します。

12. [発行 **変換ルール]** タブを選択し、新しい変換ルールが正常に作成されたことを確認します。

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>クライアント認証ADサポートするための FS 2.0 の構成

FS 2.0 でスマート カードを使用した認証をサポートAD、次の 2 種類の認証を構成できます。

- フォーム ベース認証 (FBA)

- トランスポート層セキュリティ クライアント認証

フォーム ベース認証を使用すると、ユーザー名/パスワードを使用するか、スマート カードと PIN を使用してユーザーを認証できる Web ページを開発できます。 このトピックでは、FS 2.0 でトランスポート層セキュリティ クライアント認証を実装するADについて説明します。 FS 2.0 認証のAD詳細については、「AD FS [2.0: How to Change the Local Authentication Type](https://go.microsoft.com/fwlink/p/?LinkId=313384).

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>クライアント認証AD FS 2.0 を構成するには

1. ドメイン管理者アカウントをAD FS 2.0 コンピューターにログインします。

2. Windows エクスプローラーを起動します。

3. C:\inetpub\adfs\ls に移動します。

4. 既存のファイルのバックアップ コピーをweb.configします。

5. メモ帳を使用してweb.configファイルを開きます。

6. メニュー バーから [編集] **を選択し** 、[検索] を **選択します**。

7. を検索します \<localAuthenticationTypes\> 。

    4 種類の認証が 1 行に 1 つ表示されます。

8. TLSClient 認証の種類を含む行を、セクションの一覧の一番上に移動します。

9. ファイルを保存して閉web.configします。

10. 管理者特権でコマンド プロンプトを起動します。

11. 次のコマンドを実行して IIS を再起動します。

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>Skype for Business Server パッシブ認証の構成

次のセクションでは、パッシブ認証をサポートするために Skype for Business Server を構成する方法について説明します。 有効にすると、2 要素認証が有効になっているユーザーは、物理スマート カードまたは仮想スマート カードと有効な PIN を使用して Skype for Business クライアントを使用してサインインする必要があります。

> [!NOTE]
> お客様は、サービス レベルでレジストラーと Web サービスのパッシブ認証を有効に強く推奨します。 レジストラーと Web サービスでパッシブ認証がグローバル レベルで有効になっている場合、サポートされているデスクトップ クライアントでサインインしていないユーザーに対して組織全体の認証エラーが発生する可能性があります。

### <a name="web-service-configuration"></a>Web サービスの構成

以下の手順では、パッシブ認証を有効にするディレクター、エンタープライズ プール、および Standard Edition サーバー用のカスタム Web サービス構成を作成する方法について説明します。

### <a name="to-create-a-custom-web-service-configuration"></a>カスタム Web サービス構成を作成するには

1. Skype for Business 管理者アカウントを使用して、Skype for Business Server フロントエンド サーバーにログインします。

2. Skype for Business Server 管理シェルを起動します。

3. Skype for Business Server 管理シェル コマンドラインから、次のコマンドを実行してパッシブ認証を有効にするディレクター、エンタープライズ プール、および Standard Edition サーバーごとに新しい Web サービス構成を作成します。

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

    > [!CAUTION]
    > WsFedPassiveMetadataUri FQDN の値は、AD FS 2.0 サーバーのフェデレーション サービス名です。 フェデレーション サービス名の値は、ナビゲーション ウィンドウから [サービス] を右クリックし、[フェデレーション サービスのプロパティの編集] を選択すると、AD FS 2.0 管理コンソール **にあります。**

4. 次のコマンドを実行して、UseWsFedPassiveAuth と WsFedPassiveMetadataUri の値が正しく設定されていることを確認します。

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. クライアントの場合、パッシブ認証は Webticket 認証の最も優先される認証方法です。 パッシブ認証が有効になるすべてのディレクター、エンタープライズ プール、および Standard Edition サーバーでは、次のコマンドレットを実行して、Skype for Business Web サービスで他のすべての種類の認証を無効にする必要があります。

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. 次のコマンドレットを実行して、他のすべての認証の種類が正常に無効にされたことを確認します。

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>プロキシ構成

Skype for Business Web サービスに対して証明書認証が無効になっている場合、Skype for Business クライアントは、Kerberos や NTLM などの優先されない認証の種類を使用してレジストラー サービスへの認証を行います。 ただし、クライアントが Webticket を取得するには証明書認証が必要ですが、レジストラー サービスに対して Kerberos と NTLM を無効にする必要があります。

次の手順では、パッシブ認証が有効になるエッジ プール、エンタープライズ プール、および Standard Edition サーバー用のカスタム プロキシ構成を作成する方法について説明します。

### <a name="to-create-a-custom-proxy-configuration"></a>カスタム プロキシ構成を作成するには

1. Skype for Business Server 管理シェル コマンドラインから、次のコマンドを実行してパッシブ認証を有効にする Skype for Business Server エッジ プール、エンタープライズ プール、および Standard Edition サーバーごとに新しいプロキシ構成を作成します。

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

  ```PowerShell
  New-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
  ```

2. 次のコマンドを実行して、他のすべてのプロキシ認証の種類が正常に無効にされたことを確認します。

  ```PowerShell
  Get-CsProxyConfiguration -Identity "Service:Registrar:SfBPool01.contoso.com" | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
  ```

## <a name="see-also"></a>関連項目

[Skype for Business Server で 2 要素認証を管理する](two-factor-authentication.md)

[Skype for Business クライアントと Skype for Business Server で 2 要素認証を使用する](use-two-factor.md)
