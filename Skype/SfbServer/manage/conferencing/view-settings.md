---
title: Skype for Business Server で会議構成の設定を表示する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '概要: Skype for Business Server で会議の構成設定を表示する方法について説明します。'
ms.openlocfilehash: 13d91bc4c0335d8c069e0b0d9bc41efd8714f112
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280370"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="65e7a-103">Skype for Business Server で会議構成の設定を表示する</span><span class="sxs-lookup"><span data-stu-id="65e7a-103">View meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="65e7a-104">**概要:** Skype for Business Server で会議の構成設定を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65e7a-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="65e7a-105">会議の設定を表示するには、Skype for Business Server コントロールパネルを使用するか、Skype for Business Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="65e7a-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="65e7a-106">Skype for Business Server コントロールパネルを使用して会議構成の設定を表示する</span><span class="sxs-lookup"><span data-stu-id="65e7a-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="65e7a-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="65e7a-107"></span></span>

1. <span data-ttu-id="65e7a-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="65e7a-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="65e7a-109">Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="65e7a-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="65e7a-110">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="65e7a-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="65e7a-111">[**会議の構成**] ページで、表示する会議構成をクリックします。</span><span class="sxs-lookup"><span data-stu-id="65e7a-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="65e7a-112">[**ファイル フィルターの編集**] で、[**詳細の表示**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="65e7a-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="65e7a-113">[**会議の構成\<の\>編集]-** 選択したポリシーの設定が表示されたポリシーが開きます。</span><span class="sxs-lookup"><span data-stu-id="65e7a-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="65e7a-114">設定の構成の詳細については、「 [Skype For Business Server で会議の構成設定を作成](create-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65e7a-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="65e7a-115">Skype for Business Server 管理シェルを使用して会議構成の設定を表示する</span><span class="sxs-lookup"><span data-stu-id="65e7a-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="65e7a-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="65e7a-116"></span></span>

<span data-ttu-id="65e7a-117">すべての会議の構成設定に関する情報を表示するには、**Get-CsMeetingConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="65e7a-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="65e7a-118">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="65e7a-118">This command will return information similar to the following:</span></span>
  
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

<span data-ttu-id="65e7a-119">パラメーターの完全な一覧を含む、詳細については、「 [Cs会議の構成](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65e7a-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

