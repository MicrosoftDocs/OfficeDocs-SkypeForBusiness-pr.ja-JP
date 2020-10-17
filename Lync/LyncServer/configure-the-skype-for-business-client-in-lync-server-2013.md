---
title: Lync Server 2013 で Skype for Business クライアントを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20980f0f0b6697eada6c237aa8d2297b0fd227d9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503304"
---
# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="fe048-102">Skype for Business でクライアント環境を構成する</span><span class="sxs-lookup"><span data-stu-id="fe048-102">Configure the client experience with Skype for Business</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe048-103">_**トピックの最終更新日:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="fe048-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="fe048-104">**概要:** このトピックでは、Lync Server 2013 環境で Skype for Business クライアントユーザーのクライアント環境を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe048-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="fe048-105">クライアント環境を構成するには、2013年 12 2014 月の累積的な更新プログラム (5.0.8308.857) 以降がインストールされている Lync Server を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe048-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="fe048-106">Lync Server 2013 の更新については、「 [Lync server 2013 の更新プログラム](https://go.microsoft.com/fwlink/p/?linkid=532651)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe048-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="fe048-107">Skype for Business では、Skype コンシューマー製品の使用状況に基づいて新しいユーザー環境が提供されます。</span><span class="sxs-lookup"><span data-stu-id="fe048-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="fe048-108">Lync のすべての機能に加えて、Skype for Business には、シンプルなコントロールと使い慣れたアイコンを備えた新しい機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fe048-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="fe048-109">新しいクライアント環境の詳細については、「 [Lync が Skype For business で提供されるようになりました--新機能」を参照](https://go.microsoft.com/fwlink/?linkid=529022)してください。</span><span class="sxs-lookup"><span data-stu-id="fe048-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="fe048-110">Lync Server 2013 では、新しい Skype for Business クライアントの利便性と Lync クライアントの機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="fe048-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="fe048-111">管理者は、ユーザーに対して推奨されるクライアント環境を選択できます。</span><span class="sxs-lookup"><span data-stu-id="fe048-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="fe048-112">たとえば、組織内のユーザーが新しい Skype for Business の経験で完全にトレーニングされるまで、Lync クライアント環境を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="fe048-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="fe048-113">または、すべてのユーザーが Skype for Business Server 2015 にまだアップグレードされていない場合は、すべてのユーザーが新しいサーバーにアップグレードされるまで、すべてのユーザーが同じクライアントの機能を使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe048-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fe048-114">組織で Skype for Business Server 2015 と Lync Server 2013 の両方が展開されている場合、サーバーバージョンと UI 設定に応じて、既定のクライアント環境が異なります。</span><span class="sxs-lookup"><span data-stu-id="fe048-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="fe048-115">ユーザーが Skype for Business を初めて起動すると、Lync ユーザーインターフェイスが選択されている場合でも、Skype for business のユーザーインターフェイスは常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe048-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="fe048-116">数分後、ユーザーに Lync モードに切り替えるかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe048-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="fe048-117">詳細については、このトピックで後述する「 <STRONG>最初の起動クライアントの動作</STRONG> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe048-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fe048-118">Lync 2013 クライアントの機能は、Skype for Business 2016 クライアントバージョンのオプションではありません。</span><span class="sxs-lookup"><span data-stu-id="fe048-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="fe048-119">Lync 2013 クライアントを使用するようにクライアント環境を構成しようとする前に、クライアントバージョンをチェックして、番号16で始まらないことを確認してください。例: x.x.x.</span><span class="sxs-lookup"><span data-stu-id="fe048-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="fe048-120">クライアント エクスペリエンスの構成</span><span class="sxs-lookup"><span data-stu-id="fe048-120">Configure the client experience</span></span>

<span data-ttu-id="fe048-121">EnableSkypeUI パラメーターを指定したコマンドレットを使用すると **、組織** 内のユーザーに表示されるクライアントの操作を指定できます。</span><span class="sxs-lookup"><span data-stu-id="fe048-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="fe048-122">次のコマンドは、グローバルポリシーの影響を受ける組織内のすべてのユーザーに対して Skype for Business クライアントの機能を選択します (サイトまたはユーザー固有のポリシーはグローバルポリシーよりも優先されることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="fe048-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="fe048-123">次のコマンドは、グローバルポリシーの影響を受ける組織内のすべてのユーザーに対して Lync クライアント環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe048-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="fe048-124">次のコマンドは、Redmond サイト内のすべてのユーザーに対して Skype for Business クライアント環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe048-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="fe048-125">組織内の特定のユーザーに対してクライアント環境を構成する場合は、 **新しい-CsClientPolicy** コマンドレットを使用して新しいユーザーポリシーを作成し、そのポリシーを特定のユーザーに割り当てるには、 **Grant-csclientpolicy** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe048-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="fe048-126">たとえば、次のコマンドを実行すると、Skype for Business クライアントの動作を選択する新しいクライアントポリシーである SalesClientUI が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fe048-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="fe048-127">次のコマンドは、policy (SalesClientUI) を Sales department のすべてのメンバーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="fe048-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="fe048-128">最初に起動するクライアントの動作</span><span class="sxs-lookup"><span data-stu-id="fe048-128">First launch client behaviors</span></span>

<span data-ttu-id="fe048-129">既定では、ユーザーが Skype for business を初めて起動したときに、以前に説明したように、EnableSkypeUI パラメーターの値を $False に設定して、Lync クライアント環境を選択した場合でも、Skype for business のユーザーインターフェイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe048-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="fe048-130">数分後、ユーザーは Lync モードに切り替えるかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe048-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="fe048-131">ユーザーが Skype for Business クライアントを初めて起動したときに、Lync ユーザーインターフェイスを表示する場合は、更新された後に初めてクライアントを起動する前に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe048-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="fe048-132">前述のように使用しているポリシーで、の値 `EnableSkypeUI` が $False に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe048-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="fe048-133">ユーザーのコンピューターのシステムレジストリを更新します。</span><span class="sxs-lookup"><span data-stu-id="fe048-133">Update the system registry on the user's computer.</span></span> <span data-ttu-id="fe048-134">この操作は、ユーザーが Skype for Business クライアントを初めて起動する前に行う必要があります。これは、一度だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe048-134">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="fe048-135">ドメインに参加しているコンピューターのレジストリを更新するグループポリシーオブジェクトを作成する方法については、このトピックの後半のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe048-135">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="fe048-136">[ \*\* \[ 現在の \_ ユーザーソフトウェアの HKEY] \_ \\ \\ Microsoft \\ Office \\ \] Lync**キーで、新しい**バイナリ\*\*値を作成します。</span><span class="sxs-lookup"><span data-stu-id="fe048-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="fe048-137">**値の名前**は、 **Enableskypeui**で、**値のデータ**は**00 00 00 00**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe048-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="fe048-138">キーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fe048-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="fe048-139">これで、ユーザーが初めて Skype for Business クライアントを起動したときに、Lync ユーザーインターフェイスが表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="fe048-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="fe048-140">ようこそ画面のチュートリアルの表示を制御する</span><span class="sxs-lookup"><span data-stu-id="fe048-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="fe048-141">ユーザーが Skype for Business クライアントを開くと、既定の動作として、ようこそ画面が表示さ*れます。*</span><span class="sxs-lookup"><span data-stu-id="fe048-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="fe048-142">ようこそ画面の表示をオフにしても、ユーザーがクライアントコンピューターに次のレジストリ値を追加して、チュートリアルにアクセスできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe048-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="fe048-143">[ \*\* \[ 現在の \_ ユーザーソフトウェアの HKEY] \_ \\ \\ Microsoft \\ Office \\ 15.0 \\ Lync \] **キーで、新しい**DWORD (32 ビット) の値\*\*を作成します。</span><span class="sxs-lookup"><span data-stu-id="fe048-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="fe048-144">**値の名前**は**IsBasicTutorialSeenByUser**にする必要があり、**値のデータ**は**1**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe048-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="fe048-145">キーは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fe048-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="fe048-146">クライアントチュートリアルをオフにする</span><span class="sxs-lookup"><span data-stu-id="fe048-146">Turn off the client tutorial</span></span>

<span data-ttu-id="fe048-147">ユーザーがチュートリアルにアクセスできないようにするには、次のレジストリ値を使用してクライアントチュートリアルをオフにします。</span><span class="sxs-lookup"><span data-stu-id="fe048-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="fe048-148">[ \*\* \[ 現在の \_ ユーザーソフトウェアの HKEY] \_ \\ \\ Microsoft \\ Office \\ 15.0 \\ Lync \] **キーで、新しい**DWORD (32 ビット) の値\*\*を作成します。</span><span class="sxs-lookup"><span data-stu-id="fe048-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="fe048-149">**値の名前**は**TutorialFeatureEnabled**で、値の**データ**は**0**に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe048-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="fe048-150">[ **値のデータ** ] を **1**に設定することによって、チュートリアルをオンに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="fe048-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="fe048-151">既定のクライアントエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="fe048-151">Default client experiences</span></span>

<span data-ttu-id="fe048-152">組織で Skype for Business Server 2015 と Lync Server の両方が展開されている場合は、サーバーのバージョンと Skype UI の設定に応じて、クライアントの操作が異なります。</span><span class="sxs-lookup"><span data-stu-id="fe048-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="fe048-153">次の表に、サーバーバージョンと UI 設定に基づく最初のクライアント環境を示します。</span><span class="sxs-lookup"><span data-stu-id="fe048-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fe048-154">サーバーのバージョン</span><span class="sxs-lookup"><span data-stu-id="fe048-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="fe048-155">EnableSkypeUI 設定</span><span class="sxs-lookup"><span data-stu-id="fe048-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="fe048-156">クライアント環境</span><span class="sxs-lookup"><span data-stu-id="fe048-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe048-157">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe048-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="fe048-158">既定値</span><span class="sxs-lookup"><span data-stu-id="fe048-158">Default</span></span></p></td>
<td><p><span data-ttu-id="fe048-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fe048-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe048-160">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe048-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="fe048-161">正</span><span class="sxs-lookup"><span data-stu-id="fe048-161">True</span></span></p></td>
<td><p><span data-ttu-id="fe048-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fe048-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe048-163">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe048-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="fe048-164">False</span><span class="sxs-lookup"><span data-stu-id="fe048-164">False</span></span></p></td>
<td><p><span data-ttu-id="fe048-165">ユーザーが Lync モードに切り替えることを求められた (UI 設定を $true に変更した場合、ユーザーは後で Skype for business に切り替えることができます)</span><span class="sxs-lookup"><span data-stu-id="fe048-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe048-166">Lync Server 2010 または Lync Server 2013 (適切なパッチを適用)</span><span class="sxs-lookup"><span data-stu-id="fe048-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="fe048-167">既定値</span><span class="sxs-lookup"><span data-stu-id="fe048-167">Default</span></span></p></td>
<td><p><span data-ttu-id="fe048-168">ユーザーが Lync モードに切り替えることを求められた (UI 設定を $true に変更した場合、ユーザーは後で Skype for business に切り替えることができます)</span><span class="sxs-lookup"><span data-stu-id="fe048-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe048-169">Lync Server 2010 または Lync Server 2013 (適切なパッチを適用)</span><span class="sxs-lookup"><span data-stu-id="fe048-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="fe048-170">正</span><span class="sxs-lookup"><span data-stu-id="fe048-170">True</span></span></p></td>
<td><p><span data-ttu-id="fe048-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fe048-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe048-172">Lync Server 2010 または Lync Server 2013 (適切なパッチを適用)</span><span class="sxs-lookup"><span data-stu-id="fe048-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="fe048-173">False</span><span class="sxs-lookup"><span data-stu-id="fe048-173">False</span></span></p></td>
<td><p><span data-ttu-id="fe048-174">ユーザーが Lync モードに切り替えることを求められた (UI 設定を $true に変更した場合、ユーザーは後で Skype for business に切り替えることができます)</span><span class="sxs-lookup"><span data-stu-id="fe048-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe048-175">Lync Server 2010 または Lync Server 2013 (パッチなし)</span><span class="sxs-lookup"><span data-stu-id="fe048-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="fe048-176">既定値</span><span class="sxs-lookup"><span data-stu-id="fe048-176">Default</span></span></p></td>
<td><p><span data-ttu-id="fe048-177">ユーザーが Lync クライアント環境に切り替えることを求められた (ユーザーは後で Skype for Business に切り替えることができない)</span><span class="sxs-lookup"><span data-stu-id="fe048-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fe048-178">次の表は、管理者が Skype UI 環境の初期設定を変更した場合のクライアントの動作を示しています。</span><span class="sxs-lookup"><span data-stu-id="fe048-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fe048-179">サーバーのバージョン</span><span class="sxs-lookup"><span data-stu-id="fe048-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="fe048-180">Skype UI 設定</span><span class="sxs-lookup"><span data-stu-id="fe048-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="fe048-181">クライアント UI = Lync</span><span class="sxs-lookup"><span data-stu-id="fe048-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="fe048-182">クライアント UI = Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fe048-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe048-183">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe048-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="fe048-184">正</span><span class="sxs-lookup"><span data-stu-id="fe048-184">True</span></span></p></td>
<td><p><span data-ttu-id="fe048-185">ユーザーが Skype for Business への切り替えを要求した</span><span class="sxs-lookup"><span data-stu-id="fe048-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="fe048-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fe048-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe048-187">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe048-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="fe048-188">False</span><span class="sxs-lookup"><span data-stu-id="fe048-188">False</span></span></p></td>
<td><p><span data-ttu-id="fe048-189">Lync UI</span><span class="sxs-lookup"><span data-stu-id="fe048-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="fe048-190">ユーザーが Lync UI への切り替えを要求した</span><span class="sxs-lookup"><span data-stu-id="fe048-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe048-191">Lync Server 2010 または Lync Server 2013 (適切なパッチを適用)</span><span class="sxs-lookup"><span data-stu-id="fe048-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="fe048-192">正</span><span class="sxs-lookup"><span data-stu-id="fe048-192">True</span></span></p></td>
<td><p><span data-ttu-id="fe048-193">ユーザーが Skype for Business への切り替えを要求した</span><span class="sxs-lookup"><span data-stu-id="fe048-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="fe048-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fe048-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe048-195">Lync Server 2010 または Lync Server 2013 (適切なパッチを適用)</span><span class="sxs-lookup"><span data-stu-id="fe048-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="fe048-196">False</span><span class="sxs-lookup"><span data-stu-id="fe048-196">False</span></span></p></td>
<td><p><span data-ttu-id="fe048-197">Lync UI</span><span class="sxs-lookup"><span data-stu-id="fe048-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="fe048-198">ユーザーが Lync UI への切り替えを要求した</span><span class="sxs-lookup"><span data-stu-id="fe048-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe048-199">Lync Server 2010 または Lync Server 2013 (パッチなし)</span><span class="sxs-lookup"><span data-stu-id="fe048-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="fe048-200">既定値</span><span class="sxs-lookup"><span data-stu-id="fe048-200">Default</span></span></p></td>
<td><p><span data-ttu-id="fe048-201">Lync モード (Skype for Business に切り替えることはできません)</span><span class="sxs-lookup"><span data-stu-id="fe048-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="fe048-202">Lync UI (Skype for Business に切り替えることはできません)</span><span class="sxs-lookup"><span data-stu-id="fe048-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fe048-203">Skype for Business クライアントの構成を管理するために必要なパッチのバージョンは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe048-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="fe048-204">Lync Server 2010-Lync Server 2010 の累積的な更新プログラム (4.0.7577.710) (2 月 2015)</span><span class="sxs-lookup"><span data-stu-id="fe048-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="fe048-205">詳細については、「 [Lync Server 2010 の更新プログラム](https://go.microsoft.com/fwlink/p/?linkid=532771)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe048-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="fe048-206">Lync Server 2013-Lync Server 2013 の累積的な更新プログラム (5.0.8308.857) (12 月 2014)</span><span class="sxs-lookup"><span data-stu-id="fe048-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="fe048-207">詳細については、「 [Lync Server 2013 の更新プログラム](https://go.microsoft.com/fwlink/p/?linkid=532772)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe048-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="fe048-208">ドメインに参加しているコンピューターのレジストリを変更するグループポリシーオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="fe048-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="fe048-209">ユーザーが初めて Skype for Business クライアントを起動したときに Lync クライアントの機能を表示するレジストリを更新するには、一度だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe048-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="fe048-210">グループポリシーオブジェクト (GPO) を使用してレジストリを更新する場合は、値のデータを更新するのではなく、新しい値を作成するオブジェクトを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe048-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="fe048-211">GPO が適用されると、新しい値が存在しない場合、GPO によって作成され、値のデータが0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="fe048-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="fe048-212">次の手順では、ユーザーが Skype for Business を初めて起動したときに Lync クライアントの機能が表示されるように、レジストリを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe048-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="fe048-213">この手順を使用してレジストリを更新し、前に説明したようにようこそ画面のチュートリアルを無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fe048-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="fe048-214">**GPO を作成するには**</span><span class="sxs-lookup"><span data-stu-id="fe048-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="fe048-215">**グループポリシー管理コンソール**を起動します。</span><span class="sxs-lookup"><span data-stu-id="fe048-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="fe048-216">グループポリシー管理コンソールの使用方法については、「 [グループポリシー管理コンソール](https://go.microsoft.com/fwlink/?linkid=532759)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe048-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="fe048-217">[ **グループポリシーオブジェクト** ] ノードを右クリックし、メニューの [ **新規** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe048-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="fe048-218">[ **新しい gpo** ] ダイアログボックスで、「 **MakeLyncDefaultUI**」のように、gpo の名前を入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe048-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="fe048-219">作成したばかりの新しい GPO を右クリックして、メニューから [ **編集** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe048-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="fe048-220">**グループポリシー管理エディター**で、[**ユーザーの構成**]、[**環境設定**]、[ **Windows の設定**] の順に展開し、[**レジストリ**] ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="fe048-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="fe048-221">**レジストリ**ノードを右クリックし、[**新しい** \> **レジストリ項目**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe048-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="fe048-222">[ **新しいレジストリのプロパティ** ] ダイアログで、次の内容を更新します。</span><span class="sxs-lookup"><span data-stu-id="fe048-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="fe048-223">Field</span><span class="sxs-lookup"><span data-stu-id="fe048-223">Field</span></span></th>
    <th><span data-ttu-id="fe048-224">選択または入力する値</span><span class="sxs-lookup"><span data-stu-id="fe048-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="fe048-225"><strong>操作</strong></span><span class="sxs-lookup"><span data-stu-id="fe048-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="fe048-226"><strong>Create</strong></span><span class="sxs-lookup"><span data-stu-id="fe048-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fe048-227"><strong>ハイブ</strong></span><span class="sxs-lookup"><span data-stu-id="fe048-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="fe048-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="fe048-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fe048-229"><strong>キーパス</strong></span><span class="sxs-lookup"><span data-stu-id="fe048-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="fe048-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="fe048-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fe048-231"><strong>値の名前</strong></span><span class="sxs-lookup"><span data-stu-id="fe048-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="fe048-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="fe048-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="fe048-233"><strong>値の型</strong></span><span class="sxs-lookup"><span data-stu-id="fe048-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="fe048-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="fe048-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="fe048-235"><strong>Value data</strong></span><span class="sxs-lookup"><span data-stu-id="fe048-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="fe048-236">00000000</span><span class="sxs-lookup"><span data-stu-id="fe048-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="fe048-237">[ **OK]** をクリックして変更を保存し、GPO を閉じます。</span><span class="sxs-lookup"><span data-stu-id="fe048-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="fe048-238">次に、ポリシーを割り当てるユーザーのグループ (OU など) に、作成した GPO をリンクする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe048-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="fe048-239">**GPO を使用してポリシーを割り当てるには**</span><span class="sxs-lookup"><span data-stu-id="fe048-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="fe048-240">グループポリシー管理コンソールで、ポリシーを割り当てる OU を右クリックし、[ **既存の GPO にリンクする**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe048-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="fe048-241">[ **Gpo の選択** ] ダイアログで、作成した gpo を選択し、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe048-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="fe048-242">ターゲットユーザーのコンピューターで、コマンドプロンプトを開き、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="fe048-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="fe048-243">**gpupdate/target: user**</span><span class="sxs-lookup"><span data-stu-id="fe048-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="fe048-244">"ポリシーの更新" というメッセージが表示されます。GPO が適用されている間に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe048-244">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="fe048-245">完了すると、"ユーザーポリシーの更新が正常に完了しました" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe048-245">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="fe048-246">コマンド プロンプトで、以下のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="fe048-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="fe048-247">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="fe048-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="fe048-248">[割り当てられたグループポリシーオブジェクト] と共に、作成した GPO の名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe048-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="fe048-249">レジストリを調べることによって、ユーザーのコンピューターのレジストリが GPO によって正常に更新されたことを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe048-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="fe048-250">レジストリエディターを開いて、[ \*\* \[ HKEY \_ CURRENT \_ USER \\ Software \\ ] \\ Microsoft \\ Office \] Lync\*\*キーに移動します。</span><span class="sxs-lookup"><span data-stu-id="fe048-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="fe048-251">GPO によってレジストリが正常に更新された場合は、値が0の EnableSkypeUI という値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe048-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

