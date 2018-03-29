---
title: Skype for Business Server 2015 での会議の構成設定の削除
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: '概要: を削除する方法を説明する会議出席ビジネス サーバー 2015 の Skype の設定を構成します。'
ms.openlocfilehash: dec2e51dfe6ae0b9983515d849bc9fc416e9bcc4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="4c0e4-103">Skype for Business Server 2015 での会議の構成設定の削除</span><span class="sxs-lookup"><span data-stu-id="4c0e4-103">Delete meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4c0e4-104">**の概要:**削除する方法について説明会議出席ビジネス サーバー 2015 の Skype の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="4c0e4-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4c0e4-105">削除することができます Skype ビジネス サーバーのコントロール パネルを使用するか、Skype ビジネス サーバー管理シェルを使用して会議の構成設定。</span><span class="sxs-lookup"><span data-stu-id="4c0e4-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="4c0e4-p101">サイト構成やユーザー構成は削除できますが、グローバル構成は削除できません。グローバル構成を削除しようとすると、グローバル構成は自動的に既定値にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="4c0e4-p101">You can delete a site or user configuration, but you cannot delete the global configuration. If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="4c0e4-108">削除ビジネス サーバーのコントロール パネルの Skype を使用して、会議の構成設定</span><span class="sxs-lookup"><span data-stu-id="4c0e4-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="4c0e4-109">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="4c0e4-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="4c0e4-110">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4c0e4-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4c0e4-111">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c0e4-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="4c0e4-112">会議構成の一覧で、削除するサイトまたはプールの構成をクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c0e4-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="4c0e4-113">削除ビジネス サーバー管理シェルの Skype を使用して、会議の構成設定</span><span class="sxs-lookup"><span data-stu-id="4c0e4-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="4c0e4-114">会議の構成設定を削除するには、**Remove-CsMeetingConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c0e4-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="4c0e4-115">次のコマンドを実行すると、Redmond サイトに適用されていた会議の構成設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="4c0e4-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="4c0e4-116">次のコマンドは、サイト スコープに適用された会議構成設定をすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="4c0e4-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="4c0e4-117">パラメーターの完全な一覧を含む詳細については、[削除 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c0e4-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

