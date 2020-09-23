---
title: 特定のユーザーの SharePoint へのアクセスをブロックする
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 特定のユーザーの SharePoint へのアクセスをブロックする方法について説明します。
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203840"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="84a76-103">特定のユーザーの SharePoint へのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="84a76-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="84a76-104">Microsoft 365 の SharePoint で、条件付きアクセス (CA) ポリシーを適用することは、Teams にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="84a76-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="84a76-105">ただし、一部の組織では、SharePoint ファイルへのアクセス (アップロード、ダウンロード、表示、編集、作成) を禁止していますが、従業員は、管理されていないデバイスで Teams のデスクトップ、モバイル、web クライアントを使用することを許可しています。</span><span class="sxs-lookup"><span data-stu-id="84a76-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="84a76-106">CA ポリシールールの下では、Sharepoint をブロックすると、チームもブロックされます。</span><span class="sxs-lookup"><span data-stu-id="84a76-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="84a76-107">この記事では、SharePoint に保存されているファイルへのアクセスを完全にブロックしながら、この制限を回避し、従業員がチームを引き続き使用できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="84a76-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="84a76-108">非管理対象デバイスでアクセスをブロックまたは制限することは、Azure AD の条件付きアクセスポリシーに依存します。</span><span class="sxs-lookup"><span data-stu-id="84a76-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="84a76-109">[AZURE AD ライセンス](https://azure.microsoft.com/pricing/details/active-directory/)について説明します。</span><span class="sxs-lookup"><span data-stu-id="84a76-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="84a76-110">Azure AD での条件付きアクセスの概要については、「 [Azure Active Directory の条件付きアクセス](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84a76-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="84a76-111">推奨される SharePoint Online access ポリシーの詳細については、「 [sharepoint サイトとファイルをセキュリティで保護するためのポリシー推奨事項](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84a76-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="84a76-112">管理対象外のデバイスでアクセスを制限する場合、管理対象デバイス上のユーザーは、 [サポートされている OS とブラウザーの組み合わせ](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)のいずれかを使用する必要があります。また、アクセスも制限されます。</span><span class="sxs-lookup"><span data-stu-id="84a76-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="84a76-113">次の場合に、アクセスをブロックまたは制限することができます。</span><span class="sxs-lookup"><span data-stu-id="84a76-113">You can block or limit access for:</span></span>

- <span data-ttu-id="84a76-114">組織内のユーザーまたは一部のユーザーまたはセキュリティグループのみ。</span><span class="sxs-lookup"><span data-stu-id="84a76-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="84a76-115">組織内のすべてのサイト、または一部のサイトのみ。</span><span class="sxs-lookup"><span data-stu-id="84a76-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="84a76-116">アクセスがブロックされると、ユーザーにエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84a76-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="84a76-117">アクセスをブロックすると、セキュリティが確保され、安全なデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="84a76-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="84a76-118">アクセスがブロックされると、ユーザーにエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84a76-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="84a76-119">SharePoint 管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="84a76-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="84a76-120">[**ポリシー**  >  **アクセスポリシー**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="84a76-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="84a76-121">[ **非管理デバイス** ] セクションで、[ **アクセスのブロック** ] を選択し、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="84a76-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![ポリシーの [管理されていないデバイス] セクション](media/no-sharepoint-access1.png)

4. <span data-ttu-id="84a76-123">[Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)ポータルを開き、[**条件付きアクセスポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="84a76-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="84a76-124">次の例のような新しいポリシーが SharePoint によって作成されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="84a76-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![ブラウザーアクセスに対してアプリで適用される制限という名前の新しいポリシー](media/no-sharepoint-access2.png)

5. <span data-ttu-id="84a76-126">特定のユーザーまたはグループのみを対象とするようにポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="84a76-126">Update the policy to target only specific users or a group.</span></span>

    ![[ユーザーの選択] セクションが強調表示された Sharepoint 管理センター](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="84a76-128">このポリシーを設定すると、SharePoint 管理ポータルへのアクセスが切断されます。</span><span class="sxs-lookup"><span data-stu-id="84a76-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="84a76-129">除外ポリシーを構成して、グローバルと SharePoint の管理者を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84a76-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="84a76-130">ターゲットクラウドアプリとして SharePoint が選択されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="84a76-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![ターゲットアプリとして Sharepoint が選択されます。](media/no-sharepoint-access3.png)

7. <span data-ttu-id="84a76-132">**条件**を更新して、デスクトップクライアントを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="84a76-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![デスクトップとモバイルアプリが強調表示されています。](media/no-sharepoint-access4.png)

8. <span data-ttu-id="84a76-134">**アクセス権の付与**が有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="84a76-134">Make sure that **Grant access** is enabled</span></span>

    ![アクセス権の付与が有効になっています。](media/no-sharepoint-access5.png)

9. <span data-ttu-id="84a76-136">アプリに **適用** された制限の使用が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="84a76-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="84a76-137">ポリシーを有効にして、[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="84a76-137">Enable your policy and select **Save**.</span></span>

    ![アプリで適用された制限が有効になっている。](media/no-sharepoint-access6.png)

<span data-ttu-id="84a76-139">ポリシーをテストするには、Teams デスクトップアプリや OneDrive for Business 同期クライアントなどの任意のクライアントからサインアウトし、もう一度サインインして、ポリシーが機能していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84a76-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="84a76-140">アクセスがブロックされている場合は、アイテムが存在しない可能性があるというメッセージが Teams に表示されます。</span><span class="sxs-lookup"><span data-stu-id="84a76-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 !["アイテムは見つかりませんでした" というメッセージ。](media/access-denied-sharepoint.png)

<span data-ttu-id="84a76-142">Sharepoint では、アクセス拒否メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84a76-142">In Sharepoint, you'll receive an access denied message.</span></span>

![アクセス拒否メッセージ。](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="84a76-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="84a76-144">Related topics</span></span>

[<span data-ttu-id="84a76-145">SharePoint で管理されていないデバイスへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="84a76-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
