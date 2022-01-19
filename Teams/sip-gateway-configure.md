---
title: SIP ゲートウェイの構成
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: SIP ゲートウェイを構成する方法について説明します。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1af44c5e3962f89346cae166bf40efa6a8622338
ms.sourcegitcommit: eddc03f777ce78bd5273708da9b1ab609ee20099
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2022
ms.locfileid: "62065183"
---
# <a name="configure-sip-gateway"></a>SIP ゲートウェイの構成

この記事では、組織がデバイスと互換性のある SIP デバイスを使用できるよう SIP ゲートウェイを構成する方法についてMicrosoft Teams。 組織に対して SIP ゲートウェイが実行できる機能と、組織に必要なハードウェア、ソフトウェア、ライセンスを確認するには、「SIP ゲートウェイの計画」 [を参照してください](sip-gateway-plan.md)。

SIP ゲートウェイを構成する前に、次の操作を行います。

- **SIP デバイスを出荷時の既定の設定にリセットします。** お客様または組織のユーザーは、SIP ゲートウェイで使用される各 SIP デバイスを出荷時の既定の設定にリセットする必要があります。 その方法については、製造元の手順を参照してください。

- **ファイアウォールを開き、Microsoft 365をTeams。** ネットワークのファイアウォールを開き、Microsoft 365 URL と IP Teamsの範囲に関するページで説明Office 365トラフィック[を制御します](/microsoft-365/enterprise/urls-and-ip-address-ranges)。

- **SIP デバイスがプロキシの背後に接続されていないか確認します。** http/s トラフィックが企業の http/s プロキシをバイパスします。

- **UDP ポートを開きます。** IP 範囲が 52.112.0.0/14 ~ 52.120.0.0/14 の場合は、49152 ~ 53247 の範囲で UDP ポートを開きます。

- **TCP ポートを開きます。** IP 範囲 52.112.0.0/14 ~ 52.120.0.0/14 の TCP ポート 5061 を開きます。

- **次の https エンドポイント (IP アドレスと URL) を開きます。**

  - 13.75.175.145
  - 52.189.219.201
  - 51.124.34.164
  - 13.74.250.91
  - 13.83.55.36
  - 23.96.103.40
  - https://blobsdgapac.blob.core.windows.net
  - https://blobsdgemea.blob.core.windows.net
  - https://blobsdgnoam.blob.core.windows.net
  - https://httpblobsdgapac.blob.core.windows.net
  - https://httpblobsdgemea.blob.core.windows.net
  - https://httpblobsdgnoam.blob.core.windows.net



次のセクションでは、SIP ゲートウェイを構成するために管理者として行う必要がある操作について説明します。

- [SIP ゲートウェイが組織で使用できると確認します](#verify-that-sip-gateway-is-available-for-your-organization)。

- [組織内のユーザーに対して SIP ゲートウェイを有効にします](#enable-sip-gateway-for-the-users-in-your-organization)。

- [SIP ゲートウェイ プロビジョニング サーバーの URL を設定します](#set-the-sip-gateway-provisioning-server-url)。

この記事では、次の方法も説明します。

- [便宜上、SIP デバイスを個別に登録するか、バッチで登録します](#provision-and-enroll-sip-devices-as-common-area-phones)。  


- [SIP デバイスを表示および監視します。](#view-and-monitor-sip-devices)

- [多言語ユーザー インターフェイスのサポートを有効にします。](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>組織で SIP ゲートウェイを使用できると確認する

1. 管理センター[にTeamsします](https://admin-teams.microsoft.com/)。

2. 左側の [デバイス] **Teamsを選択し****、[SIP デバイス] タブが表示** されていないか確認します。 その場合、組織で SIP ゲートウェイ サービスが有効になります。

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>組織内のユーザーに対して SIP ゲートウェイを有効にする

組織で SIP Gateway を有効にするには、Teams 管理センターを使用するか、PowerShell コマンドレットを使用します。

### <a name="by-using-teams-admin-center"></a>管理センター Teams使用する

管理センターで SIP ゲートウェイをTeamsするには、次の手順に従います。

1. 管理センター [Teams移動する](https://admin.teams.microsoft.com/)

2. 左側の [音声] で **、[通話** ポリシー] **を選択します**。

3. [ポリシーの管理 **]** の右側で、ユーザーに割り当てられている適切な呼び出しポリシーを選択するか、必要に応じて新しい呼び出しポリシーを作成して、必要なユーザーに割り当てることができます。

4. [ポリシー **の管理] を選択** し、ポリシーを選択し、[編集] を **選択します**。

5. SIP デバイスの設定を **有効にし、 を呼び出し** に使用し、[保存] を **選択します**。


### <a name="by-using-powershell"></a>PowerShell を使用する

PowerShell [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) コマンドレットを使用して SIP ゲートウェイを有効にすることもできます。 SIP デバイスのユーザーを有効にするには、ポリシーを選択し、 属性を `-AllowSIPDevicesCalling` に設定します `True` 。 既定値は です。そのため、ユーザーは SIP デバイスを有効にしない `False` 限り使用できません。


> [!NOTE]
> - ポリシーの伝達には最大 24 時間かかる場合があります。

## <a name="set-the-sip-gateway-provisioning-server-url"></a>SIP ゲートウェイ プロビジョニング サーバーの URL を設定する

SIP ゲートウェイ プロビジョニング サーバーの URL は、動的ホスト構成プロトコル (DHCP) サーバーで設定できます。 リモートで作業するユーザーは、手動で構成する必要があります。

### <a name="using-dhcp"></a>DHCP の使用

SIP デバイスごとに、次のいずれかの SIP Gateway プロビジョニング サーバー URL を設定します。 

- EMEA: `http://emea.ipp.sdg.teams.microsoft.com`
- アメリカ: `http://noam.ipp.sdg.teams.microsoft.com`
- APAC: `http://apac.ipp.sdg.teams.microsoft.com`

DHCP サーバーで上記の SIP Teams サーバー URL を構成して、SIP デバイスを組織に追加します。 DHCP サーバーの詳細については、DHCP のデプロイと管理に関 [するページを参照してください](/learn/modules/deploy-manage-dynamic-host-configuration-protocol)。 また、DHCP オプション 42 を使用してネットワーク タイム プロトコル (NTP) サーバーを指定し、DHCP オプション 2 を使用して協定世界時 (UTC) からのオフセットを秒で指定できます。 組織内のデバイスは、SIP Gateway プロビジョニング サーバーにルーティングされます。 正常にプロビジョニングされた SIP 電話には、サインインTeamsロゴとソフト ボタンが表示されます。

SIP デバイスがオンボードでサポートされているファームウェアの最小バージョンにインストールされている必要があります。 オンボード中に、SIP ゲートウェイは既定の構成と認証ユーザー インターフェイスをデバイスにプッシュします。 SIP デバイスに必要なファームウェア バージョンについては、「SIP ゲートウェイの計画 [」を参照してください](sip-gateway-plan.md)。

### <a name="manually"></a>手動

リモートで作業するユーザーは、次の手順を使用して、プロビジョニング サーバーの URL を SIP デバイスに手動で構成する必要があります。

1. デバイス **設定** を開き、デバイスの IP アドレスを取得します。

2. ブラウザー ウィンドウを開き、デバイスの IP アドレスを入力し、(必要に応じて) ログインし、デバイスの Web ユーティリティでプロビジョニング サーバーの URL を構成します。

3. [設定 **Web** ユーティリティの [詳細設定] で、上記のプロビジョニング サーバー URL を入力します。 

> [!NOTE]
> - SIP ゲートウェイにオンボードできるのは、互換性のある SIP デバイスのみです。 
> - Cisco IP 電話は、オンボードする前に、マルチプラットフォーム ファームウェアにフラッシュする必要があります。 方法については、Cisco ファームウェア変換 [ガイド を参照してください](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)。
> - Yealink 電話の場合は、オプション 66 を使用します。
> - Cisco、Poly、AudioCode 電話機の場合は、オプション 160 を使用します。 
> - Cisco デバイスの場合は、プロビジョニング **サーバーの URLPSN.xml/$** を追加します。


## <a name="configure-conditional-access"></a>条件付きアクセスを構成する

条件付きアクセスは、Azure Active Directory (Azure AD) 機能であり、Microsoft 365 リソースにアクセスするデバイスを適切に管理し、セキュリティで保護するのに役立ちます。 SIP ゲートウェイは、AZURE AD で SIP デバイスを認証します。そのため、組織が企業ネットワーク内のデバイスに条件付きアクセスを使用している場合は、次の IP アドレスを除外する必要があります。

- 北米:
    - 米国東部: 52.170.38.140
    - 米国西部: 40.112.144.212
-   EMEA リージョン:
    - 北 EU: 40.112.71.149
    - 西 EU: 40.113.112.67
-   APAC リージョン:
    - オーストラリア東部: 20.92.120.71
    - オーストラリア南東部: 13.73.115.90

詳細については、IP アドレス範囲 [に関するページを参照してください](/azure/active-directory/conditional-access/location-condition#ip-address-ranges)。


## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>SIP デバイスを共通領域の電話としてプロビジョニングおよび登録する
> [!NOTE]
> SIP デバイスを登録するには、SIP ゲートウェイにオンボードする必要があります。

タスクを効率化するために、SIP デバイスを一度に 1 Teamsまたはバッチで管理センターに登録できます。 次の操作を実行してください。

1. 管理センター [**にログインTeamsします**](https://admin.teams.microsoft.com)。

2. [デバイス **TEAMS SIP デバイス]**  >  **を選択します**。

3. 右上にある [アクション] [デバイスの **プロビジョニング**]  >  **を選択し**、次のいずれかの手順に従います。

  - **1 つのデバイスをプロビジョニングするには:**

     a. [アクティブ **化の待機中] で、[** 追加] **を選択します**。

     b. [MAC **アドレスの追加]** ウィンドウで、デバイスの **MAC アドレス** と **場所** を入力し、[適用] を **選択します**。
     
     c. [ **アクティブ化の待機中**] で、追加したデバイスを選択し、[確認コードの生成 **] を選択します**。
     
     d. [デバイス **のプロビジョニング]** ウィンドウの **[確認コード] で**、SIP デバイスの確認コードをメモします。

   - **多くのデバイスをプロビジョニングするには:**

     a. 右側 **の [アクティブ化の待機** 中] で、[**エクスポート]** ([エクスポート] アイコン) Microsoft Excelします。
     
     b. [デバイス **のプロビジョニング] ウィンドウ** の [複数 **の MAC アップロード] で**、[テンプレートのダウンロード]**を選択します**。
     
     c. コンピューター **Template_Provisioning.csv** 保存し **、[MAC ID]** フィールドと [場所] フィールドに **入力** します。
    
     d. [デバイスの **プロビジョニング] ウィンドウ** で、[複数の **MAC アップロードを選択します**。 

     e. [MAC アドレスのアップロード **ウィンドウ** の右側で、[ファイルの選択] を選択し、データを **Template_Provisioning.csvファイルを** 選択します。

     f. [**デバイスのプロビジョニング**] ウィンドウの [**アクティブ** 化待ち] でデバイスを選択し、[確認コードの生成] を選択して、プロビジョニングされたデバイスごとに 1 回の確認コードを生成します。 各 SIP デバイスの確認コードをメモします。

4. SIP デバイスで、登録機能コードに続いて確認コードをダイヤルします。 SIP デバイスで、登録機能コード \* 55* (SIP ゲートウェイで 1 回認証コードの検証に使用) にダイヤルし、その後、この特定のデバイスの Teams 管理センターで生成される確認コードをダイヤルします。 たとえば、確認コードが有効な場合は、123456 \* 55 をダイヤル123456 \* デバイスを登録します。

5.  [デバイスの **プロビジョニング] ウィンドウ** の [サインイン **待ち] で、[** サインアウト] **を選択します**。

6. [ユーザー **のサインイン] ダイアログで** 、SIP デバイスのペアリング コードをコピーまたはメモします。

7. に移動 [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) し、[コードの入力 **]** で SIP デバイスのペアリング コードを入力し、[次へ] を選択 **します**。

8. [Microsoft **サインイン] ページの**  [電子メールまたは電話] フィールドに SIP デバイスのメール アドレスを入力し、[次へ] を選択 **します**。

9. [パスワード **] ページ** で、SIP デバイスのメール アドレスのパスワードを入力し、[サインイン] **を選択します**。

10. [Sip **デバイス ゲートウェイへのサインインを試みTeams] ページで、[続行**] を **選択します**。

## <a name="how-to-sign-in-and-sign-out"></a>サインインしてサインアウトする方法

ユーザーの個人用デバイスでは、ローカル サインインだけがサポートされます。 管理センターからデバイスをサインアウトするには、次の手順に従います。

1. 管理センター [**にログインTeamsします**](https://admin.teams.microsoft.com)。

2. [デバイス **TEAMS SIP デバイス]**  >  **を選択します**。

3. 右側で SIP デバイスを選択し、[サインアウト] **を選択します**。


### <a name="user-pairing-and-sign-in"></a>ユーザーのペアリングとサインイン

ユーザーが会社の資格情報を使用して認証した後に SIP デバイスをペアリングするには、次の条件を実行する必要があります。

1. SIP **電話で [サインイン** ] を押して、認証 URL とペアリング コードを表示します。 ペアリング コードは時間依存です。 有効期限が切れた場合、ユーザーは電話で **Back キー** を押し、サインイン プロセスを再度開始する必要があります。

2. ユーザーのデスクトップまたはモバイル ブラウザーで認証 URL に移動し、会社の資格情報を使用してログインします。

3. SIP 電話に表示されるペアリング コードを Web 認証アプリに入力して、SIP 電話をユーザーのアカウントとペアリングします。 サインインに成功すると、しばらく時間がかかる場合があります。デバイスでサポートされている場合、SIP 電話には電話番号とユーザー名が表示されます。

> [!NOTE]
> Azure Active Directory Web 認証アプリに表示されるデバイスの場所は、デバイスが接続されている SIP ゲートウェイ データセンターです。 スコープ内の SIP 電話は OAuth 対応ではないので、SIP Gateway は Web 認証アプリを介してユーザーを認証し、デバイスをユーザーの資格情報とペアにします。 詳細については、「Microsoft ID プラットフォーム[OAuth 2.0 デバイス承認付与フロー」を参照してください](/azure/active-directory/develop/v2-oauth2-device-code)。

### <a name="sign-out"></a>サインアウト

サインアウトするには、デバイス ユーザーは次の方法を実行できます。

- SIP **デバイスでサイン** アウトを押し、デバイスで説明されている手順に従います。 

管理センターでデバイスをTeamsするには:

1. 管理センター [**にログインTeamsします**](https://admin.teams.microsoft.com)。

2. [デバイス **TEAMS SIP デバイス]**  >  **を選択します**。

3. 右側の [SIP デバイス] **ウィンドウで** 、デバイスを選択します。

4. デバイスの [詳細]**ウィンドウで**、[詳細] タブを選択し、[操作]メニューの右上にある [サインアウト]**を選択します**。 


## <a name="view-and-monitor-sip-devices"></a>SIP デバイスの表示と監視

デバイスのユーザーが少なくとも 1 回サインインした後、Teams センターで SIP デバイスのインベントリを表示および監視できます。 次の操作を実行してください。

1. 管理センター[にログインTeamsします](https://admin.teams.microsoft.com/)。

2. [デバイス **TEAMS SIP デバイス]**  >  **を選択します**。 サインインしている SIP デバイスはすべて右側に表示されます。

## <a name="restart-a-sip-device"></a>SIP デバイスを再起動する

1. 管理センター[にログインTeamsします](https://admin.teams.microsoft.com)。

2. [デバイス **TEAMS SIP デバイス]**  >  **を選択します**。 

3. 右側で、再起動する SIP デバイスを選択し、[再起動] を **選択します**。

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>ポリシーの変更を SIP デバイスに同期してポリシーを適用する

ユーザーの詳細とポリシーは、ユーザーがサインインするときに SIP デバイスにフェッチされます。 その後、サインインしているユーザーに対するポリシーの変更は、1 時間以内にデバイスに同期されます。 デバイスは、SIP ゲートウェイで登録を定期的に更新する必要があります。 SIP 電話はコール リダイレクトに依存します。そのため、管理者は 属性を に `AllowCallRedirect` 設定する必要 `Set-CsTeamsCallingPolicy` があります `Enabled` 。


## <a name="set-a-sip-devices-ui-language"></a>SIP デバイスの UI 言語を設定する

SIP デバイスは通常、多くの言語で情報を表示できます。 UI 言語を設定すると、ソフトキーやサインイン/サインアウト システム メッセージなど、インターフェイスに影響します。 UI 言語の設定は、プロビジョニング サーバーで DHCP サーバーを使用するか、次の例のように URL にコード文字列を追加して手動で行います。

Polycom、AudioCodes、Yealink 電話にドイツ語を設定する方法:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Cisco 電話に日本語を設定する方法:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>サポートされている言語

|言語名|言語コード]
|-------------|-------------|
|英語 (既定値)|en       |
|スペイン語      |es           |
|日本語     |ja           |
|ドイツ語       |de           |
|フランス語       |fr           |
|ポルトガル語   |pt           |

> [!Note]
> - 日本語は Yealink ではサポートされていません。Polycom VVX では部分的にサポートされています。
> - 選択した言語が SIP エンドポイントでサポートされていない場合、システムの既定値は英語です。
> - プロビジョニング URL **lang_xx** パラメーターが設定されていない場合は、既定の言語として英語が使用されます。
> - 緊急 **通話** のテキストが他の言語に翻訳されていない場合、スクリーン サイズの制限により、次の IP 電話モデルの [サインイン]に英語の省略版だけが表示されます。
>   - Poly VVX 150、VVX 201
>   - Cisco CP-6821、CP-7811、CP-7821、CP-7841、CP-7861
>   - ボイス メール ソフトキー ラベルは、文字列の長さが制限されたため、Poly VVX のすべての言語で **VM** テキストでハードコーディングされます。

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams IPv6

SIP ゲートウェイは IPv4 のみをサポートします。 Microsoft Teamsクライアントは、IPv4 と IPv6 の両方をサポートします。 グループへの通信を制御する場合Microsoft Teams URL と IP アドレス範囲で IP [Microsoft 365を使用します](/microsoft-365/enterprise/urls-and-ip-address-ranges)。

## <a name="emergency-calling"></a>緊急通話

SIP ゲートウェイは、静的 (登録済みとも呼ばれる) の緊急対応アドレスのみをサポートします。 現時点では、登録済みのアドレスは、直接ルーティングシナリオではサポートされていません。 緊急通話の詳細については、「緊急通話の計画と [管理」を参照してください](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)。

## <a name="report-problems-to-microsoft"></a>Microsoft に問題を報告する

問題を報告するには、Microsoft サポート にお [問い合わせください](https://support.microsoft.com)。
