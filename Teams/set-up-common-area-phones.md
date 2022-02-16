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
ms.openlocfilehash: 144e32e1bf56bc3e2d64d0c6a1a137fd501442b7
ms.sourcegitcommit: 5aae5eace62e491dac655882d24974824ce1aa07
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2022
ms.locfileid: "62856665"
---
# <a name="deploy-common-area-phones-for-microsoft-teams"></a>一般的な地域の電話を展開Microsoft Teams

通常、共通領域電話はロビーなどのエリアや、多くの人が通話できる別のエリアに配置されます。たとえば、受付エリア、ロビー、会議電話などです。 共通領域電話は、共通領域電話ライセンスに関連付けられているアカウントでサインインします。

この記事では、共有スペースの共通領域電話としてTeams電話を展開および構成する方法の概要を説明します。 電話会議を含む、より完全な会議室エクスペリエンスを実現するには、会議室デバイスで専用のミーティング ルーム ライセンスのご購入を検討してください。

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
> 一般的なエリア電話オブジェクトのアカウントは、Skype for Business Serverに移行Microsoft Teams。 この記事の手順に従って、これらのアカウントを Teamsし、必要に応じて PTSN 接続を移行します。

## <a name="step-1---buy-the-licenses"></a>手順 1 - ライセンスを購入する

まず、共通領域電話 (CAP) のライセンスを購入し、認定された電話があることを確認する必要があります。 認定された電話の検索方法、および詳細情報を確認するには、[Microsoft Teams デバイス](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)にアクセスしてください。

1. 次のMicrosoft 365 管理センター **BillingPurchase** >  サービスに移動します。 

2. [カテゴリ **別に表示]** セクションが表示されていない場合は、[ **Microsoft** から購入] に移動し、[製品の表示] **を選択します**。 次に、[ **コラボレーションとコミュニケーション] を選択します**。  

3. 製品一覧で [共通領域] を **探電話** 詳細] を **選択します**。

4. 必要なライセンス数を入力し、[購入] を **選択します**。

>[!NOTE]
>環境内で Intune を使用し、デバイスのコンプライアンスを必要とする条件付きアクセス規則がある場合は、共通領域電話のデバイス アカウントに Azure Active Directory Premium プラン 1 と Intune ライセンスを割り当てる必要があります。
>
>一般的なエリア電話は、条件付きアクセス規則や、Multi-Factor Authentication などの他の ID 構成の影響を受け得る可能性があります。 詳細については[、「Teams Android デバイスの認証のベスト プラクティス](devices/authentication-best-practices-for-android-devices.md)」を参照してください。

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>手順 2 - 新しいユーザー アカウントを作成し、ライセンスを割り当てる

### <a name="using-the-microsoft-365-admin-center"></a>アプリケーションのMicrosoft 365 管理センター

一度に複数の共通領域電話を展開する場合は、PowerShell を使用してアカウントを作成し、ライセンスを割り当てる [方法について説明します](#using-powershell)。

1 つのデバイスをデプロイする場合:

1. [ユーザー] Microsoft 365 管理センターユーザーの **追加]** > **に** > **移動します**。

2. 名には "Main" のようなユーザー名を入力し、2 番目の名前には "フロント" を入力します。

3. "受け付け メイン" のように自動生成されない場合は、表示名を入力します。

4. "MainReception" や "Mainlobby" のようなユーザー名を入力します。

5. 防ぐために、共通の地域の電話のパスワードを手動で設定します。 これを行うには、[パスワードを自動的 **に作成** する] チェック ボックスをオフにして、最初にサインインするときにこのユーザーにパスワードの変更 **を要求します**。  

    >[!Important]
    > エンド ユーザーのサインインの問題を防ぐために、共通エリアの電話にパスワードを手動で設定することを強くお勧めします。

6. デバイスの使用場所を選択し、アカウントに共通領域電話割り当てる必要があります。 通話プランなどの他のライセンスが必要な場合は、割り当てします。

>[!NOTE]
> 電話システムのライセンスは必要ありません。 共通領域電話のライセンスに含まれています。
>
>システム ダイレクト ルーティングまたはオペレーター Microsoft 電話を使用していないConnect、通話プランライセンスを追加できます。 ライセンスの詳細については、「[Microsoft Teams のアドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用

複数のユーザー アカウントのライセンスを一度に作成して割り当てる場合は、PowerShell を使用します。 詳細[については、「PowerShell Microsoft 365を使用して](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide)ユーザー アカウントを作成する」および「[PowerShell Microsoft 365 ライセンス](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide)をユーザー アカウントに割り当てる」を参照してください。

## <a name="step-3---set-policies-for-common-area-phones"></a>手順 3 - 共通エリア電話のポリシーを設定する

ポリシーを使用して、一般的な地域の電話でユーザーが使用できる機能を制御します。

>[!NOTE]
>ポリシーを割り当て後、電話からサインアウトしてサインインし戻します。 ポリシーの割り当てが有効な場合、最大で 1 時間かかる場合があります。

### <a name="ip-phone-policies"></a>IP 電話ポリシー

共通領域ライセンスが割り当てられているアカウントでサインイン電話、共通領域のユーザー エクスペリエンスが表示されます。

電話の既定のインターフェイスをオーバーライドする場合は、IP 電話ポリシーの [作成を検討してください](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps)。 たとえば、パブリック エリアで共通エリアの電話が使用されている場合は、IP 電話ポリシーを設定して、組織のグローバル アドレス帳の検索を制限し、ホットデスクをブロックします。 詳細[については、「Teams Android デバイスのユーザー インターフェイスを設定する](devices/Teams-Android-devices-user-interface.md)」を参照してください。

### <a name="calling-policies"></a>通話ポリシー

通話ポリシーを使用して、プライベート通話、着信の転送、または共通エリアの電話での同時呼び出しを有効にします。 詳細[については、「通話と転送」](teams-calling-policy.md)Teamsを参照してください。

既定では、コール パークは一般的なエリアの電話に対して有効になっていません。 ポリシーを有効にするには、ポリシーを作成する必要があります。 詳細[については、「Call park and retrieve in Microsoft Teams in](call-park-and-retrieve.md) Microsoft Teams」を参照してください。

## <a name="step-4---acquire-and-assign-phone-numbers"></a>手順 4 - 電話番号を取得して割り当てる

PSTN [接続オプションに基づいて電話番号](manage-phone-numbers-landing-page.md) を取得して割り当てる方法については、「組織の電話番号を管理する」を参照してください。

## <a name="step-5---sign-in"></a>手順 5 - サインイン

ユーザー アカウントを作成して構成したら、電話にサインインできます。 展開している電話の数に応じて、次の 3 つのサインイン オプションがあります。

- [ローカル サインイン](#local-sign-in)
- [別のデバイスからサインインする](#sign-in-from-another-device)
- [管理センターでサインインTeamsする](#sign-in-using-the-teams-admin-center)

### <a name="local-sign-in"></a>ローカル サインイン

ユーザー名とパスワードでローカルにサインインするには: 

1. 共通エリアの電話をオンにする

2. [この **デバイスにサインインする] を選択します。**

3. デバイスのサインインの指示に従います。 サインインすると、電話に共通領域の電話ユーザー エクスペリエンスが表示されます。

### <a name="sign-in-from-another-device"></a>別のデバイスからサインインする

コードを使用して、別のデバイスから共通のエリア電話にサインインすることもできます。 この方法でサインインすると、電話自体ではなく、別のデバイスでユーザー名とパスワードを入力します。

1. まず、一般的なエリアの電話で、サインイン画面に表示されるコードを探します。

2. 別のデバイスで、 に移動します https://www.microsoft.com/devicelogin。

3. コードを入力し、指示に従ってサインインを完了します。

### <a name="sign-in-using-the-teams-admin-center"></a>管理センターでサインインTeamsする

管理者は、管理センターから一般的な地域の電話をリモートでプロビジョニングTeamsできます。 これは、一度に多数の電話を展開する場合に最も効率的なサインイン方法です。 詳細[については、「Android デバイスのリモート プロビジョニングTeamsサインイン」](devices/remote-provision-remote-login.md)を参照してください。

## <a name="next-steps"></a>次の手順

組織の共通領域電話をセットアップしてサインインしたので、管理センターで管理Teamsできます。 詳細[についてはMicrosoft Teams: デバイスの管理に関するページ](devices/device-management.md)を参照してください。

## <a name="related-topics"></a>関連項目

- [デバイスMicrosoft Teamsをリモートで更新する](devices/remote-update.md)
- [デバイス タグMicrosoft Teams管理する](devices/manage-device-tags.md)
- [Microsoft Teams正常性の監視](alerts/device-health-status.md)
