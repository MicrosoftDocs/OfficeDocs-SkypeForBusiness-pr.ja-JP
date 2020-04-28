---
title: Teams のリソース アカウントを管理する
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: この記事では、Microsoft Teams でリソースアカウントを作成、編集、管理する方法について説明します。
ms.openlocfilehash: 07f6f15f3ed3fc1e115ae672ef1eac89b5eab12f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905009"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams のリソースのアカウントの管理

リソースアカウントは、Azure AD で*無効になったユーザーオブジェクト*とも呼ばれ、一般にリソースを表すために使うことができます。 Exchange では、会議室の代表として使用され、電話番号を割り当てることができます。 リソースアカウントは、Skype for Business Server 2019 を使って、Microsoft 365 またはオンプレミスのホームにすることができます。

Microsoft Teams または Skype for Business Online では、各電話システムの通話キューまたは自動応答に、少なくとも1つのリソースアカウントが含まれている必要があります。 リソースアカウントが割り当てられた電話番号を必要とするかどうかは、次の図に示すように、関連付けられた通話キューまたは自動応答の用途によって異なります。 また、リソースアカウントに電話番号を割り当てる前に、この記事の下部にある通話キューと自動応答の記事を参照することもできます。

![リソースアカウントとユーザーライセンスの例](media/resource-account.png)

> [!NOTE]
> この記事は、Microsoft Teams と Skype for Business Online の両方に適用されます。 Skype for Business Server 2019 を使用しているリソースアカウントの場合は、「[リソースアカウントを構成する](/SkypeForBusiness/hybrid/configure-onprem-ra)」を参照してください。

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a>電話システムの通話キューに電話番号を割り当てる

組織が既に少なくとも1つの電話システムライセンスを使用している場合、電話システムの通話キューに電話番号を割り当てるには、次の手順を実行します。

1. サービス番号を取得します。
2. リソースアカウントまたは電話システムのライセンスと共に使用する、無料の電話システム[仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md)または有料電話システムライセンスを取得します。
3. リソースアカウントを作成します。 関連付けられているリソースアカウントを持つには、自動応答または通話キューが必要です。
4. 電話システムまたは電話システム仮想ユーザーライセンスをリソースアカウントに割り当てます。
5. ライセンスを割り当てたリソースアカウントにサービスの電話番号を割り当てます。
6. 電話システムの通話キューまたは自動応答を作成する
7. リソースアカウントを通話キューまたは自動応答にリンクします。

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

自動応答または通話キューが最上位レベルの自動応答の下に入れ子になっている場合、関連付けられたリソースアカウントには、自動応答と通話キューの構造に複数のエントリポイントが必要な場合は、電話番号のみが必要になります。

組織内のユーザーにオンラインで接続されているユーザーに通話をリダイレクトするには、**電話システム**のライセンスが必要です。また、エンタープライズボイスに対して有効になっているか、Office 365 通話プランを持っている必要があります。 [Assign Microsoft Teams ライセンスを割り当てる](assign-teams-licenses.md) を参照してください。 エンタープライズ VoIP を有効にするには、Windows PowerShell を使用できます。 たとえば、次のように実行します。`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

> [!WARNING]
> リソースアカウントで問題が発生しないようにするには、次の手順を順番に実行します。

作成している電話システムの通話キューまたは自動応答がネストされ、電話番号が必要ない場合は、次の手順を実行します。

1. リソースアカウントを作成する
2. 電話システムの通話キューまたは自動応答を作成する
3. リソースアカウントを電話システムの通話キューまたは自動応答に関連付ける

### <a name="create-a-resource-account-with-a-phone-number"></a>電話番号を使用してリソースアカウントを作成する

<a name="phonenumber"> </a>

> [!IMPORTANT]
> 電話番号は、自動応答または通話キューに直接割り当てられるのではなく、自動応答または通話キューに関連付けられているリソースアカウントに割り当てられます。

トップレベルの自動応答または通話キューでは、電話番号を自動応答にリンクさせる必要があります。 電話番号を使用するリソースアカウントを作成するには、次の手順を実行します。

1. 有料または無料の有料サービス番号を取得できます。 この番号は、他のボイスサービスやリソースアカウントに割り当てることはできません。

   リソースアカウントに電話番号を割り当てる前に、既存の有料または無料サービス番号を取得または移植する必要があります。 有料またはフリーダイヤルのサービス電話番号を取得すると、 **Microsoft Teams 管理センター** > **のボイス** > **電話番号**が表示され、**番号の種類**は [**サービスの有料**電話] と表示されます。 サービス番号を取得するには、「[サービスの電話番号を取得](getting-service-phone-numbers.md)する」または「既存のサービス番号を移行する」を参照してください。「[チームに電話番号を移行](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)する」をご覧ください。

   リソースアカウントに電話番号を割り当てる場合は、無料電話システムの仮想ユーザーライセンスを使用できるようになりました。 これにより、組織レベルで電話番号に電話システム機能が提供され、自動応答と通話キュー機能を作成できます。

2. 電話システムの仮想ユーザーライセンスまたは通常の電話システムのライセンスを取得します。

   仮想ユーザーライセンスを取得するには、Microsoft 365 管理センターから開始し、[**課金** > **購入サービス** > **アドオンサブスクリプション**] に移動して、"電話システム-仮想ユーザー" ライセンスが表示されます。 [**今すぐ購入**] を選択します。 料金はゼロですが、ライセンスを取得するには、次の手順に従う必要があります。
3. 新しいリソースアカウントを作成します。 「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。
4. 電話システムの[仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md)または電話システムのライセンスをリソースアカウントに割り当てます。 「 [Microsoft Teams ライセンスを割り当て](assign-teams-licenses.md)て、 [1 人のユーザーにライセンスを割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user)」を参照してください。
5. サービス番号をリソースアカウントに割り当てます。 「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。
6. 次のいずれかを設定します。
   - [クラウド自動応答](create-a-phone-system-auto-attendant.md)
   - [クラウド通話キュー](create-a-phone-system-call-queue.md)
7. リソースアカウントを自動応答または通話キューにリンクします。 「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。

自動応答の作成中にリソースアカウントを作成すると、ライセンスが自動的に適用されます。

### <a name="create-a-resource-account-without-a-phone-number"></a>電話番号のないリソースアカウントを作成する

入れ子になった自動応答または通話キューにはリソースアカウントが必要ですが、多くの場合、対応するリソースアカウントには電話番号とライセンスが必要であり、電話番号をサポートする必要はありません。 電話番号を必要としないリソースアカウントを作成する場合は、次の手順で次の作業を行う必要があります。

1. 新しいリソースアカウントを作成します。 「 [Microsoft Teams 管理センターでリソースアカウントを作成](#create-a-resource-account-in-microsoft-teams-admin-center)する」または「 [Powershell でリソースアカウントを作成](#create-a-resource-account-in-powershell)する」を参照してください。
2. 次のいずれかを設定します。
   - [クラウド自動応答](create-a-phone-system-auto-attendant.md)
   - [クラウド通話キュー](create-a-phone-system-call-queue.md)
3. リソースアカウントを通話キューまたは自動応答に割り当てます。 「[電話番号とサービスの割り当て/割り当て解除」を](#assignunassign-phone-numbers-and-services)参照してください。


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでリソースアカウントを作成する

電話システムのライセンスを購入した後、Microsoft Teams 管理センターを使用して、[**組織全体の設定** > ]**リソースアカウント**に移動します。

![[リソースアカウント] ページのスクリーンショット](media/r-a-master.png)

![前のスクリーンショットで吹き出しを参照する数値1のアイコン](media/teamscallout1.png)

新しいリソースアカウントを作成するには、[ **+ 追加**] をクリックします。 ポップアップで、**表示名**、**ユーザー名**(ドメイン名が自動的に設定される必要があります)、リソースアカウントの**リソースアカウントの種類**を入力します。 リソースアカウントの種類には、リソースアカウントに関連付けるアプリに応じて、**自動応答**または**通話キュー**のいずれかを使うことができます。 準備ができたら、[**保存**] をクリックします。

![新しいリソースアカウントオプションのスクリーンショット](media/res-acct.png)

次に、「一般[法人向け Office 365 でライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)」の説明に従って、O365 管理センターのリソースアカウントにライセンスを適用します。

### <a name="edit-resource-account"></a>リソースアカウントを編集する 

![数字 2](media/teamscallout2.png)のアイコン。前のスクリーンショットで吹き出しを参照すると、[**編集**] オプションを使用してリソースアカウントの**表示名**と**リソースアカウント**の種類を編集できます。 完了したら、[**保存**] をクリックします。

![[リソースアカウントの編集] オプションのスクリーンショット](media/r-a-edit.png)

<a name="phonenumber"> </a>

### <a name="assignunassign-phone-numbers-and-services"></a>電話番号とサービスの割り当て/割り当て解除を行う

![番号3のアイコン、前のスクリーンショット](media/teamscallout3.png)で吹き出しを参照するリソースアカウントを作成してライセンスを割り当てた後、[**割り当て/割り当て解除**] をクリックして、リソースアカウントにサービス番号を割り当てるか、電話番号の種類を設定するか、または既に存在する特定の自動応答または通話キューにリソースアカウントを割り当てます。 直接ルーティング番号の割り当ては、コマンドレットを使用する場合にのみ行うことができます。 リソースアカウントに関連付ける通話キューまたは自動応答をまだ作成していない場合は、このフィールドを空白のままにします。 リソースアカウントを作成するときに、リンクを設定することができます。 完了したら、[**保存**] をクリックします。

**電話番号の種類**のオプションは次のとおりです。

- なし
- オンライン
- フリーダイヤル
- オンプレミス

![[割り当て/割り当て解除] オプションのスクリーンショット](media/r-a-assign.png)

リソースアカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、PowerShell を使用する必要があります。次のセクションを参照してください。

> [!IMPORTANT]
> リソースアカウントに有効なライセンスがない場合は、リソースアカウントに電話番号を割り当てようとしたときに、内部チェックによってエラーが発生します。 番号を割り当てることも、リソースアカウントを通話キューまたは自動応答に関連付けることもできません。

> [!IMPORTANT]
> 電話番号は、自動応答または通話キューに直接割り当てられるのではなく、自動応答または通話キューに関連付けられているリソースアカウントに割り当てられます。



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>仮想ユーザーライセンスを使用するように既存のリソースアカウントを変更する

既存のリソースアカウントのライセンスを電話システムのライセンスから仮想ユーザーライセンスに切り替える場合は、無料の仮想ユーザーライセンスを取得してから、Microsoft 365 管理センターのリンクされた手順に従って、[ユーザーを別のサブスクリプションに移動](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)する必要があります。 

> [!WARNING]
> 常に完全な電話システムのライセンスを削除し、同じライセンスアクティビティに仮想ユーザーライセンスを割り当てます。 古いライセンスを削除した場合は、アカウントの変更を保存し、新しいライセンスを追加してから、アカウント設定をもう一度保存すると、リソースアカウントが予期したとおりに機能しなくなることがあります。 この問題が発生した場合は、仮想ユーザーライセンス用の新しいリソースアカウントを作成し、破損したリソースアカウントを削除することをお勧めします。 

## <a name="create-a-resource-account-in-powershell"></a>Powershell でリソースアカウントを作成する

リソースアカウントがオンラインであるか、Skype for Business Server 2019 にあるかに応じて、管理者特権で適切な Powershell プロンプトに接続する必要があります。

- 次の Powershell コマンドレットの例は、[新しい-csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps)を使って、オンラインでホームリソースアカウントを作成する方法を示しています。 

- クラウド通話キューとクラウド自動応答で使用できる Skype For Business Server 2019 上のリソースアカウントの場合は、「[クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue)」または「[クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)」を参照してください。 ハイブリッド実装 (直接ルーティングによる番号) は、オンプレミスの Skype for Business Server 2019 サーバー上の[CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)コマンドレットを使用して構成されます。

アプリケーションインスタンスの作成時に使う必要があるアプリケーション ID は、次のとおりです。

- **自動応答:** ce933385-9390-45d1-9512-c8d228074e07
- **通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Skype For Business Server 2019 ユーザーが通話キューまたは自動応答を検索できるようにするには、オンラインリソースアカウントが Active Directory に同期されていないため、Skype For Business Server 2019 でリソースアカウントを作成する必要があります。 Sipfederationtls 用の DNS SRV レコードが Skype for Business Server 2019 に解決される場合は、SfB 管理シェルを使用して、オンライン Azure AD に同期されるように、Skype For Business Server 2019 でリソースアカウントを作成する**必要があり**ます。

 

1. 自動応答で使用するためにオンラインでリソースアカウントを作成するには、次のコマンドを使用します。

    ``` Powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
    ```

2. リソースアカウントは、ライセンスが適用されるまで使用できません。 O365 管理センターのアカウントにライセンスを適用する方法については、「一般[法人向け Office 365 のライセンスをユーザーに割り当てる](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user)」および「 [Skype for business のライセンスを割り当てる](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)」を参照してください。

3. 省略リソースアカウントに適切なライセンスが適用されると、次に示すように、リソースアカウントに電話番号を割り当てることができます。 すべてのリソースアカウントで電話番号が必要になるわけではありません。 リソースアカウントにライセンスが適用されていない場合、電話番号の割り当ては失敗します。

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   このコマンドの詳細については[、「Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) 」を参照してください。

   > [!NOTE]
   > 前に説明したように、Microsoft Teams 管理センターを使用してオンライン電話番号を設定するのが最も簡単です。

   Microsoft Teams または Skype For Business Server 2019 でのリソースアカウントに直接ルーティング電話番号を割り当てるには、次のコマンドレットを使用して Skype for Business Online Powershell を使用します。

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Microsoft Teams 管理センターでリソースアカウント設定を管理する

Microsoft Teams 管理センターでリソースアカウントの設定を管理するには、[**組織全体の設定** > ]**リソースアカウント**に移動し、設定を変更する必要があるリソースアカウントを選び、[**編集**] ボタンをクリックします。 [**リソースアカウントの編集**] 画面では、次の設定を変更できます。

- アカウントの**表示名**
- アカウントを使う通話キューまたは自動応答
- アカウントに割り当てられている電話番号

完了したら、[**保存**] をクリックします。

## <a name="delete-a-resource-account"></a>リソースアカウントを削除する

サービス番号が保留モードで停止しないようにするには、削除する前に必ず電話番号とリソースアカウントの関連付けを解除してください。 これは、次のレットを使用して行うことができます。

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

この操作を行うと、O365 管理ポータルの [ユーザー] タブでリソースアカウントを削除することができます。

リソースアカウントから直接ルーティングする電話番号との関連付けを解除するには、次のコマンドレットを使用します。

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a>トラブルシューティング

Teams 管理センターのリソースアカウントに割り当てられている電話番号が表示されず、その番号を割り当てることができない場合は、次の点を確認してください。

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

Department 属性で Skype for Business アプリケーションエンドポイントが表示される場合は、次のコマンドレットを実行してください。

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> Cmldet を実行した後に Teams 管理センターの web ページを更新すると、番号を正しく割り当てることができます。

## <a name="related-information"></a>関連情報

Skype for Business Server とハイブリッドの実装の場合:

   [クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [オンプレミスのリソースアカウントを構成する](/SkypeForBusiness/hybrid/configure-onprem-ra)


Teams または Skype for Business Online の実装の場合:

   [クラウドの自動応答とは](what-are-phone-system-auto-attendants.md)

   [クラウドの自動応答をセットアップする](/microsoftteams/create-a-phone-system-auto-attendant)

   [小規模ビジネスの例: 自動応答をセットアップする](/microsoftteams/tutorial-org-aa)

   [クラウドの通話キューを作成する](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[新規-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[新しい Csonline Applicationinstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[電話システム-仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md)
