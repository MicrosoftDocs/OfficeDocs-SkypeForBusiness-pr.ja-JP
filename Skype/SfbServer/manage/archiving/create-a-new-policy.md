---
title: Skype のビジネス サーバーの新しいアーカイブ ・ ポリシーを作成します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: '概要: は、Skype のビジネス サーバーの新しいアーカイブ ・ ポリシーを作成する方法を説明します。'
ms.openlocfilehash: b8cd31e1fb921313cdbd53ad67ba55a81dda81ce
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893442"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="9062e-103">Skype のビジネス サーバーの新しいアーカイブ ・ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9062e-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="9062e-104">**の概要:** Skype のビジネス サーバーの新しいアーカイブ ・ ポリシーを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9062e-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="9062e-105">新しいアーカイブ ポリシーの作成には、コントロール パネルまたは Windows PowerShell コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9062e-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="9062e-106">コントロール パネルを使用して新しいアーカイブ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="9062e-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="9062e-107">コントロール パネルを使用して新しいアーカイブ ポリシーを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9062e-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="9062e-108">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="9062e-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9062e-109">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="9062e-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9062e-110">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9062e-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="9062e-111">[**新規**] をクリックし、次のいずれかの操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9062e-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="9062e-112">サイトレベルのアーカイブ ポリシーを作成するには、[**サイト ポリシー**] をクリックし、[**サイトの選択**] で、ポリシーを適用するサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9062e-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="9062e-113">ユーザーレベルのアーカイブ ポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9062e-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="9062e-114">[**新しいアーカイブ ポリシー**] で、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="9062e-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="9062e-115">[**名前**] で、新しいポリシーの名前を指定します (externalContoso など)。</span><span class="sxs-lookup"><span data-stu-id="9062e-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="9062e-116">[**説明**] に、そのポリシーの内容に関する詳細を入力します (「Contoso の外部ユーザー アーカイブ ポリシー」など)。</span><span class="sxs-lookup"><span data-stu-id="9062e-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="9062e-117">内部ユーザーとの通信のアーカイブを制御するには、[**内部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="9062e-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="9062e-118">外部ユーザーとの通信のアーカイブを制御するには、[**外部通信をアーカイブする**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="9062e-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="9062e-119">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9062e-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9062e-120">ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="9062e-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="9062e-121">詳細については、 [Skype のビジネス サーバー内のユーザーにアーカイブ ・ ポリシーの適用](apply-a-policy-to-users.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9062e-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="9062e-122">Windows PowerShell を使用して新しいアーカイブ ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="9062e-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="9062e-123">新しいアーカイブ ポリシーの作成には、Windows PowerShell の **New-CsArchivingPolicy** コマンドレットも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9062e-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="9062e-124">詳細については、[新規 CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9062e-124">For more information, see the help topic for the [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="9062e-125">サイト レベルでの新しいアーカイブ ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="9062e-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="9062e-126">次のコマンドは、Redmond サイトの新しいアーカイブ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9062e-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="9062e-127">ユーザーごとのレベルで新しいアーカイブ ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="9062e-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="9062e-128">ユーザーごとのレベルで新しいアーカイブ ポリシーを作成するには、ポリシーの作成時に一意の ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="9062e-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="9062e-129">内部通信セッションのアーカイブを有効にする新しいアーカイブ ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="9062e-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="9062e-130">前の各コマンドでは (必須の ID パラメーター以外に) パラメーターが指定されていないため、新しいポリシーではすべてのプロパティで既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9062e-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="9062e-131">別のプロパティ値を使用するポリシーを作成するには、該当するパラメーターとパラメーター値を含めます。</span><span class="sxs-lookup"><span data-stu-id="9062e-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="9062e-132">たとえば、次のコマンドは、内部のインスタント メッセージング セッションのアーカイブを許可するアーカイブ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9062e-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="9062e-133">内部と外部の両通信セッションのアーカイブを有効にする新しいアーカイブ ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="9062e-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="9062e-p104">複数のパラメーターを含めることで、複数のプロパティ値を変更できます。たとえば、次のコマンドは、内部と外部の両方のインスタント メッセージング セッションをアーカイブするように新しいポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="9062e-p104">Multiple property values can be modified by including multiple parameters. For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
