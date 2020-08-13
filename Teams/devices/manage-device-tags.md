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
ms.openlocfilehash: f428a40e5a9adf4a53d4b2e12064b90b4ceebe43
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46657102"
---
# <a name="manage-microsoft-teams-device-tags"></a><span data-ttu-id="1e95a-103">Microsoft Teams のデバイスタグを管理する</span><span class="sxs-lookup"><span data-stu-id="1e95a-103">Manage Microsoft Teams device tags</span></span>

> [!NOTE]
> <span data-ttu-id="1e95a-104">デバイスにタグを追加する機能は、Microsoft Teams ユーザーに対してウェーブで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="1e95a-104">The ability to add tags to devices is being made available to Microsoft Teams customers in waves.</span></span> <span data-ttu-id="1e95a-105">Teams 管理センターでタグを管理するオプションが表示されない場合は、テナントでデバイスタグが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="1e95a-105">If you don't see the option to manage tags in the Teams admin center, device tags haven't been enabled on your tenant yet.</span></span> <span data-ttu-id="1e95a-106">後でもう一度確認してください。</span><span class="sxs-lookup"><span data-stu-id="1e95a-106">Check back again at a later date.</span></span>

<span data-ttu-id="1e95a-107">Microsoft Teams のデバイスタグを使用すると、組織に展開したデバイスのグループ化、整理、管理が簡単に行えるようになります。</span><span class="sxs-lookup"><span data-stu-id="1e95a-107">Device tags in Microsoft Teams let you group, organize, and more easily manage the devices you've deployed in your organization.</span></span> <span data-ttu-id="1e95a-108">Microsoft Teams 管理センターでは、デバイスに1つまたは複数のタグを追加したり、フィルターを使用して、指定したタグと一致するデバイスを表示したり、そのタグを持つデバイスに対して操作を実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-108">With the Microsoft Teams admin center, you can add one or more tags to devices, use filters to view devices that match the tag you specify, and then perform actions the devices that have that tag.</span></span>

<span data-ttu-id="1e95a-109">複数のデバイスの種類にデバイスタグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-109">You can add a device tag to more than one device type.</span></span> <span data-ttu-id="1e95a-110">ただし、管理センターでデバイスウィンドウを開くと、その種類のデバイスだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-110">However, when you open a device pane in the admin center, only the devices of that type are returned.</span></span> <span data-ttu-id="1e95a-111">たとえば、電話と Teams のルームデバイスの両方に "Corporate" タグを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-111">For example, you can assign the "Corporate" tag to both phones and Teams Rooms devices.</span></span> <span data-ttu-id="1e95a-112">**Devices**phone で「Corporate」 (会社) タグを検索すると  >  **Phones**、電話のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-112">If you search for the "Corporate" tag while in **Devices** > **Phones**, only phones are returned.</span></span> <span data-ttu-id="1e95a-113">同様に、 **Devices**Teams ルームで「Corporate」 (会社) タグを検索すると、  >  **Teams Rooms**チームルームのデバイスだけが返されます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-113">Similarly, if you search for the "Corporate" tag in **Devices** > **Teams Rooms**, only Teams Rooms devices are returned.</span></span>

<span data-ttu-id="1e95a-114">デバイスタグを管理するには、グローバル管理者または Teams サービス管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e95a-114">To manage device tags, you need to be either a Global admin or a Teams service admin.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e95a-115">デバイスタグは、デバイスにログインしているリソースアカウントに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-115">Device tags are assigned to the resource account that's logged into a device.</span></span> <span data-ttu-id="1e95a-116">1つのデバイスからリソースアカウントに署名し、それを使って別のデバイスにサインインした場合、デバイスタグが新しいデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-116">If you sign a resource account out of one device and then use it to sign into another devices, the device tags are applied to new device.</span></span>

## <a name="create-remove-or-rename-device-tags"></a><span data-ttu-id="1e95a-117">デバイスタグの作成、削除、名前の変更</span><span class="sxs-lookup"><span data-stu-id="1e95a-117">Create, remove, or rename device tags</span></span>

<span data-ttu-id="1e95a-118">Device tag 管理パネルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-118">Using the device tag management panel, you can:</span></span>

- <span data-ttu-id="1e95a-119">すべてのデバイスタグを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e95a-119">See all your device tags.</span></span>
- <span data-ttu-id="1e95a-120">複数のデバイスタグを簡単に作成して、後でデバイスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-120">Create multiple device tags easily and then assign them to devices at a later time.</span></span> <span data-ttu-id="1e95a-121">タグには最大25文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-121">Tags can be up to 25 characters.</span></span>
- <span data-ttu-id="1e95a-122">不要になったデバイスタグを削除します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-122">Remove device tags that are no longer needed.</span></span> <span data-ttu-id="1e95a-123">デバイスタグを削除するには、そのタグが追加されたすべてのデバイスから削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e95a-123">Before you can remove a device tag, you'll need to remove it from all of the devices it has been added to.</span></span>
- <span data-ttu-id="1e95a-124">デバイスタグの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-124">Rename device tags.</span></span> <span data-ttu-id="1e95a-125">デバイスタグの名前を変更すると、その変更は追加されたすべてのデバイスに反映されます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-125">When you rename a device tag, that change is reflected on all the devices it's been added to.</span></span> <span data-ttu-id="1e95a-126">タグには最大25文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-126">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="1e95a-127">アクセスして、Microsoft Teams 管理センターにサインインします。https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1e95a-127">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="1e95a-128">[**デバイス**] に移動し、[**電話**] など、任意のデバイスウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-128">Navigate to **Devices** and then choose any device pane, such as **Phones**</span></span>
3. <span data-ttu-id="1e95a-129">ページの右上隅にある [**アクション**] を選択し、**すべてのデバイスタグ**を選択する</span><span class="sxs-lookup"><span data-stu-id="1e95a-129">Select **Actions** in the upper-right corner of the page and select **All device tags**</span></span>
4. <span data-ttu-id="1e95a-130">デバイスタグを作成するには、[ **+ 追加**] を選択し、デバイスタグの値を指定して、[**保存**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-130">To create a device tag, select **+ Add**, provide a value for the device tag, and select the **Save** icon</span></span>
5. <span data-ttu-id="1e95a-131">デバイスタグを削除するには、削除するデバイスタグの横にある省略**記号 (.** ..) を選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-131">To remove a device tag, select the ellipsis **...** next to the device tag you want to remove, and select **Delete**</span></span>
    > [!NOTE]
    > <span data-ttu-id="1e95a-132">デバイスに追加されたデバイスタグを削除しようとすると、すべてのデバイスから削除するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-132">If you try to remove a device tag that's been added to devices, you'll receive a message asking if you want to remove it from all devices.</span></span> <span data-ttu-id="1e95a-133">この操作を続行してデバイスタグを削除する場合は、[**デバイス**の削除] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-133">If you want to do this and continue to remove the device tag, select **Untag devices**.</span></span>
6. <span data-ttu-id="1e95a-134">デバイスタグの名前を変更するには、名前を変更するデバイスタグの横に**ある省略記号 (.** ..) を選択し、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-134">To rename a device tag, select the ellipsis **...** next to the device tag you want to rename, and select **Edit**.</span></span> <span data-ttu-id="1e95a-135">Device tag の新しい値を指定して、[**保存**] アイコンを選びます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-135">Provide a new value for the device tag and select the **Save** icon</span></span>

## <a name="add-or-remove-tags-on-a-single-device"></a><span data-ttu-id="1e95a-136">1つのデバイスでタグを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="1e95a-136">Add or remove tags on a single device</span></span>

<span data-ttu-id="1e95a-137">デバイスにタグを追加する場合は、既存のタグを選ぶか、新しいタグを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-137">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="1e95a-138">タグには最大25文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-138">Tags can be up to 25 characters.</span></span>

1. <span data-ttu-id="1e95a-139">アクセスして、Microsoft Teams 管理センターにサインインします。https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1e95a-139">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="1e95a-140">[**デバイス**] に移動し、タグを追加または削除するデバイスが含まれているデバイスウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-140">Navigate to **Devices** and then choose the device pane that contains the device you want to add or remove tags on</span></span>
3. <span data-ttu-id="1e95a-141">タグを追加または削除するデバイスの横にチェックマークを付けて、[**タグの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-141">Place a check mark next to the device you want to add or remove tags on and select **Manage tags**</span></span>
4. <span data-ttu-id="1e95a-142">タグを追加する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1e95a-142">If you want to add a tag:</span></span>
    1. <span data-ttu-id="1e95a-143">追加するタグ名の入力を開始する</span><span class="sxs-lookup"><span data-stu-id="1e95a-143">Start typing the tag name you want to add</span></span>
    2. <span data-ttu-id="1e95a-144">タグが既に存在する場合は、返されるタグの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-144">If the tag already exists, select it from the list of tags that are returned</span></span>
    3. <span data-ttu-id="1e95a-145">タグが存在しない場合は、[ \*\* \<tag name> 新しいタグとして追加]\*\* を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-145">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**.</span></span> <span data-ttu-id="1e95a-146">タグには最大25文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-146">Tags can be up to 25 characters.</span></span>
5. <span data-ttu-id="1e95a-147">タグを削除する場合は、削除するノートシールの横にある [ **X** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-147">If you want to remove a tag, select **X** next to the tag you want to remove</span></span>
6. <span data-ttu-id="1e95a-148">タグを追加または削除する場合は、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-148">Repeat the steps above if you want to add or remove more tags</span></span>
7. <span data-ttu-id="1e95a-149">[**適用**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="1e95a-149">Select **Apply**</span></span>

## <a name="add-or-remove-tags-on-multiple-devices"></a><span data-ttu-id="1e95a-150">複数のデバイスのタグを追加または削除する</span><span class="sxs-lookup"><span data-stu-id="1e95a-150">Add or remove tags on multiple devices</span></span>

<span data-ttu-id="1e95a-151">デバイスにタグを追加する場合は、既存のタグを選ぶか、新しいタグを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-151">When you add tags to a device, you can either select an existing tag or create a new one.</span></span> <span data-ttu-id="1e95a-152">タグには最大25文字まで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-152">Tags can be up to 25 characters.</span></span> <span data-ttu-id="1e95a-153">複数のデバイスからタグを削除する場合は、デバイスに関連付けられている Teams ユーザーを選択し、ユーザーからタグを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e95a-153">If you want to remove a tag from multiple devices, you need to select the Teams user that's associated with the device and remove the tag from the user.</span></span>

1. <span data-ttu-id="1e95a-154">アクセスして、Microsoft Teams 管理センターにサインインします。https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1e95a-154">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="1e95a-155">[**デバイス**] に移動し、タグを追加または削除するデバイスが含まれているデバイスウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-155">Navigate to **Devices** and then choose the device pane that contains the devices you want to add or remove tags on</span></span>
3. <span data-ttu-id="1e95a-156">タグを追加または削除するデバイスの横にチェックマークを付けて、[**タグの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-156">Place a check mark next to the devices you want to add or remove tags on and select **Manage tags**</span></span>
4. <span data-ttu-id="1e95a-157">タグを追加する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1e95a-157">If you want to add a tag:</span></span>
    1. <span data-ttu-id="1e95a-158">追加するタグ名の入力を開始します。 **Teams ユーザーのすべてのデバイスの [タグを管理**します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-158">Start typing the tag name you want to add in **Manage tags for all devices of Teams users**</span></span>
    2. <span data-ttu-id="1e95a-159">タグが既に存在する場合は、返されるタグの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-159">If the tag already exists, select it from the list of tags that are returned</span></span>
    3. <span data-ttu-id="1e95a-160">タグが存在しない場合は、[ \*\* \<tag name> 新しいタグとして追加]\*\* を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-160">If the tag doesn't exist, select **Add "\<tag name>" as a new tag**</span></span>
5. <span data-ttu-id="1e95a-161">タグを削除する場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1e95a-161">If you want to remove a tag:</span></span>
    1. <span data-ttu-id="1e95a-162">**[Teams ユーザーの選択] を**展開する</span><span class="sxs-lookup"><span data-stu-id="1e95a-162">Expand **Select Teams users**</span></span>
    2. <span data-ttu-id="1e95a-163">タグを削除する Teams ユーザーの名前の下にある\*\* \<x> タグ\*\*を展開します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-163">Expand **\<x> tags** under the name of the Teams user you want to remove tags from</span></span>
    3. <span data-ttu-id="1e95a-164">削除するノートシールの横にある [ **X** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-164">Select **X** next to the tag you want to remove</span></span>
6. <span data-ttu-id="1e95a-165">タグを追加または削除する場合は、上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-165">Repeat the steps above if you want to add or remove more tags</span></span>
7. <span data-ttu-id="1e95a-166">[**適用**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="1e95a-166">Select **Apply**</span></span>

## <a name="use-filters-to-return-devices-with-a-specific-tag"></a><span data-ttu-id="1e95a-167">フィルターを使用して特定のタグでデバイスを返す</span><span class="sxs-lookup"><span data-stu-id="1e95a-167">Use filters to return devices with a specific tag</span></span>

<span data-ttu-id="1e95a-168">デバイスにデバイスタグを追加した場合は、デバイスの一覧をフィルター処理して、指定したタグが追加されているデバイスのみを返すようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-168">If you've added device tags to your devices, you can use them to filter the device list to return only the devices that have had a specified tag added to them.</span></span> <span data-ttu-id="1e95a-169">これは、特定の部屋のすべてのデバイス、特定の種類のすべてのデバイス、またはタグの追加時に使用したその他の条件を表示する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="1e95a-169">This can be helpful if you just want to view all the devices in a specific room, all the devices of a certain type, or any other criteria you used when adding your tags.</span></span> <span data-ttu-id="1e95a-170">また、デバイスタグを使用して識別されたデバイスのグループに応じて、複数の設定ポリシーを設定して、返されたデバイスで一括操作を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-170">You can also perform bulk actions on returned devices, such as applying updates in waves, or setting different configuration policies depending on the groups of devices identified using device tags.</span></span>

1. <span data-ttu-id="1e95a-171">アクセスして、Microsoft Teams 管理センターにサインインします。https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1e95a-171">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="1e95a-172">[**デバイス**] に移動し、フィルターを適用するデバイスが含まれているデバイスウィンドウを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-172">Navigate to **Devices** and then choose the device pane that contains the devices you want to filter</span></span>
3. <span data-ttu-id="1e95a-173">**フィルター**アイコンを選択する</span><span class="sxs-lookup"><span data-stu-id="1e95a-173">Select the **Filter** icon</span></span>
4. <span data-ttu-id="1e95a-174">1つのノートシールのみを指定する場合、または指定したすべてのタグを含むデバイスを検索する場合は、[**次の条件をすべて満たす**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-174">If you only want to specify a single tag, or if you want to find devices that have all the tags you specify, select **Match all of these conditions**.</span></span>
5. <span data-ttu-id="1e95a-175">1つ以上のデバイスタグと一致するデバイスを検索する場合は、**次のいずれかの条件に一致**するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-175">If you want to find devices that match one or more device tags, select **Match any one of these conditions**</span></span>
6. <span data-ttu-id="1e95a-176">[**タグ**] フィールドを選択し、[**値の入力**] フィールドにデバイスタグ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-176">Select the **Tag** field and then specify a device tag name in the **Enter a value** field</span></span>
7. <span data-ttu-id="1e95a-177">さらに多くのデバイスタグを追加する場合は、[**追加**] を選択し、追加するノートシールごとに手順6を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1e95a-177">If you want to add more device tags, select **Add more** and repeat step 6 for each tag you want to add</span></span>
8. <span data-ttu-id="1e95a-178">[**適用**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="1e95a-178">Select **Apply**</span></span>

<span data-ttu-id="1e95a-179">デバイスの一覧でデバイスをフィルター処理すると、通常どおりに操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-179">After you've filtered the devices in your device list, you can perform actions on them as you normally would.</span></span> <span data-ttu-id="1e95a-180">たとえば、ユーザーを選択して、構成を割り当てたり、設定を編集したりできます (チームルームデバイスの場合)。</span><span class="sxs-lookup"><span data-stu-id="1e95a-180">For example, you can select them and then assign configurations, edit their settings (if they're Teams Rooms devices), and so on.</span></span> <span data-ttu-id="1e95a-181">完了したら、[**タグ**フィルター] エントリの横にある [ **X** ] を選択するか、リストの右側にある [**すべてクリア**] を選択して、フィルターを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="1e95a-181">When you're done, you can remove the filter by selecting the **X**  next to the **Tag** filter entry or by selecting **Clear all** on the right side of the list.</span></span>
