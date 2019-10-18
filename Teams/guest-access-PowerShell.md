---
title: PowerShell を使用してチームへのゲスト アクセスを制御する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: PowerShell を使用して、Microsoft Teams のチームへのゲスト アクセスを許可または拒否できます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1cecceb81b967d4c6d2f4c9ca440e04d6fec9518
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563484"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>PowerShell を使用してチームへのゲスト アクセスを制御する
================================================

Microsoft 365 管理センターと Azure Active Directory (Azure AD) ポータルのほかに、Windows PowerShell を使用してゲストアクセスを制御することもできます。 PowerShell を使用すると、次の操作を行うことができます。
  
- すべてのチームと Office 365 グループへのゲストアクセスを許可またはブロックする

- すべてのチームと Office 365 グループにゲストを追加できるようにする

- 特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する

詳細については、「 [Office 365 グループでゲストアクセスを管理](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access)する」の「PowerShell を使用してゲストアクセスを制御する」を参照してください。
  
PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。 たとえば、ある企業 (Contoso) が別の企業 (Fabrikam) とパートナーシップを結んでいると仮定します。 Fabrikam 社を [許可] リストに追加すると、Contoso 社のユーザーは Fabrikam のユーザーをゲストとしてグループに追加できるようになります。 詳細については、「 [Office 365 グループへのゲストアクセスを許可/ブロックする](https://go.microsoft.com/fwlink/?linkid=854001)」を参照してください。
  
チーム内のゲストをブロックし、それでも SharePoint サイトへのアクセスを許可する場合は、Azure AD Powershell コマンドレットを使用して、SharePoint サイトの外部共有が有効であることを前提として、Company オブジェクトの AllowGuestsToAccessGroups パラメーターを無効にすることができます。.

## <a name="guest-access-vs-external-access"></a>ゲストアクセスと外部アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
