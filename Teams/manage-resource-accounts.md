---
title: Teams のリソース アカウントを管理する
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: この記事では、Microsoft Teams でリソースアカウントを作成、編集、管理する方法について説明します。
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031023"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams のリソースのアカウントの管理

リソースアカウントは、Azure AD で無効になったユーザーオブジェクトであり、一般的なリソースを表すために使用できます。 たとえば、リソースアカウントを Exchange で使って会議室を表示し、電話番号と予定表を割り当てることができます。 リソースアカウントは、Skype for Business Server 2019 を使って、Microsoft 365 またはオンプレミスのホームにすることができます。

Microsoft Teams では、各自動応答または通話キューにリソースアカウントが必要です。 リソースアカウントには、サービスの電話番号を割り当てることもできます。 これは、外部のチームからの発信者が自動応答または通話キューに到達することを許可する自動応答と通話キューに電話番号を割り当てる方法です。

この記事では、リソースアカウントを作成し、自動応答と通話キューで使用できるようにする方法について説明します。

この記事の手順を開始する前に、次の操作を実行していることを確認します。

- [仮想ユーザーライセンスを取得する](#obtain-virtual-user-licenses)
- [サービス番号を取得する](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>仮想ユーザーライセンスを取得する

自動応答と通話キューを使用するためには、各リソースアカウントにライセンスが必要です。 無料の *Microsoft 365 電話システム仮想ユーザー* ライセンスを使用できます。 これらのライセンスを取得するには、「 [仮想ユーザーライセンス](teams-add-on-licensing/virtual-user.md)」を参照してください。

この記事で後述するリソースアカウントにライセンスを割り当てる方法について説明します。

仮想ユーザーライセンスを取得するには、Microsoft 365 管理センターで [ **課金**  >  **購入サービス**  >  **アドオンサブスクリプション** ] に移動し、[ *電話システム-仮想ユーザー* ライセンス] と表示されるまでスクロールします。 [ **今すぐ購入** ] を選択します。 料金はゼロですが、ライセンスを取得するには、次の手順に従う必要があります。

### <a name="obtain-service-numbers"></a>サービス番号を取得する

サービス番号は自動応答と通話キューではオプションですが、発信者が自動応答と通話キューの構成に到達するためには、少なくとも1つのサービス番号が必要です。 サービス番号によって直接アクセスできるようにする自動応答または通話キューについては、関連付けられたサービス番号を持つリソースアカウントを持っている必要があります。

リソースアカウントでは、有料または無料のサービス番号を使用できます。 別の電話会社から新しい番号を要求するか、既存の電話番号を移植できます。

新しいサービス番号を取得するには、「 [サービスの電話番号を取得](getting-service-phone-numbers.md)する」を参照してください。

別の電話会社の番号を移植するには、「 [電話番号を Teams に転送](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)する」を参照してください。

## <a name="create-a-resource-account"></a>リソースアカウントを作成する

Teams 管理センターでリソースアカウントを作成できます。

![リソースアカウントの追加のユーザーインターフェイスのスクリーンショット](media/resource-account-add.png)

1. Teams 管理センターで、[ **組織全体の設定** ] を展開し、[ **リソースアカウント** ] をクリックします。

2. **[追加]** をクリックします。

3. [ **リソースアカウントの追加** ] ウィンドウで、 **表示名** 、 **ユーザー名** 、 **リソースアカウントの種類** を入力します。 リソースアカウントの種類は、このリソースアカウントの使用方法に応じて、 **自動応答** または **通話キュー** のいずれかになります。

4. [ **保存** ] をクリックします。

![リソースアカウントの一覧のスクリーンショット](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>ライセンスを割り当てる

リソースアカウントごとに、 *Microsoft 365 電話システム仮想ユーザー* ライセンスまたは *電話システム* ライセンスを割り当てる必要があります。

![Microsoft 365 管理センターのライセンスの割り当てユーザーインターフェイスのスクリーンショット](media/resource-account-assign-virtual-user-license.png)

1. Microsoft 365 管理センターで、ライセンスを割り当てるリソースアカウントをクリックします。

2. [ **ライセンスとアプリ** ] タブの [ **ライセンス** ] で、[ **Microsoft 365 Phone システム仮想ユーザー** ] を選択します。

3. [ **Save changes** ] をクリックします。

## <a name="assign-a-service-number"></a>サービス番号を割り当てる

自動応答または通話キューでサービス番号を必要とするリソースアカウントの使用を計画している場合は、リソースアカウントに番号を割り当てます。

![サービス番号の割り当てユーザーインターフェイスのスクリーンショット](media/resource-account-assign-phone-number.png)

1. Teams 管理センターの [ **リソースアカウント** ] ページで、サービス番号を割り当てるリソースアカウントを選び、[ **割り当て/割り当て解除** ] をクリックします。

2. [ **電話番号の種類** ] ドロップダウンで、使用する番号の種類を選択します。

3. [ **割り当てられた電話番号** ] ボックスで、使用する番号を検索して [ **追加** ] をクリックします。

4. [ **保存** ] をクリックします。


リソースアカウントに直接ルーティングまたはハイブリッド番号を割り当てるには、PowerShell を使用する必要があります。

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>次のステップ

リソースアカウントの設定が完了し、必要に応じてサービス番号を割り当てると、自動応答または通話キューでリソースアカウントを使用できるようになります。

次の参考資料を参照してください。

 - [クラウド自動応答](create-a-phone-system-auto-attendant.md)

 - [クラウド通話キュー](create-a-phone-system-call-queue.md)

[ **編集** ] オプションを使用して、リソースアカウントの **表示名** と **リソースアカウント** の種類を編集できます。 完了したら、[ **保存** ] をクリックします。

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>仮想ユーザーライセンスを使用するように既存のリソースアカウントを変更する

既存のリソースアカウントのライセンスを **電話システム** のライセンスから仮想ユーザーライセンスに切り替える場合は、無料の仮想ユーザーライセンスを取得してから、Microsoft 365 管理センターの手順に従って、 [ユーザーを別のサブスクリプションに移動](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)する必要があります。

> [!WARNING]
> 常に完全な電話システムのライセンスを削除し、同じライセンスアクティビティに仮想ユーザーライセンスを割り当てます。 古いライセンスを削除した場合は、アカウントの変更を保存し、新しいライセンスを追加してから、アカウント設定をもう一度保存すると、リソースアカウントが予期したとおりに機能しなくなることがあります。 この問題が発生した場合は、仮想ユーザーライセンス用の新しいリソースアカウントを作成し、破損したリソースアカウントを削除することをお勧めします。

## <a name="skype-for-business-server-2019"></a>Skype For Business Server 2019

クラウド通話キューとクラウド自動応答で使用できる Skype For Business Server 2019 上のリソースアカウントの場合は、「 [クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue) 」または「 [クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)」を参照してください。 ハイブリッド実装 (直接ルーティングによる番号) は、オンプレミスの Skype for Business Server 2019 サーバー上の [CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) コマンドレットを使用して構成されます。

アプリケーションインスタンスの作成時に使用する必要があるアプリケーション Id は、次のとおりです。

- **自動応答:** ce933385-9390-45d1-9512-c8d228074e07
- **通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Skype For Business Server 2019 ユーザーが通話キューまたは自動応答を検索できるようにするには、オンラインリソースアカウントが Active Directory に同期されていないため、Skype For Business Server 2019 でリソースアカウントを作成する必要があります。 Sipfederationtls 用の DNS SRV レコードが Skype for Business Server 2019 に解決された場合、SfB 管理シェルを使用して、Azure AD に同期されるように、Skype For Business Server 2019 でリソースアカウントを作成する **必要があり** ます。

Skype for Business Server とハイブリッドの実装の場合:

   [クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [オンプレミスのリソースアカウントを構成する](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>リソースアカウントを削除する

サービス番号が保留モードで停止しないようにするには、削除する前に必ず電話番号とリソースアカウントの関連付けを解除してください。

この操作を行うと、Microsoft 365 管理センターの [ユーザー] タブでリソースアカウントを削除することができます。

リソースアカウントから直接ルーティングする電話番号との関連付けを解除するには、次のコマンドレットを使用します。

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
