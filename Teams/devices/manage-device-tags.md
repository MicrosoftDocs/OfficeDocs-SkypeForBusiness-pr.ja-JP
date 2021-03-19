---
title: Microsoft Teams デバイス タグを管理およびフィルター処理する
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
description: Microsoft Teams デバイスでタグを管理およびフィルター処理する方法について説明します。
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
# <a name="manage-microsoft-teams-device-tags"></a><span data-ttu-id="63751-103">Microsoft Teams デバイス タグを管理する</span><span class="sxs-lookup"><span data-stu-id="63751-103">Manage Microsoft Teams device tags</span></span>

<span data-ttu-id="63751-104">Microsoft Teams のデバイス タグを使用すると、組織に展開したデバイスのグループ化、整理、管理を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="63751-104">Device tags in Microsoft Teams let you group, organize, and more easily manage the devices you've deployed in your organization.</span></span> <span data-ttu-id="63751-105">Microsoft Teams 管理センターでは、1 つ以上のタグをデバイスに追加し、フィルターを使用して指定したタグに一致するデバイスを表示し、そのタグを持つデバイスに対してアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="63751-105">With the Microsoft Teams admin center, you can add one or more tags to devices, use filters to view devices that match the tag you specify, and then perform actions on the devices that have that tag.</span></span>

<span data-ttu-id="63751-106">複数の種類のデバイスにデバイス タグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="63751-106">You can add a device tag to more than one device type.</span></span> <span data-ttu-id="63751-107">ただし、管理センターでデバイス ウィンドウを開いた場合は、その種類のデバイスだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="63751-107">However, when you open a device pane in the admin center, only the devices of that type are returned.</span></span> <span data-ttu-id="63751-108">たとえば、電話機と Teams Rooms デバイスの両方に "Corporate" タグを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="63751-108">For example, you can assign the "Corporate" tag to both phones and Teams Rooms devices.</span></span> <span data-ttu-id="63751-109">デバイスの電話で "企業" タグを検索すると、電話  >  だけが返されます。</span><span class="sxs-lookup"><span data-stu-id="63751-109">If you search for the "Corporate" tag while in **Devices** > **Phones**, only phones are returned.</span></span> <span data-ttu-id="63751-110">同様に、Devices Teams Rooms で "Corporate" タグを検索すると  >  、Teams Rooms デバイスだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="63751-110">Similarly, if you search for the "Corporate" tag in **Devices** > **Teams Rooms**, only Teams Rooms devices are returned.</span></span>

<span data-ttu-id="63751-111">デバイス タグを管理するには、グローバル管理者、Teams サービス管理者、または Teams デバイス管理者である必要があります。管理者ロールの詳細については、「Microsoft Teams 管理者ロールを使用して Teams を管理 [する」を参照してください](../using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="63751-111">To manage device tags, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63751-112">デバイス タグは、デバイスにログインしているリソース アカウントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="63751-112">Device tags are assigned to the resource account that's logged into a device.</span></span> <span data-ttu-id="63751-113">あるデバイスからリソース アカウントをサインアウトし、それを使用して別のデバイスにサインインすると、デバイス タグが新しいデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="63751-113">If you sign a resource account out of one device and then use it to sign in to another device, the device tags are applied to the new device.</span></span>

## <a name="create-remove-or-rename-device-tags"></a><span data-ttu-id="63751-114">デバイス タグを作成、削除、または名前変更する</span><span class="sxs-lookup"><span data-stu-id="63751-114">Create, remove, or rename device tags</span></span>

<span data-ttu-id="63751-115">デバイス のタグ管理パネルを使用すると、次の操作を行えます。</span><span class="sxs-lookup"><span data-stu-id="63751-115">Using the device tag management panel, you can:</span></span>

- <span data-ttu-id="63751-116">すべてのデバイス タグを表示します。</span><span class="sxs-lookup"><span data-stu-id="63751-116">See all your device tags.</span></span>
- <span data-ttu-id="63751-117">複数のデバイス タグを簡単に作成し、後でデバイスに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="63751-117">Create multiple device tags easily and then assign them to devices at a later time.</span></span> <span data-ttu-id="63751-118">タグは最大 25 文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="63751-118">Tags can be up to 25 characters.</span></span>
- <span data-ttu-id="63751-119">不要になったデバイス タグを削除します。</span><span class="sxs-lookup"><span data-stu-id="63751-119">Remove device tags that are no longer needed.</span></span> <span data-ttu-id="63751-120">デバイス タグを削除する前に、追加されているすべてのデバイスからデバイス タグを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63751-120">Before you can remove a device tag, you'll need to remove it from all of the devices it has been added to.</span></span>
- <span data-ttu-id="63751-121">デバイス タグの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="63751-121">Rename device tags.</span></span> <span data-ttu-id="63751-122">デバイス タグの名前を変更すると、その変更は追加されたデバイスすべてに反映されます。</span><span class="sxs-lookup"><span data-stu-id="63751-122">When you rename a device tag, that change is reflected on all the devices it's been added to.</span></span> <span data-ttu-id="63751-123">タグは最大 25 文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="63751-123">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="63751-124">Microsoft Teams 管理センターにアクセスしてサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="63751-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="63751-125">[デバイス **] に移動** し、[電話] などの任意のデバイス ウィンドウ **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="63751-125">Navigate to **Devices** and then choose any device pane, such as **Phones**.</span></span>
3. <span data-ttu-id="63751-126">ページ **の右上隅** にある [アクション] を選択し、[すべてのデバイス タグ **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="63751-126">Select **Actions** in the upper-right corner of the page and select **All device tags**.</span></span>
4. <span data-ttu-id="63751-127">デバイス タグを作成するには、[+ **追加**] を選択し、デバイス タグの値を指定して、[保存] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="63751-127">To create a device tag, select **+ Add**, provide a value for the device tag, and select the **Save** icon.</span></span>
5. <span data-ttu-id="63751-128">デバイス タグを削除するには、削除するデバイス タグの横にある省略記号 **[...]** を選択し、[削除] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="63751-128">To remove a device tag, select the ellipsis **...** next to the device tag you want to remove, and select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="63751-129">デバイスに追加されたデバイス タグを削除しようとして、すべてのデバイスから削除する必要があるというメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63751-129">If you try to remove a device tag that's been added to devices, you'll receive a message asking if you want to remove it from all devices.</span></span> <span data-ttu-id="63751-130">この操作を行い、デバイス タグの削除を続ける場合は、[デバイスのタグ解除 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="63751-130">If you want to do this and continue to remove the device tag, select **Untag devices**.</span></span>
6. <span data-ttu-id="63751-131">デバイス タグの名前を変更するには、名前を変更するデバイス タグの横にある省略記号 **[...]** を選択し、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="63751-131">To rename a device tag, select the ellipsis **...** next to the device tag you want to rename, and select **Edit**.</span></span> <span data-ttu-id="63751-132">デバイス タグに新しい値を入力し、[保存] アイコン **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="63751-132">Provide a new value for the device tag and select the **Save** icon.</span></span>

## <a name="add-or-remove-tags-on-a-single-device"></a><span data-ttu-id="63751-133">1 台のデバイスでタグを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="63751-133">Add or remove tags on a single device</span></span>

<span data-ttu-id="63751-134">デバイスにタグを追加する場合は、既存のタグを選択するか、新しいタグを作成できます。</span><span class="sxs-lookup"><span data-stu-id="63751-134">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="63751-135">タグは最大 25 文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="63751-135">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="63751-136">Microsoft Teams 管理センターにアクセスしてサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="63751-136">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="63751-137">[デバイス **] に** 移動し、タグを追加または削除するデバイスを含むデバイス ウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="63751-137">Navigate to **Devices** and then choose the device pane that contains the device you want to add or remove tags on.</span></span>
3. <span data-ttu-id="63751-138">タグを追加または削除するデバイスの横にチェック マークを付け、[タグの管理] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="63751-138">Place a check mark next to the device you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="63751-139">タグを追加する場合:</span><span class="sxs-lookup"><span data-stu-id="63751-139">If you want to add a tag:</span></span>
    1. <span data-ttu-id="63751-140">追加するタグ名の入力を開始します。</span><span class="sxs-lookup"><span data-stu-id="63751-140">Start typing the tag name you want to add.</span></span>
    2. <span data-ttu-id="63751-141">タグが既に存在する場合は、返されるタグの一覧からタグを選択します。</span><span class="sxs-lookup"><span data-stu-id="63751-141">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="63751-142">タグが存在しない場合は、新しいタグ **として [追加] \<tag name> を選択します**。</span><span class="sxs-lookup"><span data-stu-id="63751-142">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span> <span data-ttu-id="63751-143">タグは最大 25 文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="63751-143">Tags can be up to 25 characters.</span></span>
5. <span data-ttu-id="63751-144">タグを削除する場合は、削除するタグの横にある **[X]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63751-144">If you want to remove a tag, select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="63751-145">他のタグを追加または削除する場合は、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63751-145">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="63751-146">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63751-146">Select **Apply**.</span></span>

## <a name="add-or-remove-tags-on-multiple-devices"></a><span data-ttu-id="63751-147">複数のデバイスでタグを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="63751-147">Add or remove tags on multiple devices</span></span>

<span data-ttu-id="63751-148">デバイスにタグを追加する場合は、既存のタグを選択するか、新しいタグを作成できます。</span><span class="sxs-lookup"><span data-stu-id="63751-148">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="63751-149">タグは最大 25 文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="63751-149">Tags can be up to 25 characters.</span></span> <span data-ttu-id="63751-150">複数のデバイスからタグを削除する場合は、デバイスに関連付けられている Teams ユーザーを選択し、そのユーザーからタグを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63751-150">If you want to remove a tag from multiple devices, you need to select the Teams user that's associated with the device and remove the tag from the user.</span></span>

1. <span data-ttu-id="63751-151">Microsoft Teams 管理センターにアクセスしてサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="63751-151">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="63751-152">[デバイス **] に** 移動し、タグを追加または削除するデバイスを含むデバイス ウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="63751-152">Navigate to **Devices** and then choose the device pane that contains the devices you want to add or remove tags on.</span></span>
3. <span data-ttu-id="63751-153">タグを追加または削除するデバイスの横にチェック マークを付け、[タグの管理] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="63751-153">Place a check mark next to the devices you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="63751-154">タグを追加する場合:</span><span class="sxs-lookup"><span data-stu-id="63751-154">If you want to add a tag:</span></span>
    1. <span data-ttu-id="63751-155">Teams ユーザーのすべてのデバイスの [タグの管理] に追加するタグ **名の入力を開始します**。</span><span class="sxs-lookup"><span data-stu-id="63751-155">Start typing the tag name you want to add in **Manage tags for all devices of Teams users**.</span></span>
    2. <span data-ttu-id="63751-156">タグが既に存在する場合は、返されるタグの一覧からタグを選択します。</span><span class="sxs-lookup"><span data-stu-id="63751-156">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="63751-157">タグが存在しない場合は、新しいタグ **として [追加] \<tag name> を選択します**。</span><span class="sxs-lookup"><span data-stu-id="63751-157">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span>
5. <span data-ttu-id="63751-158">タグを削除する場合:</span><span class="sxs-lookup"><span data-stu-id="63751-158">If you want to remove a tag:</span></span>
    1. <span data-ttu-id="63751-159">[Teams **ユーザーの選択] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="63751-159">Expand **Select Teams users**.</span></span>
    2. <span data-ttu-id="63751-160">タグ **\<x> を** 削除する Teams ユーザーの名前の下にあるタグを展開します。</span><span class="sxs-lookup"><span data-stu-id="63751-160">Expand **\<x> tags** under the name of the Teams user you want to remove tags from.</span></span>
    3. <span data-ttu-id="63751-161">削除 **するタグ** の横にある [X] を選択します。</span><span class="sxs-lookup"><span data-stu-id="63751-161">Select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="63751-162">他のタグを追加または削除する場合は、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63751-162">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="63751-163">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63751-163">Select **Apply**.</span></span>

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a><span data-ttu-id="63751-164">フィルターを使用して特定のタグを持つデバイスを返す</span><span class="sxs-lookup"><span data-stu-id="63751-164">Use filters to return devices with a specific tag</span></span>

<span data-ttu-id="63751-165">デバイスにデバイス タグを追加した場合は、それらを使用してデバイス一覧をフィルター処理し、指定したタグが追加されたデバイスのみを返します。</span><span class="sxs-lookup"><span data-stu-id="63751-165">If you've added device tags to your devices, you can use them to filter the device list to return only the devices that have had a specified tag added to them.</span></span> <span data-ttu-id="63751-166">これは、特定の部屋のすべてのデバイス、特定の種類のすべてのデバイス、またはタグを追加するときに使用したその他の条件を表示するだけの場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="63751-166">This can be helpful if you just want to view all the devices in a specific room, all the devices of a certain type, or any other criteria you used when adding your tags.</span></span> <span data-ttu-id="63751-167">また、ウェーブで更新プログラムを適用したり、デバイス タグを使用して識別されたデバイスのグループに応じて異なる構成ポリシーを設定したりなど、返されたデバイスに対して一括アクションを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="63751-167">You can also perform bulk actions on returned devices, such as applying updates in waves, or setting different configuration policies depending on the groups of devices identified using device tags.</span></span>

1. <span data-ttu-id="63751-168">Microsoft Teams 管理センターにアクセスしてサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="63751-168">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="63751-169">[デバイス **] に** 移動し、フィルター処理するデバイスを含むデバイス ウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="63751-169">Navigate to **Devices** and then choose the device pane that contains the devices you want to filter.</span></span>
3. <span data-ttu-id="63751-170">[フィルター] **アイコンを選択** します。</span><span class="sxs-lookup"><span data-stu-id="63751-170">Select the **Filter** icon.</span></span>
4. <span data-ttu-id="63751-171">1 つのタグのみを指定する場合、または指定したタグが設定されているデバイスを検索する場合は、[これらの条件すべて一致] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="63751-171">If you only want to specify a single tag, or if you want to find devices that have all the tags you specify, select **Match all of these conditions**.</span></span>
5. <span data-ttu-id="63751-172">1 つ以上のデバイス タグに一致するデバイスを検索する場合は、[次のいずれかの条件に一致 **する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="63751-172">If you want to find devices that match one or more device tags, select **Match any one of these conditions**.</span></span>
6. <span data-ttu-id="63751-173">[タグ **] フィールド** を選択し、[値の入力] フィールドにデバイス タグ **名を指定** します。</span><span class="sxs-lookup"><span data-stu-id="63751-173">Select the **Tag** field and then specify a device tag name in the **Enter a value** field.</span></span>
7. <span data-ttu-id="63751-174">デバイス タグを追加する場合は、[追加] を選択し、追加するタグごとに手順 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="63751-174">If you want to add more device tags, select **Add more** and repeat step 6 for each tag you want to add.</span></span>
8. <span data-ttu-id="63751-175">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="63751-175">Select **Apply**.</span></span>

<span data-ttu-id="63751-176">デバイス一覧でデバイスをフィルター処理した後は、通常と同じ方法でデバイスに対してアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="63751-176">After you've filtered the devices in your device list, you can perform actions on them as you normally would.</span></span> <span data-ttu-id="63751-177">たとえば、それらを選び、構成を割り当て、設定を編集できます (Teams Rooms デバイスの場合)。</span><span class="sxs-lookup"><span data-stu-id="63751-177">For example, you can select them and then assign configurations, edit their settings (if they're Teams Rooms devices), and so on.</span></span> <span data-ttu-id="63751-178">完了したら、タグ フィルター エントリの横にある **[X]** を選択するか、リストの右側の [すべてクリア] を選択して、フィルターを削除できます。</span><span class="sxs-lookup"><span data-stu-id="63751-178">When you're done, you can remove the filter by selecting the **X**  next to the **Tag** filter entry or by selecting **Clear all** on the right side of the list.</span></span>
