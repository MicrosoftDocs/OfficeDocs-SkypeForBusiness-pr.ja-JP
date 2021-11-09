---
title: 2 要素認証を構成Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
description: '概要: 2 要素認証を 2 要素認証で構成Skype for Business Server。'
ms.openlocfilehash: 1e28c88f28d765737415b01d82e2e8a7621c3744
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844250"
---
# <a name="configure-two-factor-authentication-in-skype-for-business-server"></a>2 要素認証を構成Skype for Business Server

**概要:** サーバーで 2 要素認証をSkype for Business Server。

以下のセクションでは、展開の 2 要素認証を構成するために必要な手順について説明します。 2 要素認証の詳細については、「オンライン管理者Office 365多要素認証の有効化 - Grid User Post 」[を参照してください](https://go.microsoft.com/fwlink/p/?LinkId=313332)。

## <a name="configure-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>スマート カードEnterpriseをサポートするルート証明機関を構成する

次の手順では、スマート カード認証をサポートEnterpriseルート CA を構成する方法について説明します。

ルート CA のインストール方法については、「Enterpriseルート証明機関のインストール[」を参照Enterpriseしてください](/previous-versions/windows/it-pro/windows-server-2003/cc776709(v=ws.10))。

1. ドメイン管理者アカウントを使用Enterprise CA コンピューターにログインします。

2. System Manager を起動し、証明機関 Web 登録の役割がインストールされていることを確認します。

3. [管理 **ツール] メニュー** から、証明機関の **管理コンソールを** 開きます。

4. [ナビゲーション] ウィンドウで、[証明機関] **を展開します**。

5. [証明書テンプレート]**を右クリックし、[****新規]** を選択し、[**発行する証明書テンプレート] を選択します**。

6. [ **登録エージェント]** **、[Smartcard ユーザー] 、** および **[スマートカード ログオン] を選択します**。

7. **[OK]** をクリックします。

8. [証明書テンプレート] **を右クリックします**。

9. [管理 **] を選択します**。

10. Smartcard ユーザー テンプレートのプロパティを開きます。

11. [セキュリティ] タブ **をクリック** します。

12. アクセス許可を次のように変更します。

    - 読み取り/登録ADアクセス許可を持つ個々のユーザー アカウントを追加するか、または

    - 読み取り/登録 (許可) アクセス許可を持つスマート カード ユーザーを含むセキュリティ グループを追加する、または

    - 読み取り/登録 (許可) アクセス許可を持つドメイン ユーザー グループを追加する

## <a name="configure-windows-8-for-virtual-smart-cards"></a>仮想Windows 8カードの構成

2 要素認証とスマート カード テクノロジを展開する際に考慮すべき 1 つの要素は、実装のコストです。 Windows 8新しいセキュリティ機能が多数提供され、最も興味深い新機能の 1 つは仮想スマート カードのサポートです。

仕様バージョン 1.2 を満たすトラステッド プラットフォーム モジュール (TPM) チップを搭載したコンピューターの場合、組織はハードウェアに追加の投資をすることなく、スマート カード ログオンの利点を得る事が可能になります。 詳細については、「仮想スマート カード[と仮想スマート カードを使用する」を参照Windows 8。](https://go.microsoft.com/fwlink/p/?LinkId=313365)

### <a name="to-configure-windows-8-for-virtual-smart-cards"></a>仮想スマート カードWindows 8を構成するには

1. ユーザーが有効なWindows 8の資格情報を使用して、Skype for Businessコンピューターにログインします。

2. [スタートWindows 8画面で、画面の右下隅にカーソルを移動します。

3. [検索] **オプションを** 選択し、[コマンド プロンプト] を検索します。

4. [コマンド プロンプト] **を右クリックし**、[管理者として **実行] を選択します**。

5. 次のコマンドを実行して、信頼できるプラットフォーム モジュール (TPM) 管理コンソールを開きます。

   ```console
   Tpm.msc
   ```

6. TPM 管理コンソールで、TPM 仕様のバージョンが 1.2 以上である必要があります。

    > [!NOTE]
    > 互換性のある信頼プラットフォーム モジュール (TPM) が見つからないことを示すダイアログが表示される場合は、コンピューターに互換性のある TPM モジュールがあり、システム BIOS で有効になっていることを確認します。

7. TPM 管理コンソールを閉じる

8. コマンド プロンプトから、次のコマンドを使用して新しい仮想スマート カードを作成します。

  ```console
  TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
  ```

   > [!NOTE]
   > 仮想スマート カードの作成時にカスタム PIN 値を指定するには、代わりに /pin プロンプトを使用します。

9. コマンド プロンプトから、次のコマンドを実行してコンピューター管理コンソールを開きます。

  ```console
  CompMgmt.msc
  ```

10. [コンピューターの管理] コンソールで、[デバイスの管理] **を選択します**。

11. [ **スマート カード リーダー] を展開します**。

12. 新しい仮想スマート カード リーダーが正常に作成されたことを確認します。

## <a name="enroll-users-for-smart-card-authentication"></a>スマート カード認証用にユーザーを登録する

スマート カード認証用にユーザーを登録するには、通常 2 つの方法があります。 簡単な方法では、ユーザーが Web 登録を使用してスマート カード認証に直接登録する方法と、登録エージェントを使用する方法が複雑になります。 このトピックでは、スマートカード証明書の自己登録について説明します。

登録エージェントとしてユーザーに代わって登録する方法の詳細については、「他のユーザーに代わって証明書を登録する」 [を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770802(v=ws.11))。

### <a name="to-enroll-users-for-smart-card-authentication"></a>スマート カード認証のユーザーを登録するには

1. 有効なユーザーのWindows 8を使用して、Skype for Businessワークステーションにログインします。

2. 起動Internet Explorer。

3. [証明機関 Web **登録] ページを参照** します (例 https://MyCA.contoso.com/certsrv) : .

    > [!NOTE]
    > アプリを使用しているInternet Explorer 10、互換モードでこの Web サイトを表示する必要がある場合があります。

4. [ようこそ] **ページで** 、[証明書の **要求] を選択します**。

5. 次に、[高度な **要求] を選択します**。

6. [この **CA に要求を作成して送信する] を選択します**。

7. [ **証明書テンプレート] セクションで [Smartcard User]** **を** 選択し、次の値で高度な証明書要求を完了します。

  - **キー オプションは、** 次の設定を確認します。

    - [新しい **キー セットの作成] ラジオ ボタンを** 選択する

    - **CSP の場合** は **、[Microsoft Base Smart Card Crypto Provider] (Microsoft Base Smart Card Crypto Provider) を選択します。**

    - [**キーの使用法]****で、[Exchange** を選択します (これは、使用可能な唯一のオプションです)。

    - [ **キー のサイズ]** に「2048」と入力します。

    - [自動キー **コンテナー名] が選択** されているのを確認する

    - 他のボックスはオフのままにします。

  - [追加 **オプション] で** 、次の値を確認します。

    - [要求 **形式] で****[CMC] を選択します**。

    - [ハッシュ **アルゴリズム] で** **[sha1] を選択します**。

    - [ **フレンドリー名] に** 「Smardcard Certificate」と入力します。

8. 物理スマートカード リーダーを使用している場合は、スマート カードをデバイスに挿入します。

9. [送信 **] を** クリックして証明書要求を送信します。

10. メッセージが表示されたら、仮想スマート カードの作成に使用した PIN を入力します。

    > [!NOTE]
    > 既定の仮想スマート カードの PIN 値は '12345678' です。

11. 証明書が発行された後、[この証明書のインストール] **を** クリックして登録プロセスを完了します。

    > [!NOTE]
    >  "この Web ブラウザーは証明書要求の生成をサポートしません" というエラーで証明書要求が失敗した場合、次の 3 つの方法で問題を解決できます。
    >- [互換性ビューを有効にする] Internet Explorer。
    >- [イントラネットの設定を有効にする] オプションを [イントラネットの設定] Internet Explorer。
    >- [オプション] メニューの [セキュリティ] タブの [すべてのゾーンを既定のレベルにリセットInternet Explorer選択します。

## <a name="configure-active-directory-federation-services-ad-fs-20"></a>Active Directory フェデレーション サービスの構成 (AD FS 2.0)

次のセクションでは、多要素認証をサポートするために Active Directory フェデレーション サービス (AD FS 2.0) を構成する方法について説明します。 FS 2.0 をADする方法については [、「AD FS 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))のステップ バイ ステップ」および「How To Guides」を参照してください。

> [!NOTE]
> FS 2.0 ADインストールする場合は、Active Directory フェデレーション サービスの役割を追加Windowsサーバー マネージャーを使用しません。 代わりに、Active Directory フェデレーション サービス [をダウンロードしてインストールします](/troubleshoot/windows-server/identity/availability-description-afds)。

### <a name="to-configure-ad-fs-for-two-factor-authentication"></a>2 要素認証AD FS を構成するには

1. ドメイン管理者アカウントをAD FS 2.0 コンピューターにログインします。

2. Windows PowerShell を起動します。

3. コマンド ラインWindows PowerShell、次のコマンドを実行します。

  ```PowerShell
  add-pssnapin Microsoft.Adfs.PowerShell
  ```

4. 次のコマンドを実行して、展開に固有のサーバー名を置き換え、パッシブ認証を有効にする各サーバーとのパートナーシップを確立します。

  ```PowerShell
  Add-ADFSRelyingPartyTrust -Name SfBPool01-PassiveAuth -MetadataURL https://SfBpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
  ```

5. [管理ツール] メニューから、FS 2.0 ADを起動します。

6. [**信頼関係証明書利用者**  >  **の信頼] を展開します**。

7. サーバーに新しい信頼が作成Skype for Business Server。

8. 次のコマンドを実行して、証明書利用者信頼の発行承認ルールを作成Windows PowerShell証明書利用者信頼に割り当てる。

  ```PowerShell
  $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "https://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth
-IssuanceAuthorizationRules $IssuanceAuthorizationRules
  ```

9. 次のコマンドを実行して、証明書利用者信頼の発行変換ルールを作成してWindows PowerShell証明書利用者信頼に割り当てる。

  ```PowerShell
  $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "https://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
  ```

  ```PowerShell
  Set-ADFSRelyingPartyTrust -TargetName SfBPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
  ```

10. FS 2.0 ADから、証明書利用者の信頼を右クリックし、[クレーム ルールの編集 **] を選択します**。

11. [発行 **承認ルール] タブを** 選択し、新しい承認ルールが正常に作成されたことを確認します。

12. [発行 **変換ルール] タブを** 選択し、新しい変換ルールが正常に作成されたことを確認します。

## <a name="configuring-ad-fs-20-to-support-client-authentication"></a>クライアント認証AD FS 2.0 の構成

FS 2.0 でスマート カードを使用した認証をサポートAD、次の 2 種類の認証を構成できます。

- フォーム ベース認証 (FBA)

- トランスポート層セキュリティ クライアント認証

フォーム ベース認証を使用すると、ユーザーがユーザー名/パスワードを使用するか、スマート カードと PIN を使用して認証できる Web ページを開発できます。 このトピックでは、FS 2.0 を使用してトランスポート層セキュリティ クライアント認証を実装するADを説明します。 FS 2.0 認証ADの詳細については [、「AD FS 2.0: ローカル](https://go.microsoft.com/fwlink/p/?LinkId=313384)認証の種類を変更する方法」を参照してください。

### <a name="to-configure-ad-fs-20-to-support-client-authentication"></a>クライアント認証AD FS 2.0 を構成するには

1. ドメイン管理者アカウントをAD FS 2.0 コンピューターにログインします。

2. Windows エクスプローラーを起動します。

3. C:\inetpub\adfs\ls への参照

4. 既存のファイルのバックアップ コピーをweb.configします。

5. 既存のファイルを開web.configを使用メモ帳。

6. メニュー バーで [編集] を選択 **し** 、[検索] を **選択します**。

7. \<localAuthenticationTypes\> を検索します。

    一覧には、1 行に 1 つの 4 つの認証の種類があります。

8. TLSClient 認証の種類を含む行をセクションの一覧の一番上に移動します。

9. ファイルを保存して閉web.configします。

10. 管理者特権でコマンド プロンプトを起動します。

11. 次のコマンドを実行して IIS を再起動します。

  ```console
  IISReset /Restart /NoForce
  ```

## <a name="configuring-skype-for-business-server-passive-authentication"></a>パッシブ認証Skype for Business Server構成する

次のセクションでは、パッシブ認証をサポートSkype for Business Server構成する方法について説明します。 有効にすると、2 要素認証が有効になっているユーザーは、物理スマート カードまたは仮想スマート カードと有効な PIN を使用して、Skype for Business クライアントを使用してサインインする必要があります。

> [!NOTE]
> レジストラーと Web サービスのパッシブ認証をサービス レベルで有効に強く推奨します。 レジストラーと Web サービスでグローバル レベルでパッシブ認証が有効になっている場合、サポートされているデスクトップ クライアントでサインインしていないユーザーの組織全体の認証エラーが発生する可能性があります。

### <a name="web-service-configuration"></a>Web サービスの構成

次の手順では、パッシブ認証を有効にするディレクター、Enterprise プール、Standard Editionサーバーのカスタム Web サービス構成を作成する方法について説明します。

### <a name="to-create-a-custom-web-service-configuration"></a>カスタム Web サービス構成を作成するには

1. 管理者アカウントを使用Skype for Business Serverフロント エンド サーバー Skype for Businessログインします。

2. 管理シェルSkype for Business Server起動します。

3. Skype for Business Server 管理シェル コマンド ラインから、次のコマンドを実行してパッシブ認証を有効にするディレクター、Enterprise プール、および Standard Edition サーバーごとに新しい Web サービス構成を作成します。

  ```PowerShell
  New-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
  ```

   > [!CAUTION]
   > WsFedPassiveMetadataUri FQDN の値は、FS 2.0 サーバーのADサービス名です。 フェデレーション サービス名の値は、AD FS 2.0 管理コンソールのナビゲーション ウィンドウで [サービス] を右クリックし、[フェデレーション サービスのプロパティの編集] を選択することで **確認できます**。

4. 次のコマンドを実行して、UseWsFedPassiveAuth および WsFedPassiveMetadataUri の値が正しく設定されていることを確認します。

  ```PowerShell
  Get-CsWebServiceConfiguration -identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
  ```

5. クライアントの場合、パッシブ認証は Web チケット認証の最も優先される認証方法です。 パッシブ認証が有効になるすべてのディレクター、Enterprise プール、および Standard Edition サーバーでは、次のコマンドレットを実行して、Skype for Business Web Services で他のすべての認証の種類を無効にする必要があります。

  ```PowerShell
  Set-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
  ```

6. 次のコマンドレットを実行して、他のすべての認証の種類が正常に無効にされたことを確認します。

  ```PowerShell
  Get-CsWebServiceConfiguration -Identity "Service:WebServer:SfBPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
  ```

### <a name="proxy-configuration"></a>プロキシ構成

Skype for Business Web サービスで証明書認証が無効になっている場合、Skype for Business クライアントは、レジストラー サービスに対する認証に Kerberos や NTLM などのあまり優先されない認証の種類を使用します。 クライアントが Web チケットを取得するには、証明書認証が必要ですが、レジストラー サービスでは Kerberos と NTLM を無効にする必要があります。

次の手順では、パッシブ認証を有効にするエッジ プール、Enterprise プール、および Standard Edition サーバーのカスタム プロキシ構成を作成する方法について説明します。

### <a name="to-create-a-custom-proxy-configuration"></a>カスタム プロキシ構成を作成するには

1. Skype for Business Server 管理シェル コマンド ラインから、次の手順を実行してパッシブ認証を有効にする Skype for Business Server エッジ プール、Enterprise プール、および Standard Edition サーバーごとに新しいプロキシ構成を作成します。コマンド:

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

[2 要素認証を管理Skype for Business Server](two-factor-authentication.md)

[クライアントとクライアントで 2 要素認証Skype for Business使用Skype for Business Server](use-two-factor.md)
