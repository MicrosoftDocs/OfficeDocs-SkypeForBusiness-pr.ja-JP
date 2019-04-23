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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: マイクロソフトのチーム内のリソース アカウントの管理についてください。
ms.openlocfilehash: a5b03c8bca7bcc8e012331afe9835a8de6cfe99a
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "31959506"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams のリソースのアカウントの管理

リソース アカウントとも呼ばれる、一般にリソースを表すために使用できます、Azure Active Directory 内の無効なユーザー オブジェクトです。 Exchange ホスト ・ エージェントを使用するには、たとえば、会議室を表すし、電話番号を許可するようにすることがあります。 Microsoft 365 またはビジネス サーバーでは、Skype を使用して社内のリソース アカウントが所属することができ、Powershell コマンドを使用してこれらのアカウントを作成します。

マイクロソフト チームまたは Skype のオンライン ビジネス、各呼び出しキュー、または自動アテンダントに関連するリソース アカウントを持っている必要があります。 リソース アカウントに、割り当てられた電話番号が必要かどうか、関連付けられている呼び出しキューの使用目的に依存しているまたは自動アテンダントです。 呼び出しキューでの記事を参照してくださいし、自動アテンダントのリソース アカウントに電話番号を割り当てる前に、この資料の下部にあるリンクされています。

> [!NOTE]
> この資料は、オンライン ビジネスは、マイクロソフトのチームと Skype の両方に適用されます。

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>リソース アカウントに電話番号を割り当てるための前提条件

開始することに注意することが重要。
  
- 自動アテンダントまたは呼び出しキューは、関連するリソース アカウントを持っている必要があります。 リソース アカウントの詳細については、[チーム内のリソース アカウントの管理](manage-resource-accounts.md)を参照してください。
- 取得し、リソース アカウントに次のライセンスを割り当てる必要があります直接ルーティング番号を割り当てる場合は、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを\)。
- 取得し、リソース アカウントに次のライセンスを割り当てる必要がある場合は代わりに、マイクロソフトのサービス番号を割り当てることは、 \(Office 365 エンタープライズ E1、E3、E5、電話システムのアドオンを呼び出す計画と\)。
- のみ、電話番号が割り当てられているリソース アカウントのライセンスを取得する必要があります。 入れ子になった自動アテンダントまたは呼び出しキューでは自動応答の残りの部分にライセンスを取得またはそれに関連付けられた電話番号がない場合は、キューを呼び出す必要はありません。

> [!NOTE] 
> 直接ルーティング サービス番号の自動アテンダントと時点でのみマイクロソフトのチームのユーザーとエージェントのキューの呼び出しがサポートされています。

> [!NOTE] 
> マイクロソフトは、ユーザー数ライセンス モデルを使用する必要がありますのクラウドの自動応答、通話キューなどのアプリケーションの適切なライセンス ・ モデルの中です。
    
> [!NOTE]
> オンラインにいる人が、組織内への呼び出しをリダイレクトするには、エンタープライズ VoIP を有効にするし、Office 365 のプランを呼び出すことがある、**電話システム**のライセンスが必要です。 [マイクロソフトのチームを割り当てるライセンス](assign-teams-licenses.md)を参照してください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 たとえば、次を実行します。
  
- リソース アカウントに直接ルーティング ハイブリッドの番号を割り当てることができます。  詳細については、[直接ルーティングの計画](direct-routing-plan.md)を参照してください。
- マイクロソフトの通話プランを割り当てることができますのみ有料電話番号と**マイクロソフトのチーム管理センター**にするか、または移植するフリー ダイヤル サービスの電話番号別のサービス プロバイダーからリソース アカウントにします。 取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。

> [!NOTE]
> (サブスクライバー) をユーザーの電話番号は、リソース アカウントに割り当てることができません。 サービスの有料または無料の電話番号のみを使用することができます。

リソース アカウントに電話番号を割り当てる、する必要が取得するか、既存の有料または無料のサービスのポート番号です。 有料または無料のサービスの電話番号を取得した後表示されます**マイクロソフトのチーム管理センター**の > **音声** > **の電話番号**、および記述されている**数値型**は、**サービスのフリー ダイヤル**として一覧表示されます。 サービス番号を取得するには、[取得サービスの電話番号](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)を参照するか、既存のサービス番号に転送する場合は、 [Office 365 に転送電話の番号](transfer-phone-numbers-to-office-365.md)を参照してください。
  
> [!NOTE]
> 米国以外のユーザーは、サービス番号を取得するマイクロソフトのチームの管理センターを使うことはできません。 [組織の電話番号を管理](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)する代わりに、米国の外側から行う方法を参照してください。

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>マイクロソフトのチーム管理センターのリソース アカウントを作成します。

マイクロソフトのチーム管理センターでは、**組織全体の設定**に移動 > **リソースのアカウント**です。 

![asd](media/r-a-master.png)

![番号 1](media/sfbcallout1.png)

新しいリソースを作成するには、アカウント**と新しいアカウント**をクリックします。 、ポップアップで表示名を入力し、(ドメイン名を自動的に設定する必要があります)、リソース アカウントのユーザー名、[**保存**] をクリックします。

![リソース アカウント](media/res-acct.png)

次に、する必要があります、リソース アカウントにライセンスを適用する[ビジネス向けの Office 365 のユーザーにライセンスを割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)で説明するよう

![番号の 3](media/sfbcallout3.png)リソース アカウントを作成したら、ライセンスが割り当てられているをクリックすると、リソース アカウントに電話番号を割り当てるには、**割り当て/割り当て解除**または割り当てリソースのアカウントの自動応答をまたは呼び出しキューが既に存在します。 場合、呼び出しキューまたは自動アテンダントを作成する必要がある、それを作成するときにリソース アカウントをリンクすることができます。 終わったら、[**保存**] をクリックします。

![リソース アカウントを割り当てる](media/r-a-assign.png)

![番号の 2](media/sfbcallout2.png) **の編集**] オプションを使用してリソース アカウントの表示名を編集することができます。  終わったら、[**保存**] をクリックします。
![リソース アカウントを編集します。](media/r-a-edit.png)

## <a name="create-a-resource-account-in-powershell"></a>Powershell でのリソース アカウントを作成します。

マイクロソフトの通話プランを割り当てることができますのみ有料電話番号と**マイクロソフトのチーム管理センター**にするか、または移植するフリー ダイヤル サービスの電話番号別のサービス プロバイダーからリソース アカウントにします。 取得し、サービスのフリー ダイヤル番号を使用して、通信のクレジットを設定する必要があります。

かどうかによって、リソース アカウントにあるオンライン施設内で、適切な管理者特権を持つ Powershell プロンプトに接続する必要があります。 
- [新規 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使用してオンラインのホーム リソース アカウントを作成するのには次の Powershell コマンドレットの例は、リソース アカウントのオンライン ホームをしました。

- リソース アカウント ホーム設置型では、Skype のビジネス サーバー 2019 を呼び出してキューのクラウドとクラウドの自動応答で使用できる、[クラウドを呼び出してキューの構成](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md)や[クラウドの自動応答の構成](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md)を参照してください。 (番号が置かれている直接ルーティング) ハイブリッド実装では、[新しい CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)を使用します。

アプリケーション ID のインスタンスは、アプリケーションの作成時に使用する必要があります。
- **自動応答:** ce933385-9390-45d1-9512-c8d228074e07
- **キューの呼び出し:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 呼び出しキューを選択した場合、または自動アテンダントのオンプレミスのユーザーが検索できるようにする場合は、オンラインのリソース アカウントが Active Directory に同期されていないため、リソース アカウントの設置型を作成してください。

1. 作成するには、オンライン リソース アカウントを使用、自動アテンダントを使用して次のコマンドです。  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. ライセンスを適用するまで、リソース アカウントを使用することはできません。 O365 管理センターのアカウントにライセンスを適用するには、[企業向け Office 365 のユーザーに割り当てるライセンス] を参照してください方法については (https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user [ビジネス ライセンスの Skype を割り当てる](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)とします。

3. (省略可能)リソース アカウントに適切なライセンスが適用されるとは、次のように、リソース アカウントに電話番号を設定できます。 すべてのリソース アカウントには、電話番号が必要となります。 リソース アカウントにライセンスを適用しなかった場合は、電話番号の割り当ては失敗します。

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

このコマンドの詳細については、[一連の CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps)を参照してください。

> [!NOTE]
> 前述のように、マイクロソフトのチーム管理センターを使用してオンラインの電話番号を設定するのには最も簡単です。

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>マイクロソフトのチーム管理センターのリソース アカウントの設定を管理します。

マイクロソフトのチーム管理センターのリソース アカウントの設定を管理する**組織全体の設定**に移動  > **リソース アカウント**、リソース アカウントの設定を変更する必要があり、[**編集**] ボタンをクリックします。 **リソース アカウントの編集**画面で、これらの設定を変更することができます。

- アカウントの**表示名**
- キューを呼び出したり、自動アテンダント アカウントを使用します。
- アカウントに割り当てられた電話番号

終了したら、**保存**をクリックします。

## <a name="related-information"></a>関連情報

ハイブリッド ビジネス サーバーの Skype では、実装。

[クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[クラウド自動応答の構成](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

チームまたは Skype のオンライン ビジネスの実装では。

[クラウドの自動応答とは](what-are-phone-system-auto-attendants.md)

[クラウドの自動応答をセットアップする](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[小規模ビジネスの例: 自動応答をセットアップする](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[クラウドの通話キューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[新しい-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[新しい-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
