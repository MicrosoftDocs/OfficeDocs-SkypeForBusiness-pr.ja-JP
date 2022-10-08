---
title: 共通領域電話のライセンスをセットアップする
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.date: 1/28/2022
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
- admindeeplinkMAC
- admindeeplinkTEAMS
description: ロビー、受付エリア、会議室用に共通エリアフォンを設定する方法について説明します。
ms.openlocfilehash: 74809ffdf4f11b91584f770e7dc817543fccc98e
ms.sourcegitcommit: 3ad7b46e31890fba7abe739138cd49527d5ca6b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2022
ms.locfileid: "68475509"
---
# <a name="set-up-common-area-phones-for-microsoft-teams"></a>Microsoft Teams 用の共通エリア電話を設定する

共通エリア電話は、通常、ロビーなどのエリアや、多くの人が電話を発信できる別のエリア (受信エリア、ロビー、会議電話) に配置されます。 共通エリア電話は、 **Common Area Phone** ライセンスに関連付けられたアカウントでサインインされます。

この記事では、Teams の電話デバイスを共有スペースの共通領域の電話として展開および構成する方法の概要について説明します。 電話会議を含む、より完全な会議室エクスペリエンスを実現するには、Teams Rooms デバイスで専用 **のTeams Rooms** ライセンスを購入することを検討してください。

## <a name="overview"></a>概要

**Common Area Phone** ライセンスは、次をサポートしています。

|                                           | 共通領域電話                                 |
|-------------------------------------------|---------------------------------------------------|
| **Microsoft Teams**                       | &#x2714;                                          |
| **Teams Phone**  &sup1;                   | &#x2714;                                          |
| **電話会議**                    | &#x2718; &sup2;                                   |
| **Microsoft Intune**                      | &#x2714;                                          |
| **Azure Active Directory Premiumプラン 1** | &#x2714;                                          |
| **Exchange Online プラン 2**                | &#x2714;  &sup3;                                  |
| **世界的な可用性**                | &#x2714;                                          |
| **チャネルの可用性**                  | EA、EAS、EES、CSP、Web Direct、GCC、GCC-High、DoD |

&sup1;以前は *電話システムと呼ばられていました*。
&sup2;共通エリアの電話は、会議の開催者が提供するダイヤルイン番号を使用して電話会議に参加できます。
&sup3;クラウドベースのボイスメール機能のみ。

> [!NOTE]
> Skype for Business Serverで作成された共通領域の電話オブジェクトのアカウントを Microsoft Teams に移行することはできません。 この記事の手順に従って Teams のアカウントを再作成し、必要に応じて公衆交換電話網 (PSTN) 接続を移行します。

## <a name="step-1---buy-the-licenses"></a>手順 1 - ライセンスを購入する

まず、 **Common Area Phone** (CAP) ライセンスを購入し、認定された電話があることを確認する必要があります。 認定された電話の検索方法、および詳細情報を確認するには、[Microsoft Teams デバイス](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)にアクセスしてください。

1. [Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)で、**課金** > **購入サービス** に移動します。

2. [ **カテゴリ別の表示** ] セクションがまだ表示されていない場合は、[ **Microsoft から購入**] に移動し、[ **製品の表示**] を選択します。 次に、[ **コラボレーションと通信**] を選択します。  

3. 製品の一覧で[ **共通エリアの電話**]、[ **詳細**] の順に選択します。

4. 必要なライセンスの数を入力し、[ **購入**] を選択します。

> [!NOTE]
> 環境でIntuneを使用していて、デバイスコンプライアンスを必要とする条件付きアクセス規則がある場合は、**Azure Active Directory Premiumプラン 1** を割り当て、共通エリア電話のデバイス アカウントにライセンスを **Intune** する必要があります。
>
> 共通領域の電話は、条件付きアクセス 規則や、Multi-Factor Authentication などの他の ID 構成の影響を受ける可能性があります。 詳細については、「 [Teams Android デバイスの認証のベスト プラクティス](devices/authentication-best-practices-for-android-devices.md) 」を参照してください。

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>手順 2 - 新しいユーザー アカウントを作成し、ライセンスを割り当てる

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

複数の共通エリア電話を一度にデプロイする場合は、 [PowerShell を使用して](#using-powershell)アカウントを作成し、ライセンスを割り当てる方法について説明します。

1 つのデバイスをデプロイする場合:

1. [Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)で、[**ユーザーアクティブ ユーザー** > の追加 **]** >  に移動 **します**。

2. 名と 2 番目の名前`Reception`のような`Main`ユーザー名を入力します。

3. 表示名が自動生成されない場合は、次のように `Main Reception`入力します。

4. のようなユーザー名 `MainReception` を入力します `Mainlobby`。

5. 共通エリアの電話のパスワードを手動で設定します。 パスワードを設定するには、[ **パスワードを自動的に作成する** ] をオフにし、 **このユーザーが最初にサインインするときにパスワードを変更する必要があります**。  

    > [!IMPORTANT]
    > エンド ユーザーのサインインの問題を防ぐために、共通領域の電話のパスワードを手動で設定することを強くお勧めします。

6. デバイスの使用場所を選択し、 **共通エリア電話** ライセンスをアカウントに割り当てます。 通話プランなどの他のライセンスが必要な場合は、割り当てます。

> [!NOTE]
> 電話システム機能を使用してライセンスを追加する必要はありません。 **共用エリア電話機** のライセンスに含まれています。
>
> 直接ルーティングまたはオペレーター接続で Microsoft Phone System を使用していない場合は、 **通話プラン** ライセンスを追加できます。 ライセンスの詳細については、「[Microsoft Teams のアドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用

複数のユーザー アカウントのライセンスを一度に作成して割り当てる場合は、PowerShell を使用します。 詳細については、「[PowerShell を使用して Microsoft 365 ユーザー アカウントを作成する」と「PowerShell を使用](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)[してユーザー アカウントに Microsoft 365 ライセンスを割り当てる](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)」を参照してください。

## <a name="step-3---set-policies-for-common-area-phones"></a>手順 3 - 共通エリア電話のポリシーを設定する

ポリシーを使用して、共通エリアの電話でユーザーが使用できる機能を制御します。

### <a name="ip-phone-policies"></a>IP Phone ポリシー

Teams IP Phone ポリシーを使用して、 [SignInMode パラメーター](/powershell/module/skype/new-csteamsipphonepolicy#parameters) を設定して `CommonAreaPhoneSignIn` 、Teams の電話デバイスで共通エリアの電話エクスペリエンスを有効にします。

他のパラメーターを構成するには、 [IP 電話ポリシー](/powershell/module/skype/new-csteamsipphonepolicy)の作成を検討してください。 たとえば、共用エリアの電話がパブリック エリアで使用されている場合は、組織のグローバル アドレス帳の検索を制限し、ホットデスクをブロックするように IP 電話ポリシーを設定します。 詳細については、「 [Teams Android デバイスのユーザー インターフェイスの設定](/microsoftteams/devices/Teams-Android-devices-user-interface)」を参照してください。

### <a name="calling-policies"></a>通話ポリシー

通話ポリシーを使用して、共通エリアの電話でプライベート通話、通話転送、または同時リングを有効にします。 詳細については、「 [Teams での通話と通話転送](teams-calling-policy.md)」を参照してください。

既定では、コール パークは共通エリアの電話では有効になっていません。 ポリシーを有効にするには、ポリシーを作成する必要があります。 詳細については、 [Microsoft Teams でのコール パークと取得に関するページを参照してください](call-park-and-retrieve.md)。

> [!NOTE]
> ポリシーを割り当てた後、電話からサインアウトして、もう一度サインインします。 ポリシーの割り当てが有効になるまでには、最大で 1 時間かかる場合があります。

## <a name="step-4---acquire-and-assign-phone-numbers"></a>手順 4 - 電話番号を取得して割り当てる

PSTN 接続オプションに基づいて [電話番号を](manage-phone-numbers-landing-page.md) 取得して割り当てる方法については、「組織の電話番号を管理する」を参照してください。

## <a name="step-5---sign-in"></a>手順 5 - サインイン

ユーザー アカウントを作成して構成したら、電話にサインインできます。 展開する電話の数に応じて、次の 3 つのサインイン オプションがあります。

- [ローカル サインイン](#local-sign-in)。
- [別のデバイスからサインインします](#sign-in-from-another-device)。
- [Teams 管理センターを使用してサインインします](#sign-in-using-the-teams-admin-center)。

### <a name="local-sign-in"></a>ローカル サインイン

ユーザー名とパスワードを使用してローカルにサインインするには:

1. 共通領域の電話をオンにします。
2. **このデバイスで [サインイン**] を選択します。
3. デバイスのサインインの指示に従います。 サインインすると、共通領域の電話ユーザー エクスペリエンスが電話に表示されます。

> [!NOTE]
> 呼び出し元のアプリの固定を解除するカスタム セットアップ ポリシーを使用している場合、ダイヤル パッドは共通領域の電話には表示されません。 Teams セットアップ ポリシーの詳細については、「 [Microsoft Teams でアプリセットアップ ポリシーを管理する」を参照してください](teams-app-setup-policies.md)。

### <a name="sign-in-from-another-device"></a>別のデバイスからサインインする

コードを使用して、別のデバイスから共通エリアの電話にサインインすることもできます。 この方法でサインインすると、電話自体ではなく、別のデバイスでユーザー名とパスワードを入力します。

1. 共通エリアの電話で、サインイン画面に表示されているコードを見つけます。
2. 別のデバイスで、 [https://www.microsoft.com/devicelogin](https://www.microsoft.com/devicelogin).
3. コードを入力し、指示に従ってサインインを完了します。

### <a name="sign-in-using-the-teams-admin-center"></a>Teams 管理センターを使用してサインインする

管理者は、 [Teams 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2066851)からリモートで共通領域の電話をプロビジョニングしてサインインできます。 この方法は、多数の電話を一度に展開する場合に最も効率的なサインイン方法です。 詳細については、「 [Teams Android デバイスのリモート プロビジョニングとサインイン](devices/remote-provision-remote-login.md) 」を参照してください。

## <a name="step-6---set-up-advanced-calling-on-common-area-phones-optional"></a>手順 6 - 共通エリアの電話で高度な通話を設定する (省略可能)

既定では、基本的な通話エクスペリエンスは共通エリアの電話のホーム画面に表示されますが、高度な通話エクスペリエンスを有効にできます。

**共通エリア** 電話ライセンスと最新の Teams 更新プログラム (最小バージョン: 1449/1.0.94.2022061702) でサポートされている Teams 電話デバイス モデルでは、次の高度な通話機能を利用できます。

- [パークを呼び出して取得します](call-park-and-retrieve.md)。
- [Exchange Online プラン 2 を介したクラウドベースのボイスメール](set-up-phone-system-voicemail.md)。
  - クラウドベースのボイスメールを無効にするには、「 [PowerShell を使用したボイスメール ユーザー設定](/powershell/module/skype/set-csonlinevoicemailusersettings)」を参照してください。
- [キューを呼び出します](create-a-phone-system-call-queue.md)。
- [自動応答](create-a-phone-system-auto-attendant.md)。
- [グループ通話のピックアップ](call-sharing-and-group-call-pickup.md)。
- [転送ルール](teams-calling-policy.md)。

サポートされている Teams の電話デバイス モデルでこれらの高度な通話機能を使用するには、[Teams 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2066851)または共通エリア電話アカウントにサインインしている Teams の電話デバイスで **、[詳細通話**] トグルをオンにします。

高度な通話機能を有効にするには、必要なすべての機能をサポートできるハードウェア モデルを購入する必要があります。

### <a name="turn-on-advanced-calling-in-teams-admin-center"></a>Teams 管理センターで高度な通話を有効にする

1. Microsoft 365 管理者アカウントを使用して [Teams 管理センター](https://admin.teams.microsoft.com/dashboard) にサインインします。
1. 左側のメニューから Teams **デバイス** > **の [電話** ] >に移動し、[ **構成プロファイル** ] タブを選択します。
1. 一覧から、共通エリアの電話に割り当てられている構成プロファイルを選択します。
1. [ **通話の設定]** セクションで、[ **高度な呼び出し]** トグルを見つけます。
1. トグルをオンにします。
1. ページの下部にある [ **保存** ] ボタンを選択します。

### <a name="turn-on-advanced-calling-from-a-teams-phone-device"></a>Teams の電話デバイスから高度な通話を有効にする

1. Teams の電話デバイスにサインインしたら、[設定 **デバイスの設定** > **]** >  に移動 **管理通話のみ** > 行 **います**。
1. **高度な呼び出し** トグルを見つけて、オンにします。

## <a name="next-steps"></a>次の手順

組織の共通領域の電話を設定してサインインしたので、Teams 管理センターで管理できます。 詳細については、「 [Microsoft Teams: デバイスの管理](devices/device-management.md) 」を参照してください。

## <a name="related-articles"></a>関連記事

- [Microsoft Teams デバイスをリモートで更新します](devices/remote-update.md)。
- [Microsoft Teams デバイス タグを管理します](devices/manage-device-tags.md)。
- [Microsoft Teams デバイスの正常性監視](alerts/device-health-status.md)。
