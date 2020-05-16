---
title: Microsoft 365 管理センターを使用してリソースアカウントを作成する
description: グラフィカルユーザーインターフェイスを使用する場合は、microsoft 365 管理センターを使用して、microsoft teams の会議室とコラボレーションバーのリソースアカウントを作成することができます。
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: デバイスアカウントの作成、Microsoft 365 UI、Microsoft 365 管理センター
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268037"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a><span data-ttu-id="5bb27-104">Microsoft 365 管理センターを使用して Microsoft 365 リソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="5bb27-104">Create a Microsoft 365 resource account using the Microsoft 365 admin center</span></span>

<span data-ttu-id="5bb27-105">Microsoft 365 リソースアカウントは、会議室、プロジェクターなどの特定のリソース専用のメールボックスおよび Teams アカウントです。</span><span class="sxs-lookup"><span data-stu-id="5bb27-105">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="5bb27-106">これらのリソースアカウントは、作成時に定義したルールを使って、会議出席依頼に自動的に応答できます。</span><span class="sxs-lookup"><span data-stu-id="5bb27-106">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="5bb27-107">たとえば、会議室などの共通のリソースがある場合は、その会議室のリソースアカウントを設定して、会議の出席依頼を自動的に承諾または拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="5bb27-107">For example, if you have a common resource such as a conference room, you can set up a resource account for that conference room that will automatically accept or decline meeting invites depending on its calendar availability.</span></span>

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a><span data-ttu-id="5bb27-108">ライセンス</span><span class="sxs-lookup"><span data-stu-id="5bb27-108">Licensing</span></span>

<span data-ttu-id="5bb27-109">Microsoft 365 リソースアカウントを作成する前に、必要なライセンスの種類を確認してください。</span><span class="sxs-lookup"><span data-stu-id="5bb27-109">Before you create a Microsoft 365 resource account, check to see what kind of license it needs.</span></span> <span data-ttu-id="5bb27-110">リソースアカウントを使用してリソースを予約する場合 (つまり、会議にリソースを招待し、招待を自動的に承諾または辞退した場合)、リソースアカウントにライセンスを割り当てる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5bb27-110">If you'll only use a resource account to book a resource (that is, invite the resource to your meeting and have it automatically accept or decline the invitation), you don't need to assign a license to a resource account.</span></span> <span data-ttu-id="5bb27-111">次のような場合は、リソースアカウントにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bb27-111">You'll need to assign a license to the resource account in the following situations:</span></span>

- <span data-ttu-id="5bb27-112">**Teams 会議**リソース (Microsoft Teams のルーム本体、コラボレーションバーなど) を Teams 会議に参加させて、参加者がビデオや音声を使ってビデオや音声を表示できるようにするには、会議室のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="5bb27-112">**Teams meeting** If you want the resource (such as a Microsoft Teams Rooms console, collaboration bar, and so on) to join a Teams meeting so attendees can use it to present video and audio through it, you need a Meeting Room license.</span></span> 
- <span data-ttu-id="5bb27-113">**PSTN 通話**リソースが外部電話番号 (公衆交換電話網または PSTN 通話と呼ばれます) に対して通話を発信または受信できるようにするには、Microsoft 365 電話システムまたは Microsoft 365 Business Voice license が必要です。</span><span class="sxs-lookup"><span data-stu-id="5bb27-113">**PSTN calls** If you want the resource to make or receive calls to or from an external phone numbers (called a Public Switched Telephone Network or PSTN call), you need a Microsoft 365 Phone System or Microsoft 365 Business Voice license.</span></span>

<span data-ttu-id="5bb27-114">会議室、電話システム、ビジネス用ボイスライセンスの詳細については、「 [Microsoft Teams のアドオンライセンス](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bb27-114">For more information about Meeting Room, Phone System, and Business Voice licenses, see [Microsoft Teams add-on licenses](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a><span data-ttu-id="5bb27-115">Microsoft 365 管理センターでリソースアカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="5bb27-115">Create a resource account in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="5bb27-116">アクセスして、Microsoft 365 にサインインします。https://admin.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5bb27-116">Sign in to Microsoft 365 by visiting https://admin.microsoft.com</span></span>
2. <span data-ttu-id="5bb27-117">Microsoft 365 テナントの管理者資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5bb27-117">Provide the admin credentials for your Microsoft 365 tenant.</span></span> <span data-ttu-id="5bb27-118">この操作を行うと、Microsoft 365 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="5bb27-118">This will take you to your Microsoft 365 admin center.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 管理センター":::
3. <span data-ttu-id="5bb27-120">管理センターで、左側のパネルの [**リソース**] に移動し ([**すべて表示**] を選択します)、[**会議室] & [備品**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bb27-120">In the admin center, navigate to **Resources** in the left panel (you might need to select **Show all** first), and then select **Rooms & equipment**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 管理センター-リソース":::
4. <span data-ttu-id="5bb27-122">[**リソースメールボックスの追加**] を選択して、新しい会議室アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="5bb27-122">Select **Add a resource mailbox** to create a new room account.</span></span> <span data-ttu-id="5bb27-123">アカウントの表示名とメールアドレスを入力し、[**追加**]、[**閉じる**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="5bb27-123">Enter a display name and email address for the account, select **Add**, and then select **Close**.</span></span> <span data-ttu-id="5bb27-124">すべてのリソースアカウントの命名規則を標準化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5bb27-124">We recommend you standardize on a naming convention for all of your resource accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="5bb27-125">既定では、リソースアカウントは次の設定で設定されます。</span><span class="sxs-lookup"><span data-stu-id="5bb27-125">By default, resource accounts are set up with the following settings.</span></span> <span data-ttu-id="5bb27-126">設定を変更する場合は、[**閉じる**] を選択する前に、[**スケジュールオプションの設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bb27-126">If you want to change them, select **Set scheduling options** before you select **Close**.</span></span> <span data-ttu-id="5bb27-127">後で変更する場合は、[**リソース**  >  **ルーム & 備品**] に移動してリソースアカウントを選択し、[**予約オプション**] の [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bb27-127">If you want to change them later, navigate to **Resources** > **Rooms & equipment**, select the resource account and then select **Edit** under **Booking options**.</span></span>
>
> - <span data-ttu-id="5bb27-128">会議の繰り返しを許可する</span><span class="sxs-lookup"><span data-stu-id="5bb27-128">Allow repeat meetings</span></span>
> - <span data-ttu-id="5bb27-129">次の制限を超えて会議を自動的に辞退する</span><span class="sxs-lookup"><span data-stu-id="5bb27-129">Automatically decline meetings outside of the following limits</span></span>
>   - <span data-ttu-id="5bb27-130">予約ウィンドウ (日数): 180</span><span class="sxs-lookup"><span data-stu-id="5bb27-130">Booking window (days): 180</span></span>
>   - <span data-ttu-id="5bb27-131">最大期間 (時間):24</span><span class="sxs-lookup"><span data-stu-id="5bb27-131">Maximum duration (hours): 24</span></span>
> - <span data-ttu-id="5bb27-132">会議出席依頼を自動承諾する</span><span class="sxs-lookup"><span data-stu-id="5bb27-132">Auto accept meeting requests</span></span>

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 管理センター-リソースを追加する":::
5. <span data-ttu-id="5bb27-134">管理センターの [**ユーザー** ] セクションに移動し、[**アクティブなユーザー** ] の一覧に、作成した会議室が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bb27-134">Navigate to the **Users** section in admin center and, in the **Active users** list, you will see the room you just created.</span></span>

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 管理センター-アクティブなユーザーを表示する":::
6. <span data-ttu-id="5bb27-136">会議室の名前を選択すると、アカウントのプロパティパネルが右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bb27-136">Select on the name of the room and an account properties panel will appear on the right.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 管理センター-ユーザープロパティ":::
7. <span data-ttu-id="5bb27-138">次に、リソースアカウントにパスワードを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bb27-138">Now you need to assign a password to the resource account.</span></span> <span data-ttu-id="5bb27-139">パネルでは、アカウントのプロパティといくつかのオプションの操作を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5bb27-139">In the panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="5bb27-140">[パスワードを変更するには、ユーザー名] の下にあるパスワードキーの**リセット**アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5bb27-140">Select the **Reset password** key icon under the username to change the password.</span></span> <span data-ttu-id="5bb27-141">**[ユーザーが最初にサインインしたときに、このユーザーにパスワードの変更を要求する**(オフ)。</span><span class="sxs-lookup"><span data-stu-id="5bb27-141">Unselect **Require this user to change their password when they first sign in**.</span></span> <span data-ttu-id="5bb27-142">デバイスのサインイン処理を使用してパスワードを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5bb27-142">It is not possible to change the password via the device sign-in process.</span></span> <span data-ttu-id="5bb27-143">[**リセット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5bb27-143">Select **Reset**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 管理センター-パスワードの再設定":::
8. <span data-ttu-id="5bb27-145">[**ライセンスとアプリ**] セクションで、デバイスのインストール先の国または地域を **[場所]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="5bb27-145">In the **Licenses and Apps** section, set **Select location** to the country or region where the device will be installed.</span></span> <span data-ttu-id="5bb27-146">下にスクロールし、会議室など、割り当てるライセンスの隣にあるチェックボックスをオンにして、[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bb27-146">Scroll down and check the box next to the license to be assigned - such as Meeting Room - and then select **Save changes**.</span></span> <span data-ttu-id="5bb27-147">ライセンスは、組織によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5bb27-147">The license may vary depending on your organization.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 管理センター-ライセンスの割り当て":::
