---
title: Teams のリソース アカウントを管理する
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: この記事では、Microsoft Teamsでリソース アカウントを作成、編集、管理する方法について説明します。
ms.openlocfilehash: cb89621d6049106cb090d72244644a4b14565657
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592712"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams のリソースのアカウントの管理

Microsoft Teamsでは、自動応答または通話キューごとにリソース アカウントが必要です。 リソース アカウントには、サービス電話番号を割り当てることもできます。 これは、自動応答と通話キューに電話番号を割り当てる方法です。これにより、外部の発信者が自動応答または通話キューに到達Teams。

この記事では、リソース アカウントを作成し、自動応答と呼び出しキューで使用できるように準備する方法について説明します。

この記事の手順を開始する前に、次のことを行っていることを確認します。

- [仮想ユーザー ライセンスを取得する](#obtain-virtual-user-licenses)
- [サービス番号を取得する](#obtain-service-numbers)

> [!NOTE]
> 自動応答と呼び出しキューに使用されるリソース アカウントは、サインインのために無効になっているため、そのままにする必要があります。 チャットとプレゼンスは、これらのアカウントでは利用できません。

### <a name="obtain-virtual-user-licenses"></a>仮想ユーザー ライセンスを取得する

各リソース アカウントには、自動応答と呼び出しキューを操作するためにライセンスが必要です。 *無料のMicrosoft 365 電話システム - 仮想ユーザー ライセンスを* 使用できます。 これらのライセンスを取得するには、 [仮想ユーザー ライセンスに関するページを](teams-add-on-licensing/virtual-user.md)参照してください。

この記事の後半で、リソース アカウントにライセンスを割り当てる方法について説明します。

仮想ユーザー ライセンスを取得するには、Microsoft 365 管理センターで **BillingPurchase** >  **servicesAdd-on** >  サブスクリプションに移動し、最後までスクロールすると *、電話システム - 仮想ユーザー* ライセンスが表示されます。 [ **今すぐ購入]** を選択します。 コストはゼロですが、ライセンスを取得するには、次の手順に従う必要があります。

### <a name="obtain-service-numbers"></a>サービス番号を取得する

自動応答と通話キューではサービス番号は省略可能ですが、発信者が自動応答と通話キューの構成に到達するには、少なくとも 1 つのサービス番号が必要です。 サービス番号で直接到達する自動応答または通話キューの場合は、関連付けられたサービス番号を持つリソース アカウントが必要です。

リソース アカウントでは、有料または無料のサービス番号を使用できます。 新しい番号を要求したり、別の通信事業者に既存の番号を移植したりできます。

新しいサービス番号を取得するには、「 [サービス電話番号の取得](getting-service-phone-numbers.md)」を参照してください。

別の通信事業者から番号を移植するには、「[電話番号をTeamsに転送する」を](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)参照してください。

## <a name="create-a-resource-account"></a>リソース アカウントを作成する

Teams管理センターでリソース アカウントを作成できます。

![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット。](media/resource-account-add.png)

1. Teams管理センターで **[音声**]、[**リソース アカウント**] の順にクリックします。

2. **[追加]** をクリックします。

3. [ **リソース アカウントの追加]** ウィンドウで、 **表示名**、 **ユーザー名**、リソース **アカウントの種類** を入力します。 リソース アカウントの種類は、このリソース アカウントの使用方法に応じて、 **自動応答** または **通話キュー** のいずれかになります。

4. **[保存]** をクリックします。

![リソース アカウントの一覧のスクリーンショット。](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>ライセンスを割り当てる

リソース アカウントごとに、*仮想ユーザー* ライセンスまたは電話システム ライセンスの *Microsoft 365 電話システム* を割り当てる必要があります。

![Microsoft 365 管理センターのライセンスの割り当てユーザー インターフェイスのスクリーンショット。](media/resource-account-assign-virtual-user-license.png)

1. Microsoft 365 管理センターで、ライセンスを割り当てるリソース アカウントをクリックします。

2. [**ライセンスとアプリ**] タブの [**ライセンス**] で、[**Microsoft 365 電話システム - 仮想ユーザー**] を選択します。

3. **[変更の保存]** をクリックします。

## <a name="assign-a-service-number"></a>サービス番号を割り当てる

サービス番号を必要とする自動応答または通話キューでリソース アカウントを使用する予定がある場合は、リソース アカウントに番号を割り当てます。

![サービス番号の割り当てユーザー インターフェイスのスクリーンショット。](media/resource-account-assign-phone-number.png)

1. Teams管理センターの [**リソース アカウント**] ページで、サービス番号を割り当てるリソース アカウントを選択し、[**割り当て/割り当て解除**] をクリックします。

2. **[電話番号の種類**] ドロップダウンで、使用する番号の種類を選択します。

3. [ **割り当てられた電話番号** ] ボックスで、使用する番号を検索し、[ **追加**] をクリックします。

4. **[保存]** をクリックします。


リソース アカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、PowerShell を使用する必要があります。

```powershell
Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting
```

## <a name="next-steps"></a>次のステップ

リソース アカウントのセットアップが完了し、必要に応じてサービス番号を割り当てると、自動応答または通話キューでリソース アカウントを使用できるようになります。

次のリファレンスを参照してください。

 - [クラウド自動応答](create-a-phone-system-auto-attendant.md)

 - [クラウド呼び出しキュー](create-a-phone-system-call-queue.md)

**[編集]** オプションを使用して、リソース アカウント **の表示名** と **リソース アカウント** の種類を編集できます。 完了したら、[ **保存] をクリックします** 。

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>仮想ユーザー ライセンスを使用するように既存のリソース アカウントを変更する

既存のリソース アカウントのライセンスを **電話システム** ライセンスから仮想ユーザー ライセンスに切り替える場合は、無料の仮想ユーザー ライセンスを取得し、Microsoft 365 管理センターの手順に従って [ユーザーを別のサブスクリプションに移動する必要があります](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 常に完全な電話システム ライセンスを削除し、同じライセンス アクティビティで仮想ユーザー ライセンスを割り当てます。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加して、アカウント設定をもう一度保存すると、リソース アカウントが期待どおりに機能しなくなる可能性があります。 このような場合は、仮想ユーザー ライセンスの新しいリソース アカウントを作成し、壊れたリソース アカウントを削除することをお勧めします。

## <a name="skype-for-business-server-2019"></a>Skype For Business Server 2019

クラウド通話キューとクラウド自動応答で使用できる Skype For Business Server 2019 にホームされているリソース アカウントについては、「[クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue)」または「[クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)」を参照してください。 ハイブリッド実装 (ダイレクト ルーティングに基づく番号) は、オンプレミスの 2019 サーバー上の [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) コマンドレットを使用Skype for Business Server構成されます。

アプリケーション インスタンスの作成時に使用する必要があるアプリケーション ID は次のとおりです。

- **自動応答:** ce933385-9390-45d1-9512-c8d228074e07
- **通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 通話キューまたは自動応答を Skype For Business Server 2019 ユーザーが検索できるようにするには、オンライン リソース アカウントが Active Directory に同期されないため、Skype For Business Server 2019 でリソース アカウントを作成する必要があります。 sipfederationtls の DNS SRV レコードが Skype for Business Server 2019 に解決される場合は、SfB Management シェルを使用して Skype For Business Server 2019 にリソース アカウントを作成し、Azure ADに同期する **必要があります**。

Skype for Business Serverとハイブリッドである実装の場合:

   [クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [オンプレミスのリソース アカウントを構成する](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>リソース アカウントを削除する

サービス番号が保留中モードで停止しないように、リソース アカウントから電話番号を削除する前に、電話番号を関連付け解除してください。

その後、Microsoft 365 管理センターの [ユーザー] タブでリソース アカウントを削除できます。

リソース アカウントから直接ルーティング電話番号の関連付けを解除するには、次のコマンドレットを使用します。

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
