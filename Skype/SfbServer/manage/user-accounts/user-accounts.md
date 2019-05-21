---
title: Skype for Business Server のユーザーアカウントを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: この記事のセクションでは、Skype for Business Server の Active Directory ユーザーを有効にしたり、一時的に無効にしたり、削除したりする方法について説明します。
ms.openlocfilehash: 83ab64415b21d37f12d3768feeb39b11491787af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275109"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="375c7-103">Skype for Business Server のユーザーアカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="375c7-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="375c7-104">この記事のセクションでは、Skype for Business Server の Active Directory ユーザーを有効にしたり、一時的に無効にしたり、削除したりする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="375c7-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="375c7-105">Active Directory ユーザーを有効にする方法については、「[新しいユーザーアカウントを作成](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="375c7-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="375c7-106">Active Directory ユーザーを削除する方法については、「[ユーザーアカウントを削除](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="375c7-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="375c7-107">以下の手順は、Skype for Business の使用が最も低い場合にメンテナンスウィンドウで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="375c7-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="375c7-108">このスケジュールが毎日または毎週のどちらで実行されるかは、組織のニーズによって決まります。</span><span class="sxs-lookup"><span data-stu-id="375c7-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="375c7-109">この記事では、次の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="375c7-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="375c7-110">1人以上のユーザーを検索するには</span><span class="sxs-lookup"><span data-stu-id="375c7-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="375c7-111">新しい Skype for Business Server ユーザーを追加して有効にする</span><span class="sxs-lookup"><span data-stu-id="375c7-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="375c7-112">Skype for Business Server で既に有効になっていたユーザーアカウントを無効にするか、再び有効にする</span><span class="sxs-lookup"><span data-stu-id="375c7-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="375c7-113">エンタープライズ Voip のユーザーを無効にする</span><span class="sxs-lookup"><span data-stu-id="375c7-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="375c7-114">Skype for Business Server 管理シェルを使用してユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="375c7-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="375c7-115">1人以上のユーザーを検索するには</span><span class="sxs-lookup"><span data-stu-id="375c7-115">To search for one or more users</span></span>
<span data-ttu-id="375c7-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="375c7-116"></span></span>

<span data-ttu-id="375c7-117">検索クエリの結果を使用して、Skype for Business Server の Active Directory ユーザーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="375c7-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="375c7-118">ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。</span><span class="sxs-lookup"><span data-stu-id="375c7-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="375c7-119">ユーザーを検索するには、[Skype for Business Server] コントロールパネルまたは [Active Directory ユーザーとコンピューター] スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="375c7-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="375c7-120">次の手順では、Skype for Business Server コントロールパネルを使用してユーザーを検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="375c7-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="375c7-121">中央フォレストトポロジを持つ環境では、ユーザーのメールアドレスでユーザーを検索すると、検索結果が正確でない場合があります。</span><span class="sxs-lookup"><span data-stu-id="375c7-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="375c7-122">代わりに、SIP アドレスプレフィックスを指定してユーザーを検索することもできます。たとえば、sip: name、検索フィルターを追加して、メールアドレスの一部を含む SIP アドレスを選ぶか、または、**ユーザー**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="375c7-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="375c7-123">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="375c7-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="375c7-124">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="375c7-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="375c7-125">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="375c7-126">[**ユーザーの検索**] ボックスに、検索するユーザーアカウントの表示名、姓、名、SAM アカウント名、SIP アドレス、またはライン URI のすべてまたは最初の部分を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="375c7-127">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="375c7-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="375c7-128">a.</span><span class="sxs-lookup"><span data-stu-id="375c7-128">a.</span></span> <span data-ttu-id="375c7-129">**検索結果**の上にある画面の右上隅にある展開矢印ボタンをクリックし、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="375c7-130">b.</span><span class="sxs-lookup"><span data-stu-id="375c7-130">b.</span></span> <span data-ttu-id="375c7-131">[ユーザー] プロパティを入力するか、ドロップダウンリストの矢印をクリックして、ユーザープロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="375c7-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="375c7-132">c.</span><span class="sxs-lookup"><span data-stu-id="375c7-132">c.</span></span> <span data-ttu-id="375c7-133">[指定の**値**に等しい] \*\*\*\* または [ \*\*\*\* 指定の値に等しい] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="375c7-134">d.</span><span class="sxs-lookup"><span data-stu-id="375c7-134">d.</span></span> <span data-ttu-id="375c7-135">検索結果をフィルター処理するために使用する検索条件をテキストボックスに入力し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="375c7-136">検索結果が [**検索結果**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="375c7-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="375c7-137">リスト内の任意またはすべてのユーザーを選択し、選択したユーザーに対して構成タスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="375c7-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="375c7-138">新しい Skype for Business Server ユーザーを追加して有効にする</span><span class="sxs-lookup"><span data-stu-id="375c7-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="375c7-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="375c7-139"></span></span>

<span data-ttu-id="375c7-140">Active Directory ユーザーとコンピューターでユーザーアカウントを有効にした後は、skype for business server コントロールパネルを使用して、Active Directory ユーザーを Skype for Business Server に追加することで、新しい Skype for business server のユーザーアカウントを作成して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="375c7-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="375c7-141">コマンドレットを使用することもできます。特[に、CsUser を有効に](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)することもできます。</span><span class="sxs-lookup"><span data-stu-id="375c7-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="375c7-142">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="375c7-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="375c7-143">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="375c7-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="375c7-144">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="375c7-145">[**ユーザーを有効にする] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="375c7-146">[**新しい Lync Server ユーザー** ] ダイアログボックスで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="375c7-147">[**ユーザーの検索**] ボックスに、必要な Active Directory ユーザーアカウントの名前、[表示名]、[名]、[姓]、[名前]、[アカウント名]、[電子メールアドレス]、[ユーザープリンシパル名 (UPN)]、または [電話番号] のすべてまたは最初の部分を入力します。[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="375c7-148">表で、Skype for Business Server に追加するアカウントを選び、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="375c7-149">プールにユーザーを割り当て、追加の詳細を指定して、ポリシーを目的のユーザーに割り当て、[**有効に**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="375c7-150">Skype for Business Server で既に有効になっていたユーザーアカウントを無効にするか、再び有効にする</span><span class="sxs-lookup"><span data-stu-id="375c7-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="375c7-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="375c7-151"></span></span>

<span data-ttu-id="375c7-152">次の手順を使用して、ユーザーアカウント用に構成した Skype for business Server の設定を失わずに、Skype for Business Server で事前に有効になっているユーザーアカウントを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="375c7-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="375c7-153">Skype for Business Server のユーザーアカウント設定が失われないため、ユーザーアカウントを再構成せずに、以前に有効になっていたユーザーアカウントを再び有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="375c7-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="375c7-154">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="375c7-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="375c7-155">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="375c7-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="375c7-156">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="375c7-157">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、またはもう一度有効にするユーザーアカウントの Ip Uniform リソース識別子 (URI) のすべてまたは最初の部分を入力します。[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="375c7-158">表で、無効にする、またはもう一度有効にするユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="375c7-159">[**アクション**] メニューで、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="375c7-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="375c7-160">Skype for Business Server のユーザーアカウントを一時的に無効にするには、[ **Lync server に対して一時的に無効**にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="375c7-161">Skype for Business Server のユーザーアカウントを有効にするには、[ **Lync server のために再度有効**にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="375c7-162">Windows Powershell を使用して、ユーザーアカウントを無効にするか、再び有効にする</span><span class="sxs-lookup"><span data-stu-id="375c7-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="375c7-163">ユーザーアカウントは一時的に無効にすることができます。また、**設定-CsUser**コマンドレットを使用して、後で再び有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="375c7-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="375c7-164">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションからでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="375c7-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="375c7-165">リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="375c7-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="375c7-166">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="375c7-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="375c7-167">ユーザーアカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="375c7-167">To disable a user account</span></span>

- <span data-ttu-id="375c7-168">ユーザーアカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="375c7-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="375c7-169">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="375c7-169">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="375c7-170">ユーザーアカウントを再度有効にするには</span><span class="sxs-lookup"><span data-stu-id="375c7-170">To re-enable a user account</span></span>

- <span data-ttu-id="375c7-171">無効のユーザーアカウントを再び有効にするには、Enabled プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="375c7-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="375c7-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="375c7-172">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="375c7-173">詳細については、「 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="375c7-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="375c7-174">エンタープライズ Voip のユーザーを無効にする</span><span class="sxs-lookup"><span data-stu-id="375c7-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="375c7-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="375c7-175"></span></span>

<span data-ttu-id="375c7-176">Skype for Business Server を有効にしているユーザーアカウントのエンタープライズ Voip を無効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="375c7-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="375c7-177">エンタープライズ Voip のユーザーアカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="375c7-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="375c7-178">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="375c7-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="375c7-179">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="375c7-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="375c7-180">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="375c7-181">[**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="375c7-182">表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="375c7-183">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="375c7-184">[ **Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ voip**] 以外のオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="375c7-185">ユーザーが Lync を使って音声またはビデオ通話を発信することを制限するには、[**テレフォニー**] で [**オーディオ/ビデオを無効**にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="375c7-186">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-186">Click **Commit**.</span></span>

<span data-ttu-id="375c7-187">これで、ユーザーはエンタープライズ Voip 機能を使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="375c7-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="375c7-188">関連情報:</span><span class="sxs-lookup"><span data-stu-id="375c7-188">Related information:</span></span> <br/>[<span data-ttu-id="375c7-189">エンタープライズ音声とモバイル機能</span><span class="sxs-lookup"><span data-stu-id="375c7-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="375c7-190">Skype for Business Server でエンタープライズ Voip のユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="375c7-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="375c7-191">Skype for Business Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="375c7-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="375c7-192">Skype for Business Server 管理シェルを使用してユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="375c7-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="375c7-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="375c7-193"></span></span>

<span data-ttu-id="375c7-194">Skype for Business Server で以前に追加したユーザーアカウントを削除するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="375c7-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="375c7-195">ユーザーを削除すると、ユーザーアカウントに対して構成した設定が失われます。</span><span class="sxs-lookup"><span data-stu-id="375c7-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="375c7-196">代わりに、ユーザーアカウントを一時的に無効にする場合は、「 [Skype For Business Server 用に有効になっていたユーザーアカウントを無効にする、またはもう一度有効](user-accounts.md#Disable)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="375c7-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="375c7-197">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="375c7-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="375c7-198">ブラウザーウィンドウを開き、管理 URL を入力して、Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="375c7-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="375c7-199">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="375c7-200">[**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、またはもう一度有効にするユーザーアカウントの Ip Uniform リソース識別子 (URI) のすべてまたは最初の部分を入力します。[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="375c7-201">テーブルで、削除するユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="375c7-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="375c7-202">[**操作**] メニューの [ **Lync Server から削除**] を選択すると、ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="375c7-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="375c7-203">ダイアログボックスで、[ **OK** ] を選択してユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="375c7-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="375c7-204">Windows Powershell コマンドレットを使用してユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="375c7-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="375c7-205">ユーザーアカウントを削除するには、ユーザーの無効化コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="375c7-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="375c7-206">このコマンドレットは、Skype for Business Server 管理シェルから、またはリモートセッション Windows PowerShell から実行できます。</span><span class="sxs-lookup"><span data-stu-id="375c7-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="375c7-207">リモートの Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「[クイックスタート: リモート PowerShell を使用した Microsoft Lync server 2010 の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="375c7-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="375c7-208">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="375c7-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="375c7-209">ユーザーアカウントを削除するには</span><span class="sxs-lookup"><span data-stu-id="375c7-209">To remove a user account</span></span>
<span data-ttu-id="375c7-210">ユーザーアカウントを削除するには、ユーザーの無効化コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="375c7-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="375c7-211">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="375c7-211">For example:</span></span>

  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="375c7-212">詳細については、「[ユーザーの無効化](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)」コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="375c7-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="375c7-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="375c7-213">See also</span></span>
<span data-ttu-id="375c7-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="375c7-214"></span></span>

[<span data-ttu-id="375c7-215">(CsUser) を有効にする</span><span class="sxs-lookup"><span data-stu-id="375c7-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="375c7-216">無効-CsUser</span><span class="sxs-lookup"><span data-stu-id="375c7-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
