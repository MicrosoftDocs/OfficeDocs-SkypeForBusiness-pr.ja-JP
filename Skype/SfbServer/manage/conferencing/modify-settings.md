---
title: 変更会議の Skype ビジネス サーバーの構成設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: '概要: を変更する方法を学習する Skype ビジネス サーバーの構成設定に対応します。'
ms.openlocfilehash: 73127bfce04c8c124ce8036222d755de6bc37058
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876049"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c1b8c-103">変更会議の Skype ビジネス サーバーの構成設定</span><span class="sxs-lookup"><span data-stu-id="c1b8c-103">Modify meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c1b8c-104">**の概要:** 変更する方法を学習 Skype ビジネス サーバーの構成設定に対応します。</span><span class="sxs-lookup"><span data-stu-id="c1b8c-104">**Summary:** Learn how to modify meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="c1b8c-105">変更することができます Skype ビジネス サーバーのコントロール パネルを使用するか、Skype ビジネス サーバー管理シェルを使用して会議の構成設定。</span><span class="sxs-lookup"><span data-stu-id="c1b8c-105">You can modify meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c1b8c-106">変更ビジネス サーバーのコントロール パネルの Skype を使用して、会議の構成設定</span><span class="sxs-lookup"><span data-stu-id="c1b8c-106">Modify meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c1b8c-107">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c1b8c-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="c1b8c-108">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c1b8c-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c1b8c-109">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1b8c-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="c1b8c-110">会議構成の一覧で、変更する構成をクリックし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1b8c-110">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c1b8c-111">[**会議の構成の編集**] で、構成名以外の構成設定を変更します (構成名は変更不可です)。</span><span class="sxs-lookup"><span data-stu-id="c1b8c-111">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="c1b8c-112">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1b8c-112">Click **Commit**.</span></span>
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c1b8c-113">変更ビジネス サーバー管理シェルの Skype を使用して、会議の構成設定</span><span class="sxs-lookup"><span data-stu-id="c1b8c-113">Modify meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c1b8c-114">会議の構成設定を変更するには、**Set-CsMeetingConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1b8c-114">To modify meeting configuration settings, use the **Set-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="c1b8c-p101">次の例に示すコマンドは、Redmond サイト (-Identity site:Redmond) に割り当てられている会議構成設定を変更します。この場合、DesignateAsPresenter プロパティの値が "Everyone" に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c1b8c-p101">The command shown in the following example modifies the meeting configuration settings assigned to the Redmond site (-Identity site:Redmond). In this case, the value of the DesignateAsPresenter property is set to Everyone:</span></span>
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="c1b8c-117">詳細については、パラメーターの一覧を含む[セット CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1b8c-117">For more information, including a complete list of parameters, see [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps).</span></span>
  

