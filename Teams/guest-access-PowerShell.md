---
title: PowerShell を使用してチームへのゲスト アクセスを制御する
author: somakbhattacharyya
ms.author: sbhatta
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
ms.openlocfilehash: 0efb3a8054008d179b9d2e7e674b3482fe62a32c
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865091"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>PowerShell を使用してチームへのゲスト アクセスを制御する
================================================

Microsoft 365 管理センターでは、Active Directory の Azure ポータルを使用する以外は、ゲスト アクセスを制御するのに Windows PowerShell を使用できます。 PowerShell を使用すると、次の操作を行うことができます。
  
- すべてのチームおよび Office 365 グループへのゲスト アクセスを許可または拒否する
    
- すべてのチームおよび Office 365 グループへのゲストの追加を許可する
      
- 特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する
    
詳細については、 [Office 365 のグループでのゲスト アクセス](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)の管理] タブの「ゲスト アクセスを制御する PowerShell を使用」のセクションを参照してください。
  
PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。 たとえば、ある企業 (Contoso) が別の企業 (Fabrikam) とパートナーシップを結んでいると仮定します。 Fabrikam 社を [許可] リストに追加すると、Contoso 社のユーザーは Fabrikam のユーザーをゲストとしてグループに追加できるようになります。 詳細については、「[Allow/Block guest access to Office 365 groups (Office 365 グループへのゲスト アクセスを許可/拒否する)](https://go.microsoft.com/fwlink/?linkid=854001)」をご覧ください。
  
チームには、来園者をブロックし、SharePoint サイトにアクセスできるようにする場合は、コマンドレットを使用できます Azure Active Directory Powershell 会社オブジェクトでは、AllowGuestsToAccessGroups パラメーターを無効にする外部の共有がオンの場合SharePoint サイトです。   

## <a name="guest-access-vs-external-access"></a>ゲスト アクセスを外部からのアクセスとの比較

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
