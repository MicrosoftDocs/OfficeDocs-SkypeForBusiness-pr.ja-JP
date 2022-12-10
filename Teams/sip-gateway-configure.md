---
title: SIP ゲートウェイの構成
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/8/2022
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
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
ms.openlocfilehash: c93aec7cb65cdd40c05a540b51a3da8ba268c7e9
ms.sourcegitcommit: feb9b7d10e38f5a629ee9202b5aaec5beef4de9b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2022
ms.locfileid: "69343294"
---
# <a name="configure-sip-gateway"></a>SIP ゲートウェイの構成

この記事では、組織が Microsoft Teams で互換性のある SIP デバイスを使用できるように SIP ゲートウェイを構成する方法について説明します。 組織に対して SIP ゲートウェイが実行できる内容と、組織に必要なハードウェア、ソフトウェア、ライセンスについては、「 [SIP ゲートウェイの計画」](sip-gateway-plan.md)を参照してください。

SIP ゲートウェイを構成する前に、次の操作を行います。

- **SIP デバイスを出荷時の既定の設定にリセットします。** ユーザーまたは組織のユーザーは、SIP ゲートウェイで使用される各 SIP デバイスを出荷時の既定の設定にリセットする必要があります。 その方法については、製造元の手順を参照してください。

- **ファイアウォールを開き、365 と Teams をMicrosoftします。** 「[OFFICE 365 URL と IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges)」で説明されているように、ネットワークのファイアウォールを開いて 365 と Teams のトラフィックをMicrosoftします。 ファイアウォール規則は、送信トラフィックにのみ必要です。

- **SIP デバイスがプロキシの背後にないことを確認します。** http/s トラフィックが企業の http/s プロキシをバイパスすることを確認します。

- **UDP ポートを開きます。** IP 範囲 52.112.0.0/14 および 52.122.0.0/15 の範囲 49152 から 53247 の UDP ポートを開きます。

- **TCP ポートを開きます。** IP 範囲 52.112.0.0/14 および 52.122.0.0/15 の TCP ポート 5061 を開きます。

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


次のセクションでは、SIP ゲートウェイを構成するために管理者として実行する必要がある操作について説明します。

- [SIP ゲートウェイが組織で使用可能であることを確認します](#verify-that-sip-gateway-is-available-for-your-organization)。

- [組織内のユーザーに対して SIP ゲートウェイを有効にします](#enable-sip-gateway-for-the-users-in-your-organization)。

- [SIP ゲートウェイ プロビジョニング サーバー URL を設定します](#set-the-sip-gateway-provisioning-server-url)。

この記事では、次の方法についても説明します。

- [便宜上、SIP デバイスを個別またはバッチで登録します](#provision-and-enroll-sip-devices-as-common-area-phones)。  

- [SIP デバイスを表示および監視します。](#view-and-monitor-sip-devices)

- [多言語ユーザー インターフェイスのサポートを有効にします。](#set-a-sip-devices-ui-language)

## <a name="verify-that-sip-gateway-is-available-for-your-organization"></a>組織で SIP ゲートウェイが使用可能であることを確認する

1. [Teams 管理センター](https://admin.teams.microsoft.com/)にサインインします。

2. 左側の [ **Teams デバイス** ] を選択し、[ **SIP デバイス** ] タブが表示されているかどうかを確認します。 その場合は、組織で SIP ゲートウェイ サービスが有効になります。

## <a name="enable-sip-gateway-for-the-users-in-your-organization"></a>組織内のユーザーに対して SIP ゲートウェイを有効にする

組織に対して SIP ゲートウェイを有効にするには、Teams 管理センターを使用するか、PowerShell コマンドレットを使用します。

### <a name="by-using-teams-admin-center"></a>Teams 管理センターを使用する

Teams 管理センターで SIP ゲートウェイを有効にするには、次の手順に従います。

1. [Teams 管理センター](https://admin.teams.microsoft.com/)に移動する

2. 左側の [ **音声**] で、[ **通話ポリシー**] を選択します。

3. [ **ポリシーの管理**] の右側で、ユーザーに割り当てられている適切な通話ポリシーを選択するか、必要に応じて新しい通話ポリシーを作成し、必要なユーザーに割り当てます。

4. [ **ポリシーの管理**] を選択し、ポリシーを選択し、[編集] を選択 **します**。

5. **通話に使用できる SIP デバイス** の設定をオンにし、[保存] を選択 **します**。


### <a name="by-using-powershell"></a>PowerShell を使用する

PowerShell [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy) コマンドレットを使用して SIP ゲートウェイを有効にすることもできます。 SIP デバイスのユーザーを有効にするには、ポリシーを選択し、 属性を に`True`設定します`-AllowSIPDevicesCalling`。 既定値は です `False`。そのため、有効にしない限り、ユーザーは SIP デバイスを使用できません。

> [!NOTE]
> - ポリシーの伝達には最大 24 時間かかることがあります。

## <a name="set-the-sip-gateway-provisioning-server-url"></a>SIP ゲートウェイ プロビジョニング サーバーの URL を設定する

SIP ゲートウェイ プロビジョニング サーバーの URL は、動的ホスト構成プロトコル (DHCP) サーバーで設定できます。 リモートで作業するユーザーは、手動で構成する必要があります。

### <a name="using-dhcp"></a>DHCP の使用

SIP デバイスごとに、次のいずれかの SIP ゲートウェイ プロビジョニング サーバー URL を設定します。 

- Emea： `http://emea.ipp.sdg.teams.microsoft.com`
- アメリカ： `http://noam.ipp.sdg.teams.microsoft.com`
- Apac： `http://apac.ipp.sdg.teams.microsoft.com`

DHCP サーバーで上記の SIP ゲートウェイ プロビジョニング サーバー URL を構成して、TEAMS 組織に SIP デバイスを追加します。 DHCP サーバーの詳細については、「DHCP の [展開と管理](/training/modules/deploy-manage-dynamic-host-configuration-protocol)」を参照してください。 また、DHCP オプション 42 を使用してネットワーク タイム プロトコル (NTP) サーバーを指定し、DHCP オプション 2 を使用して協定世界時 (UTC) からのオフセットを秒単位で指定できます。 組織内のデバイスは、SIP ゲートウェイ プロビジョニング サーバーにルーティングされます。 正常にプロビジョニングされた SIP 電話には、Teams ロゴとサインイン用のソフト ボタンが表示されます。

SIP デバイスがオンボードでサポートされている最小ファームウェア バージョンにあることを確認します。 オンボード中、SIP ゲートウェイは既定の構成と認証ユーザー インターフェイスをデバイスにプッシュします。 SIP デバイスに必要なファームウェア バージョンを確認するには、「 [SIP ゲートウェイの計画](sip-gateway-plan.md)」を参照してください。

### <a name="manually"></a>手動

リモートで作業するユーザーは、次の手順を使用して、プロビジョニング サーバー URL を SIP デバイスに手動で構成する必要があります。

1. デバイスで **[設定] を** 開き、デバイスの IP アドレスを取得します。

2. ブラウザー ウィンドウを開き、デバイスの IP アドレスを入力し、必要に応じてログインし、デバイスの Web ユーティリティでプロビジョニング サーバーの URL を構成します。

3. [ **設定]** または [Web ユーティリティの **詳細設定]** で、上記のプロビジョニング サーバー URL を入力します。

> [!NOTE]
> - SIP ゲートウェイにオンボードできるのは、互換性のある SIP デバイスのみです。 
> - Cisco IP フォンは、オンボードする前にマルチプラットフォーム ファームウェアにフラッシュする必要があります。 方法については、「 [Cisco ファームウェア変換ガイド](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)」を参照してください。
> - Yealink 電話の場合は、オプション 66 を使用します。
> - Cisco、Poly、AudioCode フォンの場合は、オプション 160 を使用します。 
> - Cisco デバイスの場合は、プロビジョニング サーバー URL に **/$PSN.xml** を追加します。


## <a name="configure-conditional-access"></a>条件付きアクセスを構成する

条件付きアクセスは、Microsoft 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されていることを確認するのに役立つ Azure Active Directory (Azure AD) 機能です。 SIP ゲートウェイは Azure AD で SIP デバイスを認証するため、組織が企業ネットワーク内のデバイスに条件付きアクセスを使用する場合は、次の IP アドレスを除外する必要があります。

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

## <a name="provision-and-enroll-sip-devices-as-common-area-phones"></a>SIP デバイスを共通エリア電話としてプロビジョニングおよび登録する

> [!NOTE]
> SIP デバイスを登録するには、SIP ゲートウェイにオンボードする必要があります。

タスクを効率化するために、SIP デバイスを Teams 管理センターに一度に 1 つずつ、またはバッチで登録できます。 次の操作を実行してください。

1. [**Teams 管理センター**](https://admin.teams.microsoft.com)にログインします。

2. **[Teams デバイス****] [SIP デバイス** > ] の順に選択します。

3. 右上にある [**アクション]**[**デバイスのプロビジョニング**]  >  の順に選択し、次のいずれかの手順に従います。

  - **1 つのデバイスをプロビジョニングするには:**

     a. [ **アクティブ化の待機** 中] で、[追加] を選択 **します**。

     b. [ **MAC アドレスの追加** ] ウィンドウで、デバイスの **MAC アドレス** と **場所** を入力し、[ **適用**] を選択します。
     
     c. [ **アクティブ化の待機** 中] で、追加したデバイスを選択し、[ **確認コードの生成**] を選択します。
     
     d. [ **デバイスのプロビジョニング** ] ウィンドウの [ **確認コード**] で、SIP デバイスの検証コードをメモします。

   - **多くのデバイスをプロビジョニングするには:**

     a. [**アクティブ化の待機** 中] で、右側の [**エクスポート**] (Microsoft Excel アイコン) を選択します。
     
     b. [ **デバイスのプロビジョニング** ] ウィンドウの [ **複数の MAC アドレスのアップロード**] で、[ **テンプレートのダウンロード**] を選択します。
     
     c. **Template_Provisioning.csv** をコンピューターに保存し、[**MAC ID**] フィールドと [**場所**] フィールドを入力します。
    
     d. [ **デバイスのプロビジョニング** ] ウィンドウで、[ **複数の MAC アドレスのアップロード**] を選択します。 

     E。 [ **MAC アドレスのアップロード** ] ウィンドウの右側にある [ **ファイルの選択**] を選択し、データを含む **Template_Provisioning.csv** ファイルを選択します。

     F。 [ **デバイスのプロビジョニング** ] ウィンドウ **の [アクティブ化の待機** 中] で、デバイスを選択し、[ **検証コードの生成** ] を選択して、プロビジョニングされたデバイスごとに 1 回限りの検証コードを生成します。 各 SIP デバイスの検証コードに注意してください。

4. SIP デバイスで、登録機能コードに続けて確認コードをダイヤルします。 SIP デバイスで、登録機能コード 55* (登録 1 回限りの検証コード\*検証に SIP ゲートウェイで使用) にダイヤルし、その後、この特定のデバイスの Teams 管理 Center で生成された検証コードをダイヤルします。 たとえば、確認コードが123456されている場合は、55\*123456にダイヤル\*してデバイスを登録します。

5.  [ **デバイスのプロビジョニング** ] ウィンドウの [ **サインイン待ち] で**、[ **サインアウト**] を選択します。

6. [ **ユーザーのサインイン** ] ダイアログで、SIP デバイスのペアリング コードをコピーまたはメモします。

7. に [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin)移動し、[ **コードの入力**] で SIP デバイスのペアリング コードを入力し、[ **次へ**] を選択します。

8. [サインインのMicrosoft] ページ **の** **[Emailまたは電話**] フィールドに SIP デバイスのメール アドレスを入力し、[**次へ**] を選択します。

9. [ **パスワード** ] ページで、SIP デバイスのメール アドレスのパスワードを入力し、[ **サインイン**] を選択します。

10. [ **Teams SIP デバイス ゲートウェイにサインインしようとしています** か] ページで、[続行] を選択 **します**。

## <a name="how-to-sign-in-and-sign-out"></a>サインインしてサインアウトする方法

ユーザーの個人用デバイスでは、ローカル サインインのみがサポートされています。 管理 センターからデバイスをサインアウトするには、次の手順に従います。

1. [**Teams 管理センター**](https://admin.teams.microsoft.com)にログインします。

2. **[Teams デバイス****] [SIP デバイス** > ] の順に選択します。

3. 右側で SIP デバイスを選択し、[ **サインアウト**] を選択します。


### <a name="user-pairing-and-sign-in"></a>ユーザーのペアリングとサインイン

ユーザーが企業の資格情報を使用して認証した後で SIP デバイスをペアリングするには、ユーザーは次の手順を実行する必要があります。

1. SIP 電話 **で [サインイン** ] を押して、認証 URL とペアリング コードを表示します。 ペアリング コードは時間の影響を受けます。 有効期限が切れた場合、ユーザーは電話で **[戻る** ] を押し、サインイン プロセスをもう一度開始する必要があります。

2. ユーザーのデスクトップまたはモバイル ブラウザーの認証 URL に移動し、企業の資格情報を使用してログインします。

3. SIP 電話に表示されるペアリング コードを Web 認証アプリに入力して、SIP 電話をユーザーのアカウントとペアリングします。 サインインが成功すると、しばらく時間がかかる場合があります。デバイスでサポートされている場合は、SIP 電話に電話番号とユーザー名が表示されます。

> [!NOTE]
> Azure Active Directory Web 認証アプリに表示されるデバイスの場所は、デバイスが接続されている SIP ゲートウェイ データセンターです。 スコープ内の SIP 電話は OAuth 対応ではないため、SIP ゲートウェイは Web 認証アプリを介してユーザーを認証し、デバイスをユーザーの資格情報とペアリングします。 詳細については、[Microsoft ID プラットフォームと OAuth 2.0 デバイス承認付与フロー](/azure/active-directory/develop/v2-oauth2-device-code)を参照してください。

### <a name="sign-out"></a>サインアウト

サインアウトするには、デバイス ユーザーは次のことができます。

- SIP デバイス **でサインアウト** を押し、デバイスで説明されている手順に従います。 

Teams 管理センターでデバイスをサインアウトするには:

1. [**Teams 管理センター**](https://admin.teams.microsoft.com)にログインします。

2. **[Teams デバイス****] [SIP デバイス** > ] の順に選択します。

3. 右側の **[SIP デバイス** ] ウィンドウで、デバイスを選択します。

4. デバイスの **[詳細] ウィンドウで** [ **詳細** ] タブを選択し、[ **アクション]** メニューの右上にある [ **サインアウト**] を選択します。 

## <a name="view-and-monitor-sip-devices"></a>SIP デバイスの表示と監視

デバイスのユーザーが少なくとも 1 回サインインした後、Teams 管理センターで SIP デバイス インベントリを表示および監視できます。 次の操作を実行してください。

1. [Teams 管理センター](https://admin.teams.microsoft.com/)にログインします。

2. **[Teams デバイス****] [SIP デバイス** > ] の順に選択します。 右側には、すべてのサインイン SIP デバイスが一覧表示されます。

## <a name="restart-a-sip-device"></a>SIP デバイスを再起動する

1. [Teams 管理センター](https://admin.teams.microsoft.com)にログインします。

2. **[Teams デバイス****] [SIP デバイス** > ] の順に選択します。 

3. 右側で、再起動する SIP デバイスを選択し、[再起動] を選択 **します**。


> [!NOTE]
> - 現在、テナントから SIP デバイスを削除することは、Teams 管理センターでは使用できません。 
> - コマンドの実行はデバイスの可用性によって異なり、Teams 管理センターに表示される実行状態と一致しない場合があります。 サポートされていないデバイスで SIP ゲートウェイを有効にしようとすると、コマンドは実行されません。

## <a name="sync-policy-changes-to-sip-devices-to-enforce-policies"></a>ポリシーを適用するためにポリシーの変更を SIP デバイスに同期する

ユーザーがサインインすると、ユーザーの詳細とポリシーが SIP デバイスにフェッチされます。 サインインしたユーザーに対するその後のポリシーの変更は、1 時間以内にデバイスに同期されます。 デバイスは、SIP ゲートウェイで定期的に登録を更新する必要があります。 SIP 電話はコール リダイレクトに依存するため、管理者は に属性を `AllowCallRedirect` 設定する`Enabled`必要`Set-CsTeamsCallingPolicy`があります。


## <a name="set-a-sip-devices-ui-language"></a>SIP デバイスの UI 言語を設定する

SIP デバイスは通常、多くの言語で情報を表示できます。 UI 言語の設定は、ソフトキーやサインイン/サインアウト システム メッセージなど、インターフェイスに影響します。 UI 言語の設定は、次の例のように、プロビジョニング サーバー、DHCP サーバー、または URL にコード文字列を追加して手動で行います。

Polycom、AudioCodes、Yealink 電話にドイツ語を設定する方法:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_de`

Cisco 電話に日本語を設定する方法:
- `http://emea.ipp.sdg.teams.microsoft.com/lang_ja/$PSN.xml` 


### <a name="supported-languages"></a>サポートされている言語

|言語名|言語コード]
|-------------|-------------|
|英語 (既定値)|Ja       |
|スペイン語      |Es           |
|日本語     |ja           |
|ドイツ語       |デ           |
|フランス語       |神父           |
|ポルトガル語   |Pt           |

> [!Note]
> - 日本語は Yealink ではサポートされておらず、Polycom VVX では部分的にサポートされています。
> - 選択した言語が SIP エンドポイントでサポートされていない場合、システムは既定で英語になります。
> - プロビジョニング URL を使用して **lang_xx** パラメーターが設定されていない場合は、既定の言語として英語が使用されます。
> - **緊急通報テキストを作成するためのサインイン** が他の言語に翻訳されていない場合は、画面サイズの制限により、次の IP 電話モデルの **[Press Sign In]\(サインインを押す**\) にのみ英語の短縮版が表示されます。
>   - Poly VVX 150、VVX 201
>   - Cisco CP-6821、CP-7811、CP-7821、CP-7841、CP-7861
>   - ボイス メール ソフトキー ラベルは、文字列の長さの制限があるため、Poly VVX のすべての言語で **VM** テキストでハードコーディングされます。

## <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams と IPv6

SIP ゲートウェイは IPv4 のみをサポートします。 Microsoft Teams サービスとクライアントは、IPv4 と IPv6 の両方をサポートします。 Microsoft Teams への通信を制御する場合は、[Microsoft 365 URL と IP アドレス範囲の IP アドレス範囲](/microsoft-365/enterprise/urls-and-ip-address-ranges)を使用します。

## <a name="emergency-calling"></a>緊急通話

SIP ゲートウェイは、ネットワーク属性をネットワーク上で共有する互換性のある SIP デバイスに対して、動的緊急通話 (動的 E911) をサポートします。 これらの属性は Teams 管理センターでプロビジョニングされ、ローカル IP とサブネットの長さの組み合わせ、またはシャーシ ID とネットワーク ポート番号を組み合わせて使用できます。 場所属性を共有しないデバイスの場合、または何らかの理由で場所が動的に解決されない場合、SIP ゲートウェイは登録されたアドレスに基づいて緊急通話を引き続きサポートします。 現在、登録済みアドレスはダイレクト ルーティング シナリオではサポートされていません。 緊急通報の詳細については、「緊急通報の [計画と管理](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)」を参照してください。

## <a name="report-problems-to-microsoft"></a>問題をMicrosoftに報告する

問題を報告するには、[Microsoft サポート](https://support.microsoft.com)にお問い合わせください。
