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
ms.openlocfilehash: 6aafd5cbdd1ae44844f69b78234f10a54abe7b85
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824908"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="a46ba-103">Microsoft Teams 管理センターでアプリのアクセス許可を表示し、管理者の同承認を付与する</span><span class="sxs-lookup"><span data-stu-id="a46ba-103">View app permissions and grant admin consent in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="a46ba-104">Microsoft Teams [管理センター](manage-apps.md) の [アプリの管理] ページでは、組織のすべての Teams アプリを表示して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-104">The [Manage apps](manage-apps.md) page in the Microsoft Teams admin center is where you view and manage all Teams apps for your organization.</span></span> <span data-ttu-id="a46ba-105">たとえば、アプリのプロパティの組織レベルの状態とプロパティの確認、新しいカスタム アプリを組織のアプリ ストアに承認またはアップロードしたり、組織レベルのアプリをブロックまたは許可したり、組織全体のアプリ設定を管理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-105">For example, you can see the org-level status and properties of apps, approve or upload new custom apps to your organization's app store, block or allow apps at the org level, and manage org-wide app settings.</span></span>

<span data-ttu-id="a46ba-106">ここでは、データへのアクセス許可を要求するアプリに対する組織全体の管理者の同じ設定を、アプリに対するリソース固有の同一 (RSC) アクセス許可を表示する方法もあります。</span><span class="sxs-lookup"><span data-stu-id="a46ba-106">Here, you can also grant org-wide admin consent to apps that request permissions to access data and view resource-specific consent (RSC) permissions for apps.</span></span>

## <a name="grant-org-wide-admin-consent-to-an-app"></a><span data-ttu-id="a46ba-107">組織全体の管理者におもならず、アプリに管理者の承認を付けます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-107">Grant org-wide admin consent to an app</span></span>

<span data-ttu-id="a46ba-108">全体管理者の場合は、組織内のすべてのユーザーに代わってアクセス許可をリクエストするアプリに対する同じ権限を確認して付与することができます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-108">If you're a global admin, you can review and grant consent to apps that request permissions on behalf of all users in your organization.</span></span> <span data-ttu-id="a46ba-109">この操作を行うことで、ユーザーがアプリを起動したときにアプリから要求されたアクセス許可を確認して承諾する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="a46ba-109">You do this so that users don't have to review and accept the permissions requested by the app when they start the app.</span></span> <span data-ttu-id="a46ba-110">また、Azure Active Directory (Azure AD) の [ユーザー](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) の同済設定によっては、一部のユーザーが、会社データにアクセスするアプリに同時に同済を許可できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a46ba-110">Additionally, depending on the user's [consent settings](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) in Azure Active Directory (Azure AD), some users may not be allowed to grant consent to apps that access company data.</span></span>

<span data-ttu-id="a46ba-111">アプリによって要求されるアクセス許可の例としては、チームに保存されている情報を読み取り、ユーザーのプロフィールを読み、ユーザーの代理でメールを送信する機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-111">Examples of permissions requested by apps include the ability to read information stored in a team, read a user's profile, and send an email on behalf of users.</span></span> <span data-ttu-id="a46ba-112">詳細については、Microsoft ID プラットフォームエンドポイントの権限 [と同同編集を参照してください](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。</span><span class="sxs-lookup"><span data-stu-id="a46ba-112">To learn more, see [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent).</span></span> 

<span data-ttu-id="a46ba-113">[ **権限]** 列は、アプリに同一の権限が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a46ba-113">The **Permissions** column indicates whether an app has permissions that need consent.</span></span> <span data-ttu-id="a46ba-114">Azure アカウント **に登録されている** アプリごとに、同じように同じ権限が必要なアクセス許可を持 ADつアプリごとに、[詳細の表示] リンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-114">You'll see a **View details** link for each app registered in Azure AD that has permissions that need consent.</span></span> <span data-ttu-id="a46ba-115">これは、カスタム アプリとサードパーティのアプリとサードパーティのアプリにのみ適用されることに留まることに留めてください。</span><span class="sxs-lookup"><span data-stu-id="a46ba-115">Keep in mind that this applies only to custom and third-party apps and.</span></span> <span data-ttu-id="a46ba-116">このリンクは表示されないか、Microsoft が発行したアプリに管理者の同同同権限を付けたりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a46ba-116">You won't see this link or need to grant admin consent for apps published by Microsoft.</span></span>

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="[アプリの管理] ページの [アクセス許可] 列のスクリーンショット":::

<span data-ttu-id="a46ba-118">組織全体のユーザーにアプリのユーザーに認識するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="a46ba-118">To grant org-wide consent to an app, follow these steps:</span></span>

1. <span data-ttu-id="a46ba-119">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの管理**アプリ**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a46ba-119">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="a46ba-120">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a46ba-120">Do one of the following:</span></span>
    - <span data-ttu-id="a46ba-121">目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[アクセス許可] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="a46ba-121">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
    - <span data-ttu-id="a46ba-122">[アクセス **許可] 列** を降順で並べ替え、アプリを見つけ、[詳細の **表示] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a46ba-122">Sort the **Permissions** column in descending order to find the app, and then select **View details**.</span></span> <span data-ttu-id="a46ba-123">これを行うと、アプリの **詳細ページの** [アクセス許可] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="a46ba-123">Doing this takes you to the **Permissions** tab of the app details page.</span></span>

3. <span data-ttu-id="a46ba-124">[ **組織全体のアクセス許可] で [** アクセス許可と **同同編集] を選びます**。</span><span class="sxs-lookup"><span data-stu-id="a46ba-124">Under **Org-wide permissions**, select **Review permissions and consent**.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="アプリの [アクセス許可] タブにある、既定のアクセス許可のスクリーンショット":::

    <span data-ttu-id="a46ba-126">これを行うには、グローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a46ba-126">You must be a global admin to do this.</span></span> <span data-ttu-id="a46ba-127">このオプションは、Teams のサービス管理者は使用できません。</span><span class="sxs-lookup"><span data-stu-id="a46ba-127">This option isn't available to Teams service admins.</span></span>

4. <span data-ttu-id="a46ba-128">[権限 **] タブ** で、アプリから要求されたアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="a46ba-128">On the **Permissions** tab, review the permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="アプリから要求されたアクセス許可のスクリーンショット":::

    > [!IMPORTANT]
    > <span data-ttu-id="a46ba-130">アプリに組織全体のユーザーを付付けると、アプリが組織のデータにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="a46ba-130">Granting org-wide consent to an app allows the app to access your organization's data.</span></span> <span data-ttu-id="a46ba-131">同ユーザーに同済を付与する前に、アプリによって要求されたアクセス許可を正常に確認してください。</span><span class="sxs-lookup"><span data-stu-id="a46ba-131">Carefully review the permissions requested by the app before you grant consent.</span></span>
5. <span data-ttu-id="a46ba-132">アプリから要求されたアクセス許可に同意したら、[承諾] を **クリックして同** 意を許可します。</span><span class="sxs-lookup"><span data-stu-id="a46ba-132">If you agree with the permissions requested by the app, click **Accept** to grant consent.</span></span> <span data-ttu-id="a46ba-133">アプリに対して要求されたアクセス許可がアプリに対して与えされたことを知らせるバナーがページの上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-133">A banner temporarily appears at the top of the page to let you know that the requested permissions have been granted for the app.</span></span> <span data-ttu-id="a46ba-134">これでアプリは組織内のすべてのユーザーに対して指定されたリソースにアクセスでき、他のユーザーには権限を確認するように求めるメッセージが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="a46ba-134">The app now has access to the specified resources for all users in your organization and no one else will be prompted to review the permissions.</span></span>

<span data-ttu-id="a46ba-135">アクセス許可を承諾すると、アプリ全体のアクセス許可ページに **[組織** 全体のアクセス許可] に、同意が付与されたことを知らせるメッセージがアプリの詳細ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-135">After you accept the permissions, you'll see a message under **Org-wide permissions** on the app details page to let you know that consent was granted.</span></span> <span data-ttu-id="a46ba-136">アプリのアクセス許可の詳細を表示するには **、Azure Active Directory** リンクをクリックして、Azure AD ポータルのアプリのページに移動します。</span><span class="sxs-lookup"><span data-stu-id="a46ba-136">To view details about the app's permissions, click the **Azure Active Directory** link to go to the app's page in the Azure AD portal.</span></span>

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="ユーザーからの資オン時に表示されるメッセージのスクリーンショット":::

<span data-ttu-id="a46ba-138">組織内のユーザーが同じ内容を付けたり、1 人以上のユーザーに対して特定のアプリに同じ同資を付けた場合は、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示され、同じメッセージが表示されます。このメッセージは、同じメッセージが表示されます。このメッセージは、同じメッセージを表示し、同じメッセージが表示されます。同じメッセージが表示されます。このメッセージは、同じメッセージと同じです。このメッセージは、同じメッセージを表示し、同じメッセージが表示されます。同じメッセージが表示されます。このメッセージは、同じメッセージと、Azure AD ポータルのアプリのページにアクセスできることを知らせるメッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-138">If users in your organization are allowed to grant consent and if one or more users granted consent to a particular app, you'll also see the same message to let you know that consent was granted and the Azure Active Directory link to the app's page in the Azure AD portal.</span></span>

> [!NOTE]
> <span data-ttu-id="a46ba-139">Teams サービス管理者 **は [アクセス許可と同時編集** ] オプションを使用できません。また、アプリに対する組織全体の管理者の同同権限を付与できませんが、Teams サービス管理者はアプリの [ **アクセス** 許可] タブでコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-139">Although, the **Review permissions and consent** option isn't available to Teams service admins and they can't grant org-wide admin consent to apps, Teams service admins can view the content on the **Permissions** tab for an app.</span></span> <span data-ttu-id="a46ba-140">たとえば、Teams サービス管理者は Azure **Active Directory リンクをクリックして、Azure レポート** ポータルでアプリのアクセス許可の詳細をADできます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-140">For example, a Teams service admin can click the **Azure Active Directory** link to view app permissions details in the Azure AD portal.</span></span> 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a><span data-ttu-id="a46ba-141">アプリのリソース固有の同同権限を表示する</span><span class="sxs-lookup"><span data-stu-id="a46ba-141">View resource-specific consent permissions of an app</span></span>

<span data-ttu-id="a46ba-142">RSC 権限を使用すると、チーム所有者はアプリに同でき、チームのデータにアクセスして変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-142">RSC permissions let team owners grant consent for an app to access and modify a team's data.</span></span> <span data-ttu-id="a46ba-143">RSC アクセス許可は、定期的に、特定のチームでアプリを実行できる操作を定義する Teams 固有のアクセス許可です。</span><span class="sxs-lookup"><span data-stu-id="a46ba-143">RSC permissions are granular, Teams-specific permissions that define what an app can do in a specific team.</span></span> <span data-ttu-id="a46ba-144">RSC アクセス許可の例としては、チャネルの作成と削除、チームの設定の取得、チャネル タブの作成と削除などがあります。</span><span class="sxs-lookup"><span data-stu-id="a46ba-144">Examples of RSC permissions include the ability to create and delete channels, get the settings for a team, and create and remove channel tabs.</span></span> 

<span data-ttu-id="a46ba-145">RSC アクセス許可は、Azure アクセス許可には含め、アプリ マニフェストで定義AD。</span><span class="sxs-lookup"><span data-stu-id="a46ba-145">RSC permissions are defined in the app manifest and not in Azure AD.</span></span> <span data-ttu-id="a46ba-146">アプリをチームに追加するときに RSC 権限に同与します。</span><span class="sxs-lookup"><span data-stu-id="a46ba-146">You grant consent to RSC permissions when you add the app to a team.</span></span> <span data-ttu-id="a46ba-147">詳細については、 [リソース固有の問題 (RSC) を参照してください](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)。</span><span class="sxs-lookup"><span data-stu-id="a46ba-147">To learn more, see [Resource-specific consent (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent).</span></span>

<span data-ttu-id="a46ba-148">グローバル管理者と Teams サービス管理者は、アプリの詳細ページの [**Permissions**アクセス許可] タブでアプリの RSC 権限を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-148">Global admins and Teams service admin can view RSC permissions for an app on the **Permissions** tab of the app details page.</span></span> 

<span data-ttu-id="a46ba-149">アプリの RSC 権限を表示するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a46ba-149">To view RSC permissions for an app, follow these steps:</span></span>

1. <span data-ttu-id="a46ba-150">Microsoft Teams 管理センターの左側のナビゲーションで、Teams アプリの管理**アプリ**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="a46ba-150">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>
2. <span data-ttu-id="a46ba-151">目的のアプリを検索し、アプリ名をクリックしてアプリの詳細ページに移動し、[アクセス許可] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="a46ba-151">Search for the app you want, click the app name to go to the app details page, and then select the **Permissions** tab.</span></span>
3. <span data-ttu-id="a46ba-152">**Microsoft Graph のリソース固有の同同権限の下で、** アプリによって要求された RSC 権限を確認します。</span><span class="sxs-lookup"><span data-stu-id="a46ba-152">Under **Microsoft Graph resource-specific consent (RSC) permissions**, review the RSC permissions requested by the app.</span></span>

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="アプリの RSC アクセス許可のスクリーンショット":::

## <a name="known-issues"></a><span data-ttu-id="a46ba-154">既知の問題</span><span class="sxs-lookup"><span data-stu-id="a46ba-154">Known issues</span></span>

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a><span data-ttu-id="a46ba-155">アクセス許可を要求する一部のサード パーティのアプリの [アクセス許可] 列に [詳細の表示] リンクは表示されません</span><span class="sxs-lookup"><span data-stu-id="a46ba-155">The "View details" link isn't displayed in the Permissions column for some third-party apps that request permissions</span></span>

<span data-ttu-id="a46ba-156">現時代、アクセス許可を確認して同じように、アクセス許可を要求するすべてのサード パーティのアプリで、同じ資オンを ADできません。</span><span class="sxs-lookup"><span data-stu-id="a46ba-156">Currently, the ability to review permissions and grant consent isn't available for all third-party apps registered in Azure AD that request permissions.</span></span> <span data-ttu-id="a46ba-157">[詳細の表示 **] リンクではなく** 、[アクセス許可] 列 **--** に **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="a46ba-157">Instead of the **View details** link, you'll see **--** in the **Permissions** column.</span></span> <span data-ttu-id="a46ba-158">MICROSOFT では、お客様のアプリでこの機能を有効にする ISV と一回用しています。</span><span class="sxs-lookup"><span data-stu-id="a46ba-158">We're working with ISVs to enable this feature for their apps.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a46ba-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="a46ba-159">Related topics</span></span>

- [<span data-ttu-id="a46ba-160">Microsoft Teams 管理センターでアプリを管理する</span><span class="sxs-lookup"><span data-stu-id="a46ba-160">Manage your apps in the Microsoft Teams admin center</span></span>](manage-apps.md)
- [<span data-ttu-id="a46ba-161">Microsoft ID プラットフォーム エンドポイントでのアクセス許可と同同編集</span><span class="sxs-lookup"><span data-stu-id="a46ba-161">Permissions and consent in the Microsoft identity platform endpoint</span></span>](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [<span data-ttu-id="a46ba-162">Teams でのリソース固有の問題</span><span class="sxs-lookup"><span data-stu-id="a46ba-162">Resource-specific consent in Teams</span></span>](resource-specific-consent.md)
- [<span data-ttu-id="a46ba-163">リソース固有の問題 (RSC)</span><span class="sxs-lookup"><span data-stu-id="a46ba-163">Resource-specific consent (RSC)</span></span>](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


