---
title: ビジネス サーバーの Skype で既存の PIN ポリシーを変更します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
description: '概要: ビジネス サーバーの Skype で既存の PIN ポリシーを変更します。'
ms.openlocfilehash: 30b9926a7f8094cae1e23be6d0e9a0ade6d8d8a6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006186"
---
# <a name="modify-an-existing-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="bb776-103">ビジネス サーバーの Skype で既存の PIN ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="bb776-103">Modify an existing PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="bb776-104">**の概要:** ビジネス サーバーの Skype で既存の PIN ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="bb776-104">**Summary:** Modify an existing PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="bb776-105">ビジネス IP 電話の Skype に接続しているユーザーに個人識別番号 (PIN) 認証を提供するのには、[ **PIN ポリシー** ] タブを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb776-105">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="bb776-106">PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bb776-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="bb776-107">ユーザー レベルまたはサイト レベルの PIN ポリシーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bb776-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="bb776-108">既存の PIN ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="bb776-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="bb776-109">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ)、ユーザー アカウントのロールに割り当てられた、CsServerAdministrator または CsAdministrator、ビジネス サーバーの Skype を導入してネットワーク内の任意のコンピューターにログオンまたは.</span><span class="sxs-lookup"><span data-stu-id="bb776-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="bb776-110">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="bb776-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="bb776-111">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb776-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="bb776-112">[**PIN ポリシー**] ページでポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb776-112">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="bb776-p102">[**PIN ポリシーの編集**] の [**最小 PIN サイズ**] で、許可する PIN の最小文字数を入力または選択します。既定の最小サイズは 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="bb776-p102">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="bb776-p103">ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。既定では、最大試行回数は自動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="bb776-p103">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="bb776-118">[**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="bb776-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="bb776-p104">PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。このオプションをオンにしない限り、PIN が期限切れになることはありません。既定では、PIN に有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="bb776-p104">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="bb776-122">[**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="bb776-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="bb776-p105">[**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。既定では、ユーザーは自分の PIN を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="bb776-p105">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="bb776-p106">PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。既定では、複雑なパターンの数字のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="bb776-p106">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="bb776-128">共通のパターンは許可しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bb776-128">We recommend that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="bb776-129">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb776-129">Click **Commit**.</span></span>
    

