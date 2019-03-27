---
title: Skype のビジネス サーバーの暗証番号 (pin) ポリシー情報を表示します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
description: '概要: ビジネス サーバーの Skype のユーザーの暗証番号 (pin) ポリシー情報を表示します。'
ms.openlocfilehash: 5fdd042f01c325bfffedbfa32fa14d9e667ef7be
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888924"
---
# <a name="view-pin-policy-information-in-skype-for-business-server"></a><span data-ttu-id="dc3ec-103">Skype のビジネス サーバーの暗証番号 (pin) ポリシー情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-103">View PIN policy information in Skype for Business Server</span></span>
 
<span data-ttu-id="dc3ec-104">**の概要:** ビジネス サーバーの Skype のユーザーの暗証番号 (pin) ポリシー情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-104">**Summary:** View a user's PIN policy information for Skype for Business Server.</span></span>
  
<span data-ttu-id="dc3ec-105">ビュー個人識別番号 (PIN) 認証の IP 電話でのビジネス用の Skype に接続しているユーザーに**暗証番号 (pin) ポリシー** ] タブを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-105">You can use the **PIN Policy** tab to view personal identification number (PIN) authentication of users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="dc3ec-106">PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="dc3ec-107">ユーザー レベルまたはサイト レベルの PIN ポリシーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-view-information-about-a-pin-policy-in-skype-for-business-server-control-panel"></a><span data-ttu-id="dc3ec-108">Skype のビジネス サーバーのコントロール パネルの暗証番号 (pin) のポリシーに関する情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="dc3ec-108">To view information about a PIN policy in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="dc3ec-109">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="dc3ec-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="dc3ec-110">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="dc3ec-111">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="dc3ec-112">[**PIN ポリシー**] ページでポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dc3ec-113">Windows PowerShell コマンドレットを使用して、暗証番号 (pin) ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-113">Viewing PIN Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dc3ec-114">Windows PowerShell と Get CsPinPolicy コマンドレットを使用して、暗証番号 (pin) ポリシーを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-114">You can also view PIN policies by using Windows PowerShell and the Get-CsPinPolicy cmdlet.</span></span> <span data-ttu-id="dc3ec-115">ビジネス サーバー管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-115">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dc3ec-116">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-116">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="dc3ec-117">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-117">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-pin-policies"></a><span data-ttu-id="dc3ec-118">PIN ポリシーを表示するには</span><span class="sxs-lookup"><span data-stu-id="dc3ec-118">To view PIN policies</span></span>

<span data-ttu-id="dc3ec-119">すべての PIN ポリシーに関する情報を表示するのには、Skype のビジネス サーバー管理シェルの次のコマンドを入力し、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-119">To view information about all your PIN policies, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsPinPolicy
  ```

<span data-ttu-id="dc3ec-120">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-120">That will return information similar to this:</span></span>

<pre>
Identity             : Global
Description          :
MinPasswordLength    : 5
PINHistoryCount      : 0
AllowCommonPatterns  : False
PINLifetime          : 0
MaximumLogonAttempts :
</pre>

<span data-ttu-id="dc3ec-121">詳細については、 [Get CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-121">For more information, see the help topic for the [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="dc3ec-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc3ec-122">See also</span></span>

[<span data-ttu-id="dc3ec-123">Skype のビジネス サーバーの新しい暗証番号 (pin) ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dc3ec-123">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
