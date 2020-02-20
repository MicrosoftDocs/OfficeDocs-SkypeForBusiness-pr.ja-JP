---
title: 'Lync Server 2013: サイトまたはユーザーのグループのダイヤルイン会議の PIN 設定を作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b65d62514cabe64381fc002e4c7242c9a782acb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a><span data-ttu-id="0afd4-102">サイトまたはユーザーのグループに対して Lync Server 2013 でダイヤルイン会議の PIN 設定を作成または変更する</span><span class="sxs-lookup"><span data-stu-id="0afd4-102">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0afd4-103">_**トピックの最終更新日:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="0afd4-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="0afd4-104">ユーザー レベルまたはサイト レベルのダイヤルイン会議の暗証番号 (PIN) ポリシーを作成または変更するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0afd4-104">Follow these steps to create or modify a user-level or a site-level dial-in conferencing personal identification number (PIN) policy.</span></span> <span data-ttu-id="0afd4-105">グローバル PIN ポリシーの変更方法の詳細については、「 [Lync Server 2013 で既定のダイヤルイン会議 PIN 設定を変更](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0afd4-105">For details about how to change the global PIN policy, see [Modify the default dial-in conferencing PIN settings in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="0afd4-106">ユーザーまたはサイトの PIN ポリシーを作成するには</span><span class="sxs-lookup"><span data-stu-id="0afd4-106">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="0afd4-107">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0afd4-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="0afd4-108">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0afd4-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0afd4-109">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0afd4-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0afd4-110">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0afd4-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="0afd4-111">[**PIN ポリシー**] ページで [**新規**] をクリックして、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="0afd4-111">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="0afd4-p103">ユーザーレベルのポリシーを作成するには、[**ユーザー ポリシー**] をクリックします。 [**新しい PIN ポリシー**] の [**名前**] に、ポリシーを説明する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0afd4-p103">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="0afd4-p104">サイトレベルのポリシーを作成するには、[**サイト ポリシー**] をクリックします。[**サイトの選択**] 検索フィールドに、ポリシーを作成するサイトの名前または名前の一部を入力します。 サイトの一覧で、対象のサイトをクリックして [**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0afd4-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="0afd4-117">[**説明**] フィールドに、PIN ポリシーの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="0afd4-117">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="0afd4-p105">[**最小 PIN サイズ**] フィールドで、許可する PIN の最小サイズを入力または選択します。 既定の最小サイズは 5 桁です。</span><span class="sxs-lookup"><span data-stu-id="0afd4-p105">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="0afd4-p106">ユーザーがロックアウトされるまでに許可される最大ログオン試行回数を指定できるようにするには、[**最大ログオン試行回数を指定する**] チェック ボックスをオンにします。 このオプションをオンにしない場合、許可される最大試行回数は、PIN の桁数に応じて自動的に決定されます。 既定では、最大試行回数は自動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="0afd4-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="0afd4-123">[**最大ログオン試行回数を指定する**] チェック ボックスをオンにした場合は、[**最大ログオン試行回数**] に許可するログオンの最大試行回数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="0afd4-123">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="0afd4-p107">PIN の有効期限を設定するには、[**PIN の有効期限を有効にする**] チェック ボックスをオンにします。 このオプションをオンにしない限り、PIN が期限切れになることはありません。 既定では、PIN に有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="0afd4-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

10. <span data-ttu-id="0afd4-127">[**PIN の有効期限を有効にする**] チェック ボックスをオンにした場合は、[**PIN の有効期限 (日数)**] で、PIN の有効期限が切れるまでの日数を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="0afd4-127">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="0afd4-p108">[**PIN 履歴の数**] に、PIN の数を入力します。作成した PIN の数がこの数を超えると、PIN を再利用できます。 既定では、ユーザーは自分の PIN を再利用できます。</span><span class="sxs-lookup"><span data-stu-id="0afd4-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="0afd4-p109">PIN に、連続番号や同じ数字の繰り返しなどよくあるパターンの番号を許可するには、[**共通のパターンの許可**] チェック ボックスをオンにします。 このオプションをオンにしない場合は、複雑な数字パターンのみが許可されます。 既定では、複雑なパターンの数字のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="0afd4-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="0afd4-133">共通のパターンは許可しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0afd4-133">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="0afd4-134">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0afd4-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a><span data-ttu-id="0afd4-135">ユーザーまたはサイトの PIN ポリシーを変更するには</span><span class="sxs-lookup"><span data-stu-id="0afd4-135">To change a user or site PIN policy</span></span>

1.  <span data-ttu-id="0afd4-136">RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0afd4-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="0afd4-137">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0afd4-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0afd4-138">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0afd4-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0afd4-139">左側のナビゲーション バーで [**会議**]、[**PIN ポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0afd4-139">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="0afd4-140">[**PIN ポリシー**] ページで、変更する PIN ポリシーをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0afd4-140">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0afd4-141">[**PIN ポリシーの編集**] で、ポリシー名以外のポリシー設定を変更します。ポリシー名は変更できません。</span><span class="sxs-lookup"><span data-stu-id="0afd4-141">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>

6.  <span data-ttu-id="0afd4-142">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0afd4-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

