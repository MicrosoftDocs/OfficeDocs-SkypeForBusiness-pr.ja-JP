---
title: Microsoft Teams のデバイスタグを管理およびフィルター処理する
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
ms.openlocfilehash: d29bc28de39c8d145914d3bddab4ed949ad0a338
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962898"
---
# <a name="manage-microsoft-teams-device-tags"></a><span data-ttu-id="cda54-103">Microsoft Teams のデバイスタグを管理する</span><span class="sxs-lookup"><span data-stu-id="cda54-103">Manage Microsoft Teams device tags</span></span>

<span data-ttu-id="cda54-104">Microsoft Teams のデバイスタグを使用すると、組織に展開したデバイスのグループ化、整理、管理が簡単に行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="cda54-104">Device tags in Microsoft Teams let you group, organize, and more easily manage the devices you've deployed in your organization.</span></span> <span data-ttu-id="cda54-105">Microsoft Teams 管理センターでは、デバイスに1つまたは複数のタグを追加したり、フィルターを使用して、指定したタグと一致するデバイスを表示したり、そのタグを持つデバイスに対して操作を実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="cda54-105">With the Microsoft Teams admin center, you can add one or more tags to devices, use filters to view devices that match the tag you specify, and then perform actions the devices that have that tag.</span></span>

<span data-ttu-id="cda54-106">複数のデバイスの種類にデバイスタグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="cda54-106">You can add a device tag to more than one device type.</span></span> <span data-ttu-id="cda54-107">ただし、管理センターでデバイスウィンドウを開くと、その種類のデバイスだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="cda54-107">However, when you open a device pane in the admin center, only the devices of that type are returned.</span></span> <span data-ttu-id="cda54-108">たとえば、電話と Teams のルームデバイスの両方に "Corporate" タグを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cda54-108">For example, you can assign the "Corporate" tag to both phones and Teams Rooms devices.</span></span> <span data-ttu-id="cda54-109">**Devices**phone で「Corporate」 (会社) タグを検索すると  >  **Phones**、電話のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="cda54-109">If you search for the "Corporate" tag while in **Devices** > **Phones**, only phones are returned.</span></span> <span data-ttu-id="cda54-110">同様に、 **Devices**Teams ルームで「Corporate」 (会社) タグを検索すると、  >  **Teams Rooms**チームルームのデバイスだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="cda54-110">Similarly, if you search for the "Corporate" tag in **Devices** > **Teams Rooms**, only Teams Rooms devices are returned.</span></span>

<span data-ttu-id="cda54-111">デバイスタグを管理するには、グローバル管理者、Teams サービス管理者、または Teams デバイス管理者である必要があります。管理者ロールの詳細については、「 [Microsoft teams 管理者ロールを使用してチームを管理する](../using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cda54-111">To manage device tags, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cda54-112">デバイスタグは、デバイスにログインしているリソースアカウントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cda54-112">Device tags are assigned to the resource account that's logged into a device.</span></span> <span data-ttu-id="cda54-113">1つのデバイスからリソースアカウントに署名し、それを使って別のデバイスにサインインした場合、デバイスタグが新しいデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cda54-113">If you sign a resource account out of one device and then use it to sign into another devices, the device tags are applied to new device.</span></span>

## <a name="create-remove-or-rename-device-tags"></a><span data-ttu-id="cda54-114">デバイスタグの作成、削除、名前の変更</span><span class="sxs-lookup"><span data-stu-id="cda54-114">Create, remove, or rename device tags</span></span>

<span data-ttu-id="cda54-115">Device tag 管理パネルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="cda54-115">Using the device tag management panel, you can:</span></span>

- <span data-ttu-id="cda54-116">すべてのデバイスタグを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cda54-116">See all your device tags.</span></span>
- <span data-ttu-id="cda54-117">複数のデバイスタグを簡単に作成して、後でデバイスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cda54-117">Create multiple device tags easily and then assign them to devices at a later time.</span></span> <span data-ttu-id="cda54-118">タグには最大25文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cda54-118">Tags can be up to 25 characters.</span></span>
- <span data-ttu-id="cda54-119">不要になったデバイスタグを削除します。</span><span class="sxs-lookup"><span data-stu-id="cda54-119">Remove device tags that are no longer needed.</span></span> <span data-ttu-id="cda54-120">デバイスタグを削除するには、そのタグが追加されたすべてのデバイスから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cda54-120">Before you can remove a device tag, you'll need to remove it from all of the devices it has been added to.</span></span>
- <span data-ttu-id="cda54-121">デバイスタグの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="cda54-121">Rename device tags.</span></span> <span data-ttu-id="cda54-122">デバイスタグの名前を変更すると、その変更は追加されたすべてのデバイスに反映されます。</span><span class="sxs-lookup"><span data-stu-id="cda54-122">When you rename a device tag, that change is reflected on all the devices it's been added to.</span></span> <span data-ttu-id="cda54-123">タグには最大25文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cda54-123">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="cda54-124">にアクセスして、Microsoft Teams 管理センターにサインイン https://admin.teams.microsoft.com します。</span><span class="sxs-lookup"><span data-stu-id="cda54-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="cda54-125">[ **デバイス** ] に移動し、[ **電話**] など、任意のデバイスウィンドウを選びます。</span><span class="sxs-lookup"><span data-stu-id="cda54-125">Navigate to **Devices** and then choose any device pane, such as **Phones**.</span></span>
3. <span data-ttu-id="cda54-126">ページの右上隅にある [ **アクション** ] を選択し、[ **すべてのデバイスタグ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-126">Select **Actions** in the upper-right corner of the page and select **All device tags**.</span></span>
4. <span data-ttu-id="cda54-127">デバイスタグを作成するには、[ **+ 追加**] を選択し、デバイスタグの値を指定して、[ **保存** ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-127">To create a device tag, select **+ Add**, provide a value for the device tag, and select the **Save** icon.</span></span>
5. <span data-ttu-id="cda54-128">デバイスタグを削除するには、削除するデバイスタグの横にある省略 **記号 (.** ..) を選択し、[ **削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-128">To remove a device tag, select the ellipsis **...** next to the device tag you want to remove, and select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="cda54-129">デバイスに追加されたデバイスタグを削除しようとすると、すべてのデバイスから削除するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cda54-129">If you try to remove a device tag that's been added to devices, you'll receive a message asking if you want to remove it from all devices.</span></span> <span data-ttu-id="cda54-130">この操作を続行してデバイスタグを削除する場合は、[ **デバイス**の削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-130">If you want to do this and continue to remove the device tag, select **Untag devices**.</span></span>
6. <span data-ttu-id="cda54-131">デバイスタグの名前を変更するには、名前を変更するデバイスタグの横に **ある省略記号 (.** ..) を選択し、[ **編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-131">To rename a device tag, select the ellipsis **...** next to the device tag you want to rename, and select **Edit**.</span></span> <span data-ttu-id="cda54-132">Device tag の新しい値を入力して、[ **保存** ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-132">Provide a new value for the device tag and select the **Save** icon.</span></span>

## <a name="add-or-remove-tags-on-a-single-device"></a><span data-ttu-id="cda54-133">1つのデバイスでタグを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="cda54-133">Add or remove tags on a single device</span></span>

<span data-ttu-id="cda54-134">デバイスにタグを追加する場合は、既存のタグを選ぶか、新しいタグを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="cda54-134">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="cda54-135">タグには最大25文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cda54-135">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="cda54-136">にアクセスして、Microsoft Teams 管理センターにサインイン https://admin.teams.microsoft.com します。</span><span class="sxs-lookup"><span data-stu-id="cda54-136">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="cda54-137">[ **デバイス** ] に移動して、タグを追加または削除するデバイスが含まれているデバイスウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-137">Navigate to **Devices** and then choose the device pane that contains the device you want to add or remove tags on.</span></span>
3. <span data-ttu-id="cda54-138">タグを追加または削除するデバイスの横にチェックマークを付けて、[ **タグの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-138">Place a check mark next to the device you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="cda54-139">タグを追加する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cda54-139">If you want to add a tag:</span></span>
    1. <span data-ttu-id="cda54-140">追加するタグ名の入力を開始します。</span><span class="sxs-lookup"><span data-stu-id="cda54-140">Start typing the tag name you want to add.</span></span>
    2. <span data-ttu-id="cda54-141">タグが既に存在する場合は、返されるタグの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-141">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="cda54-142">タグが存在しない場合は、[ \*\* \<tag name> 新しいタグとして追加]\*\* を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-142">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span> <span data-ttu-id="cda54-143">タグには最大25文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cda54-143">Tags can be up to 25 characters.</span></span>
5. <span data-ttu-id="cda54-144">タグを削除する場合は、削除するノートシールの横にある [ **X** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-144">If you want to remove a tag, select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="cda54-145">タグを追加または削除する場合は、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cda54-145">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="cda54-146">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-146">Select **Apply**.</span></span>

## <a name="add-or-remove-tags-on-multiple-devices"></a><span data-ttu-id="cda54-147">複数のデバイスのタグを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="cda54-147">Add or remove tags on multiple devices</span></span>

<span data-ttu-id="cda54-148">デバイスにタグを追加する場合は、既存のタグを選ぶか、新しいタグを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="cda54-148">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="cda54-149">タグには最大25文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="cda54-149">Tags can be up to 25 characters.</span></span> <span data-ttu-id="cda54-150">複数のデバイスからタグを削除する場合は、デバイスに関連付けられている Teams ユーザーを選択し、ユーザーからタグを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cda54-150">If you want to remove a tag from multiple devices, you need to select the Teams user that's associated with the device and remove the tag from the user.</span></span>

1. <span data-ttu-id="cda54-151">にアクセスして、Microsoft Teams 管理センターにサインイン https://admin.teams.microsoft.com します。</span><span class="sxs-lookup"><span data-stu-id="cda54-151">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="cda54-152">[ **デバイス** ] に移動して、タグを追加または削除するデバイスが含まれているデバイスウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-152">Navigate to **Devices** and then choose the device pane that contains the devices you want to add or remove tags on.</span></span>
3. <span data-ttu-id="cda54-153">タグを追加または削除するデバイスの横にチェックマークを付けて、[ **タグの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-153">Place a check mark next to the devices you want to add or remove tags on and select **Manage tags**.</span></span>
4. <span data-ttu-id="cda54-154">タグを追加する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cda54-154">If you want to add a tag:</span></span>
    1. <span data-ttu-id="cda54-155">追加するタグ名の入力を開始します。これにより、 **Teams ユーザーのすべてのデバイスの [タグの管理を管理**することができます。</span><span class="sxs-lookup"><span data-stu-id="cda54-155">Start typing the tag name you want to add in **Manage tags for all devices of Teams users**.</span></span>
    2. <span data-ttu-id="cda54-156">タグが既に存在する場合は、返されるタグの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-156">If the tag already exists, select it from the list of tags that are returned.</span></span>
    3. <span data-ttu-id="cda54-157">タグが存在しない場合は、[ \*\* \<tag name> 新しいタグとして追加]\*\* を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-157">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span>
5. <span data-ttu-id="cda54-158">タグを削除する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="cda54-158">If you want to remove a tag:</span></span>
    1. <span data-ttu-id="cda54-159">**[Teams ユーザーの選択] を**展開します。</span><span class="sxs-lookup"><span data-stu-id="cda54-159">Expand **Select Teams users**.</span></span>
    2. <span data-ttu-id="cda54-160">タグを削除するチームユーザーの名前の下にある\*\* \<x> タグ\*\*を展開します。</span><span class="sxs-lookup"><span data-stu-id="cda54-160">Expand **\<x> tags** under the name of the Teams user you want to remove tags from.</span></span>
    3. <span data-ttu-id="cda54-161">削除するノートシールの横にある [ **X** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-161">Select **X** next to the tag you want to remove.</span></span>
6. <span data-ttu-id="cda54-162">タグを追加または削除する場合は、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cda54-162">Repeat the steps above if you want to add or remove more tags.</span></span>
7. <span data-ttu-id="cda54-163">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-163">Select **Apply**.</span></span>

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a><span data-ttu-id="cda54-164">フィルターを使用して特定のタグでデバイスを返す</span><span class="sxs-lookup"><span data-stu-id="cda54-164">Use filters to return devices with a specific tag</span></span>

<span data-ttu-id="cda54-165">デバイスにデバイスタグを追加した場合は、デバイスの一覧をフィルター処理して、指定したタグが追加されているデバイスのみを返すようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cda54-165">If you've added device tags to your devices, you can use them to filter the device list to return only the devices that have had a specified tag added to them.</span></span> <span data-ttu-id="cda54-166">これは、特定の部屋のすべてのデバイス、特定の種類のすべてのデバイス、またはタグの追加時に使用したその他の条件を表示する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="cda54-166">This can be helpful if you just want to view all the devices in a specific room, all the devices of a certain type, or any other criteria you used when adding your tags.</span></span> <span data-ttu-id="cda54-167">また、デバイスタグを使用して識別されたデバイスのグループに応じて、複数の設定ポリシーを設定して、返されたデバイスで一括操作を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="cda54-167">You can also perform bulk actions on returned devices, such as applying updates in waves, or setting different configuration policies depending on the groups of devices identified using device tags.</span></span>

1. <span data-ttu-id="cda54-168">にアクセスして、Microsoft Teams 管理センターにサインイン https://admin.teams.microsoft.com します。</span><span class="sxs-lookup"><span data-stu-id="cda54-168">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="cda54-169">[ **デバイス** ] に移動し、フィルターを適用するデバイスが含まれているデバイスウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-169">Navigate to **Devices** and then choose the device pane that contains the devices you want to filter.</span></span>
3. <span data-ttu-id="cda54-170">[ **フィルター** ] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-170">Select the **Filter** icon.</span></span>
4. <span data-ttu-id="cda54-171">1つのノートシールのみを指定する場合、または指定したすべてのタグを含むデバイスを検索する場合は、[ **次の条件をすべて満たす**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cda54-171">If you only want to specify a single tag, or if you want to find devices that have all the tags you specify, select **Match all of these conditions**.</span></span>
5. <span data-ttu-id="cda54-172">1つ以上のデバイスタグと一致するデバイスを検索する場合は、 **次のいずれかの条件に一致**するものを選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-172">If you want to find devices that match one or more device tags, select **Match any one of these conditions**.</span></span>
6. <span data-ttu-id="cda54-173">[ **タグ** ] フィールドを選択し、[ **値の入力** ] フィールドにデバイスタグ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="cda54-173">Select the **Tag** field and then specify a device tag name in the **Enter a value** field.</span></span>
7. <span data-ttu-id="cda54-174">さらに多くのデバイスタグを追加する場合は、[ **追加** ] を選択し、追加するノートシールごとに手順6を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cda54-174">If you want to add more device tags, select **Add more** and repeat step 6 for each tag you want to add.</span></span>
8. <span data-ttu-id="cda54-175">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cda54-175">Select **Apply**.</span></span>

<span data-ttu-id="cda54-176">デバイスの一覧でデバイスをフィルター処理すると、通常どおりに操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="cda54-176">After you've filtered the devices in your device list, you can perform actions on them as you normally would.</span></span> <span data-ttu-id="cda54-177">たとえば、ユーザーを選択して、構成を割り当てたり、設定を編集したりできます (チームルームデバイスの場合)。</span><span class="sxs-lookup"><span data-stu-id="cda54-177">For example, you can select them and then assign configurations, edit their settings (if they're Teams Rooms devices), and so on.</span></span> <span data-ttu-id="cda54-178">完了したら、[**タグ**フィルター] エントリの横にある [ **X** ] を選択するか、リストの右側にある [**すべてクリア**] を選択して、フィルターを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="cda54-178">When you're done, you can remove the filter by selecting the **X**  next to the **Tag** filter entry or by selecting **Clear all** on the right side of the list.</span></span>
