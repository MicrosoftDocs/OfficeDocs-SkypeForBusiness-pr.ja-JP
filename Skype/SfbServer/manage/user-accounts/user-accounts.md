---
title: Skype for Business Server のユーザー アカウントを管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: この記事のセクションでは、Skype for Business Server から Active Directory ユーザーを有効、一時的に無効、または削除する方法について説明します。
ms.openlocfilehash: 0cf78b4ebe7023bc5a0f1b4af75c5d9e5a45db1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103123"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="f088c-103">Skype for Business Server のユーザー アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="f088c-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="f088c-104">この記事のセクションでは、Skype for Business Server から Active Directory ユーザーを有効、一時的に無効、または削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f088c-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="f088c-105">Active Directory ユーザーを有効にする方法については、「Create a New User [Account」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="f088c-105">For information on how to enable an Active Directory user, see [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)).</span></span> <span data-ttu-id="f088c-106">Active Directory ユーザーを削除する方法については、「ユーザー アカウントの削除 [」を参照してください](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))。</span><span class="sxs-lookup"><span data-stu-id="f088c-106">For information on how to delete an Active Directory user, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>

<span data-ttu-id="f088c-107">これらの手順は、Skype for Business の使用状況が最も低いメンテナンス 期間中に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f088c-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="f088c-108">これが毎日または毎週のスケジュールで行われるかどうかは、組織のニーズによって決まります。</span><span class="sxs-lookup"><span data-stu-id="f088c-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="f088c-109">この記事には、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f088c-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="f088c-110">1 つ以上のユーザーを検索するには</span><span class="sxs-lookup"><span data-stu-id="f088c-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="f088c-111">新しい Skype for Business Server ユーザーを追加して有効にする</span><span class="sxs-lookup"><span data-stu-id="f088c-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="f088c-112">Skype for Business Server で以前に有効にしたユーザー アカウントを無効または再有効化する</span><span class="sxs-lookup"><span data-stu-id="f088c-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="f088c-113">ユーザーがユーザーを無効エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="f088c-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="f088c-114">Skype for Business Server 管理シェルを使用してユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="f088c-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="f088c-115">1 つ以上のユーザーを検索するには</span><span class="sxs-lookup"><span data-stu-id="f088c-115">To search for one or more users</span></span>
<span data-ttu-id="f088c-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="f088c-116"><a name="Search"> </a></span></span>

<span data-ttu-id="f088c-117">検索クエリの結果を使用して、Skype for Business Server 用の Active Directory ユーザーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f088c-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="f088c-118">ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。</span><span class="sxs-lookup"><span data-stu-id="f088c-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="f088c-119">Skype for Business Server コントロール パネルまたは Active Directory ユーザーとコンピューター スナップインを使用して、ユーザーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="f088c-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="f088c-120">次の手順では、Skype for Business Server コントロール パネルを使用してユーザーを検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f088c-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="f088c-121">中央フォレスト トポロジがある環境では、ユーザーの電子メール アドレスでユーザーを検索すると、検索結果が正確ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f088c-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="f088c-122">代わりに、SIP アドレスプレフィックス (sip:name など) を指定してユーザーを検索したり、検索フィルターを追加したり、部分的な電子メール アドレスを含む SIP アドレスを選択したり **、Get-CSUser** コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f088c-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="f088c-123">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f088c-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="f088c-124">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f088c-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f088c-125">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="f088c-126">[**ユーザーの検索**] ボックスに、検索対象のユーザー アカウントの表示名、名、姓、SAM のアカウント名、SIP アドレス、または回線 URI の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="f088c-127">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="f088c-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="f088c-128">a.</span><span class="sxs-lookup"><span data-stu-id="f088c-128">a.</span></span> <span data-ttu-id="f088c-129">画面の右上隅、[**検索結果**] の上にある展開の矢印ボタンをクリックして、[**フィルターの追加** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="f088c-130">b.</span><span class="sxs-lookup"><span data-stu-id="f088c-130">b.</span></span> <span data-ttu-id="f088c-131">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、ユーザーのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="f088c-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="f088c-132">c.</span><span class="sxs-lookup"><span data-stu-id="f088c-132">c.</span></span> <span data-ttu-id="f088c-133">[**次の値に等しい**] リストで、[**次の値に等しい**] または [**次の値に等しくない**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="f088c-134">d.</span><span class="sxs-lookup"><span data-stu-id="f088c-134">d.</span></span> <span data-ttu-id="f088c-135">テキスト ボックスで、検索結果のフィルターに使う検索条件を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="f088c-p110">[**検索結果**] に検索結果が表示されます。 リストのユーザーの一部または全部を選択して、選択したユーザーに対して構成タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f088c-p110">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="f088c-138">新しい Skype for Business Server ユーザーを追加して有効にする</span><span class="sxs-lookup"><span data-stu-id="f088c-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="f088c-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="f088c-139"><a name="Add"> </a></span></span>

<span data-ttu-id="f088c-140">Active Directory ユーザーとコンピューターでユーザー アカウントを有効にした後、Skype for Business Server コントロール パネルを使用して、Active Directory ユーザーを Skype for Business Server に追加して、新しい Skype for Business Server ユーザー アカウントを作成して有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f088c-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="f088c-141">コマンドレット (特に [Enable-CsUser) を使用することもできます](/powershell/module/skype/enable-csuser?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="f088c-141">You can also use a cmdlet, specifically [Enable-CsUser](/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="f088c-142">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f088c-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="f088c-143">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f088c-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f088c-144">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="f088c-145">[**ユーザーの有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="f088c-146">[**新規 Lync Server ユーザー**] ダイアログで [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="f088c-147">[**ユーザーの検索**] ボックスに、名前、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、電子メール アドレス、ユーザーのプリンシパル名 (UPN)、または対象の Active Directory ユーザー アカウントの電話番号の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="f088c-148">表で、Skype for Business Server に追加するアカウントを選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f088c-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="f088c-149">ユーザーをプールに割り当て、詳細情報を指定し、ポリシーを対象のユーザーに割り当て、[**有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="f088c-150">Skype for Business Server で以前に有効にしたユーザー アカウントを無効または再有効化する</span><span class="sxs-lookup"><span data-stu-id="f088c-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="f088c-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="f088c-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="f088c-152">次の手順を使用すると、ユーザー アカウント用に構成した Skype for Business Server 設定を失わずに、Skype for Business Server で以前に有効にしたユーザー アカウントを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="f088c-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="f088c-153">Skype for Business Server のユーザー アカウント設定が失われることはありませんので、ユーザー アカウントを再構成することなく、以前に有効にしたユーザー アカウントを再度有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f088c-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="f088c-154">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f088c-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="f088c-155">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f088c-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f088c-156">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="f088c-157">[**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="f088c-158">表で、無効または再度有効にするユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="f088c-159">[**アクション**] メニューで、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="f088c-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="f088c-160">Skype for Business Server のユーザー アカウントを一時的に無効にするには、[Lync Server で **一時的に無効にする] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f088c-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="f088c-161">Skype for Business Server のユーザー アカウントを有効にするには、[Lync Server の **再有効化] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f088c-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="f088c-162">Windows Powershell を使用してユーザー アカウントを無効または再有効化する</span><span class="sxs-lookup"><span data-stu-id="f088c-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="f088c-163">ユーザー アカウントは **、Set-CsUser** コマンドレットを使用して、一時的に無効にしてから、後で再び有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f088c-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="f088c-164">このコマンドレットは、Skype for Business Server 管理シェルから、またはサーバーのリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f088c-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f088c-165">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f088c-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f088c-166">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="f088c-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="f088c-167">ユーザー アカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="f088c-167">To disable a user account</span></span>

- <span data-ttu-id="f088c-168">ユーザー アカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f088c-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="f088c-169">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f088c-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="f088c-170">ユーザー アカウントを再び有効にするには</span><span class="sxs-lookup"><span data-stu-id="f088c-170">To re-enable a user account</span></span>

- <span data-ttu-id="f088c-171">無効になっているユーザー アカウントを再度有効にするには、Enabled プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="f088c-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="f088c-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f088c-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="f088c-173">詳細については [、Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f088c-173">For more information, see the help topic for the [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="f088c-174">ユーザーがユーザーを無効エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="f088c-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="f088c-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="f088c-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="f088c-176">次の手順を使用して、Skype for Business Server エンタープライズ VoIP有効になっているユーザー アカウントのユーザー アカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f088c-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="f088c-177">ユーザー アカウントを無効にするには、エンタープライズ VoIP</span><span class="sxs-lookup"><span data-stu-id="f088c-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="f088c-178">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f088c-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="f088c-179">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f088c-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f088c-180">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="f088c-181">**[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="f088c-182">表で、ユーザー アカウントで有効にするユーザー アカウントをクリックエンタープライズ VoIP。</span><span class="sxs-lookup"><span data-stu-id="f088c-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="f088c-183">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="f088c-184">[**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] 以外のオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f088c-185">Lync を使用してユーザーが音声通話またはビデオ通話を行うのを制限するには、[ **テレ** フォニー] の下の [オーディオ **/ビデオが無効] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f088c-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="f088c-186">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-186">Click **Commit**.</span></span>

<span data-ttu-id="f088c-187">これで、ユーザーは新しい機能をエンタープライズ VoIPしています。</span><span class="sxs-lookup"><span data-stu-id="f088c-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="f088c-188">関連情報:</span><span class="sxs-lookup"><span data-stu-id="f088c-188">Related information:</span></span> <br/>[<span data-ttu-id="f088c-189">エンタープライズ VoIPモビリティ</span><span class="sxs-lookup"><span data-stu-id="f088c-189">Enterprise Voice and mobility</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [<span data-ttu-id="f088c-190">Skype for Business Server でエンタープライズ VoIPユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="f088c-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="f088c-191">Skype for Business Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="f088c-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="f088c-192">Skype for Business Server 管理シェルを使用してユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="f088c-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="f088c-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="f088c-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="f088c-194">次の手順を使用して、Skype for Business Server で以前に追加したユーザー アカウントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="f088c-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="f088c-195">ユーザーを削除すると、そのユーザー アカウントに対して構成したすべての設定が失われます。</span><span class="sxs-lookup"><span data-stu-id="f088c-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="f088c-196">代わりにユーザー アカウントを一時的に無効にする場合は、「Skype for Business Server で以前に有効にしたユーザー アカウントを無効または再有効化する [」を参照してください](user-accounts.md#Disable)。</span><span class="sxs-lookup"><span data-stu-id="f088c-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="f088c-197">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="f088c-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="f088c-198">ブラウザー ウィンドウを開き、管理者 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="f088c-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f088c-199">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="f088c-200">[**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="f088c-201">表で、削除するユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="f088c-202">[**操作**] メニューの [**Lync Server から削除**] をクリックします。ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f088c-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="f088c-203">ダイアログ ボックスで、ユーザーを削除するかどうかを確認するメッセージが表示されます。[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f088c-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="f088c-204">Windows Powershell コマンドレットを使用してユーザー アカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="f088c-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="f088c-205">ユーザー アカウントは、このコマンドレットを使用Disable-CsUserできます。</span><span class="sxs-lookup"><span data-stu-id="f088c-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="f088c-206">このコマンドレットは、Skype for Business Server 管理シェルから、またはリモート セッション から実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="f088c-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="f088c-207">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f088c-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="f088c-208">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="f088c-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="f088c-209">ユーザー アカウントを削除するには</span><span class="sxs-lookup"><span data-stu-id="f088c-209">To remove a user account</span></span>
<span data-ttu-id="f088c-210">ユーザー アカウントを削除するには、Disable-CsUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f088c-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="f088c-211">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f088c-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="f088c-212">詳細については [、Disable-CsUser コマンドレット](/powershell/module/skype/disable-csuser?view=skype-ps) のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f088c-212">For more information, see the help topic for the [Disable-CsUser](/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="f088c-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="f088c-213">See also</span></span>
<span data-ttu-id="f088c-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="f088c-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="f088c-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="f088c-215">Enable-CsUser</span></span>](/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="f088c-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="f088c-216">Disable-CsUser</span></span>](/powershell/module/skype/disable-csuser?view=skype-ps)