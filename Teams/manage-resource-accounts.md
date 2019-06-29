---
title: Teams のリソース アカウントを管理する
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Microsoft Teams でリソースアカウントを管理する方法について説明します。
ms.openlocfilehash: 4dcb9327efba7be70628ad71a90734940fc3317e
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394501"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams のリソースのアカウントの管理

リソースアカウントは、Azure Active Directory で無効になったユーザーオブジェクトとも呼ばれ、一般にリソースを表すために使用できます。 Exchange では、会議室の代表として使用され、電話番号を割り当てることができます。 リソースアカウントは、Skype for Business Server 2019 を使って、Microsoft 365 またはオンプレミスのホームにすることができます。

Microsoft Teams または Skype for Business Online では、各通話キューまたは自動応答に、関連するリソースアカウントが必要です。 リソースアカウントに割り当てられた電話番号が必要かどうかは、関連付けられた通話キューまたは自動応答の用途によって異なります。 リソースアカウントに電話番号を割り当てる前に、この記事の下部にある「通話キューと自動応答」の記事を参照してください。

> [!NOTE]
> この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。 Skype for Business Server 2019 を使用しているリソースアカウントの場合は、「[リソースアカウントを構成する](/SkypeForBusiness/hybrid/configure-onprem-ra)」を参照してください。

## <a name="overview"></a>概要

電話システムサービスにサービス番号が必要な場合は、次の順序でさまざまな依存関係を満たすことができます。

1. サービス番号を取得する
2. 電話システムのライセンスを購入する (電話システムが追加されている Office 365 Enterprise E1 または E3、または電話システムを含む Office 365 Enterprise E5)
3. リソースアカウントを作成します。 関連付けられているリソースアカウントを持つには、自動応答または通話キューが必要です。
4. 電話システムのライセンスをリソースアカウントに割り当てます。
5. リソースアカウントに電話番号を割り当てます。
6. 電話システムサービス (通話キューまたは自動応答) を作成する
7. リソースアカウントをサービスに関連付ける: (新しい-CsApplicationInstanceAssociation)

自動応答または通話キューが最上位レベルの自動応答の下に入れ子になっている場合、関連付けられたリソースアカウントには、自動応答と通話キューの構造に複数のエントリポイントが必要な場合は、電話番号のみが必要になります。

組織内のユーザーにオンラインで接続されているユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要です。また、エンタープライズボイスに対して有効になっているか、Office 365 通話プランを持っている必要があります。 「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 たとえば、次を実行します。

作成している電話システムサービスがネストされ、電話番号は不要な場合は、次の手順を実行します。

1. リソースアカウントを作成する  
2. 電話システムサービスを作成する
3. リソースアカウントを電話システムサービスに関連付ける

### <a name="create-a-resource-account-with-a-phone-number"></a>電話番号を使用してリソースアカウントを作成する

電話番号を使用するリソースアカウントを作成するには、次の手順を実行する必要があります。

1. 有料または無料の有料サービス番号を取得できます。 この番号は、他のボイスサービスやリソースアカウントに割り当てることはできません。

   リソースアカウントに電話番号を割り当てる前に、既存の有料または無料サービス番号を取得または移植する必要があります。 有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター** > **ボイス** > **電話番号**が表示され、一覧表示される [**番号の種類**] は [サービスとして**無料**] と表示されます。 サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」または「既存のサービス番号を移行する」を参照してください。「 [Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)する」を参照してください。

2. 電話システムのライセンスを購入します。 て  
   - [Office 365 Enterprise E1 および E3](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [Office 365 Enterprise E5](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [Office 365 Enterprise E5 ビジネスソフトウェア](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. 新しいリソースアカウントを作成します。 「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。
4. 電話システムのライセンスをリソースアカウントに割り当てます。 「 [Microsoft Teams ライセンスを割り当て](assign-teams-licenses.md)て、 [1 人のユーザーにライセンスを割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)」を参照してください。
5. サービス番号をリソースアカウントに割り当てます。 「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。
6. 次のいずれかを設定します。
   - [クラウド自動応答](create-a-phone-system-auto-attendant.md)
   - [クラウド通話キュー](create-a-phone-system-call-queue.md)
7. リソースアカウントをサービスに割り当てます。 「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。

### <a name="create-a-resource-account-without-a-phone-number"></a>電話番号のないリソースアカウントを作成する

電話番号を必要としないリソースアカウントを作成する場合は、次の手順で次の作業を行う必要があります。

1. 新しいリソースアカウントを作成します。 「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。
2. 次のいずれかを設定します。
   - [クラウド自動応答](create-a-phone-system-auto-attendant.md)
   - [クラウド通話キュー](create-a-phone-system-call-queue.md)
3. リソースアカウントをサービスに割り当てます。 「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでリソースアカウントを作成する

Microsoft Teams 管理センターを使用して電話システムのライセンスと通話プランを購入した後、[**組織全体の設定** > ]**リソースアカウント**に移動します。

![[リソースアカウント] ページのスクリーンショット](media/r-a-master.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/sfbcallout1.png)

新しいリソースアカウントを作成するには、[ **+ 新しいアカウント**] をクリックします。 ポップアップで、リソースアカウントの表示名とユーザー名 (ドメイン名が自動的に入力されます) を入力し、[**保存**] をクリックします。

![新しいリソースアカウントオプションのスクリーンショット](media/res-acct.png)

次に、「一般[法人向け Office 365 でライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)」の説明に従って、O365 管理センターのリソースアカウントにライセンスを適用します。

### <a name="edit-resource-account-name"></a>リソースアカウント名を編集する

![数字2のアイコン。前のスクリーンショット](media/sfbcallout2.png)で吹き出しを参照すると、[**編集**] オプションを使用してリソースアカウントの表示名を編集できます。  完了したら、[**保存**] をクリックします。
![[リソースアカウントの編集] オプションのスクリーンショット](media/r-a-edit.png)

### <a name="assignunassign-phone-numbers-and-services"></a>電話番号とサービスの割り当て/割り当て解除を行う

![番号3のアイコン、前のスクリーンショット](media/sfbcallout3.png)での吹き出しの参照リソースアカウントを作成してライセンスを割り当てた後、[**割り当て/割り当て解除**] をクリックして、リソースアカウントにサービス番号を割り当てるか、リソースを割り当てることができます。既に存在する自動応答または通話キューのアカウント。 直接ルーティング番号の割り当ては、コマンドレットを使用する場合にのみ行うことができます。 通話キューまたは自動応答をまだ作成する必要がある場合は、作成時にリソースアカウントをリンクすることができます。 完了したら、[**保存**] をクリックします。

リソースアカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、PowerShell を使用する必要があります。次のセクションを参照してください。

> [!IMPORTANT]
> テナントが電話システムのライセンスを持っていない場合は、リソースアカウントに電話番号を割り当てようとしたときに、内部チェックによってエラーが発生します。 電話番号を割り当てたり、リソースアカウントをサービスに関連付けたりすることはできません。

![[割り当て/割り当て解除] オプションのスクリーンショット](media/r-a-assign.png)

## <a name="create-a-resource-account-in-powershell"></a>Powershell でリソースアカウントを作成する

リソースアカウントがオンラインとオンプレミスのどちらであるかに応じて、管理者特権で適切な Powershell プロンプトに接続する必要があります。

- 次の Powershell コマンドレットの例では、リソースアカウントが、オンラインになっているリソースアカウントを作成するために、[新しい-csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使用してオンラインであることが前提となっています。

- Skype For Business Server 2019 でホームオンプレミスのリソースアカウントを使って、クラウド通話キューとクラウド自動応答と共に使用できる場合は、「[クラウド通話キューを構成](/skypeforbusiness/hybrid/configure-call-queue.md)する、[クラウド自動応答を構成](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md)する」を参照してください。 ハイブリッド実装 (直接ルーティングによる番号) では[、CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)が使用されます。

アプリケーションインスタンスの作成時に使う必要があるアプリケーション ID は、次のとおりです。

- **自動応答:** ce933385-9390-45d1-9512-c8d228074e07
- **通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> オンプレミスのユーザーが通話キューまたは自動応答を検索できるようにする場合は、オンラインリソースアカウントが Active Directory に同期されていないため、リソースアカウントをオンプレミスで作成する必要があります。

1. 自動応答で使用するためにオンラインでリソースアカウントを作成するには、次のコマンドを使用します。  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. リソースアカウントは、ライセンスが適用されるまで使用できません。 O365 管理センターのアカウントにライセンスを適用する方法については、「一般[法人向け Office 365 のライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)」および「 [Skype for business のライセンスを割り当てる](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」を参照してください。

3. 省略リソースアカウントに適切なライセンスが適用されたら、以下に示すように、リソースアカウントに電話番号を設定することができます。 すべてのリソースアカウントで電話番号が必要になるわけではありません。 リソースアカウントにライセンスが適用されていない場合、電話番号の割り当ては失敗します。

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

このコマンドの詳細については[、「Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 」を参照してください。

> [!NOTE]
> 前に説明したように、Microsoft Teams 管理センターを使用してオンライン電話番号を設定するのが最も簡単です。

リソースアカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、次のコマンドレットを使用します。

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでリソースアカウント設定を管理する

Microsoft Teams 管理センターでリソースアカウントの設定を管理するには、[**組織全体の設定**  > ]**リソースアカウント**に移動し、設定を変更する必要があるリソースアカウントを選び、[**編集**] ボタンをクリックします。 [**リソースアカウントの編集**] 画面では、次の設定を変更できます。

- アカウントの**表示名**
- アカウントを使う通話キューまたは自動応答
- アカウントに割り当てられている電話番号

完了したら、[**保存**] をクリックします。

## <a name="delete-a-resource-account"></a>リソースアカウントを削除する

サービス番号が保留モードで停止しないようにするには、削除する前に必ず電話番号とリソースアカウントの関連付けを解除してください。 これは、次のレットを使用して行うことができます。

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

この操作を行うと、O365 管理ポータルの [ユーザー] タブでリソースアカウントを削除することができます。

## <a name="troubleshooting"></a>トラブルシューティング

Teams 管理センターのリソースアカウントに割り当てられている電話番号が表示されず、その番号を割り当てることができない場合は、次の点を確認してください。

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Department 属性で Skype for Business アプリケーションエンドポイントが表示される場合は、次のコマンドレットを実行してください。

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```
> [!NOTE]
> Cmldet を実行した後に Teams 管理センターの web ページを更新すると、番号を正しく割り当てることができます。

## <a name="related-information"></a>関連情報

Skype for Business Server とハイブリッドの実装の場合:

[クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[クラウド自動応答の構成](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Teams または Skype for Business Online の実装の場合:

[クラウドの自動応答とは](what-are-phone-system-auto-attendants.md)

[クラウドの自動応答をセットアップする](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[小規模ビジネスの例: 自動応答をセットアップする](/microsoftteams/tutorial-org-aa)

[クラウドの通話キューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[新規-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[新しい Csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
