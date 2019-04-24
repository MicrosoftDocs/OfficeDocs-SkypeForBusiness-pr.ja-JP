---
title: Skype のビジネス サーバーのユーザー アカウントを管理します。
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: この資料のセクションでは、有効にする、一時的に無効化、または、Skype のビジネス サーバーの Active Directory ユーザーを削除する方法について説明します。
ms.openlocfilehash: 2140ae4209e0b91e0d1188a01f96d2d81cac27ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214681"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="8a58c-103">Skype のビジネス サーバーのユーザー アカウントを管理します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="8a58c-104">この資料のセクションでは、有効にする、一時的に無効化、または、Skype のビジネス サーバーの Active Directory ユーザーを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="8a58c-105">Active Directory のユーザーを有効にする方法については、[新しいユーザー アカウントを作成する](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a58c-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="8a58c-106">Active Directory ユーザーを削除する方法については、[ユーザー アカウントを削除する](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a58c-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="8a58c-107">ビジネスを使用するための Skype が最も低いときに、メンテナンス時間をこれらの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a58c-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="8a58c-108">日単位または週単位のスケジュールでこれはあるかどうかは、組織のニーズによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="8a58c-109">この資料には、次の手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8a58c-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="8a58c-110">1 つまたは複数のユーザーを検索するには</span><span class="sxs-lookup"><span data-stu-id="8a58c-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="8a58c-111">追加し、ビジネスのサーバーのユーザーの新しい Skype を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="8a58c-112">無効にするか、既に有効になっている Skype のビジネス サーバーのユーザー アカウントを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="8a58c-113">エンタープライズ VoIP のユーザーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="8a58c-114">ビジネス サーバー管理シェルには、Skype でのユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="8a58c-115">1 つまたは複数のユーザーを検索するには</span><span class="sxs-lookup"><span data-stu-id="8a58c-115">To search for one or more users</span></span>
<span data-ttu-id="8a58c-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="8a58c-116"></span></span>

<span data-ttu-id="8a58c-117">検索クエリの結果を使用すると、Skype のビジネス サーバーの Active Directory ユーザーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="8a58c-118">ユーザーは、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) で検索できます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="8a58c-119">ビジネス サーバーのコントロール パネルまたは Active Directory ユーザーを Skype を使用してユーザーを検索でき、スナップインのコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="8a58c-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="8a58c-120">次の手順では、ビジネス サーバーのコントロール パネルの Skype を使用してユーザーを検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="8a58c-121">中央フォレスト トポロジの環境で検索結果があります正確なユーザーの電子メール アドレスでユーザーを検索する場合。</span><span class="sxs-lookup"><span data-stu-id="8a58c-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="8a58c-122">代わりに、SIP アドレス プレフィックス sip: 名などを指定することでユーザーを検索し、検索フィルターを追加部分のメール アドレスが含まれている SIP アドレスを選択または**Get CSUser**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="8a58c-123">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="8a58c-124">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="8a58c-125">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="8a58c-126">**ユーザーが検索**ボックス、すべての種類または表示名、名、姓、名、SAM アカウント名の最初の部分では、SIP アドレス、または行を検索して、[**検索**] をクリックするユーザー アカウントの URI。</span><span class="sxs-lookup"><span data-stu-id="8a58c-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="8a58c-127">(オプション) 結果を絞り込むための追加の検索条件を次のように指定します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="8a58c-128">a.</span><span class="sxs-lookup"><span data-stu-id="8a58c-128">a.</span></span> <span data-ttu-id="8a58c-129">**検索の結果**、上の画面の右上隅の矢印ボタンをクリックし、[**フィルターの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="8a58c-130">b.</span><span class="sxs-lookup"><span data-stu-id="8a58c-130">b.</span></span> <span data-ttu-id="8a58c-131">それを入力するか、ユーザーのプロパティを選択するドロップダウン リストの矢印をクリックすると、ユーザーのプロパティを入力します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="8a58c-132">c.</span><span class="sxs-lookup"><span data-stu-id="8a58c-132">c.</span></span> <span data-ttu-id="8a58c-133">**等しい**] ボックスの一覧では、**等しい**か**等しくない**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="8a58c-134">d.</span><span class="sxs-lookup"><span data-stu-id="8a58c-134">d.</span></span> <span data-ttu-id="8a58c-135">テキスト ボックスで、検索結果にフィルターを使用する検索条件を入力し、**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="8a58c-136">[**検索結果**] で、検索結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="8a58c-137">一覧でいずれかまたはすべてのユーザーを選択し、選択したユーザーの構成タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="8a58c-138">追加し、ビジネスのサーバーのユーザーの新しい Skype を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="8a58c-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="8a58c-139"></span></span>

<span data-ttu-id="8a58c-140">Active Directory ユーザーとコンピューター内のユーザー アカウントを有効にすると、Skype をビジネスのサーバーの Active Directory ユーザーを追加することによってビジネスのサーバーのユーザー アカウントの新しい Skype を有効にするを作成してビジネス サーバーのコントロール パネルの Skype を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="8a58c-141">[Csuser からの有効にする](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)具体的には、コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="8a58c-142">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="8a58c-143">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="8a58c-144">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="8a58c-145">**ユーザーを有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="8a58c-146">**新しい Lync Server のユーザー**ダイアログ ボックスで、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="8a58c-147">**ユーザーが検索**ボックス、すべての種類または名前の最初の部分では、表示名、名、姓、セキュリティ アカウント マネージャー (SAM) アカウント名、電子メール アドレス、ユーザー プリンシパル名 (UPN)、または使用する Active Directory ユーザー アカウントの電話番号、し、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="8a58c-148">テーブルのビジネス サーバーでは、Skype を追加しアカウントを選択し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="8a58c-149">ユーザーをプールに割り当てる、その他の詳細を指定するは、ユーザーにポリシーを割り当てるし、**を有効にする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="8a58c-150">無効にするか、既に有効になっている Skype のビジネス サーバーのユーザー アカウントを再度有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="8a58c-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="8a58c-151"></span></span>

<span data-ttu-id="8a58c-152">Business Server のビジネス サーバー構成設定をユーザー アカウント用の Skype を失うことがなく Skype 内の以前の有効なユーザー アカウントを無効にするのには、次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="8a58c-153">Skype ビジネス サーバーのユーザー アカウントの設定を失わないようにするためことができます再再度有効にする以前に有効なユーザー アカウント、ユーザー アカウントを再構成することがなく。</span><span class="sxs-lookup"><span data-stu-id="8a58c-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="8a58c-154">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="8a58c-155">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="8a58c-156">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="8a58c-157">**ユーザーが検索**ボックス、すべての種類、または表示名、名、姓、セキュリティ アカウント マネージャー (SAM) アカウント名、SIP アドレス、または行を無効にするか、再度有効にするユーザー アカウントの統一リソース識別子 (URI) の最初の部分で[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="8a58c-158">テーブルでは、ユーザー アカウントを無効または再度有効にするをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="8a58c-159">[**操作**] メニューには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8a58c-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="8a58c-160">Skype のビジネス サーバーのユーザー アカウントを一時的に無効には、 **Lync Server を一時的に無効にする**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="8a58c-161">ビジネスのサーバーでは、Skype のユーザー アカウントを有効に、 **Lync Server を再度有効にする**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="8a58c-162">Windows Powershell を使用して、無効にするか、ユーザー アカウントを再度有効にするには</span><span class="sxs-lookup"><span data-stu-id="8a58c-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="8a58c-163">ユーザー アカウントを一時的に無効になっているし、し、後で再度有効に、**セット CsUser**コマンドレットを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="8a58c-164">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="8a58c-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="8a58c-165">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a58c-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="8a58c-166">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="8a58c-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="8a58c-167">ユーザー アカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="8a58c-167">To disable a user account</span></span>

- <span data-ttu-id="8a58c-168">ユーザー アカウントを一時的に無効にするには、Enabled プロパティの値を False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="8a58c-169">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-169">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="8a58c-170">ユーザー アカウントを再度有効にするのには</span><span class="sxs-lookup"><span data-stu-id="8a58c-170">To re-enable a user account</span></span>

- <span data-ttu-id="8a58c-171">無効なユーザー アカウントを再度有効にするには、Enabled プロパティの値を True ($True) に設定します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="8a58c-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-172">For example:</span></span>

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="8a58c-173">詳細については、[セット CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a58c-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="8a58c-174">エンタープライズ VoIP のユーザーを無効にします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="8a58c-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="8a58c-175"></span></span>

<span data-ttu-id="8a58c-176">有効になっている Skype ビジネス サーバーのユーザー アカウントでエンタープライズ VoIP を無効にするのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="8a58c-177">エンタープライズ VoIP のユーザー アカウントを無効にするには</span><span class="sxs-lookup"><span data-stu-id="8a58c-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="8a58c-178">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="8a58c-179">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="8a58c-180">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="8a58c-181">[**ユーザーの検索**] ボックスに、有効にするユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全体か先頭の部分の文字列を入力して、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="8a58c-182">テーブルでは、エンタープライズ VoIP を有効にするユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="8a58c-183">[**編集**] メニューの [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="8a58c-184">**Lync Server ユーザーの編集**] ページで、[**テレフォニー**]、[**エンタープライズ VoIP**] 以外のオプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a58c-185">**テレフォニー**では、下の Lync を使用して、音声通話またはビデオ通話をすることからユーザーを制限するには、**オーディオとビデオを無効**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="8a58c-186">[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-186">Click **Commit**.</span></span>

<span data-ttu-id="8a58c-187">ユーザーは、ここでエンタープライズ VoIP 機能を使用することはありません。</span><span class="sxs-lookup"><span data-stu-id="8a58c-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="8a58c-188">関連情報:</span><span class="sxs-lookup"><span data-stu-id="8a58c-188">Related information:</span></span> <br/>[<span data-ttu-id="8a58c-189">エンタープライズ VoIP およびモバイル</span><span class="sxs-lookup"><span data-stu-id="8a58c-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="8a58c-190">ビジネス サーバーの Skype でエンタープライズ VoIP のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="8a58c-191">Skype for Business Server 管理シェル</span><span class="sxs-lookup"><span data-stu-id="8a58c-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="8a58c-192">ビジネス サーバー管理シェルには、Skype でのユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="8a58c-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="8a58c-193"></span></span>

<span data-ttu-id="8a58c-194">Skype でビジネスのサーバーに以前に追加したユーザー アカウントを削除するのには、次の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="8a58c-195">ユーザーを削除する、ユーザー アカウントの設定が失われます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="8a58c-196">一時的に代わりに、ユーザー アカウントを無効にしたい場合[を無効または有効にしていた Skype ビジネス サーバー用のユーザー アカウントを再度有効にする](user-accounts.md#Disable)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a58c-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="8a58c-197">CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="8a58c-198">、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="8a58c-199">左側のナビゲーション バーで [**ユーザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="8a58c-200">**ユーザーが検索**ボックス、すべての種類、または表示名、名、姓、セキュリティ アカウント マネージャー (SAM) アカウント名、SIP アドレス、または行を無効にするか、再度有効にするユーザー アカウントの統一リソース識別子 (URI) の最初の部分で[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="8a58c-201">テーブルで、削除するユーザー アカウントをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a58c-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="8a58c-202">[**アクション**] メニューの [選択して、 **Lync Server から削除する**、ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="8a58c-203">ダイアログ ボックスからユーザーを削除するのには **[ok]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="8a58c-204">Windows Powershell コマンドレットを使用するユーザー アカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="8a58c-205">Csuser からの無効化のコマンドレットを使用してユーザー アカウントを削除できます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="8a58c-206">ビジネス サーバー管理シェルの Skype から、または Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8a58c-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="8a58c-207">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a58c-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="8a58c-208">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="8a58c-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="8a58c-209">ユーザー アカウントを削除するのには</span><span class="sxs-lookup"><span data-stu-id="8a58c-209">To remove a user account</span></span>
<span data-ttu-id="8a58c-210">ユーザー アカウントを削除するには、無効にする CsUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="8a58c-211">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8a58c-211">For example:</span></span>

  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="8a58c-212">詳細については、[無効にする CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a58c-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a58c-213">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a58c-213">See also</span></span>
<span data-ttu-id="8a58c-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="8a58c-214"></span></span>

[<span data-ttu-id="8a58c-215">Csuser からの有効化</span><span class="sxs-lookup"><span data-stu-id="8a58c-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="8a58c-216">Csuser からの無効化</span><span class="sxs-lookup"><span data-stu-id="8a58c-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
