---
title: Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を与える
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: アプリから要求されたアクセス許可を表示し、Microsoft Teams 管理センターの [アプリの管理] ページのアプリに管理者の同意を与える方法について説明します。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50a9abbd7e5872229c09d7d80c00c5d432723da1
ms.sourcegitcommit: c79b83e03a89649e2b6e494a741a392819baf2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48433050"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="2afce-103">Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同意を与える</span><span class="sxs-lookup"><span data-stu-id="2afce-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

<span data-ttu-id="2afce-104">Microsoft Teams 管理センターの [ [アプリの管理](manage-apps.md) ] ページでは、組織のすべての Teams アプリを表示して管理できます。</span><span class="sxs-lookup"><span data-stu-id="2afce-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="2afce-105">たとえば、アプリの組織レベルの状態とプロパティの表示、組織のアプリストアへの新しいカスタムアプリの承認またはアップロード、組織レベルでのアプリのブロックまたは許可、組織全体のアプリ設定の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2afce-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="2afce-106">ここでは、データへのアクセス許可を要求するアプリに対して、また、アプリに対するリソース固有の同意 (RSC) のアクセス許可を表示するように、組織全体の管理者の同意を付与することもできます。</span><span class="sxs-lookup"><span data-stu-id="2afce-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="2afce-107">アプリに組織全体の管理者の同意を与える</span><span class="sxs-lookup"><span data-stu-id="2afce-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="2afce-108">グローバル管理者の場合は、組織内のすべてのユーザーの代理としてアクセス許可を要求するアプリに対して、同意を確認して付与することができます。</span><span class="sxs-lookup"><span data-stu-id="2afce-108">If you're a global admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="2afce-109">これは、ユーザーがアプリを起動したときに、アプリによって要求されたアクセス許可を確認して受け入れる必要がないようにするためです。</span><span class="sxs-lookup"><span data-stu-id="2afce-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="2afce-110">さらに、Azure Active Directory (Azure AD) でのユーザーの [同意設定](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) によっては、会社のデータにアクセスするアプリに対して承認を受けることができないユーザーもいます。</span><span class="sxs-lookup"><span data-stu-id="2afce-110">Additionally, depending on the user's [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="2afce-111">アプリから要求されるアクセス許可の例には、チームに保存されている情報の読み取り、ユーザーのプロファイルの読み取り、ユーザーに代わってメールを送信する機能などがあります。</span><span class="sxs-lookup"><span data-stu-id="2afce-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="2afce-112">詳細については、「 [Microsoft identity platform エンドポイントでの権限と同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2afce-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="2afce-113">[ **権限** の列には、アプリに承認が必要な権限が与えられているかどうかを表示します。</span><span class="sxs-lookup"><span data-stu-id="2afce-113">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="2afce-114">Azure AD に登録されている各アプリの [ **詳細の表示** ] リンクが表示されます。これには、承認が必要なアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="2afce-114">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="2afce-115">これは、カスタムアプリとサードパーティアプリにのみ適用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2afce-115">Keep in mind that this applies only to custom and third-party apps.</span></span> <span data-ttu-id="2afce-116">このリンクは表示されません。または、Microsoft が公開したアプリに管理者の同意を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="2afce-116">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="[アプリの管理] ページの [アクセス許可] 列のスクリーンショット":::

<span data-ttu-id="2afce-118">アプリに組織全体の同意を与えるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2afce-118">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="2afce-119">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="2afce-119">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="2afce-120">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2afce-120">Do one of the following:</span></span>
    - <span data-ttu-id="2afce-121">目的のアプリを検索し、アプリ名をクリックして [アプリの詳細] ページに移動し、[ **アクセス許可** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2afce-121">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="2afce-122">[ **アクセス許可** ] 列を降順で並べ替えてアプリを見つけ、[ **詳細の表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2afce-122">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="2afce-123">この操作を行うと、[アプリの詳細] ページの [ **アクセス許可** ] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="2afce-123">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="2afce-124">[ **組織全体のアクセス許可**] で、[ **アクセス許可と同意を確認**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2afce-124">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="アプリの [アクセス許可] タブにある組織全体のアクセス許可のスクリーンショット":::

    <span data-ttu-id="2afce-126">この操作を行うには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2afce-126">You must be a global admin to do this.</span></span> <span data-ttu-id="2afce-127">このオプションは、Teams サービスの管理者には使用できません。</span><span class="sxs-lookup"><span data-stu-id="2afce-127">This option isn't available to Teams service admins.</span></span>

4. <span data-ttu-id="2afce-128">[ **アクセス許可** ] タブで、アプリによって要求されたアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="2afce-128">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="アプリから要求されたアクセス許可のスクリーンショット":::

    > [!IMPORTANT]
    > <span data-ttu-id="2afce-130">アプリに組織全体の同意を付与すると、アプリは組織のデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2afce-130">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="2afce-131">同意を得る前に、アプリによって要求されたアクセス許可を慎重に確認してください。</span><span class="sxs-lookup"><span data-stu-id="2afce-131">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="2afce-132">アプリから要求されたアクセス許可に同意する場合は、[ **承諾** ] をクリックして同意を付与します。</span><span class="sxs-lookup"><span data-stu-id="2afce-132">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="2afce-133">バナーは、ページ上部に一時的に表示され、要求されたアクセス許可がアプリに付与されていることを知らせます。</span><span class="sxs-lookup"><span data-stu-id="2afce-133">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="2afce-134">これで、アプリは、組織内のすべてのユーザーに対して指定されたリソースにアクセスできるようになり、アクセス許可を確認するメッセージが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="2afce-134">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="2afce-135">権限を承諾すると、[アプリの詳細] ページの [ **組織全体の権限** ] にメッセージが表示され、承諾が許可されたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="2afce-135">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="2afce-136">アプリのアクセス許可に関する詳細を表示するには、 **Azure Active Directory** のリンクをクリックして、azure AD ポータルのアプリのページに移動します。</span><span class="sxs-lookup"><span data-stu-id="2afce-136">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="承認が付与されたときに表示されるメッセージのスクリーンショット":::

<span data-ttu-id="2afce-138">組織内のユーザーが承諾を許可することが許可されていて、1人以上のユーザーが特定のアプリへの同意を許可している場合は、同じメッセージが表示されます。これには、承認が付与されたことと、Azure AD ポータルのアプリページへの Azure Active Directory へのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2afce-138">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll also see the same message to let you know that consent was granted and the Azure Active Directory link to the app's page in the Azure AD portal.</span></span>

> [!NOTE]
> <span data-ttu-id="2afce-139">Teams サービス管理者は [ **権限の確認] と [承認** ] オプションを使用できませんが、アプリに対して組織全体の管理者の同意を付与することはできません。 teams のサービス管理者は、アプリの [ **アクセス許可** ] タブでコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="2afce-139">Although, the **Review permissions and consent** option isn't available to Teams service admins and they can't grant org-wide admin consent to apps, Teams service admins can view the content on the **Permissions** tab for an app.</span></span> <span data-ttu-id="2afce-140">たとえば、Teams サービス管理者は、 **Azure Active Directory** のリンクをクリックすると、azure AD ポータルでアプリのアクセス許可の詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="2afce-140">For example, a Teams service admin can click the **Azure Active Directory** link to view app permissions details in the Azure AD portal.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="2afce-141">アプリのリソース固有の同意権限を表示する</span><span class="sxs-lookup"><span data-stu-id="2afce-141">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="2afce-142">RSC のアクセス許可を付与すると、チームの所有者はチームのデータにアクセスして変更するために、アプリの承認を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="2afce-142">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="2afce-143">RSC 権限は、アプリが特定のチームで何を実行できるかを定義する、チーム固有の権限を細かく設定します。</span><span class="sxs-lookup"><span data-stu-id="2afce-143">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="2afce-144">RSC のアクセス許可には、チャネルの作成と削除、チームの設定の取得、チャネルタブの作成と削除などの機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2afce-144">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> 

<span data-ttu-id="2afce-145">RSC のアクセス許可は、Azure AD ではなく、アプリマニフェストで定義されます。</span><span class="sxs-lookup"><span data-stu-id="2afce-145">RSC permissions are defined in the app manifest and not in Azure AD.</span></span> <span data-ttu-id="2afce-146">アプリをチームに追加するときに、RSC のアクセス許可に同意することを許可します。</span><span class="sxs-lookup"><span data-stu-id="2afce-146">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="2afce-147">詳細については、「 [リソース固有の同意 (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2afce-147">To learn more, see [Resource-specific consent (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent).</span></span>

<span data-ttu-id="2afce-148">グローバル管理者と Teams サービス管理者は、アプリの詳細ページの [ **アクセス許可** ] タブでアプリの RSC 権限を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2afce-148">Global admins and Teams service admin can view RSC permissions for an app on the **Permissions** tab of the app details page.</span></span> 

<span data-ttu-id="2afce-149">アプリの RSC 権限を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2afce-149">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="2afce-150">Microsoft Teams 管理センターの左のナビゲーションで、[ **Teams アプリ**の管理] に移動  >  **Manage apps**します。</span><span class="sxs-lookup"><span data-stu-id="2afce-150">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="2afce-151">目的のアプリを検索し、アプリ名をクリックして [アプリの詳細] ページに移動し、[ **アクセス許可** ] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2afce-151">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="2afce-152">[ **Microsoft Graph リソース固有の同意 (RSC) の権限**] で、アプリによって要求された RSC 権限を確認します。</span><span class="sxs-lookup"><span data-stu-id="2afce-152">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="アプリの RSC のアクセス許可のスクリーンショット":::

## <a name="known-issues"></a><span data-ttu-id="2afce-154">既知の問題</span><span class="sxs-lookup"><span data-stu-id="2afce-154">Known issues</span></span>

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a><span data-ttu-id="2afce-155">権限を要求する一部のサードパーティ製アプリの [詳細の表示] リンクが [権限] 列に表示されない</span><span class="sxs-lookup"><span data-stu-id="2afce-155">The "View details" link isn't displayed in the Permissions column for some third-party apps that request permissions</span></span>

<span data-ttu-id="2afce-156">現時点では、アクセス許可を確認したり許可を付与したりする機能は、Azure AD に登録されているすべてのサードパーティアプリで、アクセス許可を要求することはできません。</span><span class="sxs-lookup"><span data-stu-id="2afce-156">Currently, the ability to review permissions and grant consent isn't available for all third-party apps registered in Azure AD that request permissions.</span></span> <span data-ttu-id="2afce-157">[詳細の **表示** ] リンクの代わりに、[ **--** **権限** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2afce-157">Instead of the **View details** link, you'll see **--** in the **Permissions** column.</span></span> <span data-ttu-id="2afce-158">弊社では、Isv と協力して、アプリのこの機能を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="2afce-158">We're working with ISVs to enable this feature for their apps.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2afce-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2afce-159">Related topics</span></span>

- [<span data-ttu-id="2afce-160">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="2afce-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="2afce-161">Microsoft identity platform エンドポイントでの権限と承認</span><span class="sxs-lookup"><span data-stu-id="2afce-161">Permissions and consent in the Microsoft identity platform endpoint</span></span>](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="2afce-162">Teams でのリソース固有の同意</span><span class="sxs-lookup"><span data-stu-id="2afce-162">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="2afce-163">リソース固有の同意 (RSC)</span><span class="sxs-lookup"><span data-stu-id="2afce-163">Resource-specific consent (RSC)</span></span>](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- <span data-ttu-id="2afce-164">[Teams アプリのライフサイクル](https://aka.ms/PR132) (Ignite 2020 セッション) に移動する</span><span class="sxs-lookup"><span data-stu-id="2afce-164">[Navigating the Teams app lifecycle](https://aka.ms/PR132) (Ignite 2020 session)</span></span>


