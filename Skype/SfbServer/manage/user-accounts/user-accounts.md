---
title: Skype for Business Server のユーザーアカウントを管理する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: この記事のセクションでは、Skype for Business Server から Active Directory ユーザーを有効または無効にしたり、削除したりする方法について説明します。
ms.openlocfilehash: aa1ed16c39141cbcd6542f2c7e254a278c345826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009640"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="07685-103">Skype for Business Server のユーザーアカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="07685-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="07685-104">この記事のセクションでは、Skype for Business Server から Active Directory ユーザーを有効または無効にしたり、削除したりする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07685-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="07685-105">Active Directory ユーザーを有効にする方法については、「[新しいユーザーアカウントを作成](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07685-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="07685-106">Active Directory ユーザーを削除する方法については、「[ユーザーアカウントを削除](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07685-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="07685-107">これらの手順は、Skype for Business の使用率が低いときに、メンテナンス期間中に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07685-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="07685-108">これが毎日または毎週のどちらのスケジュールで行われるかは、組織のニーズによって決まります。</span><span class="sxs-lookup"><span data-stu-id="07685-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="07685-109">この記事には、以下の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="07685-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="07685-110">1 つ以上のユーザーを検索するには</span><span class="sxs-lookup"><span data-stu-id="07685-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="07685-111">新しい Skype for Business Server ユーザーを追加して有効にする</span><span class="sxs-lookup"><span data-stu-id="07685-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="07685-112">Skype for Business Server で既に有効になっているユーザーアカウントを無効または再度有効にする</span><span class="sxs-lookup"><span data-stu-id="07685-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="07685-113">エンタープライズ Voip のユーザーを無効にする</span><span class="sxs-lookup"><span data-stu-id="07685-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="07685-114">Skype for Business Server 管理シェルを使用してユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="07685-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="07685-115">1 つ以上のユーザーを検索するには</span><span class="sxs-lookup"><span data-stu-id="07685-115">To search for one or more users</span></span>
<span data-ttu-id="07685-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="07685-116"><a name="Search"> </a></span></span>

<span data-ttu-id="07685-117">検索クエリの結果を使用して、Skype for Business Server の Active Directory ユーザーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="07685-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="07685-118">ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。</span><span class="sxs-lookup"><span data-stu-id="07685-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="07685-119">ユーザーを検索するには、[Skype for Business Server コントロールパネル] または [Active Directory ユーザーとコンピューター] スナップインを使用します。</span><span class="sxs-lookup"><span data-stu-id="07685-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="07685-120">次の手順では、Skype for Business Server コントロールパネルを使用してユーザーを検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07685-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="07685-121">中央フォレストトポロジを使用している環境では、ユーザーの電子メールアドレスでユーザーを検索すると、検索結果が正確でないことがあります。</span><span class="sxs-lookup"><span data-stu-id="07685-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="07685-122">代わりに、SIP アドレスプレフィックスを指定してユーザーを検索できます。たとえば、sip: name、検索フィルターを追加して、電子メールアドレスの一部を含む SIP アドレスを選択するか、または**Get-help user**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07685-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="07685-123">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="07685-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="07685-124">ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="07685-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="07685-125">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="07685-126">[**ユーザーの検索**] ボックスに、検索対象のユーザー アカウントの表示名、名、姓、SAM のアカウント名、SIP アドレス、または回線 URI の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="07685-127">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="07685-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="07685-128">a. </span><span class="sxs-lookup"><span data-stu-id="07685-128">a.</span></span> <span data-ttu-id="07685-129">画面の右上隅、[**検索結果**] の上にある展開の矢印ボタンをクリックして、[**フィルターの追加** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="07685-130">b. </span><span class="sxs-lookup"><span data-stu-id="07685-130">b.</span></span> <span data-ttu-id="07685-131">ユーザーのプロパティを入力するか、ドロップダウン リストの矢印をクリックして選択し、ユーザーのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="07685-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="07685-132">c.</span><span class="sxs-lookup"><span data-stu-id="07685-132">c.</span></span> <span data-ttu-id="07685-133">[**次の値に等しい**] リストで、[**次の値に等しい**] または [**次の値に等しくない**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="07685-134">d.</span><span class="sxs-lookup"><span data-stu-id="07685-134">d.</span></span> <span data-ttu-id="07685-135">テキスト ボックスで、検索結果のフィルターに使う検索条件を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="07685-p110">[**検索結果**] に検索結果が表示されます。 リストのユーザーの一部または全部を選択して、選択したユーザーに対して構成タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="07685-p110">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="07685-138">新しい Skype for Business Server ユーザーを追加して有効にする</span><span class="sxs-lookup"><span data-stu-id="07685-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="07685-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="07685-139"><a name="Add"> </a></span></span>

<span data-ttu-id="07685-140">Active Directory ユーザーとコンピューターでユーザーアカウントを有効にした後、skype for Business server コントロールパネルを使用して、Active Directory ユーザーを Skype for Business Server に追加することにより、新しい Skype for business Server ユーザーアカウントを作成して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="07685-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="07685-141">コマンドレットを使用することもできます。具体的には、 [-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)を使用します。</span><span class="sxs-lookup"><span data-stu-id="07685-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="07685-142">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="07685-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="07685-143">ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="07685-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="07685-144">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="07685-145">[**ユーザーの有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="07685-146">[**新規 Lync Server ユーザー**] ダイアログで [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="07685-147">[**ユーザーの検索**] ボックスに、名前、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、電子メール アドレス、ユーザーのプリンシパル名 (UPN)、または対象の Active Directory ユーザー アカウントの電話番号の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="07685-148">表で、Skype for Business Server に追加するアカウントを選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="07685-149">ユーザーをプールに割り当て、詳細情報を指定し、ポリシーを対象のユーザーに割り当て、[**有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="07685-150">Skype for Business Server で既に有効になっているユーザーアカウントを無効または再度有効にする</span><span class="sxs-lookup"><span data-stu-id="07685-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="07685-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="07685-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="07685-152">次の手順を使用して、ユーザーアカウントに対して構成した Skype for Business Server の設定を失わずに、Skype for business Server で既に有効になっているユーザーアカウントを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="07685-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="07685-153">Skype for Business Server のユーザーアカウント設定は失われないので、ユーザーアカウントを再構成せずに、以前に有効になっていたユーザーアカウントを再度有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="07685-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="07685-154">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="07685-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="07685-155">ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="07685-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="07685-156">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="07685-157">[**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="07685-158">表で、無効または再度有効にするユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="07685-159">[**アクション**] メニューで、次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="07685-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="07685-160">Skype for Business Server のユーザーアカウントを一時的に無効にするには、[ **Lync Server に対して一時的に無効**にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="07685-161">Skype for Business Server のユーザーアカウントを有効にするには、[ **Lync Server の再有効化**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="07685-162">Windows Powershell を使用してユーザーアカウントを無効にするか、再度有効にする</span><span class="sxs-lookup"><span data-stu-id="07685-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="07685-163">ユーザーアカウントを一時的に無効にして**から、ユーザーコマンドレット**を使用して再び有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="07685-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="07685-164">このコマンドレットは、Skype for Business Server 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="07685-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="07685-165">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事[「クイックスタート: Microsoft Lync Server 2010 を使用したリモート PowerShell の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07685-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="07685-166">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="07685-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="07685-167">ユーザーアカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="07685-167">To disable a user account</span></span>

- <span data-ttu-id="07685-168">ユーザー アカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="07685-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="07685-169">例:</span><span class="sxs-lookup"><span data-stu-id="07685-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="07685-170">ユーザーアカウントを再度有効にするには</span><span class="sxs-lookup"><span data-stu-id="07685-170">To re-enable a user account</span></span>

- <span data-ttu-id="07685-171">無効になっているユーザー アカウントを再度有効にするには、Enabled プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="07685-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="07685-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07685-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="07685-173">詳細については、「 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07685-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="07685-174">エンタープライズ Voip のユーザーを無効にする</span><span class="sxs-lookup"><span data-stu-id="07685-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="07685-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="07685-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="07685-176">Skype for Business Server が有効になっているユーザーアカウントのエンタープライズ Voip を無効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="07685-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="07685-177">エンタープライズ Voip のユーザーアカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="07685-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="07685-178">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="07685-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="07685-179">ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="07685-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="07685-180">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="07685-181">**[ユーザーの検索]** ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="07685-182">表で、エンタープライズ Voip を有効にするユーザーアカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="07685-183">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="07685-184">[**Lync Server ユーザーの編集**] ページの [**テレフォニー**] で、[**エンタープライズ VoIP**] 以外のオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="07685-185">ユーザーが Lync を使用して音声またはビデオ通話を行うことを制限するには、[**テレフォニー**] で [**音声ビデオを無効**にする] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="07685-186">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-186">Click **Commit**.</span></span>

<span data-ttu-id="07685-187">これで、ユーザーはエンタープライズ Voip 機能を使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="07685-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="07685-188">関連情報:</span><span class="sxs-lookup"><span data-stu-id="07685-188">Related information:</span></span> <br/>[<span data-ttu-id="07685-189">エンタープライズ Voip とモビリティ</span><span class="sxs-lookup"><span data-stu-id="07685-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="07685-190">Skype for Business Server のエンタープライズ Voip でユーザーを有効にする</span><span class="sxs-lookup"><span data-stu-id="07685-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="07685-191">Skype for Business Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="07685-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="07685-192">Skype for Business Server 管理シェルを使用してユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="07685-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="07685-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="07685-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="07685-194">Skype for Business Server で以前に追加したユーザーアカウントを削除するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="07685-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="07685-195">ユーザーを削除すると、そのユーザー アカウントに対して構成したすべての設定が失われます。</span><span class="sxs-lookup"><span data-stu-id="07685-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="07685-196">代わりにユーザーアカウントを一時的に無効にする場合は、「 [Skype For Business Server で既に有効になっているユーザーアカウントの無効化または再有効化](user-accounts.md#Disable)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07685-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="07685-197">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="07685-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="07685-198">ブラウザーウィンドウを開き、管理 URL を入力して Skype for Business Server コントロールパネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="07685-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="07685-199">左側のナビゲーション バーで **[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="07685-200">[**ユーザーの検索**] ボックスに、無効または再度有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、あるいは回線 URI (Uniform Resource Identifier) の全体か最初の一部の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="07685-201">表で、削除するユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="07685-202">[**操作**] メニューの [**Lync Server から削除**] をクリックします。ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="07685-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="07685-203">ダイアログ ボックスで、ユーザーを削除するかどうかを確認するメッセージが表示されます。[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07685-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="07685-204">Windows Powershell コマンドレットを使用してユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="07685-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="07685-205">ユーザーアカウントを削除するには、Disable-CsUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07685-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="07685-206">このコマンドレットは、Skype for Business Server 管理シェルまたはリモートセッション Windows PowerShell から実行できます。</span><span class="sxs-lookup"><span data-stu-id="07685-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="07685-207">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事[「クイックスタート: Microsoft Lync Server 2010 を使用したリモート PowerShell の管理」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07685-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="07685-208">このプロセスは、Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="07685-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="07685-209">ユーザーアカウントを削除するには</span><span class="sxs-lookup"><span data-stu-id="07685-209">To remove a user account</span></span>
<span data-ttu-id="07685-210">ユーザー アカウントを削除するには、Disable-CsUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07685-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="07685-211">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07685-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="07685-212">詳細については、「 [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)コマンドレット」のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="07685-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="07685-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="07685-213">See also</span></span>
<span data-ttu-id="07685-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="07685-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="07685-215">を有効にする-CsUser</span><span class="sxs-lookup"><span data-stu-id="07685-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="07685-216">無効-CsUser</span><span class="sxs-lookup"><span data-stu-id="07685-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
