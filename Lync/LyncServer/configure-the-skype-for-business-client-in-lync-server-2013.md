---
title: Lync Server 2013 での Skype for Business クライアントの構成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 632eed40992bfcff53072d618313afe3501431be
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="fd28a-102">Configure the client experience with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fd28a-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd28a-103">_**最終更新日:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="fd28a-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="fd28a-104">**概要:** このトピックでは、Lync Server 2013 環境での Skype for Business クライアントユーザー向けのクライアントエクスペリエンスを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="fd28a-105">クライアントエクスペリエンスを構成できるのは、2014年12月の累積更新プログラム (5.0.8308.857) 以降がインストールされている Lync Server 2013 を実行している場合のみです。</span><span class="sxs-lookup"><span data-stu-id="fd28a-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="fd28a-106">Lync Server 2013 の更新については、「 [Lync server 2013 の更新プログラム](http://go.microsoft.com/fwlink/p/?linkid=532651)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd28a-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="fd28a-107">Skype for Business は、Skype コンシューマーの製品エクスペリエンスに基づいた新しいユーザーエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="fd28a-108">Skype for Business には、Lync のすべての機能に加えて、簡単なコントロールと使い慣れたアイコンが付いた新機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fd28a-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="fd28a-109">新しいクライアントエクスペリエンスの詳細については、「 [Lync が Skype For business に変わりました。新機能」](http://go.microsoft.com/fwlink/?linkid=529022)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd28a-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](http://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="fd28a-110">Lync Server 2013 では、新しい Skype for Business クライアントエクスペリエンスと Lync クライアントエクスペリエンスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fd28a-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="fd28a-111">管理者は、ユーザー用に優先するクライアント エクスペリエンスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="fd28a-112">たとえば、新しい Skype for Business のエクスペリエンスで組織内のユーザーが完全にトレーニングを受けられるまで、Lync クライアントエクスペリエンスを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="fd28a-113">または、すべてのユーザーを Skype for Business Server 2015 にアップグレードしていない場合、すべてのユーザーが新しいサーバーにアップグレードされるまで、すべてのユーザーが同じクライアントエクスペリエンスを使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd28a-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fd28a-114">組織に Skype for Business Server 2015 と Lync Server 2013 の両方が展開されている場合、既定のクライアントエクスペリエンスは、サーバーのバージョンと UI の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fd28a-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="fd28a-115">ユーザーが Skype for Business を初めて起動すると、Lync ユーザーインターフェイスを選んだ場合でも、常に Skype for business のユーザーインターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="fd28a-116">数分後に、ユーザーは Lync モードに切り替えるように求められます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="fd28a-117">詳細については、このトピックの後半にある「<STRONG>最初の起動クライアントの動作</STRONG>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd28a-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fd28a-118">Lync 2013 クライアントエクスペリエンスは、Skype for Business 2016 クライアントバージョンでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="fd28a-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="fd28a-119">Lync 2013 クライアントを使用するようにクライアント環境を構成する前に、クライアント バージョンを調べて、バージョンの先頭が 16 ではない (16.x.x.x などではない) ことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fd28a-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="fd28a-120">Configure the client experience</span><span class="sxs-lookup"><span data-stu-id="fd28a-120">Configure the client experience</span></span>

<span data-ttu-id="fd28a-121">組織内のユーザーに表示されるクライアントエクスペリエンスを指定するには、EnableSkypeUI パラメーターを使用して、 **Set-CSClientPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="fd28a-122">次のコマンドは、組織内のすべてのユーザーに対してグローバルポリシーの影響を受ける Skype for Business クライアントのエクスペリエンスを選択します (「サイトまたはユーザー固有のポリシーはグローバルポリシーを上書きします)」を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="fd28a-123">次のコマンドでは、組織内のすべてのユーザーに対して、グローバルポリシーの影響を受ける Lync クライアントエクスペリエンスが選択されます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="fd28a-124">次のコマンドは、Redmond サイト内のすべてのユーザーに対して Skype for Business クライアントエクスペリエンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="fd28a-125">組織内の特定のユーザーに対してクライアントエクスペリエンスを構成する場合は、**新しい**ユーザーポリシーを作成して、**グラント clientpolicy**を使用して特定のユーザーにポリシーを割り当てることができます。コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="fd28a-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="fd28a-126">たとえば、次のコマンドは、Skype for Business クライアントエクスペリエンスを選択する新しいクライアントポリシー、SalesClientUI を作成します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="fd28a-127">次のコマンドを実行すると、Sales 部門のすべてのメンバーにポリシー SalesClientUI が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="fd28a-128">最初の起動クライアントの動作</span><span class="sxs-lookup"><span data-stu-id="fd28a-128">First launch client behaviors</span></span>

<span data-ttu-id="fd28a-129">既定では、ユーザーが Skype for business を初めて起動したときに、以前に説明したように、EnableSkypeUI パラメーターの値を $False に設定して、Lync クライアントエクスペリエンスを選択した場合でも、Skype for Business のユーザーインターフェイスが表示されます。.</span><span class="sxs-lookup"><span data-stu-id="fd28a-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="fd28a-130">起動から数分後に、Lync モードに切り替えるかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="fd28a-131">ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスを表示したい場合は、クライアントを更新後に初めて開始する前に、以下の手順を行います。</span><span class="sxs-lookup"><span data-stu-id="fd28a-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="fd28a-132">前に説明した`EnableSkypeUI`ように使用しているポリシーで、の値が $False に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="fd28a-p108">ユーザーのコンピューターで、システム レジストリを更新します。 レジストリの更新は、ユーザーが初めて Skype for Business クライアントを起動する前に 1 回だけ行う必要があります。 ドメインに参加しているコンピューターでレジストリを更新するグループ ポリシー オブジェクトを作成する方法については、このトピックの後半のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd28a-p108">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="fd28a-136">**\_\\\\\\\\\] [現在のユーザーのウイルスのウイルス] Microsoft Office Lync キーで、新しいバイナリ値を作成します。\_ \[** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fd28a-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="fd28a-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span><span class="sxs-lookup"><span data-stu-id="fd28a-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="fd28a-138">キーは、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="fd28a-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="fd28a-139">これで、ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザー インターフェイスが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="fd28a-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="fd28a-140">ようこそ画面のチュートリアルの表示を制御する</span><span class="sxs-lookup"><span data-stu-id="fd28a-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="fd28a-141">ユーザーが Skype for Business クライアントを開くと、既定の動作では [ようこそ] 画面が表示されます。これには、*ほとんどのユーザーからの質問に対する7つのヒント*が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd28a-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="fd28a-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span><span class="sxs-lookup"><span data-stu-id="fd28a-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="fd28a-143">[ウイルス**の\_現在\_の\\ユーザー\\ソフトウェア\\Microsoft\\Office\\15.0\] Lync キー] で、新しい DWORD (32 ビット) 値を作成します。 \[** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fd28a-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="fd28a-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span><span class="sxs-lookup"><span data-stu-id="fd28a-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="fd28a-145">キーは、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="fd28a-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="fd28a-146">クライアント チュートリアルをオフにする</span><span class="sxs-lookup"><span data-stu-id="fd28a-146">Turn off the client tutorial</span></span>

<span data-ttu-id="fd28a-147">ユーザーがチュートリアルにアクセスできないようにするには、以下のレジストリ値を指定して、クライアント チュートリアルをオフにします。</span><span class="sxs-lookup"><span data-stu-id="fd28a-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="fd28a-148">[ウイルス**の\_現在\_の\\ユーザー\\ソフトウェア\\Microsoft\\Office\\15.0\] Lync キー] で、新しい DWORD (32 ビット) 値を作成します。 \[** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="fd28a-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="fd28a-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span><span class="sxs-lookup"><span data-stu-id="fd28a-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="fd28a-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span><span class="sxs-lookup"><span data-stu-id="fd28a-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="fd28a-151">既定のクライアントエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="fd28a-151">Default client experiences</span></span>

<span data-ttu-id="fd28a-152">組織に Skype for Business Server 2015 と Lync Server の両方が展開されている場合、クライアントのエクスペリエンスはサーバーのバージョンと Skype の UI の設定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="fd28a-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="fd28a-153">以下の表に、サーバー バージョンと UI 設定に基づく最初のクライアント エクスペリエンスを示します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fd28a-154">サーバー バージョン</span><span class="sxs-lookup"><span data-stu-id="fd28a-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="fd28a-155">EnableSkypeUI 設定</span><span class="sxs-lookup"><span data-stu-id="fd28a-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="fd28a-156">クライアント エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="fd28a-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd28a-157">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fd28a-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="fd28a-158">既定</span><span class="sxs-lookup"><span data-stu-id="fd28a-158">Default</span></span></p></td>
<td><p><span data-ttu-id="fd28a-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fd28a-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd28a-160">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fd28a-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="fd28a-161">True</span><span class="sxs-lookup"><span data-stu-id="fd28a-161">True</span></span></p></td>
<td><p><span data-ttu-id="fd28a-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fd28a-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd28a-163">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fd28a-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="fd28a-164">False</span><span class="sxs-lookup"><span data-stu-id="fd28a-164">False</span></span></p></td>
<td><p><span data-ttu-id="fd28a-165">ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd28a-166">Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</span><span class="sxs-lookup"><span data-stu-id="fd28a-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="fd28a-167">既定</span><span class="sxs-lookup"><span data-stu-id="fd28a-167">Default</span></span></p></td>
<td><p><span data-ttu-id="fd28a-168">ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd28a-169">Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</span><span class="sxs-lookup"><span data-stu-id="fd28a-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="fd28a-170">True</span><span class="sxs-lookup"><span data-stu-id="fd28a-170">True</span></span></p></td>
<td><p><span data-ttu-id="fd28a-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fd28a-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd28a-172">Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</span><span class="sxs-lookup"><span data-stu-id="fd28a-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="fd28a-173">False</span><span class="sxs-lookup"><span data-stu-id="fd28a-173">False</span></span></p></td>
<td><p><span data-ttu-id="fd28a-174">ユーザーが Lync モードに切り替えるように求められた (UI 設定を $true) に変更した場合、ユーザーは後で Skype for Business に切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd28a-175">Lync Server 2010 または Lync Server 2013 (パッチなし)</span><span class="sxs-lookup"><span data-stu-id="fd28a-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="fd28a-176">既定</span><span class="sxs-lookup"><span data-stu-id="fd28a-176">Default</span></span></p></td>
<td><p><span data-ttu-id="fd28a-177">ユーザーが Lync クライアントエクスペリエンスに切り替えるように求められた (ユーザーは後で Skype for Business に切り替えることができない)</span><span class="sxs-lookup"><span data-stu-id="fd28a-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd28a-178">次の表は、管理者が Skype UI エクスペリエンスの初期設定を変更したときのクライアントエクスペリエンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="fd28a-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fd28a-179">サーバー バージョン</span><span class="sxs-lookup"><span data-stu-id="fd28a-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="fd28a-180">Skype UI の設定</span><span class="sxs-lookup"><span data-stu-id="fd28a-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="fd28a-181">クライアント UI = Lync</span><span class="sxs-lookup"><span data-stu-id="fd28a-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="fd28a-182">クライアント UI = Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fd28a-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd28a-183">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fd28a-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="fd28a-184">True</span><span class="sxs-lookup"><span data-stu-id="fd28a-184">True</span></span></p></td>
<td><p><span data-ttu-id="fd28a-185">Skype for Business に切り替えるように求められたユーザー</span><span class="sxs-lookup"><span data-stu-id="fd28a-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="fd28a-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fd28a-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd28a-187">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fd28a-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="fd28a-188">False</span><span class="sxs-lookup"><span data-stu-id="fd28a-188">False</span></span></p></td>
<td><p><span data-ttu-id="fd28a-189">Lync UI</span><span class="sxs-lookup"><span data-stu-id="fd28a-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="fd28a-190">Lync UI への切り替えを求められたユーザー</span><span class="sxs-lookup"><span data-stu-id="fd28a-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd28a-191">Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</span><span class="sxs-lookup"><span data-stu-id="fd28a-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="fd28a-192">True</span><span class="sxs-lookup"><span data-stu-id="fd28a-192">True</span></span></p></td>
<td><p><span data-ttu-id="fd28a-193">Skype for Business に切り替えるように求められたユーザー</span><span class="sxs-lookup"><span data-stu-id="fd28a-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="fd28a-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fd28a-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd28a-195">Lync Server 2010 または Lync Server 2013 (適切な更新プログラムが適用されています)</span><span class="sxs-lookup"><span data-stu-id="fd28a-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="fd28a-196">False</span><span class="sxs-lookup"><span data-stu-id="fd28a-196">False</span></span></p></td>
<td><p><span data-ttu-id="fd28a-197">Lync UI</span><span class="sxs-lookup"><span data-stu-id="fd28a-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="fd28a-198">Lync UI への切り替えを求められたユーザー</span><span class="sxs-lookup"><span data-stu-id="fd28a-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd28a-199">Lync Server 2010 または Lync Server 2013 (パッチなし)</span><span class="sxs-lookup"><span data-stu-id="fd28a-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="fd28a-200">既定</span><span class="sxs-lookup"><span data-stu-id="fd28a-200">Default</span></span></p></td>
<td><p><span data-ttu-id="fd28a-201">Lync モード (Skype for Business に切り替えることはできません)</span><span class="sxs-lookup"><span data-stu-id="fd28a-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="fd28a-202">Lync UI (Skype for Business に切り替えることはできません)</span><span class="sxs-lookup"><span data-stu-id="fd28a-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd28a-203">Skype for Business クライアントの構成を管理するために必要な更新プログラムのバージョンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fd28a-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="fd28a-204">Lync Server 2010-Lync Server 2010 用の2015年2月の累積更新プログラム (4.0.7577.710)。</span><span class="sxs-lookup"><span data-stu-id="fd28a-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="fd28a-205">詳細については、「 [Lync Server 2010 の更新プログラム](http://go.microsoft.com/fwlink/p/?linkid=532771)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd28a-205">For information, see [Updates for Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="fd28a-206">Lync Server 2013-Lync Server 2013 用に2014年12月の累積更新プログラム (5.0.8308.857)。</span><span class="sxs-lookup"><span data-stu-id="fd28a-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="fd28a-207">詳細については、「 [Lync Server 2013 の更新プログラム](http://go.microsoft.com/fwlink/p/?linkid=532772)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd28a-207">For information, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="fd28a-208">ドメインに参加しているコンピューターのレジストリを変更するグループ ポリシー オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="fd28a-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="fd28a-p115">ユーザーが初めて Skype for Business クライアントを起動したときに、Lync クライアント エクスペリエンスを表示するためのレジストリの更新は、1 回だけ行う必要があります。 グループ ポリシー オブジェクト (GPO) を使ってレジストリを更新する場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。 GPO を適用した場合、新しい値が存在しないと、その値が作成され、値のデータに 0 が設定されます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="fd28a-p116">以下の手順では、ユーザーが初めて Skype for Business を起動したときに、Lync クライアント エクスペリエンスが表示されるようにレジストリを変更する方法について説明します。 この手順を使って、前述のように [ようこそ] 画面のチュートリアルを無効にするために、レジストリを更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="fd28a-214">**GPO を作成するには**</span><span class="sxs-lookup"><span data-stu-id="fd28a-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="fd28a-215">**グループ ポリシー管理コンソール**を起動します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="fd28a-216">グループ ポリシー管理コンソールの使い方については、「[グループ ポリシー管理コンソール](http://go.microsoft.com/fwlink/?linkid=532759)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd28a-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](http://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="fd28a-217">[ **グループ ポリシー オブジェクト**] ノードを右クリックして、メニューから [ **新規作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="fd28a-218">[**新しい GPO**] ダイアログで、GPO の名前 (「**MakeLyncDefaultUI**」など) を入力し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd28a-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="fd28a-219">作成した新しい GPO を右クリックして、メニューから [**編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="fd28a-220">[ **グループ ポリシー管理エディター**] で、[ **ユーザーの構成**]、[ **ユーザー設定**]、[ **Windows 設定**] の順に展開して、[ **レジストリ**] ノードを選びます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="fd28a-221">[ **Registry** ] ノードを右クリックし、[**新しい** \> **レジストリ項目**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="fd28a-222">[**新しいレジストリのプロパティ**] ダイアログで、次の項目を更新します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="fd28a-223">フィールド</span><span class="sxs-lookup"><span data-stu-id="fd28a-223">Field</span></span></th>
    <th><span data-ttu-id="fd28a-224">選択または入力する値</span><span class="sxs-lookup"><span data-stu-id="fd28a-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="fd28a-225"><strong>アクション</strong></span><span class="sxs-lookup"><span data-stu-id="fd28a-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="fd28a-226"><strong>作成</strong></span><span class="sxs-lookup"><span data-stu-id="fd28a-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fd28a-227"><strong>ハイブ</strong></span><span class="sxs-lookup"><span data-stu-id="fd28a-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="fd28a-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="fd28a-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fd28a-229"><strong>キーのパス</strong></span><span class="sxs-lookup"><span data-stu-id="fd28a-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="fd28a-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="fd28a-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fd28a-231"><strong>値の名前</strong></span><span class="sxs-lookup"><span data-stu-id="fd28a-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="fd28a-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="fd28a-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fd28a-233"><strong>値の種類</strong></span><span class="sxs-lookup"><span data-stu-id="fd28a-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="fd28a-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fd28a-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fd28a-235"><strong>値のデータ</strong></span><span class="sxs-lookup"><span data-stu-id="fd28a-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="fd28a-236">00000000</span><span class="sxs-lookup"><span data-stu-id="fd28a-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="fd28a-237">[ **OK**] をクリックして変更を保存し、GPO を閉じます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="fd28a-238">次に、ポリシーを割り当てる OU などのユーザー グループに、作成した GPO を接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd28a-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="fd28a-239">**GPO を使ってポリシーを割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="fd28a-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="fd28a-240">[グループ ポリシー管理コンソール] で、ポリシーを割り当てる OU を右クリックして、[ **既存の GPO にリンクする**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="fd28a-241">[ **GPO の選択**] ダイアログ ボックスで、作成済みの GPO を選んで、[ **OK**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="fd28a-242">ターゲット ユーザーのコンピューターで、コマンド プロンプトを開いて、以下のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="fd28a-243">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="fd28a-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="fd28a-p117">GPO の適用中、"ポリシーを更新しています..." というメッセージが表示されます。 処理が完了すると、"ユーザー ポリシーの更新が正常に完了しました" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="fd28a-246">コマンド プロンプトに、以下のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="fd28a-247">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="fd28a-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="fd28a-248">"割り当て済みのグループ ポリシー オブジェクト" と表示され、その下に作成済みの GPO の名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd28a-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="fd28a-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span><span class="sxs-lookup"><span data-stu-id="fd28a-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="fd28a-250">レジストリエディターを開き、[ \*\* \[\_HKEY CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\] \*\* ] キーに移動します。</span><span class="sxs-lookup"><span data-stu-id="fd28a-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="fd28a-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span><span class="sxs-lookup"><span data-stu-id="fd28a-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

