---
title: Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を付与する
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: アプリから要求されたアクセス許可を表示し、Microsoft Teams 管理センターの [アプリの管理] ページでアプリに管理者の同意を付与する方法について説明します。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ec41760a7edd7de52d15995f39365b300cd797e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827537"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="b5f4c-103">Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を付与する</span><span class="sxs-lookup"><span data-stu-id="b5f4c-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

<span data-ttu-id="b5f4c-104">Microsoft Teams [管理センターの](manage-apps.md) [アプリの管理] ページは、組織のすべての Teams アプリを表示および管理する場所です。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="b5f4c-105">たとえば、アプリの組織レベルの状態とプロパティの表示、組織のアプリ ストアへの新しいカスタム アプリの承認またはアップロード、組織レベルでのアプリのブロックまたは許可、および組織全体のアプリ設定の管理を行います。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="b5f4c-106">ここでは、データへのアクセス許可を要求し、アプリのリソース固有の同意 (RSC) アクセス許可を表示するアプリに対する組織全体の管理者の同意を付与することもできます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="b5f4c-107">組織全体の管理者にアプリへの同意を付与する</span><span class="sxs-lookup"><span data-stu-id="b5f4c-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="b5f4c-108">グローバル管理者の場合は、組織内のすべてのユーザーに代わってアクセス許可を要求するアプリを確認し、同意を付与できます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-108">If you're a global admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="b5f4c-109">この操作を行って、ユーザーがアプリの起動時にアプリから要求されたアクセス許可を確認して承諾する必要が生じなかったりします。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="b5f4c-110">また、Azure Active Directory (Azure [](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) AD) のユーザーの同意設定によっては、会社のデータにアクセスするアプリに対する同意を許可されないユーザーが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-110">Additionally, depending on the user's [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="b5f4c-111">アプリから要求されたアクセス許可の例には、チームに保存されている情報の読み取り、ユーザーのプロファイルの読み取り、ユーザーの代わりにメールを送信する機能があります。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="b5f4c-112">詳細については、Microsoft ID プラットフォーム エンドポイントのアクセス許可と同意 [を参照してください](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="b5f4c-113">[ **アクセス許可]** 列は、アプリに同意が必要なアクセス許可を持っているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-113">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="b5f4c-114">同意が **必要なアクセス** 許可を持つ Azure ADアプリごとに [詳細の表示] リンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-114">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="b5f4c-115">これは、カスタム アプリとサード パーティ製アプリにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-115">Keep in mind that this applies only to custom and third-party apps.</span></span> <span data-ttu-id="b5f4c-116">このリンクは表示されません。または、Microsoft が発行するアプリに対して管理者の同意を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-116">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="[アプリの管理] ページの [アクセス許可] 列のスクリーンショット":::

<span data-ttu-id="b5f4c-118">アプリに対する組織全体の同意を付与するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-118">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="b5f4c-119">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-119">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="b5f4c-120">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-120">Do one of the following:</span></span>
    - <span data-ttu-id="b5f4c-121">目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[権限] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-121">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="b5f4c-122">アクセス許可 **列を降** 順で並べ替え、アプリを見つけ、[詳細の表示 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-122">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="b5f4c-123">これにより、アプリの詳細ページ **の** [アクセス許可] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-123">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="b5f4c-124">組織 **全体のアクセス許可の下で、[** アクセス許可と同意 **のレビュー] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-124">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="アプリの [権限] タブの組織全体のアクセス許可のスクリーンショット":::

    <span data-ttu-id="b5f4c-126">これを行うには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-126">You must be a global admin to do this.</span></span> <span data-ttu-id="b5f4c-127">このオプションは、Teams サービス管理者は使用できません。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-127">This option isn't available to Teams service admins.</span></span>

4. <span data-ttu-id="b5f4c-128">[アクセス **許可] タブ** で、アプリから要求されたアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-128">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="アプリから要求されたアクセス許可のスクリーンショット":::

    > [!IMPORTANT]
    > <span data-ttu-id="b5f4c-130">アプリに対する組織全体の同意を付与すると、アプリは組織のデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-130">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="b5f4c-131">同意を付与する前に、アプリから要求されたアクセス許可を慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-131">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="b5f4c-132">アプリから要求されたアクセス許可に同意する場合は、[承諾] をクリックして同意を付与します。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-132">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="b5f4c-133">要求されたアプリのアクセス許可が付与された場合は、ページの上部にバナーが一時的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-133">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="b5f4c-134">これで、アプリは組織内のすべてのユーザーに対して指定されたリソースにアクセスできます。アクセス許可の確認を求めるメッセージは他に表示されません。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-134">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="b5f4c-135">アクセス許可を承諾すると、アプリの詳細ページの組織全体のアクセス許可の下に、同意が許可されたというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-135">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="b5f4c-136">アプリのアクセス許可に関する詳細を表示するには **、Azure Active Directory** リンクをクリックして、Azure AD ポータルでアプリのページに移動します。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-136">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="同意が付与された場合に表示されるメッセージのスクリーンショット":::

<span data-ttu-id="b5f4c-138">組織内のユーザーが同意を許可されている場合、および 1 人または複数のユーザーが特定のアプリに対する同意を許可した場合は、同意が付与されたことを知らせる同じメッセージと、Azure AD ポータルのアプリのページへの Azure Active Directory リンクも表示されます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-138">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll also see the same message to let you know that consent was granted and the Azure Active Directory link to the app's page in the Azure AD portal.</span></span>

> [!NOTE]
> <span data-ttu-id="b5f4c-139">ただし、Teamsサービス管理者は [アクセス許可と同意の確認] オプションを使用できません。また、アプリに対する組織全体の管理者の同意を付与することはできませんが、Teams サービス管理者はアプリの [アクセス許可] タブでコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-139">Although, the **Review permissions and consent** option isn't available to Teams service admins and they can't grant org-wide admin consent to apps, Teams service admins can view the content on the **Permissions** tab for an app.</span></span> <span data-ttu-id="b5f4c-140">たとえば、Teams サービス管理者は Azure **Active Directory** リンクをクリックして、Azure Active Directory ポータルでアプリのアクセス許可の詳細ADできます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-140">For example, a Teams service admin can click the **Azure Active Directory** link to view app permissions details in the Azure AD portal.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="b5f4c-141">アプリのリソース固有の同意アクセス許可を表示する</span><span class="sxs-lookup"><span data-stu-id="b5f4c-141">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="b5f4c-142">RSC アクセス許可を使用すると、チーム所有者はアプリがチームのデータにアクセスして変更する同意を付与できます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-142">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="b5f4c-143">RSC アクセス許可は、特定のチームでアプリが実行できる操作を定義する Teams 固有の権限です。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-143">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="b5f4c-144">RSC アクセス許可の例としては、チャネルの作成と削除、チームの設定の取得、チャネル タブの作成と削除の機能があります。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-144">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> 

<span data-ttu-id="b5f4c-145">RSC アクセス許可は、Azure マニフェストではなく、アプリ マニフェストAD。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-145">RSC permissions are defined in the app manifest and not in Azure AD.</span></span> <span data-ttu-id="b5f4c-146">アプリをチームに追加すると、RSC アクセス許可に同意したと見なされます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-146">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="b5f4c-147">詳細については、リソース固有 [の同意 (RSC) を参照してください](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-147">To learn more, see [Resource-specific consent (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent).</span></span>

<span data-ttu-id="b5f4c-148">グローバル管理者と Teams サービス管理者は、アプリの詳細ページの [アクセス許可] タブで、アプリの RSC アクセス許可を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-148">Global admins and Teams service admin can view RSC permissions for an app on the **Permissions** tab of the app details page.</span></span> 

<span data-ttu-id="b5f4c-149">アプリの RSC アクセス許可を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-149">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="b5f4c-150">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの [アプリの **管理]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-150">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="b5f4c-151">目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[権限] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-151">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="b5f4c-152">**Microsoft Graph のリソース固有の同意 (RSC)** アクセス許可の下で、アプリから要求された RSC アクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-152">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="アプリの RSC アクセス許可のスクリーンショット":::

## <a name="known-issues"></a><span data-ttu-id="b5f4c-154">既知の問題</span><span class="sxs-lookup"><span data-stu-id="b5f4c-154">Known issues</span></span>

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a><span data-ttu-id="b5f4c-155">アクセス許可を要求するサード パーティ製アプリの [アクセス許可] 列に [詳細の表示] リンクが表示されない</span><span class="sxs-lookup"><span data-stu-id="b5f4c-155">The "View details" link isn't displayed in the Permissions column for some third-party apps that request permissions</span></span>

<span data-ttu-id="b5f4c-156">現在、アクセス許可を要求している Azure アカウントに登録されているサード パーティ製アプリの中には、アクセス許可を確認して同意を付与AD利用できる機能はありません。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-156">Currently, the ability to review permissions and grant consent isn't available for all third-party apps registered in Azure AD that request permissions.</span></span> <span data-ttu-id="b5f4c-157">[詳細の表示 **] リンクの** 代わりに、[アクセス許可 **--** ] 列 **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-157">Instead of the **View details** link, you'll see **--** in the **Permissions** column.</span></span> <span data-ttu-id="b5f4c-158">現在、ISV と取り組み、アプリでこの機能を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="b5f4c-158">We're working with ISVs to enable this feature for their apps.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5f4c-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5f4c-159">Related topics</span></span>

- [<span data-ttu-id="b5f4c-160">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="b5f4c-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="b5f4c-161">Microsoft ID プラットフォーム エンドポイントのアクセス許可と同意</span><span class="sxs-lookup"><span data-stu-id="b5f4c-161">Permissions and consent in the Microsoft identity platform endpoint</span></span>](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="b5f4c-162">Teams でのリソース固有の同意</span><span class="sxs-lookup"><span data-stu-id="b5f4c-162">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="b5f4c-163">リソース固有の同意 (RSC)</span><span class="sxs-lookup"><span data-stu-id="b5f4c-163">Resource-specific consent (RSC)</span></span>](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- <span data-ttu-id="b5f4c-164">[Teams アプリのライフサイクル内を移動](https://aka.ms/PR132) する (Ignite 2020 セッション)</span><span class="sxs-lookup"><span data-stu-id="b5f4c-164">[Navigating the Teams app lifecycle](https://aka.ms/PR132) (Ignite 2020 session)</span></span>


