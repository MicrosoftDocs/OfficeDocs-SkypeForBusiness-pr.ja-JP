---
title: Teams のリソース アカウントを管理する
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
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
ms.openlocfilehash: b9c7f5575d5e6df4370c07bf1cd581cbd1a396dd
ms.sourcegitcommit: 9504b7a67e593f5575060b09b69817325e2a1f77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2022
ms.locfileid: "69111134"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams のリソースのアカウントの管理

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>次の手順

リソース アカウントのセットアップを完了し、必要に応じてサービス番号を割り当てると、自動応答または通話キューでリソース アカウントを使用する準備が整います。

詳細については、次の参照を参照してください。

- [クラウド自動応答](create-a-phone-system-auto-attendant.md)
- [クラウド呼び出しキュー](create-a-phone-system-call-queue.md)

[編集] オプションを使用して、リソース アカウント **の [表示名** ] と **[リソース アカウント** の種類 **] を編集** できます。 完了したら、[ **保存] をクリックします** 。

## <a name="change-an-existing-resource-account-to-use-a-teams-phone-resource-account-license"></a>Teams Phone リソース アカウント ライセンスを使用するように既存のリソース アカウントを変更する
既存のリソース アカウントのライセンスを **Teams 電話スタンダード** ライセンスから Microsoft Teams 電話 **リソース アカウント** ライセンスに切り替えるには、**Teams 電話リソース アカウント** ライセンスを取得し、Microsoft 365 管理センターの手順に従ってユーザーを別のリソース アカウント [に移動するサブスクリプション](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 常に完全なTeams 電話スタンダード ライセンスを削除し、同じライセンス アクティビティ **でMicrosoft Teams 電話リソース アカウント** ライセンスを割り当てます。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加してから、アカウント設定をもう一度保存すると、リソース アカウントが期待どおりに機能しなくなる可能性があります。 その場合は、**Microsoft Teams 電話 リソース アカウント** ライセンスの新しいリソース アカウントを作成し、壊れたリソース アカウントを削除することをお勧めします。

## <a name="skype-for-business-server-2019"></a>Skype For Business Server 2019

クラウド通話キューとクラウド自動応答で使用できる Skype For Business Server 2019 に所属するリソース アカウントについては、「 [クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue) 」または「 [クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)」を参照してください。 ハイブリッド実装 (ダイレクト ルーティングに基づく番号) は、オンプレミスの Skype for Business Server 2019 サーバー上の [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) コマンドレットを使用して構成されます。

アプリケーション インスタンスの作成時に使用する必要があるアプリケーション ID は次のとおりです。

- **自動応答:** ce933385-9390-45d1-9512-c8d228074e07
- **通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Skype For Business Server 2019 ユーザーが通話キューまたは自動応答を検索できるようにする場合は、オンライン リソース アカウントが Active Directory に同期されないため、Skype For Business Server 2019 でリソース アカウントを作成する必要があります。 sipfederationtls の DNS SRV レコードが 2019 Skype for Business Serverに解決される場合、リソース アカウントは SfB Management シェルを使用して Skype For Business Server 2019 で作成し、Azure AD に同期する **必要があります**。

Skype for Business Serverとハイブリッドな実装の場合:

   [クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue)

   [オンプレミス リソース アカウントを構成する](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>リソース アカウントを削除する

リソース アカウントから電話番号を削除する前に、電話番号の関連付けを解除して、サービス番号が保留中のモードでスタックしないようにしてください。

その後、Microsoft 365 管理センターの [ユーザー] タブでリソース アカウントを削除できます。

リソース アカウントから直接ルーティング電話番号の関連付けを解除するには、次のコマンドレットを使用します。

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
