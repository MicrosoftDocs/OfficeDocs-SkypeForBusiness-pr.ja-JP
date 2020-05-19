---
title: Microsoft Teams でのデバイスの管理
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
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 組織内の Teams で使用されているデバイスを管理する方法について説明します。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366a24706a80f6fe96cc8a3733022cc64f78ba7e
ms.sourcegitcommit: 3ed779277540589eabef745685ab6c67d8a8ff90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44281723"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="b688b-103">Microsoft Teams でのデバイスの管理</span><span class="sxs-lookup"><span data-stu-id="b688b-103">Manage your devices in Microsoft Teams</span></span>

<span data-ttu-id="b688b-104">管理者は、Microsoft Teams 管理センターで、組織内の Teams で使用されているデバイスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b688b-104">As an admin, you can manage devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="b688b-105">組織のデバイスのインベントリを表示して管理できます。また、デバイスの診断の更新、再起動、監視などのタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="b688b-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="b688b-106">構成プロファイルを作成して、1つのデバイスまたはデバイスのグループに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="b688b-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="b688b-107">どのデバイスを管理できますか?</span><span class="sxs-lookup"><span data-stu-id="b688b-107">What devices can you manage?</span></span>
<span data-ttu-id="b688b-108">Teams で認定され、登録されているすべてのデバイスを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b688b-108">You can manage any device that's certified for, and enrolled in, Teams.</span></span> <span data-ttu-id="b688b-109">デバイスは、ユーザーが初めてデバイス上の Teams にサインインしたときに自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="b688b-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="b688b-110">管理可能なデバイスの一覧については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b688b-110">For a list of certified devices that can be managed, see:</span></span>

- [<span data-ttu-id="b688b-111">電話会議</span><span class="sxs-lookup"><span data-stu-id="b688b-111">Conference phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [<span data-ttu-id="b688b-112">卓上電話</span><span class="sxs-lookup"><span data-stu-id="b688b-112">Desk phones</span></span>](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- <span data-ttu-id="b688b-113">コラボレーションバー</span><span class="sxs-lookup"><span data-stu-id="b688b-113">Collaboration bars</span></span>

<span data-ttu-id="b688b-114">デバイスは、 [Microsoft Teams 管理センター](https://admin.teams.microsoft.com)の左側のナビゲーションにある [**デバイス**] に管理されます。</span><span class="sxs-lookup"><span data-stu-id="b688b-114">Devices are managed in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) under **Devices** in the left navigation.</span></span>

> [!NOTE]
> <span data-ttu-id="b688b-115">Microsoft Intune を使用している場合、デバイスは自動的に Intune に登録されます。</span><span class="sxs-lookup"><span data-stu-id="b688b-115">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="b688b-116">デバイスが登録されると、デバイスのコンプライアンスが確認され、条件付きアクセスポリシーがデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b688b-116">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span>

## <a name="manage-phones-and-collaboration-bars-in-teams"></a><span data-ttu-id="b688b-117">Teams で電話とコラボレーションバーを管理する</span><span class="sxs-lookup"><span data-stu-id="b688b-117">Manage phones and collaboration bars in Teams</span></span>

<span data-ttu-id="b688b-118">電話とコラボレーションバーは、Microsoft Teams 管理センターでも同じように管理されますが、[**デバイス**] の左側のナビゲーションにはそれぞれのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="b688b-118">Even though phones and collaboration bars are managed the same in the Microsoft Teams admin center, they have their own respective sections in the left navigation under **Devices**.</span></span> <span data-ttu-id="b688b-119">これにより、各種類のデバイスを個別に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b688b-119">This lets you manage each type of device separately.</span></span>

<span data-ttu-id="b688b-120">ここでは、組織のチームに登録されている携帯電話とコラボレーションバーを表示して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b688b-120">From here, you can view and manage phones and collaboration bars enrolled in Teams in your organization.</span></span> <span data-ttu-id="b688b-121">各デバイスに表示される情報には、デバイス名、製造元、モデル、ユーザー、状態、操作、最後の表示、履歴が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b688b-121">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="b688b-122">目的に合った情報が表示されるように、ビューをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="b688b-122">You can customize the view to show the information that fits your needs.</span></span>

<span data-ttu-id="b688b-123">組織のチームデバイスを管理する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b688b-123">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="b688b-124">操作方法</span><span class="sxs-lookup"><span data-stu-id="b688b-124">To do this...</span></span>  |<span data-ttu-id="b688b-125">操作</span><span class="sxs-lookup"><span data-stu-id="b688b-125">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="b688b-126">デバイスの情報を変更する</span><span class="sxs-lookup"><span data-stu-id="b688b-126">Change device information</span></span>   | <span data-ttu-id="b688b-127">[**編集**] > デバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="b688b-127">Select a device > **Edit**.</span></span> <span data-ttu-id="b688b-128">デバイス名、アセットタグ、メモの追加などの詳細を編集できます。</span><span class="sxs-lookup"><span data-stu-id="b688b-128">You can edit details such as device name, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="b688b-129">ソフトウェアの更新を管理する</span><span class="sxs-lookup"><span data-stu-id="b688b-129">Manage software updates</span></span>   |<span data-ttu-id="b688b-130">**更新**> デバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="b688b-130">Select a device > **Update**.</span></span> <span data-ttu-id="b688b-131">デバイスで利用可能なソフトウェアとファームウェアの更新プログラムの一覧を表示し、インストールする更新プログラムを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="b688b-131">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="b688b-132">デバイスを再起動する</span><span class="sxs-lookup"><span data-stu-id="b688b-132">Restart a device</span></span>   |<span data-ttu-id="b688b-133">デバイスを選択し >**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="b688b-133">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="b688b-134">デバイス履歴の表示</span><span class="sxs-lookup"><span data-stu-id="b688b-134">View device history</span></span>  | <span data-ttu-id="b688b-135">デバイス > の**履歴**を選択します。</span><span class="sxs-lookup"><span data-stu-id="b688b-135">Select a device > **History**.</span></span> <span data-ttu-id="b688b-136">デバイスの更新履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b688b-136">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="b688b-137">診断の表示</span><span class="sxs-lookup"><span data-stu-id="b688b-137">View diagnostics</span></span>  | <span data-ttu-id="b688b-138">**診断**> デバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="b688b-138">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="b688b-139">Teams で構成プロファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="b688b-139">Use configuration profiles in Teams</span></span>

<span data-ttu-id="b688b-140">構成プロファイルを使用して、組織内のチームデバイスの設定と機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="b688b-140">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="b688b-141">構成プロファイルを作成またはアップロードして、有効または無効にする設定や機能を含め、デバイスまたはデバイスのグループにプロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b688b-141">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="b688b-142">構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="b688b-142">Create a configuration profile</span></span>

1. <span data-ttu-id="b688b-143">左側のナビゲーションで、[**デバイス**  >  **構成プロファイル**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b688b-143">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="b688b-144">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b688b-144">Click **Add**.</span></span>
3. <span data-ttu-id="b688b-145">プロファイルの名前を入力し、必要に応じてわかりやすい説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="b688b-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="b688b-146">プロファイルに必要な設定を指定し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b688b-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="b688b-147">構成プロファイルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b688b-147">Assign a configuration profile</span></span>

1. <span data-ttu-id="b688b-148">左側のナビゲーションで、[**デバイス**  >  **構成プロファイル**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b688b-148">In the left navigation, go to **Devices** > **Configuration profiles**.</span></span>
2. <span data-ttu-id="b688b-149">割り当てる**構成プロファイル**を選び、[**デバイスへの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b688b-149">Select the **Configuration profile** you want to assign, and then click **Assign to device**.</span></span>  
3. <span data-ttu-id="b688b-150">[**構成プロファイルへのデバイスの割り当て**] ウィンドウで、割り当てるデバイスを検索して選びます。</span><span class="sxs-lookup"><span data-stu-id="b688b-150">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="b688b-151">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b688b-151">Click **Save**.</span></span>
