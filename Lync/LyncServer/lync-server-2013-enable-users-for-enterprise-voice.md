---
title: 'Lync Server 2013: エンタープライズ Voip でユーザーを有効にする'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d03f47cbe637e2c6fe6a0466b73a3588b842d6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501044"
---
# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="0985d-102">Lync Server 2013 のエンタープライズ Voip でユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="0985d-102">Enable users for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0985d-103">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0985d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0985d-104">1つ以上の仲介サーバーのファイルをインストールした後、発信通話ルーティングを構成し、オプションで1つ以上の高度なエンタープライズ Voip 機能を展開するには、次の手順を使用して、ユーザーがエンタープライズ Voip を使用して電話をかけることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="0985d-104">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0985d-105">次の手順では、最初の操作は Lync Server コントロールパネルを使用して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="0985d-105">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="0985d-106">その他の手順については、「Lync Server Management Shell」のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0985d-106">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="0985d-107">エンタープライズ Voip のユーザーアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0985d-107">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="0985d-108">(オプション) ユーザー アカウントにユーザー固有の音声ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0985d-108">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="0985d-109">(オプション) ユーザー アカウントにユーザー固有のダイヤル プランを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="0985d-109">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="0985d-110">エンタープライズ Voip のユーザーアカウントを有効にするには</span><span class="sxs-lookup"><span data-stu-id="0985d-110">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="0985d-111">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0985d-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0985d-112">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0985d-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0985d-113">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0985d-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0985d-114">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0985d-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="0985d-115">**[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0985d-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="0985d-116">表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0985d-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="0985d-117">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0985d-117">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="0985d-118">[**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0985d-118">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="0985d-119">[**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。</span><span class="sxs-lookup"><span data-stu-id="0985d-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="0985d-120">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0985d-120">Click **Commit**.</span></span>

<span data-ttu-id="0985d-121">エンタープライズ Voip に対してユーザーを有効にするには、ユーザーに音声ポリシーとダイヤルプランが割り当てられているかどうか (既定で割り当てられているか、ユーザー固有であるか) を確認します。</span><span class="sxs-lookup"><span data-stu-id="0985d-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="0985d-122">既定では、すべてのユーザーにグローバル音声ポリシーとダイヤル プランが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0985d-122">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="0985d-123">ユーザー アカウントが属しているサイトにサイト レベルの音声ポリシーとダイヤル プランが存在する場合は、それらのサイト ポリシーがユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0985d-123">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="0985d-124">ユーザーごとの音声ポリシーまたはダイヤル プランをユーザーに適用するには、**Grant-CsVoicePolicy** および **Grant-CsDialPlan** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0985d-124">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="0985d-125">詳細については、「 [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) 」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0985d-125">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="0985d-126">音声ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="0985d-126">Voice Policy Assignment</span></span>

<span data-ttu-id="0985d-127">エンタープライズ Voip が有効になっているすべてのユーザーアカウントに、グローバルおよびサイトレベルの音声ポリシーが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0985d-127">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="0985d-128">特定のユーザーまたはグループに適用する音声ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0985d-128">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="0985d-129">このようなユーザーごとのポリシーは、ユーザーまたはグループに明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0985d-129">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="0985d-130">エンタープライズ Voip が有効になっているすべてのユーザーに対してグローバルまたはサイトの音声ポリシーを使用する場合は、このセクションをスキップして、このトピックで後述する「ダイヤルプランの割り当て」セクションを続行することができます。</span><span class="sxs-lookup"><span data-stu-id="0985d-130">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="0985d-131">ユーザー固有の音声ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="0985d-131">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="0985d-132">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0985d-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0985d-133">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0985d-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0985d-134">既存のユーザー音声ポリシーをユーザーに割り当てるには、コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0985d-134">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="0985d-135">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="0985d-135">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="0985d-136">この例では、表示名が Bob 友野のユーザーには、 **voicepolicyjapan という**という名前の音声ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0985d-136">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="0985d-137">ユーザー固有の音声ポリシーの割り当て、または **set-csvoicepolicy** コマンドレットの実行の詳細については、「 [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) 」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0985d-137">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="0985d-138">ダイヤル プランの割り当て</span><span class="sxs-lookup"><span data-stu-id="0985d-138">Dial Plan Assignment</span></span>

<span data-ttu-id="0985d-139">エンタープライズ Voip またはダイヤルイン会議のユーザーのいずれかのユーザーアカウント構成を完了するには、ユーザーにダイヤルプランを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0985d-139">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="0985d-140">既存のユーザーごとのダイヤル プランを明示的に割り当てないと、ユーザー アカウントでは、グローバル ダイヤル プランまたは存在する場合はサイト レベルのダイヤル プランが自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0985d-140">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="0985d-141">エンタープライズ Voip が有効になっているすべてのユーザーに対してグローバルまたはサイトのダイヤルプランを使用する場合は、このセクションを省略できます。</span><span class="sxs-lookup"><span data-stu-id="0985d-141">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="0985d-142">ダイヤル プランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="0985d-142">To assign a dial plan</span></span>

1.  <span data-ttu-id="0985d-143">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="0985d-143">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0985d-144">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0985d-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0985d-145">ユーザー固有のダイヤル プランを割り当てるには、コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0985d-145">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="0985d-146">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="0985d-146">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="0985d-147">この例では、表示名が Bob 友野のユーザーには、ダイヤルプラン **日本**という名前のユーザーダイヤルプランが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0985d-147">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="0985d-148">ユーザーダイヤルプランの割り当て、または **get-csdialplan** コマンドレットの実行に関する詳細については、「 [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) 」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0985d-148">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0985d-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="0985d-149">See Also</span></span>


[<span data-ttu-id="0985d-150">Lync Server 2013 でのエンタープライズ Voip のユーザーの無効化</span><span class="sxs-lookup"><span data-stu-id="0985d-150">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

