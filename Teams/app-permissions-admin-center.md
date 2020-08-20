---
title: Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同承認を付与する
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: アプリによって要求されたアクセス許可を表示し、管理者の承認を Microsoft Teams 管理センターの [アプリの管理] ページで許可する方法について説明します。
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 737052ba5794b221caa08fa8ccfabec0d597c3ad
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814615"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="bc6a8-103">Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同承認を付与する</span><span class="sxs-lookup"><span data-stu-id="bc6a8-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="bc6a8-104">Microsoft Teams [管理センター](manage-apps.md) の [アプリの管理] ページでは、組織のすべての Teams アプリを表示して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="bc6a8-105">たとえば、アプリのプロパティの組織レベルの状態とプロパティの確認、新しいカスタム アプリを組織のアプリ ストアに承認またはアップロードしたり、組織レベルのアプリをブロックまたは許可したり、組織全体のアプリ設定を管理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="bc6a8-106">ここでは、データへのアクセス許可を要求するアプリに対する組織全体の管理者の同じ設定を、アプリに対するリソース固有の同一 (RSC) アクセス許可を表示する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="bc6a8-107">組織全体の管理者におもならず、アプリに管理者の承認を付けます。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="bc6a8-108">管理者は、組織内のすべてのユーザーに代わってアクセス許可をリクエストするアプリに対する同じ情報を確認して、付与することができます。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-108">As an admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="bc6a8-109">この操作を行うことで、ユーザーがアプリを起動したときにアプリから要求されたアクセス許可を確認して承諾する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="bc6a8-110">また、Azure Active Directory (Azure AD) の [ユーザー](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) の同済設定によっては、一部のユーザーが、会社データにアクセスするアプリに同時に同済を許可できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-110">Additionally, depending on the user's [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="bc6a8-111">アプリによって要求されるアクセス許可の例としては、チームに保存されている情報を読み取り、ユーザーのプロフィールを読み、ユーザーの代理でメールを送信する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="bc6a8-112">詳細については、Microsoft ID プラットフォームエンドポイントの権限 [と同同編集を参照してください](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="bc6a8-113">組織全体の同同権限をアプリに付けた場合は、グローバル管理者でなけけなけらない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-113">You have to be a global admin to grant org-wide consent to an app.</span></span> <span data-ttu-id="bc6a8-114">[ **権限]** 列は、アプリに同一の権限が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-114">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="bc6a8-115">Azure アカウント **に登録されている** アプリごとに、同じように同じ権限が必要なアクセス許可を持 ADつアプリごとに、[詳細の表示] リンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-115">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="bc6a8-116">これは、カスタム アプリとサードパーティのアプリとサードパーティのアプリにのみ適用されることに留まることに留めてください。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-116">Keep in mind that this applies only to custom and third-party apps and.</span></span> <span data-ttu-id="bc6a8-117">このリンクは表示されないか、Microsoft が発行したアプリに管理者の同同同権限を付けたりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-117">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="[アプリの管理] ページの [アクセス許可] 列のスクリーンショット":::

<span data-ttu-id="bc6a8-119">組織全体のユーザーにアプリのユーザーに認識するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-119">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="bc6a8-120">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの管理**アプリ**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-120">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="bc6a8-121">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-121">Do one of the following:</span></span>
    - <span data-ttu-id="bc6a8-122">目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[アクセス許可] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-122">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="bc6a8-123">[アクセス **許可] 列** を降順で並べ替え、アプリを見つけ、[詳細の **表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-123">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="bc6a8-124">これを行うと、アプリの **詳細ページの** [アクセス許可] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-124">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="bc6a8-125">[ **組織全体のアクセス許可] で [** アクセス許可と **同同編集] を選びます**。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-125">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span> <span data-ttu-id="bc6a8-126">これを行うには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-126">You must be a global admin to do this.</span></span> <span data-ttu-id="bc6a8-127">このオプションは、Teams のサービス管理者は使用できません。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-127">This option isn't available to Teams service admins.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="アプリの [アクセス許可] タブにある、既定のアクセス許可のスクリーンショット":::

4. <span data-ttu-id="bc6a8-129">[権限 **] タブ** で、アプリから要求されたアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-129">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="アプリから要求されたアクセス許可のスクリーンショット":::

    > [!IMPORTANT]
    > <span data-ttu-id="bc6a8-131">アプリに組織全体のユーザーを付付けると、アプリが組織のデータにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-131">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="bc6a8-132">同ユーザーに同済を付与する前に、アプリによって要求されたアクセス許可を正常に確認してください。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-132">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="bc6a8-133">アプリから要求されたアクセス許可に同意したら、[承諾] を **クリックして同** 意を許可します。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-133">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="bc6a8-134">アプリに対して要求されたアクセス許可がアプリに対して与えされたことを知らせるバナーがページの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-134">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="bc6a8-135">これでアプリは組織内のすべてのユーザーに対して指定されたリソースにアクセスでき、他のユーザーには権限を確認するように求めるメッセージが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-135">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="bc6a8-136">アクセス許可を承諾すると、アプリ全体のアクセス許可ページに **[組織** 全体のアクセス許可] に、同意が付与されたことを知らせるメッセージがアプリの詳細ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-136">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="bc6a8-137">アプリのアクセス許可の詳細を表示するには **、Azure Active Directory** リンクをクリックして、Azure AD ポータルのアプリのページに移動します。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-137">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="ユーザーからの資オン時に表示されるメッセージのスクリーンショット":::

<span data-ttu-id="bc6a8-139">組織内のユーザーが同済を許可し、1 人以上のユーザーによって特定のアプリに同めている同済を付けた場合、同じ承認が付けたことと Azure Active Directory リンクを知らせるメッセージのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-139">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll only see the message to let you know that consent was granted and the Azure Active Directory link.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="bc6a8-140">アプリのリソース固有の同同権限を表示する</span><span class="sxs-lookup"><span data-stu-id="bc6a8-140">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="bc6a8-141">RSC 権限を使用すると、チーム所有者はアプリに同でき、チームのデータにアクセスして変更することができます。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-141">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="bc6a8-142">RSC アクセス許可は、定期的に、特定のチームでアプリを実行できる操作を定義する Teams 固有のアクセス許可です。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-142">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="bc6a8-143">RSC アクセス許可の例としては、チャネルの作成と削除、チームの設定の取得、チャネル タブの作成と削除などがあります。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-143">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> <span data-ttu-id="bc6a8-144">RSC アクセス許可は、Azure アクセス許可には含め、アプリ マニフェストで定義AD。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-144">RSC permissions are defined in the app manifest and not in Azure AD.</span></span>

<span data-ttu-id="bc6a8-145">アプリをチームに追加するときに RSC 権限に同与します。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-145">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="bc6a8-146">詳細については [、Teams のリソース固有の問題 (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent) [とリソース固有の問題を参照してください](resource-specific-consent.md)。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-146">To learn more, see [Resource-specific consent (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent) and [Resource-specific consent in Teams](resource-specific-consent.md).</span></span>

<span data-ttu-id="bc6a8-147">グローバル管理者と Teams サービスの管理者は RSC 権限を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-147">Global admins and Teams service admin can view RSC permissions.</span></span> <span data-ttu-id="bc6a8-148">アプリの RSC 権限を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-148">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="bc6a8-149">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの管理**アプリ**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-149">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="bc6a8-150">目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[アクセス許可] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-150">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="bc6a8-151">**Microsoft Graph のリソース固有の同同権限の下で、** アプリによって要求された RSC 権限を確認します。</span><span class="sxs-lookup"><span data-stu-id="bc6a8-151">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="アプリの RSC アクセス許可のスクリーンショット":::

## <a name="related-topics"></a><span data-ttu-id="bc6a8-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc6a8-153">Related topics</span></span>

- [<span data-ttu-id="bc6a8-154">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="bc6a8-154">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="bc6a8-155">Microsoft ID プラットフォーム エンドポイントでのアクセス許可と同同編集</span><span class="sxs-lookup"><span data-stu-id="bc6a8-155">Permissions and consent in the Microsoft identity platform endpoint</span></span>](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="bc6a8-156">Teams でのリソース固有の問題</span><span class="sxs-lookup"><span data-stu-id="bc6a8-156">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="bc6a8-157">リソース固有の問題 (RSC)</span><span class="sxs-lookup"><span data-stu-id="bc6a8-157">Resource-specific consent (RSC)</span></span>](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


