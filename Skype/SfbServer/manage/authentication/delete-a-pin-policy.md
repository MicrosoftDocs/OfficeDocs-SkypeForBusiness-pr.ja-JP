---
title: Skype for Business Server で PIN ポリシーを削除する
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
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '概要: Skype for Business Server のユーザーのダイヤルイン会議 PIN を削除します。'
ms.openlocfilehash: b85d2bb29f8a1a28279a59f72957d201886d1dc4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096793"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="b3a99-103">Skype for Business Server で PIN ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="b3a99-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="b3a99-104">**概要:** Skype for Business Server のユーザーのダイヤルイン会議 PIN を削除します。</span><span class="sxs-lookup"><span data-stu-id="b3a99-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="b3a99-105">暗証番号 (PIN) ポリシーを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b3a99-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b3a99-106">グローバル PIN ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="b3a99-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b3a99-107">Skype for Business Server コントロール パネルで PIN ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="b3a99-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="b3a99-108">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator 役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="b3a99-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b3a99-109">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="b3a99-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b3a99-110">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3a99-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="b3a99-111">[**PIN ポリシー**] ページの検索フィールドにで、削除するポリシーの名前または名前の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="b3a99-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="b3a99-112">ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3a99-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="b3a99-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b3a99-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b3a99-114">コマンドレットを使用した PIN ポリシー Windows PowerShellする</span><span class="sxs-lookup"><span data-stu-id="b3a99-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b3a99-115">PIN ポリシーを削除するには、pin ポリシーと Windows PowerShellコマンドレットをRemove-CsPinPolicyします。</span><span class="sxs-lookup"><span data-stu-id="b3a99-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="b3a99-116">このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b3a99-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b3a99-117">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3a99-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b3a99-118">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="b3a99-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="b3a99-119">特定の PIN ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="b3a99-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="b3a99-120">次のコマンドは、Identity が RedmondPinPolicy の PIN ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b3a99-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```PowerShell
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="b3a99-121">サイト スコープに適用されているすべての PIN ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="b3a99-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="b3a99-122">次のコマンドは、サイト スコープで構成されたすべての PIN ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b3a99-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="b3a99-123">一般的なパターンを使用できるすべての PIN ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="b3a99-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="b3a99-124">次のコマンドは、共通パターン G の使用を許可するすべての PIN ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="b3a99-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```PowerShell
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="b3a99-125">詳細については [、Remove-CsPinPolicy コマンドレットのヘルプ トピックを参照](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) してください。</span><span class="sxs-lookup"><span data-stu-id="b3a99-125">For more information, see the help topic for the [Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
