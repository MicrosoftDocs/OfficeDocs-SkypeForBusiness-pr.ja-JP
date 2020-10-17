---
title: 'Lync Server 2013: エンタープライズ Voip でユーザーを有効にする'
description: 'Lync Server 2013: エンタープライズ Voip でユーザーを有効にします。'
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
ms.openlocfilehash: 8aa8dbbeb507ced5217e517c1608c3a2a9259668
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557653"
---
# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="40aa3-103">Lync Server 2013 のエンタープライズ Voip でユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="40aa3-103">Enable users for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40aa3-104">_**トピックの最終更新日:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="40aa3-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="40aa3-105">1つ以上の仲介サーバーのファイルをインストールした後、発信通話ルーティングを構成し、オプションで1つ以上の高度なエンタープライズ Voip 機能を展開するには、次の手順を使用して、ユーザーがエンタープライズ Voip を使用して電話をかけることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-105">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40aa3-106">次の手順では、最初の操作は Lync Server コントロールパネルを使用して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-106">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="40aa3-107">その他の手順については、「Lync Server Management Shell」のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-107">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="40aa3-108">エンタープライズ Voip のユーザーアカウントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-108">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="40aa3-109">(オプション) ユーザー アカウントにユーザー固有の音声ポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-109">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="40aa3-110">(オプション) ユーザー アカウントにユーザー固有のダイヤル プランを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-110">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="40aa3-111">エンタープライズ Voip のユーザーアカウントを有効にするには</span><span class="sxs-lookup"><span data-stu-id="40aa3-111">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="40aa3-112">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40aa3-113">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="40aa3-114">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40aa3-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="40aa3-115">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="40aa3-116">**[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="40aa3-117">表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-117">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="40aa3-118">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-118">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="40aa3-119">[**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-119">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="40aa3-120">[**回線 URI**] をクリックし、正規化された一意の電話番号 (たとえば、tel:+14255550200) を入力します。</span><span class="sxs-lookup"><span data-stu-id="40aa3-120">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="40aa3-121">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-121">Click **Commit**.</span></span>

<span data-ttu-id="40aa3-122">エンタープライズ Voip に対してユーザーを有効にするには、ユーザーに音声ポリシーとダイヤルプランが割り当てられているかどうか (既定で割り当てられているか、ユーザー固有であるか) を確認します。</span><span class="sxs-lookup"><span data-stu-id="40aa3-122">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="40aa3-123">既定では、すべてのユーザーにグローバル音声ポリシーとダイヤル プランが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-123">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="40aa3-124">ユーザー アカウントが属しているサイトにサイト レベルの音声ポリシーとダイヤル プランが存在する場合は、それらのサイト ポリシーがユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-124">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="40aa3-125">ユーザーごとの音声ポリシーまたはダイヤル プランをユーザーに適用するには、**Grant-CsVoicePolicy** および **Grant-CsDialPlan** コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40aa3-125">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="40aa3-126">詳細については、「 [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) 」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40aa3-126">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="40aa3-127">音声ポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="40aa3-127">Voice Policy Assignment</span></span>

<span data-ttu-id="40aa3-128">エンタープライズ Voip が有効になっているすべてのユーザーアカウントに、グローバルおよびサイトレベルの音声ポリシーが自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-128">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="40aa3-129">特定のユーザーまたはグループに適用する音声ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-129">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="40aa3-130">このようなユーザーごとのポリシーは、ユーザーまたはグループに明示的に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="40aa3-130">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="40aa3-131">エンタープライズ Voip が有効になっているすべてのユーザーに対してグローバルまたはサイトの音声ポリシーを使用する場合は、このセクションをスキップして、このトピックで後述する「ダイヤルプランの割り当て」セクションを続行することができます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-131">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="40aa3-132">ユーザー固有の音声ポリシーを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="40aa3-132">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="40aa3-133">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-133">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40aa3-134">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="40aa3-135">既存のユーザー音声ポリシーをユーザーに割り当てるには、コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="40aa3-135">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="40aa3-136">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="40aa3-136">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="40aa3-137">この例では、表示名が Bob 友野のユーザーには、 **voicepolicyjapan という**という名前の音声ポリシーが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-137">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="40aa3-138">ユーザー固有の音声ポリシーの割り当て、または **set-csvoicepolicy** コマンドレットの実行の詳細については、「 [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) 」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40aa3-138">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="40aa3-139">ダイヤル プランの割り当て</span><span class="sxs-lookup"><span data-stu-id="40aa3-139">Dial Plan Assignment</span></span>

<span data-ttu-id="40aa3-140">エンタープライズ Voip またはダイヤルイン会議のユーザーのいずれかのユーザーアカウント構成を完了するには、ユーザーにダイヤルプランを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="40aa3-140">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="40aa3-141">既存のユーザーごとのダイヤル プランを明示的に割り当てないと、ユーザー アカウントでは、グローバル ダイヤル プランまたは存在する場合はサイト レベルのダイヤル プランが自動的に使用されます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-141">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="40aa3-142">エンタープライズ Voip が有効になっているすべてのユーザーに対してグローバルまたはサイトのダイヤルプランを使用する場合は、このセクションを省略できます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-142">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="40aa3-143">ダイヤル プランを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="40aa3-143">To assign a dial plan</span></span>

1.  <span data-ttu-id="40aa3-144">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40aa3-145">Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="40aa3-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="40aa3-146">ユーザー固有のダイヤル プランを割り当てるには、コマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="40aa3-146">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="40aa3-147">次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="40aa3-147">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="40aa3-148">この例では、表示名が Bob 友野のユーザーには、ダイヤルプラン **日本**という名前のユーザーダイヤルプランが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="40aa3-148">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="40aa3-149">ユーザーダイヤルプランの割り当て、または **get-csdialplan** コマンドレットの実行に関する詳細については、「 [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) 」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40aa3-149">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="40aa3-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="40aa3-150">See Also</span></span>


[<span data-ttu-id="40aa3-151">Lync Server 2013 でのエンタープライズ Voip のユーザーの無効化</span><span class="sxs-lookup"><span data-stu-id="40aa3-151">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

