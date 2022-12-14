---
title: Microsoft Teams の共通エリア電話を設定する
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
description: ロビー、レセプションエリア、会議室用の共通エリア電話を設定する方法について説明します。
ms.openlocfilehash: 06005f853ac125478ae1fd99dba2d022c5eb0100
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392157"
---
# <a name="set-up-common-area-phones-for-microsoft-teams"></a>Microsoft Teams の共通エリア電話を設定する

一般的なエリア電話は、通常、ロビーや他のエリアのようなエリアに配置され、多くの人が電話をかけられます。これは、受信エリア、ロビー、または電話です。 共通エリア電話は、**Microsoft Teams 共有デバイス** ライセンスに関連付けられたアカウントでサインインします。

この記事では、Teams 電話デバイスを共有スペースの共通エリア電話として展開および構成する方法の概要について説明します。 電話会議など、より完全な会議室エクスペリエンスを実現するには、代わりにTeams Rooms デバイスを使用して専用 **のTeams Rooms** ライセンスを購入することを検討してください。 Teams Roomsの詳細については、「[Microsoft Teams Rooms](rooms/index.md)」を参照してください。

> [!NOTE]
> Skype for Business Serverで作成された共通エリア電話オブジェクトのアカウントは、Microsoft Teams に移行できません。 この記事の手順に従って Teams のアカウントを再作成し、必要に応じて公衆交換電話網 (PSTN) 接続を移行します。

## <a name="step-1---buy-the-licenses"></a>手順 1 - ライセンスを購入する

まず、 **Teams 共有デバイス** ライセンスを購入し、認定電話があることを確認する必要があります。 認定された電話の検索方法、および詳細情報を確認するには、[Microsoft Teams デバイス](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)にアクセスしてください。

1. [Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)で、[課金 **購入サービス****]** >  に移動します。

2. [**カテゴリ別に表示**] セクションがまだ表示されていない場合は、[**Microsoftから購入**] に移動し、[**製品の表示**] を選択します。 次に、[ **コラボレーションとコミュニケーション**] を選択します。  

3. 製品の一覧で、[**Microsoft Teams 共有デバイス**] を見つけて、[詳細] を選択 **します**。

4. 必要なライセンスの数を入力し、[ **購入**] を選択します。

> [!NOTE]
> 環境内でIntuneを使用していて、デバイスのコンプライアンスを必要とする条件付きアクセス規則がある場合は、**Azure Active Directory Premiumプラン 1** を割り当て、共通エリア電話のデバイス アカウントにライセンス **をIntune** する必要があります。
>
> 一般的なエリア電話は、条件付きアクセス 規則やその他の ID 構成 (Multi-Factor Authentication など) の影響を受ける可能性があります。 詳細については、「 [Teams Android デバイスの認証のベスト プラクティス](devices/authentication-best-practices-for-android-devices.md) 」を参照してください。

## <a name="step-2---create-a-new-user-account-and-assign-licenses"></a>手順 2 - 新しいユーザー アカウントを作成し、ライセンスを割り当てる

### <a name="using-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターの使用

複数の共通エリア電話を一度に展開する場合は、 [PowerShell を使用して](#using-powershell)アカウントを作成し、ライセンスを割り当てる方法について説明します。

1 つのデバイスをデプロイする場合:

1. [Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)で、[ユーザー **] [アクティブ なユーザー** > **] [ユーザー** > **の追加]** の順に移動します。

2. 名と 2 番目の名前のユーザー名`Main``Reception`を入力します。

3. のような `Main Reception`自動生成が行われない場合は、表示名を入力します。

4. または `Mainlobby`のような`MainReception`ユーザー名を入力します。

5. 共通エリア電話のパスワードを手動で設定します。 パスワードを設定するには、[ **パスワードを自動的に作成** する] をオフにして、 **このユーザーが最初にサインインするときにパスワードを変更するように要求** します。  

    > [!IMPORTANT]
    > エンド ユーザーのサインインの問題を防ぐために、共通エリア電話のパスワードを手動で設定することを強くお勧めします。

6. デバイスの使用場所を選択し、 **Teams 共有デバイス** ライセンスをアカウントに割り当てます。 通話プランなど、他のライセンスが必要な場合は、それらを割り当てます。

> [!NOTE]
> 電話システム機能を使用してライセンスを追加する必要はありません。 **Teams 共有デバイス** ライセンスに含まれています。
>
> ダイレクト ルーティングまたはオペレーター接続Microsoft電話システムを使用していない場合は、**通話プラン** ライセンスを追加できます。 ライセンスの詳細については、「[Microsoft Teams のアドオン ライセンス](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。

### <a name="using-powershell"></a>PowerShell の使用

複数のユーザー アカウントのライセンスを一度に作成して割り当てる場合は、PowerShell を使用します。 詳細については、「[PowerShell を使用して Microsoft 365 ユーザー アカウントを作成する」および「PowerShell を使用](/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)[してユーザー アカウントMicrosoft 365 ライセンスを割り当てる](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)」を参照してください。

## <a name="step-3---set-policies-for-common-area-phones"></a>手順 3 - 共通エリア電話のポリシーを設定する

ポリシーを使用して、共通エリア電話でユーザーが使用できる機能を制御します。

### <a name="ip-phone-policies"></a>IP 電話ポリシー

Teams IP Phone ポリシーは、電話にサインインするアカウントが **Teams 共有デバイス** ライセンス以外のライセンスを持つ場合にのみ変更できます。  Microsoft 365 E3または E5 サブスクリプション、または Office 365 Enterprise E1、E3、または E5 サブスクリプションでライセンスされている場合は、IP Phone ポリシーを変更できます。  共通エリアの電話アカウントで **Teams Rooms** ライセンスを使用している場合は、モードのみを使用`MeetingRoomSignIn`できます。 `MeetingRoomSignIn` モードは、ほとんどの一般的なエリア電話では使用できません。 電話インターフェイスでサポートされているオーバーライドの詳細については、「[Teams Android デバイスのユーザー インターフェイスMicrosoft設定](/microsoftteams/devices/teams-android-devices-user-interface#override-automatic-user-interface-detection)する」を参照してください。

Teams IP Phone ポリシーを使用して、 [SignInMode パラメーター](/powershell/module/skype/new-csteamsipphonepolicy#parameters) を に `CommonAreaPhoneSignIn` 設定して、Teams 電話デバイスで共通エリア電話エクスペリエンスを有効にします。

その他のパラメーターを構成するには、 [IP Phone ポリシー](/powershell/module/skype/new-csteamsipphonepolicy)の作成を検討してください。 たとえば、共通エリアの電話がパブリック エリアで使用されている場合は、IP 電話ポリシーを設定して、組織のグローバル アドレス帳の検索を制限し、ホット デスクをブロックします。 詳細については、「 [Teams Android デバイスのユーザー インターフェイスを設定する](/microsoftteams/devices/Teams-Android-devices-user-interface)」を参照してください。

### <a name="calling-policies"></a>通話ポリシー

通話ポリシーを使用して、プライベート 通話、通話転送、または共通エリア電話での同時呼び出しを有効にします。 詳細については、「 [Teams での通話と転送](teams-calling-policy.md)」を参照してください。

既定では、コール パークは共通エリア電話では有効になっていません。 有効にするには、ポリシーを作成する必要があります。 詳細については、「[Microsoft Teams でのコール パークと取得](call-park-and-retrieve.md)」を参照してください。

> [!NOTE]
> ポリシーを割り当てた後、電話からサインアウトし、もう一度サインインします。 ポリシーの割り当てが有効になるまでに最大 1 時間かかる場合があります。

## <a name="step-4---acquire-and-assign-phone-numbers"></a>手順 4 - 電話番号を取得して割り当てる

PSTN 接続オプションに基づいて電話番号を取得して割り当てる方法については、「 [組織の](manage-phone-numbers-landing-page.md) 電話番号を管理する」を参照してください。

## <a name="step-5---sign-in"></a>手順 5 - サインイン

ユーザー アカウントを作成して構成したら、電話にサインインできます。 展開している電話の数に応じて、次の 3 つのサインイン オプションがあります。

- [ローカル サインイン](#local-sign-in)。
- [別のデバイスからサインインします](#sign-in-from-another-device)。
- [Teams 管理センターを使用してサインインします](#sign-in-using-the-teams-admin-center)。

### <a name="local-sign-in"></a>ローカル サインイン

ユーザー名とパスワードを使用してローカルにサインインするには:

1. 共通エリア電話をオンにします。
2. [ **このデバイスでサインイン] を選択します**。
3. デバイスのサインインの指示に従います。 サインインすると、電話に共通エリア電話のユーザー エクスペリエンスが表示されます。

> [!NOTE]
> 呼び出し元アプリのピン留めを解除するカスタム セットアップ ポリシーを使用している場合、ダイヤル パッドは共通エリア電話に表示されません。 Teams セットアップ ポリシーの詳細については、「Microsoft [Teams でのアプリセットアップ ポリシーの管理](teams-app-setup-policies.md)」を参照してください。

### <a name="sign-in-from-another-device"></a>別のデバイスからサインインする

コードを使用して、別のデバイスから共通エリア電話にサインインすることもできます。 この方法でサインインすると、電話自体ではなく、別のデバイスでユーザー名とパスワードを入力します。

1. 共通エリア電話で、サインイン画面に表示されているコードを見つけます。
2. 別のデバイスで、 に移動します [https://www.microsoft.com/devicelogin](https://www.microsoft.com/devicelogin)。
3. コードを入力し、指示に従ってサインインを完了します。

### <a name="sign-in-using-the-teams-admin-center"></a>Teams 管理センターを使用してサインインする

管理者は、 [Teams 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2066851)から共通エリアの電話をリモートでプロビジョニングしてサインインできます。 この方法は、多数の電話を一度に展開する場合に最も効率的なサインイン方法です。 詳細については、「 [Teams Android デバイスのリモート プロビジョニングとサインイン](devices/remote-provision-remote-login.md) 」を参照してください。

## <a name="step-6---set-up-advanced-calling-on-common-area-phones-optional"></a>手順 6 - 共通エリア電話で高度な通話を設定する (省略可能)

既定では、基本的な通話エクスペリエンスは共通エリア電話のホーム画面に表示されますが、高度な通話エクスペリエンスを有効にすることができます。

**Teams 共有デバイス** ライセンスと最新の Teams 更新プログラム (最小バージョン: 1449/1.0.94.20222061702) を使用して、サポートされている Teams 電話デバイス モデルで、次の高度な通話機能を利用できます。

- [パークを呼び出して取得します](call-park-and-retrieve.md)。
- [Exchange Online プラン 2 を使用したクラウドベースのボイスメール](set-up-phone-system-voicemail.md)。
  - クラウドベースのボイスメールを無効にするには、「 [PowerShell を使用したボイスメール ユーザー設定](/powershell/module/skype/set-csonlinevoicemailusersettings)」を参照してください。
- [呼び出しキュー](create-a-phone-system-call-queue.md)。
- [自動応答](create-a-phone-system-auto-attendant.md)。
- [グループ通話のピックアップ](call-sharing-and-group-call-pickup.md)。
- [転送ルール](teams-calling-policy.md)。

サポートされている Teams 電話デバイス モデルでこれらの高度な通話機能を使用するには、[Teams 管理センターまたは Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851) 共有デバイス アカウントにサインインしている Teams 電話デバイスの **[高度な通話**] トグルをオンにします。

高度な呼び出し機能を有効にするには、必要なすべての機能をサポートできるハードウェア モデルを購入する必要があります。

### <a name="turn-on-advanced-calling-in-teams-admin-center"></a>Teams 管理センターで高度な通話を有効にする

1. Microsoft 365 管理者アカウントを使用して [Teams 管理センター](https://admin.teams.microsoft.com/dashboard)にサインインします。
1. 左側のメニューから、[ **Teams デバイス** > **] [電話** ] >に移動し、[ **構成プロファイル** ] タブを選択します。
1. 一覧から、共通エリア電話に割り当てられている構成プロファイルを選択します。
1. [ **通話の設定** ] セクションで、[ **呼び出しの詳細設定** ] トグルを見つけます。
1. トグルをオンにします。
1. ページの下部にある [ **保存** ] ボタンを選択します。

### <a name="turn-on-advanced-calling-from-a-teams-phone-device"></a>Teams 電話デバイスからの高度な通話を有効にする

1. Teams 電話デバイスにサインインしたら、[設定 **] [デバイスの設定** > **]** >  に移動し **管理通話のみ** > **行います**。
1. **[高度な通話**] トグルを見つけてオンにします。

## <a name="next-steps"></a>次の手順

組織の共通エリア電話を設定してサインインしたので、Teams 管理センターで管理できます。 詳細については、「[Microsoft Teams: デバイスの管理](devices/device-management.md)」を参照してください。

## <a name="related-articles"></a>関連記事

- [Microsoft Teams デバイスをリモートで更新します](devices/remote-update.md)。
- [Microsoft Teams デバイス タグを管理します](devices/manage-device-tags.md)。
- [Microsoft Teams デバイスの正常性の監視](alerts/device-health-status.md)。
