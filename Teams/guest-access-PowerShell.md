---
title: PowerShell を使用してチームへのゲスト アクセスを制御する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: PowerShell を使用して、Microsoft Teams のチームへのゲスト アクセスを許可または拒否できます。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 815a35efbce89404b012d5534e257752bef8d53e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886383"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>PowerShell を使用してチームへのゲスト アクセスを制御する
================================================

Microsoft 365 管理センターと Azure Active Directory ポータルのほかに、Windows PowerShell を使用してゲストアクセスを制御することもできます。 PowerShell を使用すると、次の操作を行うことができます。
  
- すべてのチームおよび Office 365 グループへのゲスト アクセスを許可または拒否する
    
- すべてのチームおよび Office 365 グループへのゲストの追加を許可する
      
- 特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する
    
詳細については、「 [Office 365 グループのゲストアクセス](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)の [管理] タブで、「PowerShell を使用してゲストアクセスを制御する」セクションを参照してください。
  
PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。 たとえば、ある企業 (Contoso) が別の企業 (Fabrikam) とパートナーシップを結んでいると仮定します。 Fabrikam 社を [許可] リストに追加すると、Contoso 社のユーザーは Fabrikam のユーザーをゲストとしてグループに追加できるようになります。 詳細については、「[Allow/Block guest access to Office 365 groups (Office 365 グループへのゲスト アクセスを許可/拒否する)](https://go.microsoft.com/fwlink/?linkid=854001)」をご覧ください。
  
チーム内のゲストをブロックし、引き続き SharePoint サイトへのアクセスを許可する場合は、Azure Active Directory Powershell コマンドレットを使用して、外部共有がオンになっていることを前提として、会社のオブジェクトの AllowGuestsToAccessGroups パラメーターを無効にすることができます。SharePoint サイト。   

## <a name="guest-access-vs-external-access"></a>ゲストアクセスと外部アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
