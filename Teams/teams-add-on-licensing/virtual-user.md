---
title: Microsoft 365 電話システム–仮想ユーザーライセンス
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: 組織内のリソースアカウントに無料の電話システム (仮想ユーザーライセンスまたは有料電話システムユーザーライセンス) を割り当てる方法について説明します。
ms.openlocfilehash: 5a60e757f4ed9dbca67219217257894a8f95a295
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904789"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 電話システム–仮想ユーザーライセンス 

電話システムライセンスを持つ組織では、無料の Microsoft 365 電話システム–仮想ユーザーライセンス、または有料電話システムユーザーライセンスをリソースアカウントに割り当てることができます。 通話プランは必要ありません。 すべての自動応答または通話キューには、関連するリソースアカウントが必要です。 電話番号が必要なリソースアカウントには、無料の Microsoft 365 電話システム–仮想ユーザーライセンスまたは有料電話システムユーザーライセンスが必要です。その前に電話番号をリソースアカウントに適用することができます。

> [!TIP]
> 入れ子になった自動応答または電話番号が割り当てられていない通話キューと共に使用されるリソースアカウントには、ライセンスは必要ありません。 リファレンスについては、次の図を参照してください。 

![仮想ユーザーライセンス](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>仮想ユーザーライセンスの割り当て

組織では、全体のサイズに応じて、Microsoft 365 電話システム–仮想ユーザーライセンスが割り当てられています。 電話システムや電話システムを含む、少なくとも1つのライセンスを持つ組織には、無料で25の仮想ユーザーライセンスが用意されています。 組織に10個の電話システムユーザーライセンスを追加すると、Microsoft 365 電話システムがさらに1つ増えます。仮想ユーザーライセンスが利用可能になります。

> [!NOTE]
> 電話システムは、Office 365 E1 および E3 で利用可能なアドオンライセンスです。 電話システムは、Office 365 E5 および Microsoft 365 Business Voice ライセンスの一部としても含まれています。

組織で利用可能な無料の Microsoft 365 電話システム–自動応答または通話キューノードを作成するための仮想ユーザーライセンスを使用している場合は、リソースアカウントを使って、有料電話システムのライセンスを使用することができます。 ほとんどの組織には、スケーリングプランに基づいて十分な仮想ユーザーライセンスがあります。 

### <a name="license-allocation-example"></a>ライセンスの割り当ての例

Contoso、Inc. は、電話システム (各従業員に1つ) が含まれている600ライセンスを購入しました。 Contoso には、最初の 25 plus 60 Microsoft 365 電話システム–仮想ユーザーライセンス、85の合計が割り当てられています。 組織には、電話番号を持つ90の通話キューと自動応答があります。 Microsoft 365 のすべての電話システムを割り当てる必要があります。仮想ユーザーライセンスを取得し、5つの標準価格の電話システムライセンスを取得する必要があります。 

Contoso は、自動応答と通話キューシステムを再設計することを検討する必要があります。 使用する電話番号の数が少なく、電話番号を必要としない下位ノードを使用している場合、実装が簡素化され、コストが削減されます。 

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>Microsoft 365 電話システムの購入方法–仮想ユーザーライセンス 

1. Microsoft 365 管理センターにサインインします。
2. **請求** > **書サービス** > **の**アドオンに移動する
3. 最後までスクロールして、 **Microsoft 365 電話システム–仮想ユーザー**ライセンスを探します。 [**今すぐ購入**] を選択します。

> [!NOTE]
> ただし、料金がゼロの場合でも、ライセンスを**購入**する必要があります。 

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 電話システムを使用するように既存のリソースアカウントを変更する–仮想ユーザーライセンス

リソースアカウントのライセンスを電話システムライセンスから Microsoft 365 電話システムに切り替える場合は、仮想ユーザーライセンス: 

1. 新しい Microsoft 365 電話システム–仮想ユーザーライセンスを取得します。 
2. Microsoft 365 管理センターのリンクされた手順に従って、[ユーザーを別のサブスクリプションに移動](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)します。 

> [!WARNING]
> 常に完全な電話システムのライセンスを削除し、Microsoft 365 電話システム–仮想ユーザーライセンスを同じライセンスアクティビティに割り当てます。 古いライセンスを削除した場合は、アカウントの変更を保存し、新しいライセンスを追加してから、アカウント設定をもう一度保存すると、リソースアカウントが予期したとおりに機能しなくなることがあります。 この問題が発生した場合は、Microsoft 365 電話システムの新しいリソースアカウントを作成することをお勧めします。仮想ユーザーライセンスは、破損したリソースアカウントを削除することをお勧めします。 

## <a name="related-information"></a>関連情報

[自動応答と通話キューサービスの更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Microsoft Teams のリソースのアカウントの管理](../manage-resource-accounts.md)
