---
title: 組織のMicrosoft Teams 無料版 (クラシック)を廃止する
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: alyake
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom:
- Licensing
- admindeeplinkMAC
robots: noindex
description: Teams 無料 (クラシック) ライセンスを削除し、組織のユーザーに有料の Teams ライセンスを割り当てる方法について説明します。
ms.openlocfilehash: 3015036d0656a80ac8440d2c193003cc7d67d9fc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767668"
---
# <a name="retire-microsoft-teams-free-classic-for-your-organization"></a>組織のMicrosoft Teams 無料版 (クラシック)を廃止する

> [!NOTE]
> Teams Free (クラシック) ユーザーの場合、IT 管理者がこの記事で次のアクションを実行しない限り、2023 年 4 月中旬に Teams にアクセスできなくなります。

2023 年 4 月中旬に、Microsoft は **Microsoft Teams 無料版 (クラシック)** ライセンスを廃止します。

この記事では、組織の **Microsoft Teams 無料版 (クラシック)** ライセンスを廃止し、有料の Teams ライセンスに移行する方法について、IT 管理者に指示を提供します。

2023 年 4 月中旬までにユーザーの無料 Teams ライセンスを有料の Teams ライセンスに移行しないと、ユーザーは Teams にアクセスできなくなります。

このプロセスを完了するには、次の 2 つの方法のいずれかを選択します。

- [Microsoft 365 管理センターを使用します。](#use-microsoft-365-admin-center-to-replace-licenses)
- [Microsoft PowerShell を使用します。](#use-microsoft-powershell-to-replace-licenses)

組織が有料の Teams ライセンスに移行しないことを決定した場合は、Teams から組織のコンテンツをエクスポートできます。 Teams コンテンツをエクスポートする方法については、「 [Microsoft Teams Export API を使用してコンテンツをエクスポートする」を](/microsoftteams/export-teams-content)参照してください。

## <a name="use-microsoft-365-admin-center-to-replace-licenses"></a>Microsoft 365 管理センターを使用してライセンスを置き換える

Teams **Free (クラシック)** ライセンスを割り当てたユーザーが少ない組織の場合は、ライセンスの削除と割り当てにMicrosoft 365 管理センターを使用することをお勧めします。

### <a name="check-users-current-teams-licensing"></a>ユーザーの現在の Teams ライセンスを確認する

1. [Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)にサインインします。
1. 左側のメニューで、[ **ユーザー** >] に移動し、[ [**アクティブ なユーザー**](https://go.microsoft.com/fwlink/p/?linkid=834822) ] を選択して、ユーザーに割り当てられているライセンスを表示します。
    1. [**ライセンス**] 列には、**そのライセンスが** 割り当てられているユーザーの横にMicrosoft Teams 無料版 (クラシック)が表示されます。
1. 左側のメニューで、[ **課金** >] に移動し、[ [**ライセンス**](https://go.microsoft.com/fwlink/p/?linkid=842264) ] を選択して、利用可能な有料 Teams ライセンスがあるかどうかを確認します。
    1. 組織に使用可能なライセンスがある場合は、「 [有料の Teams ライセンスを割り当てる](#assign-paid-teams-licenses) 」に進み、それらのライセンスを **Teams Free (クラシック)** ライセンスを持つユーザーに割り当てます。
1. 購入する必要がある有料の Teams ライセンスの数 (ある場合) を決定します。

### <a name="purchase-paid-teams-licenses"></a>有料の Teams ライセンスを購入する

1. [Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)で、[**課金**>] に移動し、[**サービスの購入**] を選択します。
1. [ **製品の表示]** を選択して、使用可能なすべてのライセンスを表示します。
1. [ **コミュニケーションとコラボレーション** ] カテゴリ フィルターを選択して、Teams ライセンスを表示します。
1. **Teams Free (クラシック)** を置き換える有料の Teams ライセンスを選択します。
    1. [**Teams Essentials** ライセンス](https://admin.microsoft.com/adminportal/home#/catalog/offer-details/microsoft-teams-essentials-aad-identity-/2D7C59AC-F814-43E0-8E8E-E4EA91A09CAF)は、最大 300 シートまで利用できます。
    1. 300 以上のシートが必要な場合は、 [Microsoft 365 E1 ライセンス](https://admin.microsoft.com/Adminportal/Home#/catalog/offer-details/office-365-e1/CF4A479A-2119-4EF2-83D1-37CF8460EADA)を購入することをお勧めします。
1. 購入するライセンスの数を入力し、課金頻度を選択します。
1. [ **購入** ] ボタンを選択して、購入プロセスを完了します。

#### <a name="purchase-licenses-in-the-admin-center-marketplace"></a>管理センター Marketplace でライセンスを購入する

一部のテナントは、Microsoft 365 管理センター Marketplace にアクセスできます。 これらのテナントの場合は、Marketplace でライセンスを購入します。

1. [Microsoft 365 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)で、左側のメニューから **[Marketplace**] を選択します。
1. [ **すべての製品** ] タブを選択します。
1. [ **コミュニケーションとコラボレーション** ] カテゴリ フィルターを選択して、Teams ライセンスを表示します。
1. **Teams Free (クラシック)** を置き換える有料の Teams ライセンスを選択します。
1. 購入するライセンスの数を入力し、課金頻度を選択します。
1. [ **購入** ] ボタンを選択して、購入プロセスを完了します。

### <a name="assign-paid-teams-licenses"></a>有料の Teams ライセンスを割り当てる

1. **Teams Free (クラシック)** ライセンスを置き換える準備ができたら、Microsoft 365 管理センターで[**ユーザー** > [**のアクティブなユーザー**](https://admin.microsoft.com/adminportal/home#/users)] に移動します。
1. [ライセンス] 列に表示されている **Teams Free (クラシック)** ライセンスを持つすべてのユーザー **を** 選択します。
1. 管理センターの上部にある [ **製品ライセンスの管理** ] オプションを選択します。
1. 右側のウィンドウで、[置換] を選択 **します**。
    1. [ **置換** ] オプションを選択すると、それらのユーザーに割り当てるすべてのライセンスを再選択する必要があります。 新しい有料 Teams ライセンスのみを選択した場合、それらのユーザーに割り当てられた他のライセンスはユーザーから削除され、Teams ライセンスに置き換えられます。
    1. ユーザーのライセンスニーズが異なる場合は、ユーザーのライセンスが間違わないように、このプロセスをバッチで完了します。
1. 配車側ウィンドウで、新しい有料 Teams ライセンスと、ユーザーに割り当てる必要があるその他のライセンスを選択し、[ **変更の保存** ] ボタンを選択します。

## <a name="use-microsoft-powershell-to-replace-licenses"></a>Microsoft PowerShell を使用してライセンスを置き換える

組織に **Teams Free (クラシック)** ライセンスが割り当てられているユーザーの数が多い場合は、PowerShell を使用して割り当てを一括解除し、ユーザーにライセンスを割り当てることをお勧めします。

このプロセスを完了するには、Teams **Free (クラシック)** ライセンスが割り当てられているユーザーに対して有料の Teams ライセンスが必要です。 これらのユーザーのライセンスを購入するには、「 [有料の Teams ライセンスを購入する](#purchase-paid-teams-licenses)」を参照してください。

1. Microsoft 365 テナントを [Microsoft Graph PowerShell SDK](/powershell/microsoftgraph/get-started) に接続します。
1. Microsoft PowerShell デスクトップ アプリを開きます。
1. [Graph APIのユーザーと組織のアクセス許可を設定](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#use-the-microsoft-graph-powershell-sdk)します。
1. [ユーザー アカウントから **Teams Free (クラシック)** ライセンスを削除します](/microsoft-365/enterprise/remove-licenses-from-user-accounts-with-microsoft-365-powershell#removing-licenses-from-user-accounts)。
1. [有料の Teams ライセンスをユーザーに割り当てます](/microsoft-365/enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell#assigning-licenses-to-user-accounts)。

Graph PowerShell SDK プロセスの詳細については、「 [Microsoft Graph PowerShell SDK を使用する](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)」を参照してください。
