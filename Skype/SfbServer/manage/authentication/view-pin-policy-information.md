---
title: Skype for Business Server で PIN ポリシー情報を表示する
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
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '概要: Skype for Business Server のユーザーの PIN ポリシー情報を表示します。'
ms.openlocfilehash: 4c223d5736df7f5f8ee1dbee11401a9fef2237cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806527"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="d8879-103">Skype for Business Server で PIN ポリシー情報を表示する</span><span class="sxs-lookup"><span data-stu-id="d8879-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="d8879-104">**概要:** Skype for Business Server のユーザーの PIN ポリシー情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d8879-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="d8879-105">[PIN ポリシー] **タブを使用** して、IP 電話で Skype for Business に接続しているユーザーの暗証番号 (PIN) 認証を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d8879-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="d8879-106">PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d8879-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="d8879-107">ユーザー レベルまたはサイト レベルの PIN ポリシーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d8879-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="d8879-108">Skype for Business Server コントロール パネルで PIN ポリシーに関する情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="d8879-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="d8879-109">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウントから、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Skype for Business Server を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="d8879-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="d8879-110">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d8879-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="d8879-111">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8879-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="d8879-112">[**PIN ポリシー**] ページでポリシーをクリックし、[**編集**]、[**詳細の表示**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8879-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d8879-113">コマンドレットを使用して PIN Windows PowerShell表示する</span><span class="sxs-lookup"><span data-stu-id="d8879-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d8879-114">また、PIN ポリシーを表示するには、Windows PowerShellコマンドレットをGet-CsPinPolicyします。</span><span class="sxs-lookup"><span data-stu-id="d8879-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="d8879-115">このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d8879-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d8879-116">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8879-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d8879-117">プロセスは Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="d8879-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="d8879-118">PIN ポリシーを表示するには</span><span class="sxs-lookup"><span data-stu-id="d8879-118">To view PIN policies</span></span>

<span data-ttu-id="d8879-119">すべての PIN ポリシーに関する情報を表示するには、Skype for Business Server 管理シェルで次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d8879-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```PowerShell
  Get-CsPinPolicy
  ```

<span data-ttu-id="d8879-120">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8879-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="d8879-121">詳細については [、Get-CsPinPolicy コマンドレットのヘルプ トピックを参照](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) してください。</span><span class="sxs-lookup"><span data-stu-id="d8879-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d8879-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8879-122">See also</span></span>

[<span data-ttu-id="d8879-123">Skype for Business Server で新しい PIN ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="d8879-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
