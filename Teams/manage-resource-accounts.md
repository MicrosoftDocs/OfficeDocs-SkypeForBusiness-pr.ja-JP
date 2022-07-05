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
description: この記事では、Microsoft Teams でリソース アカウントを作成、編集、管理する方法について説明します。
ms.openlocfilehash: 0b8c77f7d6371ba1bfefa9837488415405e48f67
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615803"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams のリソースのアカウントの管理

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>次の手順

リソース アカウントのセットアップが完了し、必要に応じてサービス番号を割り当てると、自動応答または通話キューでリソース アカウントを使用できるようになります。

詳細については、次のリファレンスを参照してください。

- [クラウド自動応答](create-a-phone-system-auto-attendant.md)
- [クラウド呼び出しキュー](create-a-phone-system-call-queue.md)

**[編集]** オプションを使用して、リソース アカウント **の表示名** と **リソース アカウント** の種類を編集できます。 完了したら、[ **保存] をクリックします** 。

## <a name="change-an-existing-resource-account-to-use-a-teams-phone-resource-account-license"></a>Teams Phone リソース アカウント ライセンスを使用するように既存のリソース アカウントを変更する

既存のリソース アカウントのライセンスを Teams 電話スタンダード ライセンスから **Microsoft Teams 電話** **リソース アカウント** ライセンスに切り替える場合は、無料 **の Teams Phone リソース アカウント** ライセンスを取得し、Microsoft 365 管理センターの手順に [従ってユーザーを別のサブスクリプションに移動します](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 常に完全なTeams 電話スタンダード ライセンスを削除し、Microsoft Teams 電話 **リソース アカウント** ライセンスを同じライセンス アクティビティに割り当てます。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加して、アカウント設定をもう一度保存すると、リソース アカウントが期待どおりに機能しなくなる可能性があります。 このような場合は、Microsoft Teams 電話 リソース アカウント ライセンスの新しいリソース アカウントを作成し、破損した **リソース アカウント** を削除することをお勧めします。

## <a name="skype-for-business-server-2019"></a>Skype For Business Server 2019

クラウド通話キューとクラウド自動応答で使用できる Skype For Business Server 2019 にホームされているリソース アカウントについては、「 [クラウド通話キューを計画](/SkypeforBusiness/hybrid/plan-call-queue) する」または「 [クラウドの自動応答を計画する](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)」を参照してください。 ハイブリッド実装 (ダイレクト ルーティングに基づく番号) は、オンプレミスの 2019 サーバー上の [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) コマンドレットを使用Skype for Business Server構成されます。

アプリケーション インスタンスの作成時に使用する必要があるアプリケーション ID は次のとおりです。

- **自動応答:** ce933385-9390-45d1-9512-c8d228074e07
- **通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 通話キューまたは自動応答を Skype For Business Server 2019 ユーザーが検索できるようにするには、オンライン リソース アカウントが Active Directory に同期されないため、Skype For Business Server 2019 でリソース アカウントを作成する必要があります。 sipfederationtls の DNS SRV レコードが Skype for Business Server 2019 に解決される場合は、SfB Management シェルを使用して Skype For Business Server 2019 でリソース アカウントを作成し、Azure AD に同期する **必要があります**。

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
