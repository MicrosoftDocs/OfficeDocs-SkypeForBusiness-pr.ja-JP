---
title: Skype for Business Server 2015 での会議の構成設定の表示
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: '概要: を表示する方法を説明する会議出席ビジネス サーバー 2015 の Skype の設定を構成します。'
ms.openlocfilehash: 382e50a0f41301953f4313c5019d1eb0d27804e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="c772c-103">Skype for Business Server 2015 での会議の構成設定の表示</span><span class="sxs-lookup"><span data-stu-id="c772c-103">View meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c772c-104">**の概要:**表示する方法について説明会議出席ビジネス サーバー 2015 の Skype の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="c772c-104">**Summary:** Learn how to view meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c772c-105">表示することができます Skype ビジネス サーバーのコントロール パネルを使用するか、Skype ビジネス サーバー管理シェルを使用して会議の構成設定。</span><span class="sxs-lookup"><span data-stu-id="c772c-105">You can view meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c772c-106">ビジネス サーバーのコントロール パネルの Skype を使用して、会議の構成設定の表示</span><span class="sxs-lookup"><span data-stu-id="c772c-106">View meeting configuration settings by using Skype for Business Server Control Panel</span></span>
<span data-ttu-id="c772c-107"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="c772c-107"></span></span>

1. <span data-ttu-id="c772c-108">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="c772c-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="c772c-109">Skype をビジネス サーバーのコントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="c772c-109">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c772c-110">左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c772c-110">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="c772c-111">[**会議の構成**] ページで、表示する会議構成をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c772c-111">On the **Meeting Configuration** page, click the meeting configuration that you would like to view.</span></span>
    
5. <span data-ttu-id="c772c-112">[**ファイル フィルターの編集**] で、[**詳細の表示**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c772c-112">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="c772c-113">**会議設定の編集 -\<ポリシー\>**が開き、選択したポリシーの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="c772c-113">**Edit Meeting Configuration - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="c772c-114">詳細設定の構成については、[会議ビジネス サーバー 2015 の Skype での構成設定の作成](create-settings.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c772c-114">For details about configuring the settings, see [Create meeting configuration settings in Skype for Business Server 2015](create-settings.md).</span></span>
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c772c-115">Skype ビジネス サーバー管理シェルを使用して会議の構成設定の表示</span><span class="sxs-lookup"><span data-stu-id="c772c-115">View meeting configuration settings by using Skype for Business Server Management Shell</span></span>
<span data-ttu-id="c772c-116"><a name="BKMK_ViewJoinSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="c772c-116"></span></span>

<span data-ttu-id="c772c-117">すべての会議の構成設定に関する情報を表示するには、**Get-CsMeetingConfiguration** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c772c-117">To view information about all your meeting configuration settings, use the **Get-CsMeetingConfiguration** cmdlet:</span></span>
  
```
Get-CsMeetingConfiguration
```

<span data-ttu-id="c772c-118">このコマンドは、次のような情報を返します。</span><span class="sxs-lookup"><span data-stu-id="c772c-118">This command will return information similar to the following:</span></span>
  
```
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

```

<span data-ttu-id="c772c-119">パラメーターの完全な一覧を含む詳細については、 [Get CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c772c-119">For more information, including a complete list of parameters, see [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).</span></span>
  

