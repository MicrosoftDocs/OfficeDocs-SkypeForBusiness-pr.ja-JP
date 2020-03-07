---
title: 教育機関管理者向け Microsoft Teams のリソース
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams for EDU のライセンスに関するチュートリアル。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b653acbe18d2247ccbf64a523fd237ca1415414
ms.sourcegitcommit: ac811017d54a55f39ecc0e3a66a883d9e027ce68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547985"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a><span data-ttu-id="f659f-103">教育機関向け Microsoft Teams ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f659f-103">Assign Microsoft Teams licenses for EDU</span></span>

<span data-ttu-id="f659f-104">Microsoft Teams は、会話、コンテンツ、アプリが 1 か所にまとめられたデジタル ハブです。</span><span class="sxs-lookup"><span data-stu-id="f659f-104">Microsoft Teams is a digital hub that brings conversations, content, and apps together in one place.</span></span> <span data-ttu-id="f659f-105">Microsoft Teams は Office 365 に組み込まれています。使い慣れている Office アプリおよびサービスと統合されているということは、学校にとって大きなメリットです。</span><span class="sxs-lookup"><span data-stu-id="f659f-105">Because it's built on Office 365, schools benefit from integration with their familiar Office apps and services.</span></span> <span data-ttu-id="f659f-106">教師は Microsoft Teams を使用することで、クラスでの共同作業環境の構築、教師仲間が集まる学習コミュニティへの参加、学校スタッフとのやり取りをすべて、Office 365 for Education の単一のエクスペリエンスで実現することができます。</span><span class="sxs-lookup"><span data-stu-id="f659f-106">Your institution can use Microsoft Teams to create collaborative classrooms, connect in professional learning communities, and communicate with school staff all from a single experience in Office 365 for Education.</span></span>

<span data-ttu-id="f659f-107">使用を開始するには、IT 管理者は、Microsoft 365 管理センターを使用して[学校向けに Microsoft Teams を有効にする](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams)必要があります。</span><span class="sxs-lookup"><span data-stu-id="f659f-107">To get started, IT administrators need to use the Microsoft 365 Admin Center to [enable Microsoft Teams for your school](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span></span>
<span data-ttu-id="f659f-108">この操作を完了したら、教職員と生徒が Microsoft Teams などの Office 365 サービスにアクセスできるよう、ユーザー アカウントにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f659f-108">Once complete, you must assign licenses to user accounts so your faculty, staff, and students can access Office 365 services, such as Microsoft Teams.</span></span>

<span data-ttu-id="f659f-109">ユーザー アカウントへのライセンスの割り当ては、個別に行うことも、グループ メンバーシップを使用して自動的に行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="f659f-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span> <span data-ttu-id="f659f-110">この記事では、Microsoft 365 管理センターで Office 365 のライセンスを個々のユーザー アカウントまたは少数のユーザー アカウントに割り当てる手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="f659f-110">This article will walk you through how to assign Office 365 licenses to an individual or a small set of user accounts via the Microsoft 365 admin center.</span></span> <span data-ttu-id="f659f-111">グループ メンバーシップを使用してライセンスを自動的に割り当てるには、次のサポート記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f659f-111">To assign licenses automatically through group membership, see one of our supporting articles:</span></span>

- [<span data-ttu-id="f659f-112">Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f659f-112">Office 365 Powershell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [<span data-ttu-id="f659f-113">Active Directory でのグループベースのライセンス認証</span><span class="sxs-lookup"><span data-stu-id="f659f-113">Group-based Licensing in Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)

<span data-ttu-id="f659f-114">ユーザーへのライセンスの割り当ては、[**ライセンス**] ページまたは [**アクティブなユーザー**] ページで行えます。</span><span class="sxs-lookup"><span data-stu-id="f659f-114">You can assign licenses to users on either the **Licenses** page, or on the **Active Users** page.</span></span> <span data-ttu-id="f659f-115">どちらの方法を使用するかは、製品ライセンスを特定のユーザーに割り当てるのか、またはユーザー ライセンスを特定の製品に割り当てるのかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="f659f-115">Which method you use depends on whether you want to assign product licenses to specific users, or assign users licenses to specific products.</span></span>

> [!NOTE]
> <span data-ttu-id="f659f-116">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f659f-116">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="assign-licenses-to-users-on-the-licenses-page"></a><span data-ttu-id="f659f-117">ライセンス ページでユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f659f-117">Assign licenses to users on the Licenses page</span></span>

> [!NOTE]
> <span data-ttu-id="f659f-118">グローバル管理者、課金管理者、ライセンス管理者、またはユーザー管理の管理者のいずれかである必要があります。詳細については、「[Office 365 の管理者ロールについて](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f659f-118">You must be a Global admin, Billing admin, License admin, or User management admin. For more information, see [About Office 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="f659f-119">[**ライセンス**] ページを使用してライセンスを割り当てる場合、特定の製品のライセンスを最大 20 人のユーザーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f659f-119">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product for up to 20 users.</span></span> <span data-ttu-id="f659f-120">[**ライセンス**] ページには、サブスクリプションを所有するすべての製品のリストが表示されます。各製品のライセンスの総数、割り当て済みのライセンスの数、および使用可能なライセンスの数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="f659f-120">On the **Licenses** page, you see a list of all the products you have subscriptions for, together with the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="f659f-121">管理センターで、[**課金**] > [[ライセンス](https://go.microsoft.com/fwlink/p/?linkid=842264)] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="f659f-121">In the admin center, go to the **Billing** > [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) page.</span></span>

   ![[課金] ウィンドウとメニュー オプションのスクリーンショット。](media/EDU-Lic-Billing-License.png)
2. <span data-ttu-id="f659f-123">ライセンスを割り当てる製品を選択します。</span><span class="sxs-lookup"><span data-stu-id="f659f-123">Select a product for which you want to assign licenses.</span></span> <span data-ttu-id="f659f-124">Microsoft Teams は、無料の Office 365 A1 for Students SKU に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f659f-124">Microsoft Teams is part of the free Office 365 A1 for Students SKU.</span></span>

   ![ライセンスを割り当てることができる製品を表示する、[ライセンス] ページのスクリーンショット。](media/EDU-Lic-Licenses-Products.png)
3. <span data-ttu-id="f659f-126">[**ライセンスの割り当て**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f659f-126">Select **Assign licenses**.</span></span>

   ![ページの [ユーザー] セクションと、正符号に続く [ライセンスの割り当て] オプションのスクリーンショット。](media/EDU-Lic-Assign-Licenses.png)
4. <span data-ttu-id="f659f-128">[**ユーザーへのライセンスの割り当て**] ウィンドウで、名前を入力し始めます。名前のリストが作られて表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="f659f-128">In the **Assign licenses to users** pane, begin typing a name, which should generate a list of names.</span></span> <span data-ttu-id="f659f-129">表示された結果から目的の名前を選択し、リストに追加します。</span><span class="sxs-lookup"><span data-stu-id="f659f-129">Choose the name you're looking for from the results to add it to the list.</span></span> <span data-ttu-id="f659f-130">最大 20 人のユーザーを同時に追加できます。</span><span class="sxs-lookup"><span data-stu-id="f659f-130">You can add up to 20 users at a time.</span></span>

   ![名前の一部が入力され、部分的な名前に基づく検索の結果を表示する、[ユーザーへのライセンスの割り当て] ウィンドウのスクリーンショット。](media/EDU-Lic-Assign-Licenses-Users.png)
5. <span data-ttu-id="f659f-132">Microsoft Teams など、特定のアイテムへのアクセス権の割り当てまたは削除を行うには、[**アプリとサービスのオン/オフの切り替え**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f659f-132">Select **Turn apps and services on or off** to assign or remove access to specific items, such as Microsoft Teams.</span></span> <span data-ttu-id="f659f-133">[**Microsoft Teams**] と [**Office for the web (Education)**] が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f659f-133">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>
6. <span data-ttu-id="f659f-134">完了したら、[**割り当て**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f659f-134">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="f659f-135">ユーザーがアクセスできるアプリとサービスを変更する方法。</span><span class="sxs-lookup"><span data-stu-id="f659f-135">To change the apps and services a user has access to:</span></span>

1. <span data-ttu-id="f659f-136">目的のユーザーが含まれている行を選択します。</span><span class="sxs-lookup"><span data-stu-id="f659f-136">Select the row that contains the user.</span></span>
1. <span data-ttu-id="f659f-137">右側のウィンドウで、アクセス権の付与または削除を行うアプリとサービスを選択または選択解除します。</span><span class="sxs-lookup"><span data-stu-id="f659f-137">In the right pane, select or deselect the apps and services that you want to give access to, or remove access from.</span></span>
1. <span data-ttu-id="f659f-138">完了したら、[**保存**] を選択し、[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f659f-138">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a><span data-ttu-id="f659f-139">[アクティブなユーザー] ページで複数のユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="f659f-139">Assign licenses to an individual or multiple users on the Active users page</span></span>

1. <span data-ttu-id="f659f-140">管理センターで、**[ユーザー]** > [[アクティブなユーザー]](https://go.microsoft.com/fwlink/p/?linkid=834822) ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="f659f-140">In the admin center, go to the **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

   ![Microsoft O365 管理センターの [アクティブなユーザー] メニュー オプションのスクリーンショット。](media/EDU-Lic-Active-Users.png)
2. <span data-ttu-id="f659f-142">ライセンスを割り当てるユーザー名の横にある丸を選択します。</span><span class="sxs-lookup"><span data-stu-id="f659f-142">Select the circles next to the name(s) of the user(s) you want to assign license(s) to.</span></span>

   ![名前の横の丸が塗りつぶされているために何人かのユーザーが選択された状態の、[アクティブなユーザー] ページとそのページに表示されるアクティブなユーザーの一覧のスクリーンショット。](media/EDU-Lic-Active-Users-List.png)
3. <span data-ttu-id="f659f-144">上部にある [**製品ライセンスの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f659f-144">At the top select **Manage product licenses**.</span></span>

   ![[製品ライセンスの管理] タブとその下に表示される、[ライセンスなし] と示されるユーザーのスクリーンショット。](media/EDU-Lic-Manage-Product-Licenses.png)
4. <span data-ttu-id="f659f-146">[**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンスの割り当てに追加**] > [**次へ**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f659f-146">In the **Manage product licenses** pane, select **Add to existing product license assignments** > **Next**.</span></span>

   ![[既存の製品ライセンスの割り当てに追加] ラジオ ボタンが選択されている、[製品ライセンスの管理] ウィンドウのスクリーンショット。](media/EDU-Lic-Add-Existing-Product.png)
5. <span data-ttu-id="f659f-148">[**既存の製品に追加**] ウィンドウで、選択したユーザーに付与するライセンスのトグルを [**オン**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f659f-148">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span> <span data-ttu-id="f659f-149">[**Microsoft Teams**] と [**Office for the web (Education)**] が選択されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f659f-149">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>

   ![[既存の製品に追加] タブで選択されている [Microsoft Teams] と [Office for the web, Education] のスクリーンショット。](media/EDU-Lic-Add-Existing-Products.png)

   <span data-ttu-id="f659f-151">既定により、これらのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="f659f-151">By default, all services associated with those license(s) are automatically assigned to the user(s).</span></span> <span data-ttu-id="f659f-152">ユーザーが利用できるサービスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="f659f-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="f659f-153">ユーザーに使用させないサービスのトグルを [**オフ**] の位置に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f659f-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="f659f-154">ウィンドウの下部で、[追加] > [閉じる] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="f659f-154">At the bottom of the pane, select Add > Close.</span></span>
