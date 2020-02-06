---
title: Skype for Business Server で既存のアーカイブポリシーを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '概要: Skype for Business Server のユーザーアーカイブポリシーを変更する方法について説明します。'
ms.openlocfilehash: 010365b5805517db8f40aa7e3e839fdb15115c06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818989"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="958ca-103">Skype for Business Server で既存のアーカイブポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="958ca-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="958ca-104">**概要:** Skype for Business Server のユーザーアーカイブポリシーを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="958ca-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="958ca-105">初めて Skype for Business Server を展開するときは、展開のユーザーに対してアーカイブを実装する方法を決定する最初のアーカイブポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="958ca-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="958ca-106">このトピックでは、ポリシーを管理および修正する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="958ca-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="958ca-107">コントロール パネルを使用してアーカイブ ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="958ca-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="958ca-108">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="958ca-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="958ca-109">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="958ca-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="958ca-110">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="958ca-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="958ca-111">ポリシー一覧で、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="958ca-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="958ca-112">展開全体のポリシーを変更するには、ポリシー一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="958ca-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="958ca-113">単一のサイトのポリシーを変更するには、ポリシー一覧のサイト名をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="958ca-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="958ca-114">単一のユーザーまたはユーザー グループのポリシーを変更するには、ポリシー一覧のユーザー名またはユーザー グループ名をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="958ca-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="958ca-115">[**アーカイブ ポリシーの編集**] ページで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="958ca-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="958ca-116">ポリシーの内部アーカイブを有効または無効にするには、[**内部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="958ca-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="958ca-117">ポリシーの外部アーカイブを有効または無効にするには、[**外部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="958ca-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="958ca-118">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="958ca-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="958ca-119">ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="958ca-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="958ca-120">詳細については、「 [Skype For Business Server でユーザーにアーカイブポリシーを適用する](apply-a-policy-to-users.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="958ca-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="958ca-121">Windows PowerShell を使用してアーカイブ ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="958ca-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="958ca-122">Windows PowerShell **Set-CsArchivingPolicy** コマンドレットを使用して、アーカイブ ポリシーを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="958ca-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="958ca-123">アーカイブ ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="958ca-123">Enable archiving policies</span></span>

<span data-ttu-id="958ca-124">内部通信セッションのアーカイブを有効にするには、 ArchiveInternal パラメーターの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="958ca-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="958ca-125">外部通信セッションのアーカイブを有効にするには、ArchiveExternal パラメーターの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="958ca-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="958ca-126">内部と外部の両方の通信セッションのアーカイブを有効にするには、アーカイブ内部パラメーターとアーカイブ外部パラメーターの両方の値を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="958ca-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="958ca-127">アーカイブ ポリシーを無効にする</span><span class="sxs-lookup"><span data-stu-id="958ca-127">Disable archiving policies</span></span>

<span data-ttu-id="958ca-128">アーカイブを全体的に無効にするには、ArchiveInternal パラメーターと ArchiveExternal パラメーターの両方の値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="958ca-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
