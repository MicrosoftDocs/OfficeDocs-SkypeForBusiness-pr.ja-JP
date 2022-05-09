---
title: 共通領域電話のライセンスをセットアップする
ms.author: czawideh
author: cazawideh
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
description: 'ロビー、受付エリア、会議室に共通領域電話を設定する方法について説明します '
ms.openlocfilehash: 313a17d1829c8f3584ec5fb7f37e5f1ec49231d0
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456940"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>Microsoft Teams用の共通領域の電話を展開する

通常、共通領域電話はロビーなどのエリアや、多くの人が通話できる別のエリアに配置されます。たとえば、受付エリア、ロビー、会議電話などです。 共通領域電話は、共通領域電話ライセンスに関連付けられているアカウントでサインインします。

この記事では、共有スペースの共通領域電話としてTeams電話を展開および構成する方法の概要について説明します。 電話会議を含む、より完全な会議室エクスペリエンスを実現するには、会議室デバイスで専用のミーティング ルーム ライセンスのご購入を検討してください。

## <a name="overview"></a>概要

共通領域電話のライセンスは以下をサポートしています: 


| &nbsp;  |  共通領域電話  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|電話システム |    &#x2714; |
|電話会議 |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|世界的な可用性 |       &#x2718; &sup2;  |
|チャネルの可用性 |    EA、EAS、CSP、GCC、EES、Web Direct  |
|      |         |

&sup1;共通領域電話は、会議開催者が提供するダイヤルイン番号を使用して音声会議に参加できます

&sup2; ソブリン クラウドでは使用できません  

>[!NOTE]
> Skype for Business Serverで作成された共通エリアフォン オブジェクトのアカウントをMicrosoft Teamsに移行することはできません。 この記事の手順に従って、Teams用にこれらのアカウントを再作成し、必要に応じて PTSN 接続を移行します。

## <a name="step-1---buy-the-licenses"></a>手順 1 - ライセンスを購入する

まず、共通領域電話 (CAP) のライセンスを購入し、認定された電話があることを確認する必要があります。 認定された電話の検索方法、および詳細情報を確認するには、[Microsoft Teams デバイス](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)にアクセスしてください。

1. Microsoft 365 管理センターで、**BillingPurchase** >  サービスに移動します。 

2. [ **カテゴリ別の表示** ] セクションがまだ表示されていない場合は、[ **Microsoft から購入**] に移動し、[ **製品の表示**] を選択します。 次に、[ **コラボレーションと通信**] を選択します。  

3. 製品の一覧で[**共通領域] 電話** を見つけて、[詳細] を選択 **します**。

4. 必要なライセンスの数を入力し、[ **購入**] を選択します。

>[!NOTE]
>環境でIntuneを使用していて、デバイスコンプライアンスを必要とする条件付きアクセス規則がある場合は、Azure Active Directory Premiumプラン 1 を割り当て、共通エリア電話のデバイス アカウントにライセンスをIntuneする必要があります。
>
>共通領域の電話は、条件付きアクセス 規則や、Multi-Factor Authentication などの他の ID 構成の影響を受ける可能性があります。 詳細については、[Teams Android デバイスの認証のベスト プラクティス](devices/authentication-best-practices-for-android-devices.md)に関するページを参照してください。

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>手順 2 - 新しいユーザー アカウントを作成し、ライセンスを割り当てる

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

複数の共通エリア電話を一度にデプロイする場合は、 [PowerShell を使用して](#using-powershell)アカウントを作成し、ライセンスを割り当てる方法について説明します。

1 つのデバイスをデプロイする場合:

1. Microsoft 365 管理センターで、**UsersActive** >  **UsersAdd** >  **a user** に移動します。

2. 名の "Main" や、2 番目の名前の "受信" などのユーザー名を入力します。

3. "受け付け メイン" のように自動生成されない場合は、表示名を入力します。

4. "MainReception" や "Mainlobby" などのユーザー名を入力します。

5. 防止するには、共通領域の電話のパスワードを手動で設定します。 これを行うには、[ **パスワードを自動的に作成する** ] をオフにし、 **このユーザーが最初にサインインするときにパスワードを変更する必要があります**。  

    >[!Important]
    > 共通領域電話のパスワードを手動で設定することは、エンド ユーザーのサインインの問題を防ぐために強くお勧めします。

6. デバイスの使用場所を選択し、共通領域電話ライセンスをアカウントに割り当てます。 通話プランなどの他のライセンスが必要な場合は、割り当てます。

>[!NOTE]
> 電話システムのライセンスは必要ありません。 共通領域電話のライセンスに含まれています。
>
>Microsoft 電話 システム ダイレクト ルーティングまたはオペレーター接続を使用していない場合は、通話プランライセンスを追加できます。 ライセンスの詳細については、「[Microsoft Teams のアドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用

複数のユーザー アカウントのライセンスを一度に作成して割り当てる場合は、PowerShell を使用します。 詳細については、「[PowerShell でMicrosoft 365ユーザー アカウントを作成](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide)する」と「PowerShell [を使用したユーザー アカウントへのMicrosoft 365 ライセンスの割り当て](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide)」を参照してください。

## <a name="step-3---set-policies-for-common-area-phones"></a>手順 3 - 共通エリア電話のポリシーを設定する

ポリシーを使用して、共通エリアの電話でユーザーが使用できる機能を制御します。

>[!NOTE]
>ポリシーを割り当てた後、電話からサインアウトして、もう一度サインインします。 ポリシーの割り当てが有効になるまでには、最大で 1 時間かかる場合があります。

### <a name="ip-phone-policies"></a>IP Phone ポリシー

共通領域電話ライセンスが割り当てられているアカウントでサインインした電話には、共通領域のユーザー エクスペリエンスが表示されます。

電話の既定のインターフェイスをオーバーライドする場合は、 [IP 電話ポリシー](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps)の作成を検討してください。 たとえば、共用エリアの電話がパブリック エリアで使用されている場合は、組織のグローバル アドレス帳の検索を制限し、ホットデスクをブロックするように IP 電話ポリシーを設定します。 詳細については、「[Android デバイスのユーザー インターフェイスTeams設定](devices/Teams-Android-devices-user-interface.md)する」を参照してください。

### <a name="calling-policies"></a>通話ポリシー

通話ポリシーを使用して、共通エリアの電話でプライベート通話、通話転送、または同時リングを有効にします。 詳細については、「[Teamsでの通話と通話転送](teams-calling-policy.md)」を参照してください。

既定では、コール パークは共通エリアの電話では有効になっていません。 ポリシーを有効にするには、ポリシーを作成する必要があります。 詳細については、「[コール パークを参照し、Microsoft Teamsで取得](call-park-and-retrieve.md)する」を参照してください。

## <a name="step-4---acquire-and-assign-phone-numbers"></a>手順 4 - 電話番号を取得して割り当てる

PSTN 接続オプションに基づいて [電話番号を](manage-phone-numbers-landing-page.md) 取得して割り当てる方法については、「組織の電話番号を管理する」を参照してください。

## <a name="step-5---sign-in"></a>手順 5 - サインイン

ユーザー アカウントを作成して構成したら、電話にサインインできます。 展開する電話の数に応じて、次の 3 つのサインイン オプションがあります。

- [ローカル サインイン](#local-sign-in)
- [別のデバイスからサインインする](#sign-in-from-another-device)
- [Teams管理センターを使用してサインインする](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>ローカル サインイン

ユーザー名とパスワードを使用してローカルにサインインするには: 

1. 共通領域の電話をオンにする

2. **このデバイスで [サインイン] を選択する**

3. デバイスのサインインの指示に従います。 サインインすると、共通領域の電話ユーザー エクスペリエンスが電話に表示されます。

> [!NOTE]
> 呼び出し元のアプリの固定を解除するカスタム セットアップ ポリシーを使用している場合、ダイヤル パッドは共通領域電話には表示されません。 Teamsセットアップ ポリシーの詳細については、「[Microsoft Teamsでのアプリセットアップ ポリシーの管理](/microsoftteams/teams-app-setup-policies)」を参照してください。

### <a name="sign-in-from-another-device"></a>別のデバイスからサインインする

コードを使用して、別のデバイスから共通エリアの電話にサインインすることもできます。 この方法でサインインすると、電話自体ではなく、別のデバイスでユーザー名とパスワードを入力します。

1. まず、共通エリアの電話で、サインイン画面に表示されるコードを探します。

2. 別のデバイスで、 https://www.microsoft.com/devicelogin.

3. コードを入力し、指示に従ってサインインを完了します。

### <a name="sign-in-using-the-teams-admin-center"></a>Teams管理センターを使用してサインインする

管理者は、Teams管理センターからリモートで共通領域の電話をプロビジョニングしてサインインできます。 これは、多数の電話を一度に展開する場合に最も効率的なサインイン方法です。 詳細については、「[リモート プロビジョニングとTeams Android デバイスのサインイン](devices/remote-provision-remote-login.md)」を参照してください。

## <a name="next-steps"></a>次のステップ

組織の共通エリア電話を設定してサインインしたので、Teams管理センターで管理できます。 詳細については、「[Microsoft Teams: デバイスの管理](devices/device-management.md)」を参照してください。

## <a name="related-topics"></a>関連項目

- [Microsoft Teamsデバイスをリモートで更新する](devices/remote-update.md)
- [デバイス タグMicrosoft Teams管理する](devices/manage-device-tags.md)
- [Microsoft Teams デバイスの正常性監視](alerts/device-health-status.md)
