---
title: 管理単位の機能を使用Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 管理単位の機能を使用する方法については、Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93add1771e76f6640b6f1fde3ee6e732499aa329
ms.sourcegitcommit: 9062b2c81c582ddc878c825ba1b22a6c23ca4b64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58399378"
---
# <a name="administrative-unit-functionality-for-device-management-in-teams"></a>デバイス管理の管理単位機能 (Teams

管理センターを使用して、デバイス管理用のロールベースのアクセスMicrosoft Teamsします。 管理センターを通じてデバイス管理の管理単位の概念Teamsしました。

管理単位の概念では、専用の管理者に特定のリソース セットへのアクセスを保証します。 管理単位は、すべてのリソースへのアクセスを制限します。 デバイスの管理に同じ機能Teams拡張できます。

> [!NOTE]
> 管理単位の概念は、現在、デバイス管理者ロールTeamsでのみ使用できます。

たとえば、Contoso は異なる地域間で操作を行います。 Alice はロンドンのグローバル IT 管理者で、Prashant はインドの IT 管理者です。 現在、Prashant がデバイス管理者ロールで Teams 管理センターにサインインすると、世界中のデバイスが表示されます。 Alice は、インドに存在するデバイスにのみ Prashant のアクセスを制限したいと考えます。 管理単位の概念は、この問題の解決に役立ちます。 詳細については、 [管理単位の概念に関する説明を参照してください](/azure/active-directory/roles/administrative-units)。

![シナリオを示す図](media/au-diagram.png)

## <a name="creation-of-administrative-units"></a>管理単位の作成

Azure Portal で管理単位を作成し、それぞれの管理単位に管理者を割り当てる。 管理単位の割り当ての詳細については、「管理単位の管理 [」を参照してください](/azure/active-directory/roles/admin-units-manage)。

![会社の管理単位の例](media/au-example.png)

グローバル IT 管理者は、作成後、その管理単位に対応するデバイス ユーザーを追加できます。

![ユーザー のプレビューを含む会社の例](media/au-example2.png)

ロールの割り当ては、PowerShell で [Add-AzureADMSScopedRoleMembership コマンドレットを使用して実行](/powershell/module/azuread/add-azureadmsscopedrolemembership?view=azureadps-2.0) できます。

管理単位のユーザーにロールを割り当てた後、ユーザーはスコープを持つデバイスの管理Teams管理センターにサインインする必要があります。

## <a name="experience-for-administrative-unit-admin"></a>管理単位管理者のエクスペリエンス

同じ管理者に複数の管理単位の責任が割り当てられている場合は、ポータルからサインアウトせずに管理単位を切り替えます。 変更された管理単位ビューには、新しい管理単位に関連付けられているデバイスのセットだけが表示されます。
