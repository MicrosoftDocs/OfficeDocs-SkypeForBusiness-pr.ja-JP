---
title: リソース アカウント ライセンスのMicrosoft Teams 電話
author: DaniEASmith
ms.author: danismith
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
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- admindeeplinkMAC
description: Microsoft Teams 電話リソース アカウント ライセンスを、組織内の自動応答と通話キューのリソース アカウントに割り当てる方法について説明します。
ms.openlocfilehash: d3eacab8569981550520385c4aee297ae6835a59
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307762"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>リソース アカウント ライセンスのMicrosoft Teams 電話

Microsoft Teams では、すべての自動応答と通話キューに関連付けられているリソース アカウントが必要です。 リソース アカウントに電話番号が割り当てられているかどうかに関係なく、システムによって正しく識別され、適切に機能するように、各リソース アカウントに Microsoft Teams 電話 *リソース アカウント ライセンスを割り当てる* 必要があります。 Teams Phone を含むサブスクリプションを持つ組織には、追加コストなしで一定量の **Teams 電話リソース アカウント** ライセンスが自動的に割り当てられます。  そのリソース アカウントを使用してダイヤルアウトできるようにする場合を除き、Microsoft通話プランは必要ありません。 詳細については、「 [Teams の自動応答と通話キューの計画](../plan-auto-attendant-call-queue.md#prerequisites)」を参照してください。

> [!NOTE]
> 以前は、 **Teams 電話リソース アカウント** ライセンス (かつて **は仮想ユーザー** ライセンスと呼ばれる) は、リソース アカウントに電話番号を割り当てるときにのみ必要でした。 これで、電話番号が割り当てられるかどうかに関係なく、すべての **リソース アカウントに Teams 電話リソース アカウント** ライセンスを割り当てる必要があります。 また、**リソース アカウントにTeams 電話スタンダード** ライセンスを割り当てないでください。 現在、**Teams 電話スタンダード** ライセンスで構成されているリソース アカウントがある場合は、以下で説明するように **Teams 電話リソース アカウント** ライセンスに切り替える必要があります。
 

## <a name="resource-account-license-allocation"></a>リソース アカウント ライセンスの割り当て

組織には、全体的なサイズに基づいて **Teams 電話リソース アカウント** ライセンスが割り当てられている。 電話システム機能を持つサブスクリプションを持つ組織 (**Teams 電話スタンダード** や **Teams Phone with Calling Plan** ライセンスなど) には、25 **個の Teams 電話リソース アカウント** ライセンスが無償で割り当てられます。 

組織内の通話プランを **使用したTeams 電話スタンダード** または **Teams Phone** の 10 ユーザー ライセンスごとに、もう 1 つの **Teams 電話リソース アカウント** ライセンスが使用可能になります。  ほとんどの組織には、このスケーリング プランに基づいて、 **Teams Phone リソース アカウント** ライセンスが十分にあります。 より多くの **Teams 電話リソース アカウント** ライセンスが必要な場合は、EA、EAS、EES、CSP、Web Direct、NCE - Customer led、NCE - Partner led、または Microsoft アカウント担当者を通じて、標準割り当てを超えて、より多くの **Teams 電話リソース** アカウント ライセンスを購入できます。

### <a name="license-allocation-example"></a>ライセンスの割り当ての例

Contoso, Inc. は、電話システム (従業員ごとに 1 つ) を含む 600 ライセンスを購入しました。 Contoso には、最初の 25 個と 60 **個の Teams 電話リソース アカウント** ライセンス (合計 85 個) が割り当てられている。 組織には、90 の通話キューと自動応答があります。 すべての **Teams 電話リソース アカウント** ライセンスを割り当て、5 つの追加 **の Teams 電話リソース アカウント** ライセンスを購入する必要があります。 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams 電話リソース アカウント ライセンスを取得する方法

1. [Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)にサインインします。
2. **[課金購入** > [**サービス**](https://go.microsoft.com/fwlink/p/?linkid=868433) > **] アドオンに移動します**。
3. スクロールして **、Microsoft Teams 電話 リソース アカウント ライセンスを** 見つけます。 [ **今すぐ購入] を選択します**。

   > [!NOTE]
   > 割り当て範囲内であっても、コストが 0 であってもライセンスを **購入** する必要があることに注意してください。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Microsoft Teams 電話 リソース アカウント ライセンスを使用するように既存のリソース アカウントを変更する

**Teams 電話スタンダード** ライセンスを使用する既存のリソース アカウントがある場合は、 を **Teams 電話リソース アカウント** ライセンスに切り替える必要があります。

1. 新しい **Teams 電話リソース アカウント ライセンスを** 取得します。
2. Microsoft 365 管理センターのリンクされた手順に従って、ユーザーを[別のサブスクリプションに移動します](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> **常にTeams 電話スタンダード** ライセンスを削除し、同じライセンス アクティビティで **Teams 電話リソース アカウント** ライセンスを割り当てます。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加し、アカウント設定をもう一度保存すると、組織の自動応答や通話キューが機能しなくなったように、リソース アカウントが期待どおりに機能しなくなる可能性があります。
>
> その場合は、 **Teams 電話** リソース アカウント ライセンスを使用して新しいリソース アカウントを作成し、壊れたリソース アカウントを削除することをお勧めします。

## <a name="related-information"></a>関連情報

[自動応答と通話キューサービスの更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[Microsoft Teams のリソースのアカウントの管理](../manage-resource-accounts.md)
