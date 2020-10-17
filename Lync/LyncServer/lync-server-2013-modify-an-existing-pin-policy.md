---
title: 'Lync Server 2013: 既存の PIN ポリシーの変更'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify an existing PIN policy
ms:assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520993(v=OCS.15)
ms:contentKeyID: 48184143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b11b9921d7eda940c5ad8debf48aeb6f2388bfda
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534384"
---
# <a name="modify-an-existing-pin-policy-in-lync-server-2013"></a><span data-ttu-id="3d691-102">Lync Server 2013 で既存の PIN ポリシーを変更する</span><span class="sxs-lookup"><span data-stu-id="3d691-102">Modify an existing PIN policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d691-103">_**トピックの最終更新日:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="3d691-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="3d691-104">[ **Pin ポリシー** ] タブを使用すると、IP 電話を使用して Lync 2013 に接続しているユーザーに暗証番号 (pin) 認証を提供できます。</span><span class="sxs-lookup"><span data-stu-id="3d691-104">You can use the **PIN Policy** tab to provide personal identification number (PIN) authentication to users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="3d691-105">PIN 認証を使用するには、Web サービス設定で [**PIN 認証を有効にする**] が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3d691-105">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="3d691-106">詳細については、「 [Lync Server 2013 で既存の Web サービス構成設定を変更](lync-server-2013-modify-existing-web-service-configuration-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d691-106">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="3d691-107">ユーザー レベルまたはサイト レベルの PIN ポリシーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3d691-107">Follow these steps to modify a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-modify-an-existing-pin-policy"></a><span data-ttu-id="3d691-108">既存の PIN ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="3d691-108">To modify an existing PIN policy</span></span>

1.  <span data-ttu-id="3d691-109">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="3d691-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="3d691-110">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="3d691-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3d691-111">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3d691-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3d691-112">左側のナビゲーション バーで [**セキュリティ**] をクリックし、[**PIN ポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d691-112">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="3d691-113">[**PIN ポリシー**] ページでポリシーをクリックし、[**編集**] に続いて [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d691-113">On the **PIN Policy** page, click a policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3d691-p103">[**PIN ポリシーの編集**] の [**最小 PIN サイズ**] で、許可する PIN の最小文字数を入力または選択します。 既定の最小サイズは 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="3d691-p103">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

6.  <span data-ttu-id="3d691-p104">ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。 このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。 既定では、最大試行回数は自動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="3d691-p104">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

7.  <span data-ttu-id="3d691-119">[**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="3d691-119">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

8.  <span data-ttu-id="3d691-p105">PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。 このオプションをオンにしない限り、PIN が期限切れになることはありません。 既定では、PIN に有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="3d691-p105">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

9.  <span data-ttu-id="3d691-123">[**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="3d691-123">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

10. <span data-ttu-id="3d691-p106">[**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。 既定では、ユーザーは自分の PIN を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="3d691-p106">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

11. <span data-ttu-id="3d691-p107">PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。 このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。 既定では、複雑なパターンの数字のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="3d691-p107">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3d691-129">共通のパターンは許可しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3d691-129">We recommend that you do not allow common patterns.</span></span>

    
    </div>

12. <span data-ttu-id="3d691-130">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3d691-130">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

