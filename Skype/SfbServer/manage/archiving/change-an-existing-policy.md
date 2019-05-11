---
title: 既存のビジネス サーバー ポリシーでは、Skype のアーカイブを変更します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: '概要: は、ユーザーのポリシーを Skype のビジネス サーバーのアーカイブを変更する方法を説明します。'
ms.openlocfilehash: 7e8cc208802af324690ff61cad971023d3a20232
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885004"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="819d9-103">既存のビジネス サーバー ポリシーでは、Skype のアーカイブを変更します。</span><span class="sxs-lookup"><span data-stu-id="819d9-103">Change an existing archiving policy in Skype for Business Server</span></span>
 
<span data-ttu-id="819d9-104">**の概要:** ユーザーのポリシーを Skype のビジネス サーバーのアーカイブを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="819d9-104">**Summary:** Learn how to change user archiving policies for Skype for Business Server.</span></span>
  
<span data-ttu-id="819d9-105">ビジネス サーバーの Skype を最初に配置するときは、展開内のユーザーのアーカイブの実装方法を決定する初期のアーカイブ ・ ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="819d9-105">When you first deploy Skype for Business Server, you set up initial archiving policies that determine how archiving is implemented for the users in your deployment.</span></span> <span data-ttu-id="819d9-106">このトピックでは、ポリシーを管理および修正する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="819d9-106">This topic describes how to manage and amend policies.</span></span> 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="819d9-107">コントロール パネルを使用してアーカイブ ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="819d9-107">Change archiving policies by using the Control Panel</span></span>

1. <span data-ttu-id="819d9-108">CsArchivingAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="819d9-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="819d9-109">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="819d9-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="819d9-110">左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**アーカイブ ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="819d9-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="819d9-111">ポリシー一覧で、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="819d9-111">In the list of policies, do one of the following:</span></span> 
    
   - <span data-ttu-id="819d9-112">展開全体のポリシーを変更するには、ポリシー一覧の [**グローバル**] をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="819d9-112">To change the policy for your entire deployment, click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="819d9-113">単一のサイトのポリシーを変更するには、ポリシー一覧のサイト名をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="819d9-113">To change the policy for a single site, click the site name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
   - <span data-ttu-id="819d9-114">単一のユーザーまたはユーザー グループのポリシーを変更するには、ポリシー一覧のユーザー名またはユーザー グループ名をクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="819d9-114">To change the policy for a single user or user group, click the user or user group name in the list of policies, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="819d9-115">[**アーカイブ ポリシーの編集**] ページで、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="819d9-115">On the **Edit Archiving Policy** page, do the following:</span></span>
    
   - <span data-ttu-id="819d9-116">ポリシーの内部アーカイブを有効または無効にするには、[**内部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="819d9-116">To enable or disable internal archiving for the policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="819d9-117">ポリシーの外部アーカイブを有効または無効にするには、[**外部通信のアーカイブ**] チェック ボックスをオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="819d9-117">To enable or disable external archiving for the policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="819d9-118">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="819d9-118">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="819d9-119">ユーザー ポリシーの設定は、そのポリシーを適用する特定のユーザーおよびユーザー グループにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="819d9-119">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="819d9-120">詳細については、 [Skype のビジネス サーバー内のユーザーにアーカイブ ・ ポリシーの適用](apply-a-policy-to-users.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="819d9-120">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="819d9-121">Windows PowerShell を使用してアーカイブ ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="819d9-121">Change archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="819d9-122">Windows PowerShell **Set-CsArchivingPolicy** コマンドレットを使用して、アーカイブ ポリシーを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="819d9-122">You can also change archiving policies by using the Windows PowerShell **Set-CsArchivingPolicy** cmdlet.</span></span>
  
### <a name="enable-archiving-policies"></a><span data-ttu-id="819d9-123">アーカイブ ポリシーを有効にする</span><span class="sxs-lookup"><span data-stu-id="819d9-123">Enable archiving policies</span></span>

<span data-ttu-id="819d9-124">内部通信セッションのアーカイブを有効にするには、 ArchiveInternal パラメーターの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="819d9-124">To enable the archiving of internal communication sessions, set the value of the ArchiveInternal parameter to True ($True):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

<span data-ttu-id="819d9-125">外部通信セッションのアーカイブを有効にするには、ArchiveExternal パラメーターの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="819d9-125">To enable the archiving of external communication sessions, set the value of the ArchiveExternal parameter to True ($True):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

<span data-ttu-id="819d9-126">両方の内部および外部の通信セッションのアーカイブを有効にするには、ArchiveInternal と ArchiveExternal の両方のパラメーターの値を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="819d9-126">To enable the archiving of both internal and external communication sessions, set the value of both the ArchiveInternal and ArchiveExternal parameters to True:</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a><span data-ttu-id="819d9-127">アーカイブ ポリシーを無効にする</span><span class="sxs-lookup"><span data-stu-id="819d9-127">Disable archiving policies</span></span>

<span data-ttu-id="819d9-128">アーカイブを全体的に無効にするには、ArchiveInternal パラメーターと ArchiveExternal パラメーターの両方の値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="819d9-128">To disable archiving altogether, set the value of both the ArchiveInternal and ArchiveExternal parameters to False ($False):</span></span> 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
