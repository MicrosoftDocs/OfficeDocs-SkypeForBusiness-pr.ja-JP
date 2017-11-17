---
title: "PowerShell を使用してチームへのゲスト アクセスを制御する"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "PowerShell を使用して、Microsoft Teams のチームへのゲスト アクセスを許可または拒否できます。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 563a1a56449be289572020dc226df69795596d1c
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2017
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>PowerShell を使用してチームへのゲスト アクセスを制御する
================================================

Office 365 管理センターと Azure Active Directory ポータルに加え、Windows PowerShell を使用してゲスト アクセスを制御することもできます。 PowerShell を使用すると、次の操作を行うことができます。
  
  
   

- すべてのチームおよび Office 365 グループへのゲスト アクセスを許可または拒否する
    
  
- すべてのチームおよび Office 365 グループへのゲストの追加を許可する
    
  
- 特定のチームまたは Office 365 グループのゲスト ユーザーを許可または拒否する
    
  
詳しくは、「[PowerShell を使用してゲスト アクセスを制御する](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)」をご覧ください。
  
    
    
PowerShell を使用して、ドメインに基づいてゲスト ユーザーの許可と拒否を行うこともできます。 たとえば、ある企業 (Contoso) が別の企業 (Fabrikam) とパートナーシップを結んでいると仮定します。 Fabrikam 社を [許可] リストに追加すると、Contoso 社のユーザーは Fabrikam のユーザーをゲストとしてグループに追加できるようになります。 詳細については、「[Allow/Block guest access to Office 365 groups (Office 365 グループへのゲスト アクセスを許可/拒否する)](https://go.microsoft.com/fwlink/?linkid=854001)」をご覧ください。
  
 
チームのゲストを拒否したいがゲストに対して SharePoint サイトへのアクセスを引き続き許可する場合は、SharePoint の外部共有をオンに設定しているという前提の上に、Azure Active Directory Powershell コマンドレットを使用して Company オブジェクトの AllowGuestAccessToGroups パラメーターを無効にすることができます。   