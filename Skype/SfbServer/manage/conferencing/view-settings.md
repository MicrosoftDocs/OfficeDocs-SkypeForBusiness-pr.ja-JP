---
title: Skype for Business Server で会議の構成設定を表示する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '概要: Skype for Business Server で会議の構成設定を表示する方法について説明します。'
ms.openlocfilehash: e30543c566775d38e20e2103c4cc0f41278c1020
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827927"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="fede1-103">Skype for Business Server で会議の構成設定を表示する</span><span class="sxs-lookup"><span data-stu-id="fede1-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="fede1-104">**概要:** Skype for Business Server で会議の構成設定を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fede1-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="fede1-105">会議の構成設定は、Skype for Business Server コントロール パネルまたは Skype for Business Server 管理シェルを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="fede1-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="fede1-106">Skype for Business Server コントロール パネルを使用して会議の構成設定を表示する</span><span class="sxs-lookup"><span data-stu-id="fede1-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="fede1-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="fede1-107"><a name="BKMK_ViewJoinSettings"> </a></span></span>

1. <span data-ttu-id="fede1-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="fede1-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="fede1-109">Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="fede1-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fede1-110">左側のナビゲーション バーで、[会議] **をクリックし**、[会議の構成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="fede1-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="fede1-111">[**会議の構成**] ページで、表示する会議構成をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fede1-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="fede1-112">[ **ファイル フィルターの編集] で**、[詳細の表示 **] チェック ボックス** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="fede1-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="fede1-113">**会議の構成の \<policy\> 編集 -** が開き、選択したポリシーの設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fede1-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="fede1-114">設定の構成の詳細については、「Skype for Business Server で会議の構成設定を作成する [」を参照してください](create-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="fede1-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="fede1-115">Skype for Business Server 管理シェルを使用して会議の構成設定を表示する</span><span class="sxs-lookup"><span data-stu-id="fede1-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="fede1-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="fede1-116"><a name="BKMK_ViewJoinSettings"> </a></span></span>

<span data-ttu-id="fede1-117">すべての会議構成設定に関する情報を表示するには **、Get-CsMeetingConfiguration コマンドレットを使用** します。</span><span class="sxs-lookup"><span data-stu-id="fede1-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="fede1-118">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="fede1-118">This command will return information similar to the following:</span></span>
  
<pre>
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True
</pre>

<span data-ttu-id="fede1-119">パラメーターの完全な一覧を含む詳細については [、「Get-CsMeetingConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="fede1-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

