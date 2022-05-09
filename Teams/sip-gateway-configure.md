---
title: SIP ゲートウェイを構成する
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
ms.openlocfilehash: 4b94251de11c302c18f7de725c76cfaaaa8b8f76
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774166"
---
# <a name="configure-sip-gateway"></a>SIP ゲートウェイを構成する

この記事では、組織がMicrosoft Teamsと互換性のある SIP デバイスを使用できるように SIP ゲートウェイを構成する方法について説明します。 組織に対して実行できる SIP ゲートウェイと、組織に必要なハードウェア、ソフトウェア、ライセンスについては、「 [SIP ゲートウェイの計画](sip-gateway-plan.md)」を参照してください。

SIP ゲートウェイを構成する前に、次の操作を行います。

- **SIP デバイスを出荷時の既定の設定にリセットします。** 自分または組織のユーザーは、SIP ゲートウェイで使用される各 SIP デバイスを工場出荷時の既定の設定にリセットする必要があります。 その方法については、製造元の手順を参照してください。

- **ファイアウォールを開いてMicrosoft 365してTeamsします。** Office 365 URL と IP アドレス範囲の説明に従って、ネットワークのファイアウォールを開いてトラフィック[をMicrosoft 365してTeamsします](/microsoft-365/enterprise/urls-and-ip-address-ranges)。

- **SIP デバイスがプロキシの背後にないことを確認します。** http/s トラフィックが企業の http/s プロキシをバイパスすることを確認します。

- **UDP ポートを開きます。** IP 範囲 52.112.0.0/14 から 52.120.0.0/14 の範囲 49152 から 53247 の UDP ポートを開きます。

- **TCP ポートを開きます。** IP 範囲 52.112.0.0/14 から 52.120.0.0/14 の TCP ポート 5061 を開きます。

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

- [組織で SIP ゲートウェイを使用できることを確認します](#verify-that-sip-gateway-is-available-for-your-organization)。

- [組織内のユーザーに対して SIP ゲートウェイを有効にします](#enable-sip-gateway-for-the-users-in-your-organization)。

- [SIP Gateway プロビジョニング サーバーの URL を設定します](#set-the-sip-gateway-provisioning-server-url)。

この記事では、次の方法についても説明します。

- [便宜上、SIP デバイスを個別に登録するか、バッチで登録します](#provision-and-enroll-sip-devices-as-common-area-phones)。  


- [SIP デバイスを表示および監視します。](#view-and-monitor-sip-devices)

- [多言語ユーザー インターフェイスのサポートを有効にします。](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>組織で SIP ゲートウェイを使用できることを確認する

1. [Teams管理センター](https://admin.teams.microsoft.com/)にサインインします。

2. 左側で **[Teams デバイス**] を選択し、[**SIP デバイス**] タブが表示されているかどうかを確認します。 その場合は、組織に対して SIP ゲートウェイ サービスが有効になります。

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>組織内のユーザーに対して SIP ゲートウェイを有効にする

組織の SIP ゲートウェイを有効にするには、Teams管理センターを使用するか、PowerShell コマンドレットを使用するかの 2 つの方法があります。

### <a name="by-using-teams-admin-center"></a>Teams管理センターを使用する

Teams管理センターで SIP ゲートウェイを有効にするには、次の手順に従います。

1. [Teams管理センター](https://admin.teams.microsoft.com/)に移動する

2. 左側の [ **音声**] で、[ **通話ポリシー**] を選択します。

3. [ **ポリシーの管理**] の右側で、ユーザーに割り当てられている適切な通話ポリシーを選択するか、必要に応じて新しい通話ポリシーを作成し、必要なユーザーに割り当てます。

4. [ **ポリシーの管理**] を選択し、ポリシーを選択して、[ **編集]** を選択します。

5. **通話に使用できる SIP デバイスの設定を** オンにし、[保存] を選択 **します**。


### <a name="by-using-powershell"></a>PowerShell を使用して

PowerShell [Set-CsTeamsCallingPolicy コマンドレットを](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps) 使用して SIP ゲートウェイを有効にすることもできます。 SIP デバイスのユーザーを有効にするには、ポリシーを選択し、属性`True`を `-AllowSIPDevicesCalling` [ . 既定値は 、ユーザーが `False`SIP デバイスを有効にしない限り使用できないようにするためです。


> [!NOTE]
> - ポリシーの伝達には最大 24 時間かかる場合があります。

## <a name="set-the-sip-gateway-provisioning-server-url"></a>SIP Gateway プロビジョニング サーバーの URL を設定する

動的ホスト構成プロトコル (DHCP) サーバーで SIP ゲートウェイ プロビジョニング サーバーの URL を設定できます。 リモートで作業するユーザーは、手動で構成する必要があります。

### <a name="using-dhcp"></a>DHCP の使用

SIP デバイスごとに、次のいずれかの SIP ゲートウェイ プロビジョニング サーバー URL を設定します。 

- EMEA： `http://emea.ipp.sdg.teams.microsoft.com`
- アメリカ： `http://noam.ipp.sdg.teams.microsoft.com`
- APAC： `http://apac.ipp.sdg.teams.microsoft.com`

上記の SIP ゲートウェイ プロビジョニング サーバー URL を DHCP サーバーで構成して、Teams組織に SIP デバイスを追加します。 DHCP サーバーの詳細については、「 [DHCP のデプロイと管理](/learn/modules/deploy-manage-dynamic-host-configuration-protocol)」を参照してください。 また、DHCP オプション 42 を使用してネットワーク タイム プロトコル (NTP) サーバーを指定し、DHCP オプション 2 を使用して協定世界時 (UTC) からのオフセットを秒単位で指定することもできます。 組織内のデバイスは、SIP ゲートウェイ プロビジョニング サーバーにルーティングされます。 正常にプロビジョニングされた SIP 電話には、Teamsロゴとサインイン用のソフト ボタンが表示されます。

SIP デバイスが、オンボードでサポートされているファームウェアの最小バージョンであることを確認します。 オンボード中、SIP Gateway は既定の構成と認証のユーザー インターフェイスをデバイスにプッシュします。 SIP デバイスに必要なファームウェアバージョンについては、「 [SIP ゲートウェイの計画](sip-gateway-plan.md)」を参照してください。

### <a name="manually"></a>手動

リモートで作業するユーザーは、次の手順を使用して、SIP デバイスへのプロビジョニング サーバー URL を手動で構成する必要があります。

1. デバイス **で設定** を開き、デバイスの IP アドレスを取得します。

2. ブラウザー ウィンドウを開き、デバイスの IP アドレスを入力し、(必要に応じて) ログインし、デバイスの Web ユーティリティでプロビジョニング サーバーの URL を構成します。

3. Web ユーティリティ **の [設定****] または [詳細設定]** で、上に示したプロビジョニング サーバーの URL を入力します。

> [!NOTE]
> - 互換性のある SIP デバイスのみを SIP ゲートウェイにオンボードできます。 
> - Cisco IP Phone は、オンボードする前にマルチプラットフォーム ファームウェアにフラッシュする必要があります。 方法については、 [Cisco ファームウェア変換ガイド](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)を参照してください。
> - Yealink スマートフォンの場合は、オプション 66 を使用します。
> - Cisco、Poly、AudioCode の電話の場合は、オプション 160 を使用します。 
> - Cisco デバイスの場合は、プロビジョニング サーバー URL に **/$PSN.xml** を追加します。


## <a name="configure-conditional-access"></a>条件付きアクセスを構成する

条件付きアクセスは、Microsoft 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されるようにするのに役立つAzure Active Directory (Azure AD) 機能です。 SIP ゲートウェイはAzure ADで SIP デバイスを認証するため、組織が企業ネットワーク内のデバイスに条件付きアクセスを使用する場合は、次の IP アドレスを除外する必要があります。

- 北米:
    - 米国東部: 52.170.38.140
    - 米国西部: 40.112.144.212
-   EMEA リージョン:
    - 北 EU: 40.112.71.149
    - 西 EU: 40.113.112.67
-   APAC リージョン:
    - オーストラリア東部: 20.92.120.71
    - オーストラリア南東部: 13.73.115.90

詳細については、「 [IP アドレス範囲](/azure/active-directory/conditional-access/location-condition#ip-address-ranges)」を参照してください。


## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>共通領域の電話として SIP デバイスをプロビジョニングして登録する
> [!NOTE]
> SIP デバイスを登録する前に、SIP ゲートウェイにオンボードする必要があります。

タスクを効率化するために、TEAMS管理センターに SIP デバイスを一度に 1 つずつ、またはバッチで登録できます。 次の操作を実行してください。

1. [**Teams管理センター**](https://admin.teams.microsoft.com)にログインします。

2. **Teams devicesSIP** >  **デバイスを選択します**。

3. 右上で **ActionsProvision デバイス****を** > 選択し、次のいずれかの手順に従います。

  - **1 つのデバイスをプロビジョニングするには:**

     a. **[アクティブ化の待機中] で**、[追加] を選択 **します**。

     b. [ **MAC アドレスの追加]** ウィンドウで、デバイスの **MAC アドレス** と **場所** を入力し、[ **適用**] を選択します。
     
     c. [ **アクティブ化を待機中] で**、追加したデバイスを選択し、[ **確認コードの生成**] を選択します。
     
     d. [ **デバイスのプロビジョニング** ] ウィンドウの [ **確認コード**] で、SIP デバイスの確認コードをメモします。

   - **多くのデバイスをプロビジョニングするには:**

     a. **[アクティブ化を待機中**] の右側にある [**エクスポート**] (Microsoft Excel アイコン) を選択します。
     
     b. [**デバイスのプロビジョニング**] ウィンドウの [**複数の MAC アドレスアップロード**] で、**テンプレートのダウンロードを選択します**。
     
     c. **Template_Provisioning.csv** をコンピューターに保存し、**MAC ID** フィールドと **[場所]** フィールドに入力します。
    
     d. [**デバイスのプロビジョニング**] ウィンドウで、**複数の MAC アドレスアップロード** 選択します。 

     E。 **[アップロード MAC アドレス**] ウィンドウの右側にある [**ファイルの選択**] を選択し、データを含む **Template_Provisioning.csv** ファイルを選択します。

     F。 [ **デバイスのプロビジョニング** ] ウィンドウの [ **アクティブ化待ち**] でデバイスを選択し、[ **確認コードの生成** ] を選択して、プロビジョニングされた各デバイスの 1 回限りの検証コードを生成します。 各 SIP デバイスの確認コードに注意してください。

4. SIP デバイスで、登録機能コードに続いて確認コードをダイヤルします。 SIP デバイスで、登録機能コード \*55* (登録 1 回限りの検証コードの検証に SIP ゲートウェイで使用) にダイヤルし、その後、この特定のデバイスの管理センターで生成された確認コードTeamsダイヤルします。 たとえば、確認コードが123456されている場合は、55\* 123456をダイヤル\*してデバイスを登録します。

5.  [ **デバイスのプロビジョニング** ] ウィンドウの [ **サインイン待ち] で**、[ **サインアウト**] を選択します。

6. [ **ユーザーのサインイン** ] ダイアログで、SIP デバイスのペアリング コードをコピーまたはメモします。

7. に [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)移動し、[ **コードの入力**] で SIP デバイスのペアリング コードを入力し、[ **次へ**] を選択します。

8. Microsoft **サインイン** ページの [ **電子メールまたは電話** ] フィールドに、SIP デバイスの電子メール アドレスを入力し、[ **次へ**] を選択します。

9. [ **パスワード** ] ページで、SIP デバイスの電子メール アドレスのパスワードを入力し、[ **サインイン**] を選択します。

10. [**Teams SIP デバイス ゲートウェイにサインインしようとしています** か] ページで、[**続行**] を選択します。

## <a name="how-to-sign-in-and-sign-out"></a>サインインしてサインアウトする方法

ユーザーの個人用デバイスでは、ローカル サインインのみがサポートされます。 管理センターからデバイスをサインアウトするには、次の手順に従います。

1. [**Teams管理センター**](https://admin.teams.microsoft.com)にログインします。

2. **Teams devicesSIP** >  **デバイスを選択します**。

3. 右側で SIP デバイスを選択し、[ **サインアウト**] を選択します。


### <a name="user-pairing-and-sign-in"></a>ユーザーのペアリングとサインイン

ユーザーが企業の資格情報を使用して認証した後に SIP デバイスをペアリングするには、ユーザーが次の操作を行う必要があります。

1. SIP Phone **でサインイン** を押して、認証 URL とペアリング コードを表示します。 ペアリング コードは時間に依存します。 有効期限が切れた場合、ユーザーは電話で **Back** キーを押し、サインイン プロセスをもう一度開始する必要があります。

2. ユーザーのデスクトップまたはモバイル ブラウザーの認証 URL に移動し、企業の資格情報を使用してログインします。

3. SIP 電話に表示されているペアリング コードを Web 認証アプリに入力して、SIP 電話とユーザーのアカウントをペアリングします。 サインインに成功すると、デバイスでサポートされている場合は、SIP 電話に電話番号とユーザー名が表示されます。

> [!NOTE]
> Azure Active Directory Web 認証アプリに表示されるデバイスの場所は、デバイスが接続されている SIP ゲートウェイ データセンターです。 スコープ内の SIP 電話は OAuth 対応ではないため、SIP Gateway は Web 認証アプリを使用してユーザーを認証し、デバイスをユーザーの資格情報とペアリングします。 詳細については、[Microsoft ID プラットフォームと OAuth 2.0 デバイス承認付与フローを](/azure/active-directory/develop/v2-oauth2-device-code)参照してください。

### <a name="sign-out"></a>サインアウト

サインアウトするには、デバイス ユーザーは次の操作を行うことができます。

- SIP デバイス **でサインアウト** を押し、デバイスで説明されている手順に従います。 

Teams管理センターでデバイスをサインアウトするには:

1. [**Teams管理センター**](https://admin.teams.microsoft.com)にログインします。

2. **Teams devicesSIP** >  **デバイスを選択します**。

3. 右側の **[SIP デバイス** ] ウィンドウで、デバイスを選択します。

4. デバイスの **[詳細] ウィンドウで** [ **詳細** ] タブを選択し、[ **操作]** メニューの右上にある [ **サインアウト**] を選択します。 


## <a name="view-and-monitor-sip-devices"></a>SIP デバイスの表示と監視

デバイスのユーザーが少なくとも 1 回サインインした後、Teams管理センターで SIP デバイス インベントリを表示および監視できます。 次の操作を実行してください。

1. [Teams管理センター](https://admin.teams.microsoft.com/)にログインします。

2. **Teams devicesSIP** >  **デバイスを選択します**。 サインインしているすべての SIP デバイスが右側に一覧表示されます。

## <a name="restart-a-sip-device"></a>SIP デバイスを再起動する

1. [Teams管理センター](https://admin.teams.microsoft.com)にログインします。

2. **Teams devicesSIP** >  **デバイスを選択します**。 

3. 右側で、再起動する SIP デバイスを選択し、[再起動] を選択 **します**。

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>ポリシーの変更を SIP デバイスに同期してポリシーを適用する

ユーザーがサインインすると、ユーザーの詳細とポリシーが SIP デバイスにフェッチされます。 その後、サインインしているユーザーに対するポリシーの変更は、1 時間以内にデバイスに同期されます。 デバイスは、SIP ゲートウェイで定期的に登録を更新する必要があります。 SIP 電話は呼び出しリダイレクトに依存するため、管理者は属性`Set-CsTeamsCallingPolicy``Enabled`を `AllowCallRedirect` .


## <a name="set-a-sip-devices-ui-language"></a>SIP デバイスの UI 言語を設定する

SIP デバイスは通常、多くの言語で情報を表示できます。 UI 言語を設定すると、ソフトキーやサインイン/サインアウト システム メッセージなど、インターフェイスに影響します。 UI 言語の設定は、次の例のように、プロビジョニング サーバー、DHCP サーバーを使用するか、URL にコード文字列を追加することによって手動で行われます。

Polycom、AudioCodes、Yealink 電話用にドイツ語を設定する方法:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Cisco Phone の日本語を設定する方法:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>サポートされている言語

|言語名|[言語コード]
|-------------|-------------|
|英語 (既定値)|Ja       |
|スペイン語      |Es           |
|日本語     |ja           |
|ドイツ語       |デ           |
|フランス語       |神父           |
|ポルトガル語   |Pt           |

> [!Note]
> - 日本語は Yealink ではサポートされておらず、Polycom VVX では部分的にサポートされています。
> - 選択した言語が SIP エンドポイントでサポートされていない場合、システムの既定値は英語になります。
> - **lang_xx** パラメーターがプロビジョニング URL で設定されていない場合は、英語が既定の言語として使用されます。
> - **緊急通報テキストを作成するためのサインイン** が他の言語に翻訳されていない場合、スクリーンサイズの制限により、次の IP 電話モデルの **サインインを押** すと、英語のみの省略版が表示されます。
>   - Poly VVX 150、VVX 201
>   - Cisco CP-6821、CP-7811、CP-7821、CP-7841、CP-7861
>   - ボイス メール ソフトキー ラベルは、文字列の長さの制限のため、Poly VVX のすべての言語で **VM** テキストでハードコーディングされます。

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teamsと IPv6

SIP ゲートウェイでは、IPv4 のみがサポートされます。 Microsoft Teamsサービスとクライアントは、IPv4 と IPv6 の両方をサポートしています。 Microsoft Teamsへの通信を制御する場合は、[Microsoft 365 URL と IP アドレス範囲の IP アドレス範囲を使用します](/microsoft-365/enterprise/urls-and-ip-address-ranges)。

## <a name="emergency-calling"></a>緊急通話

SIP ゲートウェイでは、静的な緊急アドレス (登録済みとも呼ばれます) のみがサポートされます。 現在、登録済みのアドレスは、ダイレクト ルーティングのシナリオではサポートされていません。 緊急通報の詳細については、「緊急通報の [計画と管理](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)」を参照してください。

## <a name="report-problems-to-microsoft"></a>Microsoft に問題を報告する

問題を報告するには、[Microsoft サポートにお](https://support.microsoft.com)問い合わせください。
