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
ms.openlocfilehash: f2c7b03f79a29b89c94266359f21571b1994e82a
ms.sourcegitcommit: 4b8350e5bb2ef138dcc0204d764bdf85bae539ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/21/2019
ms.locfileid: "34334928"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams のリソースのアカウントの管理

リソースアカウントは、Azure Active Directory で無効になったユーザーオブジェクトとも呼ばれ、一般にリソースを表すために使用できます。 Exchange では、会議室の代表として使用され、電話番号を割り当てることができます。 リソースアカウントは、Skype for Business server を使って Microsoft 365 またはオンプレミスで使用することができ、これらのアカウントは Powershell コマンドを使用して作成されます。

Microsoft Teams または Skype for Business Online では、各通話キューまたは自動応答に、関連するリソースアカウントが必要です。 リソースアカウントに割り当てられた電話番号が必要かどうかは、関連付けられた通話キューまたは自動応答の用途によって異なります。 リソースアカウントに電話番号を割り当てる前に、この記事の下部にある「通話キューと自動応答」の記事を参照してください。

> [!NOTE]
> この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。 Skype for Business Server 2019 をホームにしたリソースアカウントの場合は、「[クラウド自動応答を構成する](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)」を参照してください。

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>リソースアカウントに電話番号を割り当てるための前提条件

開始するには、次の点を忘れないでください。
  
- 関連付けられているリソースアカウントを持つには、自動応答または通話キューが必要です。 
- リソースアカウントがトップレベルの自動応答または通話キューに割り当てられている場合は、その電話番号が割り当てられている必要があります。 
- 自動応答または通話キューが最上位レベルの自動応答の下に入れ子になっている場合、関連付けられたリソースアカウントには、自動応答と通話キューの構造に複数のエントリポイントが必要な場合は、電話番号のみが必要になります。
- リソースアカウントには、電話番号が割り当てられている必要があります。 入れ子になった自動応答または通話キューでは、電話番号が関連付けられていない場合、自動応答または通話キューの残りのライセンスを取得する必要はありません。
- 直接ルーティングで使用される電話番号を割り当てる場合、Enterprise E1 または E3 ライセンスをお持ちの場合は、電話システムのライセンスを購入して、使用するリソースアカウントに割り当てる必要があります。 Enterprise E5 ライセンスをお持ちの場合、電話システムは既に含まれているため、購入する必要はありません。 
- 代わりに Microsoft サービス番号を割り当てる場合は、電話システムアドオンと通話プラン\(\)を使用して、次のライセンスを取得して、Office 365 Enterprise E1、E3、または E5 に割り当てる必要があります。
- リソースアカウントには、直通ルーティングハイブリッド番号を割り当てることができます。  詳しくは、「[ダイレクトルーティングを計画](direct-routing-plan.md)する」をご覧ください。
- Microsoft の通話プランでは、 **Microsoft Teams 管理センター**で入手した有料および有料サービスの電話番号を割り当てることができます。また、別のサービスプロバイダからリソースアカウントに移植することもできます。 無料サービス番号を取得して使用するには、通信クレジットを設定する必要があります。

> [!NOTE]
> 自動応答と通話キューのリソースアカウントに割り当てられている直接ルーティングサービス番号は、Microsoft Teams ユーザーとエージェントに対してのみサポートされます。
>
> Microsoft は、クラウド自動応答や通話キューなどのアプリケーションに適切なライセンスモデルを開発しています。これで、ユーザーライセンスモデルを使用する必要があります。
>
> 組織内のユーザーにオンラインで接続されているユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要です。また、エンタープライズボイスに対して有効になっているか、Office 365 通話プランを持っている必要があります。 「 [Microsoft Teams ライセンスの割り当て](assign-teams-licenses.md)」を参照してください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 たとえば、次を実行します。
>
> ユーザー (サブスクライバー) の電話番号をリソースアカウントに割り当てることはできません。 サービスの有料電話番号または無料電話番号のみを使用できます。
>
> 米国外の場合は、Microsoft Teams 管理センターを使用してサービス番号を取得することはできません。 「[組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する」に移動して、米国以外の地域での実行方法を確認します。

### <a name="phone-numbers"></a>電話番号

電話番号を使用するリソースアカウントを作成するには、次の手順を実行する必要があります。

1. 有料または無料のサービス番号を転送または取得します。 この番号は、他のボイスサービスやリソースアカウントに割り当てることはできません。

   リソースアカウントに電話番号を割り当てる前に、既存の有料または無料サービス番号を取得または移植する必要があります。 有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター** > **ボイス** > **電話番号**が表示され、一覧表示される [**番号の種類**] は [サービスとして**無料**] と表示されます。 サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」または「既存のサービス番号を移行する」を参照してください。「 [Office 365 に電話番号を転送](transfer-phone-numbers-to-office-365.md)する」を参照してください。

2. 電話システムのライセンスと通話プランを購入します。 て  
   - [Office 365 Enterprise E1 および E3](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [Office 365 Enterprise E5](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [Office 365 Enterprise E5 ビジネスソフトウェア](https://products.office.com/business/office-365-enterprise-e5-business-software)- [の office 365 の通話プラン](calling-plans-for-office-365.md)

3. 新しいリソースアカウントを作成します。 「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。
4. 電話システムのライセンスと通話プランをリソースアカウントに割り当てます。 「 [Microsoft Teams ライセンスを割り当て](assign-teams-licenses.md)て、 [1 人のユーザーにライセンスを割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)」を参照してください。
5. サービス番号をリソースアカウントに割り当てます。 「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。

電話番号を必要としないリソースアカウントでは、手順1、2、5が省略されることがあります。

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでリソースアカウントを作成する

Microsoft Teams 管理センターを使用して電話システムのライセンスと通話プランを購入した後、[**組織全体の設定** > ]**リソースアカウント**に移動します。 

![.asd](media/r-a-master.png)

![数値1](media/sfbcallout1.png)

新しいリソースアカウントを作成するには、[ **+ 新しいアカウント**] をクリックします。 ポップアップで、リソースアカウントの表示名とユーザー名 (ドメイン名が自動的に入力されます) を入力し、[**保存**] をクリックします。

![リソースアカウント](media/res-acct.png)

次に、「一般[法人向け Office 365 でライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)」の説明に従って、O365 管理センターのリソースアカウントにライセンスを適用します。

### <a name="assignunassign-phone-numbers-and-services"></a>電話番号とサービスの割り当て/割り当て解除を行う

![数値 3](media/sfbcallout3.png)リソースアカウントを作成してライセンスを割り当てたら、[**割り当て/割り当て解除**] をクリックして、通話プランサービス番号をリソースアカウントに割り当てるか、またはリソースアカウントを自動応答または通話キューに割り当てることができます。すでに存在します。 直接ルーティング番号の割り当ては、コマンドレットを使用する場合にのみ行うことができます。 通話キューまたは自動応答をまだ作成する必要がある場合は、作成時にリソースアカウントをリンクすることができます。 完了したら、[**保存**] をクリックします。

次のコマンドレットを使用して、直接ルーティング番号を割り当てます。 
``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

> [!IMPORTANT]
> テナントが電話システムのライセンスと通話プランを購入していない場合は、リソースアカウントに電話番号を割り当てようとしたときに、内部チェックによってエラーが発生します。 電話番号を割り当てたり、リソースアカウントをサービスに関連付けたりすることはできません。

![リソースアカウントの割り当て](media/r-a-assign.png)

![番号 2](media/sfbcallout2.png) [**編集**] オプションを使用して、リソースアカウントの表示名を編集できます。  完了したら、[**保存**] をクリックします。
![リソースアカウントを編集する](media/r-a-edit.png)

## <a name="create-a-resource-account-in-powershell"></a>Powershell でリソースアカウントを作成する

Microsoft の通話プランでは、 **Microsoft Teams 管理センター**で入手した有料および有料サービスの電話番号を割り当てることができます。また、別のサービスプロバイダからリソースアカウントに移植することもできます。 無料サービス番号を取得して使用するには、通信クレジットを設定する必要があります。

リソースアカウントがオンラインとオンプレミスのどちらであるかに応じて、管理者特権で適切な Powershell プロンプトに接続する必要があります。 
- 次の Powershell コマンドレットの例では、リソースアカウントが、オンラインになっているリソースアカウントを作成するために、[新しい-csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使用してオンラインであることが前提となっています。

- Skype For Business Server 2019 でホームオンプレミスのリソースアカウントを使って、クラウド通話キューとクラウド自動応答と共に使用できる場合は、「[クラウド通話キューを構成](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md)する、[クラウド自動応答を構成](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md)する」を参照してください。 ハイブリッド実装 (直接ルーティングによる番号) では[、CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)が使用されます。

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
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

このコマンドの詳細については[、「Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 」を参照してください。

> [!NOTE]
> 前に説明したように、Microsoft Teams 管理センターを使用してオンライン電話番号を設定するのが最も簡単です。

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
