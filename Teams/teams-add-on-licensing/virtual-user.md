---
title: '電話システム–仮想ユーザーライセンス '
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
description: 無料の仮想ユーザーライセンスについて説明します。
ms.openlocfilehash: 73edbae2fce7cdb2ed1fd5c499d58153d91e7086
ms.sourcegitcommit: 5f3c8ea2b3d68704885d212c8f2787c6bc7d1cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "35907674"
---
# <a name="phone-systemvirtual-user-license"></a>電話システム–仮想ユーザーライセンス 

2019年7月2日以降、電話システムライセンスを持つ組織は、無料の電話システム (仮想ユーザーライセンスまたは有料電話システムユーザーライセンス) を取得して、リソースアカウントに割り当てることができます。 通話プランは不要になりました。 すべての自動応答または通話キューには、関連するリソースアカウントが必要です。 電話番号を必要とするリソースアカウントには、無料の電話システム (仮想ユーザーライセンスまたは有料電話システムユーザーライセンス) が必要です。そのためには、リソースアカウントに電話番号を適用する必要があります。

> [!TIP]
> 入れ子になった自動応答または電話番号が割り当てられていない通話キューと共に使用されるリソースアカウントには、ライセンスは必要ありません。 リファレンスについては、次の図を参照してください。 

![仮想ユーザーライセンス](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>仮想ユーザーライセンスの割り当て

組織には、全体のサイズに応じて、電話システムと仮想ユーザーライセンスが割り当てられています。 電話システムが含まれているか、電話システムが追加されているライセンスが1つ以上ある組織は、25個の仮想ユーザーライセンスを利用できます。 組織に10個の電話システムユーザーライセンスを追加すると、1つ以上の電話システム (仮想ユーザーライセンス) が使用可能になります。

> [!NOTE]
> 電話システムは、Office 365 F1、E1、E3、Office Premium ライセンスで利用可能なアドオンライセンスです。 電話システムは、Office 365 E5 ライセンスの一部としても含まれています。

組織で利用可能な無料電話システム–仮想ユーザーライセンスが自動応答または通話キューノードの作成に使用されている場合でも、リソースアカウントを使って、有料電話システムのライセンスを使用できます。 ほとんどの組織には、スケーリングプランに基づいて十分な仮想ユーザーライセンスがあります。 

### <a name="license-allocation-example"></a>ライセンスの割り当ての例

Contoso、Inc. は、電話システム (各従業員に1つ) が含まれている600ライセンスを購入して、最初の25と追加の60電話システム (仮想ユーザーライセンス) に割り当てられます。 Contoso には、合計で85の電話システム–仮想ユーザーライセンスがあります。 組織には、電話番号を持つ90の通話キューと自動応答があります。 すべての電話システムを割り当てる必要があります。仮想ユーザーライセンスを取得し、5つの標準価格の電話システムライセンスを取得する必要があります。 

Contoso では、少なくとも電話番号を使用するように自動応答と通話キューシステムを再設計し、電話番号やライセンスを必要としない、より多くの入れ子ノードを設計することを検討する必要があります。 不要な電話番号を削除すると、実装が簡素化され、コストが削減されます。 

## <a name="how-to-acquire-phone-systemvirtual-user-licenses"></a>電話システムを取得する方法–仮想ユーザーライセンス 

1. Microsoft 365 管理センターにサインインします。
2. **Billing** > **Purchase services** > **アドオンサブスクリプション**に移動する
3. 最後までスクロールして、 **"電話システム-仮想ユーザー"** ライセンスを探します。 [**今すぐ購入**] を選択します。

> [!WARNING]
> 料金がゼロの場合でも、ライセンスを**購入**する必要があることに注意してください。 

## <a name="change-an-existing-resource-account-to-use-a-phone-systemvirtual-user-license"></a>電話システムを使用するように既存のリソースアカウントを変更する–仮想ユーザーライセンス

リソースアカウントのライセンスを電話システムのライセンスから電話システムに切り替える場合は、仮想ユーザーライセンス: 

1. 新しい電話システムを取得します (仮想ユーザーライセンス)。 
2. Microsoft 365 管理センターのリンクされた手順に従って、[ユーザーを別のサブスクリプションに移動](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription)します。 

> [!WARNING]
> 常に、完全な電話システムのライセンスを削除し、電話システム–仮想ユーザーライセンスを同じライセンスアクティビティに割り当てます。 古いライセンスを削除した場合は、アカウントの変更を保存し、新しいライセンスを追加してから、アカウント設定をもう一度保存すると、リソースアカウントが予期したとおりに機能しなくなることがあります。 この問題が発生した場合は、電話システムの新しいリソースアカウントを作成することをお勧めします。仮想ユーザーライセンスは、破損したリソースアカウントを削除することをお勧めします。 

## <a name="related-information"></a>関連情報

[自動応答と通話キューサービスの更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Microsoft Teams のリソースのアカウントの管理](../manage-resource-accounts.md)
