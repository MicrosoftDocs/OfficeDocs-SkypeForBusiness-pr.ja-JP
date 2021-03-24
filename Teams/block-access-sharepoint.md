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
description: 特定のユーザーの SharePoint へのアクセスをブロックする方法について説明します
ms.openlocfilehash: dce6581abe4fee70a6622817be7aefb0e3379e2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092895"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="da8c2-103">特定のユーザーの SharePoint へのアクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="da8c2-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="da8c2-104">Microsoft 365 の SharePoint の条件付きアクセス （CA） ポリシーを Teams に適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="da8c2-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="da8c2-105">ただし、組織によっては、SharePoint ファイルへのアクセス （アップロード、ダウンロード、表示、編集、作成） をブロックし、従業員が非管理対象デバイスで Teams デスクトップ、モバイル、Web クライアントを使用できるようにしたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="da8c2-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="da8c2-106">CA ポリシー ルールでは、SharePoint をブロックすると、Teams もブロックされます。</span><span class="sxs-lookup"><span data-stu-id="da8c2-106">Under the CA policy rules, blocking SharePoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="da8c2-107">この記事では、この制限を回避し、SharePoint に保存されているファイルへのアクセスを完全にブロックしながら、従業員が Teams を引き続き使用できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="da8c2-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="da8c2-108">非管理対象デバイスでのアクセスのブロックまたは制限は、Azure AD 条件付きアクセス ポリシーに依存します。</span><span class="sxs-lookup"><span data-stu-id="da8c2-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="da8c2-109">[Azure AD ライセンス](https://azure.microsoft.com/pricing/details/active-directory/) について説明します。</span><span class="sxs-lookup"><span data-stu-id="da8c2-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="da8c2-110">Azure AD 条件付きアクセスの概要については、「[Azure Active Directory の条件付きアクセス](/azure/active-directory/conditional-access/overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="da8c2-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="da8c2-111">推奨される SharePoint Online アクセス ポリシーの詳細については、「[SharePoint サイトとファイルをセキュリティで保護するためのポリシーの推奨事項](/microsoft-365/enterprise/sharepoint-file-access-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da8c2-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="da8c2-112">非管理対象デバイスでアクセスを制限すると、管理対象デバイス上のユーザーは [サポートされている OS とブラウザーの組み合わせ](/azure/active-directory/conditional-access/technical-reference#client-apps-condition) のいずれかを使用しなければならず、アクセスも制限されます。</span><span class="sxs-lookup"><span data-stu-id="da8c2-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="da8c2-113">次のアクセスをブロックまたは制限することができます:</span><span class="sxs-lookup"><span data-stu-id="da8c2-113">You can block or limit access for:</span></span>

- <span data-ttu-id="da8c2-114">組織内のユーザー、または一部のユーザーまたはセキュリティ グループのみ。</span><span class="sxs-lookup"><span data-stu-id="da8c2-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="da8c2-115">組織内のすべてのサイト、または一部のサイト。</span><span class="sxs-lookup"><span data-stu-id="da8c2-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="da8c2-116">アクセスがブロックされると、ユーザーにエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da8c2-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="da8c2-117">アクセスをブロックすると、セキュリティが強化され、データを保護できます。</span><span class="sxs-lookup"><span data-stu-id="da8c2-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="da8c2-118">アクセスがブロックされると、ユーザーにエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da8c2-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="da8c2-119">SharePoint 管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="da8c2-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="da8c2-120">**[ポリシー]** > **[アクセス ポリシー]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="da8c2-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="da8c2-121">**[非管理対象デバイス]** セクションで、**[アクセスのブロック]** を選択し、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8c2-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![ポリシーの非管理対象デバイス セクション](media/no-sharepoint-access1.png)

4. <span data-ttu-id="da8c2-123">[Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) ポータルを開き、**条件付きアクセス ポリシー** に移動します。</span><span class="sxs-lookup"><span data-stu-id="da8c2-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="da8c2-124">次の例のような新しいポリシーが SharePoint によって作成されていることがわかります:</span><span class="sxs-lookup"><span data-stu-id="da8c2-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    !["ブラウザー アクセスにアプリによって適用される制限を使用する" という名前の新しいポリシー](media/no-sharepoint-access2.png)

5. <span data-ttu-id="da8c2-126">特定のユーザーまたはグループのみを対象とするようにポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="da8c2-126">Update the policy to target only specific users or a group.</span></span>

    ![[ユーザーの選択] セクションが強調表示された SharePoint 管理センター。](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="da8c2-128">このポリシーを設定すると、SharePoint 管理ポータルへのアクセスが制限されます。</span><span class="sxs-lookup"><span data-stu-id="da8c2-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="da8c2-129">除外ポリシーを構成し、グローバル管理者と SharePoint 管理者を選択することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="da8c2-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="da8c2-130">ターゲット クラウド アプリとして SharePoint のみが選択されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="da8c2-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![ターゲット アプリとして SharePoint が選択されています。](media/no-sharepoint-access3.png)

7. <span data-ttu-id="da8c2-132">デスクトップ クライアントも含めるように **条件** を更新します。</span><span class="sxs-lookup"><span data-stu-id="da8c2-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![デスクトップ アプリとモバイル アプリが強調表示されています。](media/no-sharepoint-access4.png)

8. <span data-ttu-id="da8c2-134">**アクセス権の付与** が有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="da8c2-134">Make sure that **Grant access** is enabled</span></span>

    ![アクセス権の付与は有効になっています。](media/no-sharepoint-access5.png)

9. <span data-ttu-id="da8c2-136">**[アプリによって適用される制限を使用する]** が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="da8c2-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="da8c2-137">ポリシーを有効にして、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="da8c2-137">Enable your policy and select **Save**.</span></span>

    ![アプリによって適用される制限は有効になっています。](media/no-sharepoint-access6.png)

<span data-ttu-id="da8c2-139">ポリシーをテストするには、Teams デスクトップ アプリや OneDrive for Business 同期クライアントなどのクライアントからサインアウトし、再度サインインしてポリシーの動作を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="da8c2-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="da8c2-140">アクセスがブロックされている場合は、アイテムが存在しない可能性があることを示すメッセージが Teams に表示されます。</span><span class="sxs-lookup"><span data-stu-id="da8c2-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 !["アイテムが見つかりません" というメッセージ。](media/access-denied-sharepoint.png)

<span data-ttu-id="da8c2-142">SharePoint では、アクセスが拒否されたというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="da8c2-142">In SharePoint, you'll receive an access denied message.</span></span>

![アクセス拒否メッセージ。](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="da8c2-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="da8c2-144">Related topics</span></span>

[<span data-ttu-id="da8c2-145">SharePoint で非管理対象デバイスのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="da8c2-145">Control access for unmanaged devices in SharePoint</span></span>](/sharepoint/control-access-from-unmanaged-devices)