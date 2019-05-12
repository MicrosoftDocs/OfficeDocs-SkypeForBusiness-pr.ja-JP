---
title: ビジネス サーバーの Skype の暗証番号 (pin) ポリシーを削除します。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7c378927-2e41-418e-9721-327021bd2e45
description: '概要: は、Skype のビジネス サーバーのユーザーのダイヤルイン会議の PIN を削除します。'
ms.openlocfilehash: b281716c2e0560936ea2f94b773c8191f3e8987e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919648"
---
# <a name="delete-a-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="5b47d-103">ビジネス サーバーの Skype の暗証番号 (pin) ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b47d-103">Delete a PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="5b47d-104">**の概要:** Skype のビジネス サーバーのユーザーのダイヤルイン会議の PIN を削除します。</span><span class="sxs-lookup"><span data-stu-id="5b47d-104">**Summary:** Delete a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="5b47d-105">暗証番号 (PIN) ポリシーを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5b47d-105">Follow these steps to delete a personal identification number (PIN) policy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b47d-106">グローバル PIN ポリシーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="5b47d-106">You cannot delete the global PIN policy.</span></span> 
  
### <a name="to-delete-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="5b47d-107">ビジネス サーバーのコントロール パネルの Skype の暗証番号 (pin) ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="5b47d-107">To delete a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="5b47d-108">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="5b47d-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="5b47d-109">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="5b47d-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="5b47d-110">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b47d-110">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="5b47d-111">[**PIN ポリシー**] ページの検索フィールドに、削除するポリシーの名前または名前の一部を入力します。</span><span class="sxs-lookup"><span data-stu-id="5b47d-111">On the **PIN Policy** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="5b47d-112">ポリシーのリストで対象のポリシーをクリックし、[**編集**] をクリックして、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b47d-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="5b47d-113">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5b47d-113">Click **OK**.</span></span>
    
## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5b47d-114">Windows PowerShell コマンドレットを使用して、暗証番号 (pin) ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b47d-114">Removing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5b47d-115">暗証番号 (pin) ポリシーを削除するには、Windows PowerShell と削除 CsPinPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5b47d-115">You can delete PIN policies by using Windows PowerShell and the Remove-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="5b47d-116">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="5b47d-116">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5b47d-117">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b47d-117">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="5b47d-118">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="5b47d-118">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-pin-policy"></a><span data-ttu-id="5b47d-119">特定の PIN ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="5b47d-119">To remove a specific PIN policy</span></span>

- <span data-ttu-id="5b47d-120">次のコマンドは、Identity が RedmondPinPolicy の PIN ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b47d-120">This command removes the PIN policy with the Identity RedmondPinPolicy:</span></span>
    
  ```
  Remove-CsPinPolicy -Identity "RedmondPinPolicy"
  ```

### <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a><span data-ttu-id="5b47d-121">サイト スコープに適用されていたすべての PIN ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="5b47d-121">To remove all the PIN policies applied to the site scope</span></span>

- <span data-ttu-id="5b47d-122">次のコマンドは、サイト スコープで構成されたすべての PIN ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b47d-122">This command removes all the PIN policies configured at the site scope:</span></span>
    
  ```
  Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
  ```

### <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a><span data-ttu-id="5b47d-123">共通パターンの使用を許可するすべての PIN ポリシーを削除するには</span><span class="sxs-lookup"><span data-stu-id="5b47d-123">To remove all the PIN policies that allow the use of common patterns</span></span>

- <span data-ttu-id="5b47d-124">次のコマンドは、共通パターン G の使用を許可するすべての PIN ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="5b47d-124">And this one removes all the PIN policies that allow the use of common patterns:G</span></span>
    
  ```
  et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy
  ```

<span data-ttu-id="5b47d-125">詳細については、[削除 CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5b47d-125">For more information, see the help topic for the [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  

