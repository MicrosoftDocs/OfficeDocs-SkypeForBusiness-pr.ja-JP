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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886383"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>PowerShell を使用してチームへのゲスト アクセスを制御する
================================================

Microsoft 365 管理センターと Azure Active Directory ポータルに加え、Windows PowerShell を使用してゲスト アクセスを制御することもできます。 PowerShell を使用すると、次の操作を行うことができます。
  
- すべてのチームおよび Office 365 グループへのゲスト アクセスを許可または拒否する
    
- すべてのチームおよび Office 365 グループへのゲストの追加を許可する
      
- 特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する
    
詳しくは、「[Office 365 グループのゲスト アクセス](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)」の [管理] タブの「PowerShell を使用してゲスト アクセスを制御する」のセクションをご覧ください。
  
PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。 たとえば、自分の会社 (Contoso) が他の会社 (Fabrikam) とのパートナーシップを持つとします。 許可リストに Fabrikam を追加し、ユーザーが自分のグループにそれらのゲストを追加できるようにします。 詳細については、「[Allow/Block guest access to Office 365 groups (Office 365 グループへのゲスト アクセスを許可/拒否する)](https://go.microsoft.com/fwlink/?linkid=854001)」をご覧ください。
  
Teamsのゲストを拒否したいがゲストに対して SharePoint サイトへのアクセスを引き続き許可する場合は、SharePoint の外部共有をオンに設定しているという前提の上に、Azure Active Directory Powershell コマンドレットを使用して Company オブジェクトの AllowGuestsToAccessGroups パラメーターを無効にすることができます。   

## <a name="guest-access-vs-external-access"></a>ゲスト アクセスと外部アクセス

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
