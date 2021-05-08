---
title: 管理センターでリソース アカウントをMicrosoft 365する
description: グラフィカル ユーザー インターフェイスを使用する場合は、Microsoft Teams ミーティング 管理センターを使用して、Microsoft Teams ミーティング とコラボレーション バーのリソース Microsoft Teams作成Microsoft 365できます。
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: デバイス アカウントの作成、MICROSOFT 365 UI、Microsoft 365管理センター
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
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a><span data-ttu-id="f1ed8-104">管理センター Microsoft 365使用してリソース アカウントMicrosoft 365作成する</span><span class="sxs-lookup"><span data-stu-id="f1ed8-104">Create a Microsoft 365 resource account using the Microsoft 365 admin center</span></span>

<span data-ttu-id="f1ed8-105">Microsoft 365アカウントは、会議室Teamsプロジェクターなど、特定のリソース専用のメールボックス アカウントとリソース アカウントです。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-105">Microsoft 365 resource accounts are mailbox and Teams accounts that are dedicated to specific resources, such as a room, projector, and so on.</span></span> <span data-ttu-id="f1ed8-106">これらのリソース アカウントは、作成時に定義したルールを使用して、会議出席招待に自動的に応答できます。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-106">These resource accounts can automatically respond to meeting invites using rules you define when they're created.</span></span> <span data-ttu-id="f1ed8-107">たとえば、会議室などの一般的なリソースがある場合は、予定表の空き時間に応じて会議出席招待を自動的に承諾または拒否する、その会議室のリソース アカウントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-107">For example, if you have a common resource such as a conference room, you can set up a resource account for that conference room that will automatically accept or decline meeting invites depending on its calendar availability.</span></span>

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a><span data-ttu-id="f1ed8-108">ライセンス</span><span class="sxs-lookup"><span data-stu-id="f1ed8-108">Licensing</span></span>

<span data-ttu-id="f1ed8-109">リソース アカウントを作成Microsoft 365、必要なライセンスの種類を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-109">Before you create a Microsoft 365 resource account, check to see what kind of license it needs.</span></span> <span data-ttu-id="f1ed8-110">リソース アカウントを使用してリソースを予約する場合 (つまり、リソースを会議に招待し、招待を自動的に承諾または拒否する) 場合は、リソース アカウントにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-110">If you'll only use a resource account to book a resource (that is, invite the resource to your meeting and have it automatically accept or decline the invitation), you don't need to assign a license to a resource account.</span></span> <span data-ttu-id="f1ed8-111">次の状況では、リソース アカウントにライセンスを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-111">You'll need to assign a license to the resource account in the following situations:</span></span>

- <span data-ttu-id="f1ed8-112">**Teams会議** リソース (Microsoft Teams ミーティング 本体、コラボレーション バーなど) を Teams 会議に参加して、出席者がそれを使用してビデオやオーディオを表示するには、ミーティング ルーム ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-112">**Teams meeting** If you want the resource (such as a Microsoft Teams Rooms console, collaboration bar, and so on) to join a Teams meeting so attendees can use it to present video and audio through it, you need a Meeting Room license.</span></span> 
- <span data-ttu-id="f1ed8-113">**PSTN 通話** リソースが外部の電話番号 (公衆交換電話網または PSTN 通話と呼ばれる) との間で通話を発信または受信するには、Microsoft 365 電話システム または Microsoft 365 Business Voice ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-113">**PSTN calls** If you want the resource to make or receive calls to or from an external phone numbers (called a Public Switched Telephone Network or PSTN call), you need a Microsoft 365 Phone System or Microsoft 365 Business Voice license.</span></span>

<span data-ttu-id="f1ed8-114">ミーティング ルーム、電話システム、Business Voice のライセンスの詳細については、「Microsoft Teams アドオン ライセンス[」を参照してください。](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="f1ed8-114">For more information about Meeting Room, Phone System, and Business Voice licenses, see [Microsoft Teams add-on licenses](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span></span>

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a><span data-ttu-id="f1ed8-115">管理センターでリソース アカウントをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="f1ed8-115">Create a resource account in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="f1ed8-116">にアクセスして Microsoft 365 にサインインします。https://admin.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f1ed8-116">Sign in to Microsoft 365 by visiting https://admin.microsoft.com</span></span>
2. <span data-ttu-id="f1ed8-117">テナントの管理者資格情報をMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-117">Provide the admin credentials for your Microsoft 365 tenant.</span></span> <span data-ttu-id="f1ed8-118">これにより、管理センターにMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-118">This will take you to your Microsoft 365 admin center.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 管理センター":::
3. <span data-ttu-id="f1ed8-120">管理センターで、左側のパネルの **[リソース**] に移動し (最初に [すべて表示] を選択する必要がある場合があります)、[会議室] を選択&**します**。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-120">In the admin center, navigate to **Resources** in the left panel (you might need to select **Show all** first), and then select **Rooms & equipment**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365管理センター - リソース":::
4. <span data-ttu-id="f1ed8-122">[ **リソース メールボックスの追加] を選択** して、新しいルーム アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-122">Select **Add a resource mailbox** to create a new room account.</span></span> <span data-ttu-id="f1ed8-123">アカウントの表示名とメール アドレスを入力し、[追加] を選択して、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-123">Enter a display name and email address for the account, select **Add**, and then select **Close**.</span></span> <span data-ttu-id="f1ed8-124">すべてのリソース アカウントの名前付け規則を標準化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-124">We recommend you standardize on a naming convention for all of your resource accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="f1ed8-125">既定では、リソース アカウントは次の設定で設定されます。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-125">By default, resource accounts are set up with the following settings.</span></span> <span data-ttu-id="f1ed8-126">それらを変更する場合は、[閉じる] を選択 **する前** に [スケジュール オプションの設定] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-126">If you want to change them, select **Set scheduling options** before you select **Close**.</span></span> <span data-ttu-id="f1ed8-127">後で変更する場合は、[リソース ルーム] &機器] に移動し、リソース アカウントを選択し、[予約オプション] の [編集]  >  **を選択します**。 </span><span class="sxs-lookup"><span data-stu-id="f1ed8-127">If you want to change them later, navigate to **Resources** > **Rooms & equipment**, select the resource account and then select **Edit** under **Booking options**.</span></span>
>
> - <span data-ttu-id="f1ed8-128">繰り返し会議を許可する</span><span class="sxs-lookup"><span data-stu-id="f1ed8-128">Allow repeat meetings</span></span>
> - <span data-ttu-id="f1ed8-129">次の制限を超え、会議を自動的に拒否する</span><span class="sxs-lookup"><span data-stu-id="f1ed8-129">Automatically decline meetings outside of the following limits</span></span>
>   - <span data-ttu-id="f1ed8-130">予約期間 (日): 180</span><span class="sxs-lookup"><span data-stu-id="f1ed8-130">Booking window (days): 180</span></span>
>   - <span data-ttu-id="f1ed8-131">最大期間 (時間): 24</span><span class="sxs-lookup"><span data-stu-id="f1ed8-131">Maximum duration (hours): 24</span></span>
> - <span data-ttu-id="f1ed8-132">会議出席依頼を自動承諾する</span><span class="sxs-lookup"><span data-stu-id="f1ed8-132">Auto accept meeting requests</span></span>

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 - リソースの追加":::
5. <span data-ttu-id="f1ed8-134">管理センターの **[ユーザー** ] セクションに移動し、[アクティブなユーザー] の一覧に、作成したルームが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-134">Navigate to the **Users** section in admin center and, in the **Active users** list, you will see the room you just created.</span></span>

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 - アクティブなユーザーを表示する":::
6. <span data-ttu-id="f1ed8-136">ルームの名前を選択すると、アカウントのプロパティ パネルが右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-136">Select on the name of the room and an account properties panel will appear on the right.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 管理センター - ユーザー プロパティ":::
7. <span data-ttu-id="f1ed8-138">次に、リソース アカウントにパスワードを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-138">Now you need to assign a password to the resource account.</span></span> <span data-ttu-id="f1ed8-139">パネルには、アカウントのプロパティといくつかのオプションアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-139">In the panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="f1ed8-140">ユーザー名の **下にある** [パスワード キーのリセット] アイコンを選択して、パスワードを変更します。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-140">Select the **Reset password** key icon under the username to change the password.</span></span> <span data-ttu-id="f1ed8-141">[このユーザー **が初めてサインインするときにパスワードを変更する] を選択解除します**。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-141">Unselect **Require this user to change their password when they first sign in**.</span></span> <span data-ttu-id="f1ed8-142">デバイスのサインイン プロセスを使用してパスワードを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-142">It is not possible to change the password via the device sign-in process.</span></span> <span data-ttu-id="f1ed8-143">[リセット] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-143">Select **Reset**.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 管理センター - パスワードのリセット":::
8. <span data-ttu-id="f1ed8-145">[ライセンス **とアプリ] セクション** で **、[場所の** 選択] をデバイスがインストールされる国または地域に設定します。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-145">In the **Licenses and Apps** section, set **Select location** to the country or region where the device will be installed.</span></span> <span data-ttu-id="f1ed8-146">下にスクロールし、割り当てるライセンスの横にあるチェック ボックス ([変更の保存] ミーティング ルーム など)**をオンにします**。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-146">Scroll down and check the box next to the license to be assigned - such as Meeting Room - and then select **Save changes**.</span></span> <span data-ttu-id="f1ed8-147">ライセンスは組織によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1ed8-147">The license may vary depending on your organization.</span></span>

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 管理センター - ライセンスの割り当て":::
