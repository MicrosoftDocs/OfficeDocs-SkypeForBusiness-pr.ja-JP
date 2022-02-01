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
description: この記事では、リソース アカウントを作成、編集、管理する方法についてMicrosoft Teams。
ms.openlocfilehash: 11ba1600ca1da807711d4bd977abf1adfa09a612
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299032"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams のリソースのアカウントの管理

リソース アカウントは、Azure ADの無効なユーザー オブジェクトであり、一般的なリソースを表す場合に使用できます。 たとえば、会議室を表し、電話番号と予定表Exchangeリソース アカウントを使用できます。 リソース アカウントは、Microsoft 365 2019 を使用して、Skype for Business Serverできます。

このMicrosoft Teams、自動応答または通話キューごとにリソース アカウントが必要です。 リソース アカウントには、サービスの電話番号が割り当て済みである場合があります。 これは、外部の発信者が自動応答または通話キューに到達できるように、Teamsに電話番号を自動応答と通話キューに割り当てる方法です。

この記事では、リソース アカウントを作成し、自動応答と通話キューで使用する準備をする方法について説明します。

この記事の手順を開始する前に、次の手順を実行してください。

- [仮想ユーザー ライセンスの取得](#obtain-virtual-user-licenses)
- [サービス番号を取得する](#obtain-service-numbers)

> [!NOTE]
> リソース アカウントはサインインに対して無効になっているので、そのままにする必要があります。 チャットとプレゼンスは、これらのアカウントでは利用できません。

### <a name="obtain-virtual-user-licenses"></a>仮想ユーザー ライセンスの取得

各リソース アカウントでは、自動応答と通話キューを操作するためにライセンスが必要です。 無料の仮想マシン - *Microsoft 365 電話システム ライセンスを使用* できます。 これらのライセンスを取得するには、仮想ユーザー ライセンス [に関するページを参照してください](teams-add-on-licensing/virtual-user.md)。

この記事の後半では、リソース アカウントにライセンスを割り当てる方法について説明します。

仮想ユーザー ライセンスを取得するには、Microsoft 365 管理センター  >  で **BillingPurchase servicesAdd-on サブスクリプション** > に移動し、最後までスクロールします。「電話システム *- Virtual User* license」と表示されます。 [今すぐ **購入] を選択します**。 コストはかからないが、ライセンスを取得するには引き続き次の手順に従う必要があります。

### <a name="obtain-service-numbers"></a>サービス番号を取得する

サービス番号は自動応答と通話キューでは省略可能ですが、発信者が自動応答と通話キューの構成に到達するには、少なくとも 1 つのサービス番号が必要です。 サービス番号で直接到達できる自動応答または通話キューの場合は、関連付けられたサービス番号を持つリソース アカウントが必要です。

リソース アカウントでは、有料または無料のサービス番号を使用できます。 新しい番号を要求したり、別の運送業者に既存の番号を移植したりすることができます。

新しいサービス番号を取得するには、「 [サービスの電話番号を取得する」を参照してください](getting-service-phone-numbers.md)。

別の携帯電話会社から番号を移植する方法については、「電話番号を他の会社に転送[する」Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。

## <a name="create-a-resource-account"></a>リソース アカウントを作成する

リソース アカウントは、管理センター Teams作成できます。

![リソース アカウントのユーザー インターフェイスの追加のスクリーンショット。](media/resource-account-add.png)

1. 管理センター Teams Voice] を **展開し**、[リソース アカウント] **をクリックします**。

2. **[追加]** をクリックします。

3. [リソース **アカウントの追加] ウィンドウ** で、[表示名 **]、[****ユーザー** 名]、および [リソース アカウントの種類 **] に入力します**。 リソース アカウントの種類は **、このリソース** アカウントの使い方に応じて、自動応答または通話キューのいずれかになります。

4. **[保存]** をクリックします。

![リソース アカウントの一覧のスクリーンショット。](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>ライセンスを割り当てる

リソース アカウントごとに、仮想ユーザー ライセンスまたは仮想ユーザー ライセンスMicrosoft 365 電話システム *割* り当てる *電話システム* があります。

![[ライセンスの割り当て] の [ユーザー インターフェイス] のスクリーンショットMicrosoft 365 管理センター。](media/resource-account-assign-virtual-user-license.png)

1. [Microsoft 365 管理センターで、ライセンスを割り当てるリソース アカウントをクリックします。

2. [ライセンスと **アプリ] タブの** [ライセンス **] で**、[ライセンス - 仮想Microsoft 365 電話システム **] を選択します**。

3. **[変更の保存]** をクリックします。

## <a name="assign-a-service-number"></a>サービス番号を割り当てる

サービス番号を必要とする自動応答または通話キューでリソース アカウントを使用する場合は、リソース アカウントに番号を割り当てる必要があります。

![サービス番号の割り当てユーザー インターフェイスのスクリーンショット。](media/resource-account-assign-phone-number.png)

1. 管理センター Teamsの [リソース アカウント] ページで、サービス番号を割り当てるリソース アカウントを選択し、[割り当て/割り当て解除] **をクリック** します。

2. [数値 **電話ドロップダウンリスト** で、使用する数値の種類を選択します。

3. [割 **り当て済み** 電話番号] ボックスで、使用する番号を検索し、[追加] をクリック **します**。

4. **[保存]** をクリックします。


リソース アカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、PowerShell を使用する必要があります。

`Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting`

## <a name="next-steps"></a>次の手順

リソース アカウントのセットアップを完了し、必要に応じてサービス番号を割り当てると、自動応答または通話キューでリソース アカウントを使用する準備が整います。

次のリファレンスを参照してください。

 - [クラウド自動応答](create-a-phone-system-auto-attendant.md)

 - [クラウド通話キュー](create-a-phone-system-call-queue.md)

[編集] オプションを使用して、リソース アカウント **の** [表示名] と **[リソース** アカウントの種類] **を編集** できます。 完了 **したら、[** 保存] をクリックします。

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>仮想ユーザー ライセンスを使用するために既存のリソース アカウントを変更する

既存のリソース アカウントのライセンスを 電話システム ライセンスから **仮想** ユーザー ライセンスに切り替える場合は、無料の仮想ユーザー ライセンスを取得し、Microsoft 365 管理センター の手順に従ってユーザーを別のサブスクリプションに移動する必要があります。[](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> 常に完全なライセンス 電話システム削除し、同じライセンス アクティビティで仮想ユーザー ライセンスを割り当てる必要があります。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加して、アカウント設定を再度保存すると、リソース アカウントが期待した通り機能しなくなる可能性があります。 このような場合は、仮想ユーザー ライセンスの新しいリソース アカウントを作成し、壊れたリソース アカウントを削除することをお勧めします。

## <a name="skype-for-business-server-2019"></a>Skype For Business Server 2019

クラウド通話キューとクラウド自動応答で使用できる Skype For Business Server 2019 にホームされているリソース アカウントについては、「クラウド通話キューを計画する」または「[](/SkypeforBusiness/hybrid/plan-call-queue)クラウド自動応答を計画する[](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)」を参照してください。 ハイブリッド実装 (ダイレクト ルーティングに含む番号) は、オンプレミスの Skype for Business Server 2019 サーバーで [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) コマンドレットを使用して構成されます。

アプリケーション インスタンスの作成時に使用する必要があるアプリケーションの ID は次のとおりです。

- **自動応答:** ce933385-9390-45d1-9512-c8d228074e07
- **通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Skype For Business Server 2019 ユーザーが通話キューまたは自動応答を検索可能にしたい場合は、オンライン リソース アカウントが Active Directory に同期されないので、Skype For Business Server 2019 でリソース アカウントを作成する必要があります。 sipfederationtls の DNS SRV レコードが Skype for Business Server 2019 に解決された場合、SfB 管理シェルを使用して Skype For Business Server 2019 でリソース アカウントを作成し、Azure AD に同期する必要があります。

アプリケーションとハイブリッドである実装のSkype for Business Server。

   [クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [On-prem リソース アカウントを構成する](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>リソース アカウントを削除する

サービス番号が保留中モードでスタックしないように、リソース アカウントを削除する前に、リソース アカウントから電話番号の関連付け解除を行います。

その後、[ユーザー] タブの [リソース アカウント] Microsoft 365 管理センターリソース アカウントを削除できます。

直接ルーティングの電話番号とリソース アカウントの関連付けを解除するには、次のコマンドレットを使用します。

```powershell
Remove-CsPhoneNumberAssignment -Identity  <Resource Account oid> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
