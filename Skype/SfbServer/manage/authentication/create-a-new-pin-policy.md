---
title: Skype のビジネス サーバーの新しい暗証番号 (pin) ポリシーを作成します。
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: '概要: は、Skype のビジネス サーバーの新しい暗証番号 (pin) ポリシーを作成します。'
ms.openlocfilehash: ac51f0c81630969ec50494914e92c8302fa7d0aa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879526"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="e59c9-103">Skype のビジネス サーバーの新しい暗証番号 (pin) ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e59c9-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="e59c9-104">**の概要:** Skype のビジネスのサーバーに新しい暗証番号 (pin) ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="e59c9-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="e59c9-105">**暗証番号 (pin) ポリシー**のページを使用すると、IP 電話でのビジネス用の Skype に接続しているユーザーに個人識別番号 (PIN) 認証を提供します。</span><span class="sxs-lookup"><span data-stu-id="e59c9-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="e59c9-106">PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e59c9-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="e59c9-107">ユーザーレベルまたはサイトレベルの PIN ポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e59c9-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="e59c9-108">ユーザーまたはサイトの PIN ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="e59c9-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="e59c9-109">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="e59c9-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="e59c9-110">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="e59c9-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e59c9-111">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e59c9-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="e59c9-112">[**PIN ポリシー**] ページで [**新規**] をクリックして、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="e59c9-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="e59c9-p102">ユーザーレベルのポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。[**新しい PIN ポリシー**] の [**名前**] に、ポリシーを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e59c9-p102">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="e59c9-p103">サイトレベルのポリシーを作成するには、[**サイト ポリシー**] をクリックします。[**サイトの選択**] 検索フィールドに、ポリシーを作成するサイトの名前または名前の一部を入力します。サイトの結果一覧で対象のサイトをクリックして、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e59c9-p103">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="e59c9-118">[**説明**] フィールドに、PIN ポリシーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="e59c9-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="e59c9-p104">[**最小 PIN サイズ**] フィールドで、許可する PIN の最小サイズを入力または選択します。既定の最小サイズは 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="e59c9-p104">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="e59c9-p105">ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。既定では、最大試行回数は自動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="e59c9-p105">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="e59c9-124">[**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="e59c9-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="e59c9-p106">PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。このオプションをオンにしない限り、PIN が期限切れになることはありません。既定では、PIN に有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="e59c9-p106">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="e59c9-128">[**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="e59c9-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="e59c9-p107">[**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。既定では、ユーザーは自分の PIN を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="e59c9-p107">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="e59c9-p108">PIN に、"1234" や "8888" など、よくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。既定では、複雑なパターンの数字のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="e59c9-p108">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e59c9-134">共通のパターンは許可しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e59c9-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="e59c9-135">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e59c9-135">Click **Commit**.</span></span>
    

