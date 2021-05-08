---
title: デバイス タグを管理Microsoft Teamsフィルター処理する
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
description: デバイスでタグを管理およびフィルター処理するMicrosoft Teamsします。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a4f8ac718a965834678098a8960347278d13aa3
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874997"
---
# <a name="manage-microsoft-teams-device-tags"></a><span data-ttu-id="2a7a7-103">デバイス タグMicrosoft Teams管理する</span><span class="sxs-lookup"><span data-stu-id="2a7a7-103">Manage Microsoft Teams device tags</span></span>

<span data-ttu-id="2a7a7-104">デバイス タグをMicrosoft Teams、組織に展開したデバイスをグループ化、整理、および管理し、より簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-104">Device tags in Microsoft Teams let you group, organize, and more easily manage the devices you've deployed in your organization.</span></span> <span data-ttu-id="2a7a7-105">Microsoft Teams 管理センターでは、デバイスに 1 つ以上のタグを追加し、フィルターを使用して、指定したタグに一致するデバイスを表示し、そのタグを持つデバイスに対してアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-105">With the Microsoft Teams admin center, you can add one or more tags to devices, use filters to view devices that match the tag you specify, and then perform actions on the devices that have that tag.</span></span>

<span data-ttu-id="2a7a7-106">複数のデバイス の種類にデバイス タグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-106">You can add a device tag to more than one device type.</span></span> <span data-ttu-id="2a7a7-107">ただし、管理センターでデバイス ウィンドウを開いた場合は、その種類のデバイスだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-107">However, when you open a device pane in the admin center, only the devices of that type are returned.</span></span> <span data-ttu-id="2a7a7-108">たとえば、電話とデバイスの両方に "企業" タグを割り当Teams ミーティングできます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-108">For example, you can assign the "Corporate" tag to both phones and Teams Rooms devices.</span></span> <span data-ttu-id="2a7a7-109">[デバイスの電話] で "企業"タグを検索すると、  >  電話だけが返されます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-109">If you search for the "Corporate" tag while in **Devices** > **Phones**, only phones are returned.</span></span> <span data-ttu-id="2a7a7-110">同様に、[デバイス] で "企業"タグを検索  >  **Teams ミーティング、Teams ミーティング** デバイスだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-110">Similarly, if you search for the "Corporate" tag in **Devices** > **Teams Rooms**, only Teams Rooms devices are returned.</span></span>

<span data-ttu-id="2a7a7-111">デバイス タグを管理するには、グローバル管理者、サービス管理者Teams、またはデバイス管理者Teams必要があります。管理者ロールの詳細については、「管理者ロールを使用してMicrosoft Teams[を管理する」を](../using-admin-roles.md)Teams。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-111">To manage device tags, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a7a7-112">デバイス タグは、デバイスにログインしているリソース アカウントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-112">Device tags are assigned to the resource account that's logged into a device.</span></span> <span data-ttu-id="2a7a7-113">あるデバイスからリソース アカウントをサインアウトし、それを使用して別のデバイスにサインインすると、デバイス タグが新しいデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-113">If you sign a resource account out of one device and then use it to sign in to another device, the device tags are applied to the new device.</span></span>

## <a name="create-remove-or-rename-device-tags"></a><span data-ttu-id="2a7a7-114">デバイス タグを作成、削除、または名前変更する</span><span class="sxs-lookup"><span data-stu-id="2a7a7-114">Create, remove, or rename device tags</span></span>

<span data-ttu-id="2a7a7-115">デバイス タグ管理パネルを使用すると、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-115">Using the device tag management panel, you can:</span></span>

- <span data-ttu-id="2a7a7-116">すべてのデバイス タグを表示します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-116">See all your device tags.</span></span>
- <span data-ttu-id="2a7a7-117">複数のデバイス タグを簡単に作成し、後でデバイスに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-117">Create multiple device tags easily and then assign them to devices at a later time.</span></span> <span data-ttu-id="2a7a7-118">タグは最大 25 文字まで指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-118">Tags can be up to 25 characters.</span></span>
- <span data-ttu-id="2a7a7-119">不要になったデバイス タグを削除します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-119">Remove device tags that are no longer needed.</span></span> <span data-ttu-id="2a7a7-120">デバイス タグを削除する前に、デバイス タグが追加されているすべてのデバイスから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-120">Before you can remove a device tag, you'll need to remove it from all of the devices it has been added to.</span></span>
- <span data-ttu-id="2a7a7-121">デバイス タグの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-121">Rename device tags.</span></span> <span data-ttu-id="2a7a7-122">デバイス タグの名前を変更すると、その変更は追加されたデバイスすべてに反映されます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-122">When you rename a device tag, that change is reflected on all the devices it's been added to.</span></span> <span data-ttu-id="2a7a7-123">タグは最大 25 文字まで指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-123">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="2a7a7-124">にアクセスして、Microsoft Teams 管理センターにサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="2a7a7-125">[デバイス **] に** 移動し、[電話] などの任意のデバイス ウィンドウ **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-125">Navigate to **Devices** and then choose any device pane, such as **Phones**.</span></span>
3. <span data-ttu-id="2a7a7-126">ページ **の右上隅** にある [アクション] を選択し、[すべてのデバイス タグ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-126">Select **Actions** in the upper-right corner of the page and select **All device tags**.</span></span>
4. <span data-ttu-id="2a7a7-127">デバイス タグを作成するには **、[+** 追加] を選択し、デバイス タグの値を指定し、[保存] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-127">To create a device tag, select **+ Add**, provide a value for the device tag, and select the **Save** icon.</span></span>
5. <span data-ttu-id="2a7a7-128">デバイス タグを削除するには、削除するデバイス タグの横にある省略記号 **[...]** を選択し、[削除] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-128">To remove a device tag, select the ellipsis **...** next to the device tag you want to remove, and select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="2a7a7-129">デバイスに追加されたデバイス タグを削除すると、すべてのデバイスから削除する必要があるというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-129">If you try to remove a device tag that's been added to devices, you'll receive a message asking if you want to remove it from all devices.</span></span> <span data-ttu-id="2a7a7-130">これを行い、引き続きデバイス タグを削除する場合は、[デバイスのタグ付け解除 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-130">If you want to do this and continue to remove the device tag, select **Untag devices**.</span></span>
6. <span data-ttu-id="2a7a7-131">デバイス タグの名前を変更するには、名前を変更するデバイス タグの横にある省略記号 **[...]** を選択し、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-131">To rename a device tag, select the ellipsis **...** next to the device tag you want to rename, and select **Edit**.</span></span> <span data-ttu-id="2a7a7-132">デバイス タグに新しい値を指定し、[保存] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-132">Provide a new value for the device tag and select the **Save** icon.</span></span>

## <a name="add-or-remove-tags-on-a-single-device"></a><span data-ttu-id="2a7a7-133">1 台のデバイスでタグを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="2a7a7-133">Add or remove tags on a single device</span></span>

<span data-ttu-id="2a7a7-134">デバイスにタグを追加するときに、既存のタグを選択するか、新しいタグを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-134">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="2a7a7-135">タグは最大 25 文字まで指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-135">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="2a7a7-136">にアクセスして、Microsoft Teams 管理センターにサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-136">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="2a7a7-137">[デバイス **] に** 移動し、タグを追加または削除するデバイスを含むデバイス ウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-137">Navigate to **Devices** and then choose the device pane that contains the device you want to add or remove tags on.</span></span>
3. <span data-ttu-id="2a7a7-138">タグを追加または削除するデバイスの横にチェック マークを付け、[タグの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-138">Place a check mark next to the device you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="2a7a7-139">タグを追加する場合:</span><span class="sxs-lookup"><span data-stu-id="2a7a7-139">If you want to add a tag:</span></span>
    1. <span data-ttu-id="2a7a7-140">追加するタグ名の入力を開始します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-140">Start typing the tag name you want to add.</span></span>
    2. <span data-ttu-id="2a7a7-141">タグが既に存在する場合は、返されるタグの一覧からそのタグを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-141">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="2a7a7-142">タグが存在しない場合は、新しいタグ **として [追加] \<tag name> を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-142">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span> <span data-ttu-id="2a7a7-143">タグは最大 25 文字まで指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-143">Tags can be up to 25 characters.</span></span>
5. <span data-ttu-id="2a7a7-144">タグを削除する場合は、削除するタグ **の横にある [X]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-144">If you want to remove a tag, select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="2a7a7-145">タグを追加または削除する場合は、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-145">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="2a7a7-146">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-146">Select **Apply**.</span></span>

## <a name="add-or-remove-tags-on-multiple-devices"></a><span data-ttu-id="2a7a7-147">複数のデバイスでタグを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="2a7a7-147">Add or remove tags on multiple devices</span></span>

<span data-ttu-id="2a7a7-148">デバイスにタグを追加するときに、既存のタグを選択するか、新しいタグを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-148">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="2a7a7-149">タグは最大 25 文字まで指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-149">Tags can be up to 25 characters.</span></span> <span data-ttu-id="2a7a7-150">複数のデバイスからタグを削除する場合は、デバイスに関連付けられている Teams ユーザーを選択し、そのユーザーからタグを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-150">If you want to remove a tag from multiple devices, you need to select the Teams user that's associated with the device and remove the tag from the user.</span></span>

1. <span data-ttu-id="2a7a7-151">にアクセスして、Microsoft Teams 管理センターにサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-151">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="2a7a7-152">[デバイス **] に** 移動し、タグを追加または削除するデバイスを含むデバイス ウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-152">Navigate to **Devices** and then choose the device pane that contains the devices you want to add or remove tags on.</span></span>
3. <span data-ttu-id="2a7a7-153">タグを追加または削除するデバイスの横にチェック マークを付け、[タグの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-153">Place a check mark next to the devices you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="2a7a7-154">タグを追加する場合:</span><span class="sxs-lookup"><span data-stu-id="2a7a7-154">If you want to add a tag:</span></span>
    1. <span data-ttu-id="2a7a7-155">[Manage tags for all devices for Teams users ] に追加 **するタグ名の入力を開始します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-155">Start typing the tag name you want to add in **Manage tags for all devices of Teams users**.</span></span>
    2. <span data-ttu-id="2a7a7-156">タグが既に存在する場合は、返されるタグの一覧からそのタグを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-156">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="2a7a7-157">タグが存在しない場合は、新しいタグ **として [追加] \<tag name> を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-157">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span>
5. <span data-ttu-id="2a7a7-158">タグを削除する場合:</span><span class="sxs-lookup"><span data-stu-id="2a7a7-158">If you want to remove a tag:</span></span>
    1. <span data-ttu-id="2a7a7-159">[ユーザー **の選択Teams展開** します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-159">Expand **Select Teams users**.</span></span>
    2. <span data-ttu-id="2a7a7-160">タグ **\<x> を** 削除するユーザー Teamsの下にある [タグ] を展開します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-160">Expand **\<x> tags** under the name of the Teams user you want to remove tags from.</span></span>
    3. <span data-ttu-id="2a7a7-161">削除するタグの横にある **[X]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-161">Select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="2a7a7-162">タグを追加または削除する場合は、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-162">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="2a7a7-163">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-163">Select **Apply**.</span></span>

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a><span data-ttu-id="2a7a7-164">フィルターを使用して特定のタグを持つデバイスを返す</span><span class="sxs-lookup"><span data-stu-id="2a7a7-164">Use filters to return devices with a specific tag</span></span>

<span data-ttu-id="2a7a7-165">デバイスにデバイス タグを追加した場合は、デバイス の一覧をフィルター処理して、指定したタグが追加されているデバイスのみを返します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-165">If you've added device tags to your devices, you can use them to filter the device list to return only the devices that have had a specified tag added to them.</span></span> <span data-ttu-id="2a7a7-166">これは、特定の部屋内のすべてのデバイス、特定の種類のすべてのデバイス、またはタグを追加するときに使用したその他の条件を表示する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-166">This can be helpful if you just want to view all the devices in a specific room, all the devices of a certain type, or any other criteria you used when adding your tags.</span></span> <span data-ttu-id="2a7a7-167">ウェーブの更新プログラムの適用や、デバイス タグを使用して識別されたデバイスのグループに応じて異なる構成ポリシーの設定など、返されたデバイスに対して一括アクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-167">You can also perform bulk actions on returned devices, such as applying updates in waves, or setting different configuration policies depending on the groups of devices identified using device tags.</span></span>

1. <span data-ttu-id="2a7a7-168">にアクセスして、Microsoft Teams 管理センターにサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-168">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="2a7a7-169">[デバイス **] に** 移動し、フィルター処理するデバイスを含むデバイス ウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-169">Navigate to **Devices** and then choose the device pane that contains the devices you want to filter.</span></span>
3. <span data-ttu-id="2a7a7-170">[フィルター] **アイコンを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-170">Select the **Filter** icon.</span></span>
4. <span data-ttu-id="2a7a7-171">1 つのタグのみを指定する場合、または指定したタグを持つデバイスを検索する場合は、[これらの条件のすべてと一致する] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-171">If you only want to specify a single tag, or if you want to find devices that have all the tags you specify, select **Match all of these conditions**.</span></span>
5. <span data-ttu-id="2a7a7-172">1 つ以上のデバイス タグに一致するデバイスを検索する場合は、[次のいずれかの条件に一致 **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-172">If you want to find devices that match one or more device tags, select **Match any one of these conditions**.</span></span>
6. <span data-ttu-id="2a7a7-173">[タグ **] フィールド** を選択し、[値の入力] フィールドにデバイス タグ **名を指定** します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-173">Select the **Tag** field and then specify a device tag name in the **Enter a value** field.</span></span>
7. <span data-ttu-id="2a7a7-174">デバイス タグを追加する場合は、[追加] を選択し、追加するタグごとに手順 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-174">If you want to add more device tags, select **Add more** and repeat step 6 for each tag you want to add.</span></span>
8. <span data-ttu-id="2a7a7-175">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-175">Select **Apply**.</span></span>

<span data-ttu-id="2a7a7-176">デバイスの一覧でデバイスをフィルター処理した後は、通常と同じ方法でデバイスに対してアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-176">After you've filtered the devices in your device list, you can perform actions on them as you normally would.</span></span> <span data-ttu-id="2a7a7-177">たとえば、それらを選択し、構成を割り当て、設定を編集して (デバイスTeams ミーティングなどです。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-177">For example, you can select them and then assign configurations, edit their settings (if they're Teams Rooms devices), and so on.</span></span> <span data-ttu-id="2a7a7-178">完了したら、[タグ フィルター] エントリの横にある **[X]** を選択するか、一覧の右側にある[すべてクリア] を選択して、フィルターを削除できます。</span><span class="sxs-lookup"><span data-stu-id="2a7a7-178">When you're done, you can remove the filter by selecting the **X**  next to the **Tag** filter entry or by selecting **Clear all** on the right side of the list.</span></span>
