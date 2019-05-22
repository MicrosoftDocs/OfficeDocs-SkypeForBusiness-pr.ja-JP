---
title: Microsoft Teams でのデバイスを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1keywords:
- ms.teamsadmincenter.devicemanagement.overview
- ms.teamsadmincenter.managedevices.overview
description: 組織内の Teams で使用されているデバイスを管理する方法について説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76692714bbf58dca7bd74461bed4da34abf55c58
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344642"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="eb7ca-103">Microsoft Teams でのデバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="eb7ca-103">Manage your devices in Microsoft Teams</span></span>

::: zone target="docs"
<span data-ttu-id="eb7ca-104">管理者は、Microsoft Teams & Skype for Business 管理センターで、組織内の Teams で使用されているすべてのデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="eb7ca-105">組織のデバイスのインベントリを表示して管理できます。また、デバイスの診断の更新、再起動、監視などのタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="eb7ca-106">構成プロファイルを作成して、1つのデバイスまたはデバイスのグループに割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="eb7ca-107">どのデバイスを管理できますか?</span><span class="sxs-lookup"><span data-stu-id="eb7ca-107">What devices can you manage?</span></span>
<span data-ttu-id="eb7ca-108">チームに対して認定され、チームに登録されているデバイス。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="eb7ca-109">デバイスは、ユーザーが初めてデバイス上の Teams にサインインしたときに自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="eb7ca-110">管理可能なデバイスの一覧については、「[会議電話](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16)と[卓上電話](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span></span>

> [!NOTE]
> <span data-ttu-id="eb7ca-111">Microsoft Intune を使用している場合、デバイスは自動的に Intune に登録されます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="eb7ca-112">デバイスが登録されると、デバイスのコンプライアンスが確認され、条件付きアクセスポリシーがデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="eb7ca-113">Teams でデバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="eb7ca-113">Manage devices in Teams</span></span>

<span data-ttu-id="eb7ca-114">![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン</span><span class="sxs-lookup"><span data-stu-id="eb7ca-114">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="eb7ca-115">左側のナビゲーションで、[**デバイス** > の**管理**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="eb7ca-116">[**すべてのデバイス**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-116">Select **All devices**.</span></span>  

::: zone-end

 <span data-ttu-id="eb7ca-117">ここでは、組織内の Teams に登録されているすべてのデバイスを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="eb7ca-118">各デバイスに表示される情報には、デバイス名、製造元、モデル、ユーザー、状態、操作、最後の表示、履歴が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="eb7ca-119">目的に合った情報が表示されるように、ビューをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="eb7ca-120">組織のチームデバイスを管理する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="eb7ca-121">操作方法</span><span class="sxs-lookup"><span data-stu-id="eb7ca-121">To do this...</span></span>  |<span data-ttu-id="eb7ca-122">操作</span><span class="sxs-lookup"><span data-stu-id="eb7ca-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="eb7ca-123">デバイスの情報を変更する</span><span class="sxs-lookup"><span data-stu-id="eb7ca-123">Change device information</span></span>   | <span data-ttu-id="eb7ca-124">デバイス >**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-124">Select a device > **Edit**.</span></span> <span data-ttu-id="eb7ca-125">デバイス名、ユーザー情報、資産タグ、メモの追加などの詳細を編集できます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="eb7ca-126">ソフトウェアの更新を管理する</span><span class="sxs-lookup"><span data-stu-id="eb7ca-126">Manage software updates</span></span>   |<span data-ttu-id="eb7ca-127">デバイス > の**更新プログラム**を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-127">Select a device > **Update**.</span></span> <span data-ttu-id="eb7ca-128">デバイスで利用可能なソフトウェアとファームウェアの更新プログラムの一覧を表示し、インストールする更新プログラムを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="eb7ca-129">デバイスを再起動する</span><span class="sxs-lookup"><span data-stu-id="eb7ca-129">Restart a device</span></span>   |<span data-ttu-id="eb7ca-130">デバイス > を選択して**再起動**します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="eb7ca-131">デバイス履歴の表示</span><span class="sxs-lookup"><span data-stu-id="eb7ca-131">View device history</span></span>  | <span data-ttu-id="eb7ca-132">デバイスの >**履歴**を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-132">Select a device > **History**.</span></span> <span data-ttu-id="eb7ca-133">デバイスの更新履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="eb7ca-134">診断の表示</span><span class="sxs-lookup"><span data-stu-id="eb7ca-134">View diagnostics</span></span>  | <span data-ttu-id="eb7ca-135">デバイス >**診断**を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="eb7ca-136">Teams で構成プロファイルを使用する</span><span class="sxs-lookup"><span data-stu-id="eb7ca-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="eb7ca-137">構成プロファイルを使用して、組織内のチームデバイスの設定と機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="eb7ca-138">構成プロファイルを作成またはアップロードして、有効または無効にする設定や機能を含め、デバイスまたはデバイスのグループにプロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="eb7ca-139">構成プロファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="eb7ca-139">Create a configuration profile</span></span>

::: zone target="docs"

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) <span data-ttu-id="eb7ca-141">Microsoft Teams & Skype for Business 管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="eb7ca-141">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="eb7ca-142">左側のナビゲーションで、[**デバイス** > の**管理**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-142">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="eb7ca-143">[**構成プロファイル**] を選択し、[**新しい構成プロファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-143">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="eb7ca-144">プロファイルの名前を入力し、必要に応じてわかりやすい説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-144">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="eb7ca-145">プロファイルに必要な設定を指定し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-145">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="eb7ca-146">構成プロファイルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="eb7ca-146">Assign a configuration profile</span></span>

::: zone target="docs"

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) <span data-ttu-id="eb7ca-148">Microsoft Teams & Skype for Business 管理センターを使用する</span><span class="sxs-lookup"><span data-stu-id="eb7ca-148">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="eb7ca-149">左側のナビゲーションで、[**デバイス** > の**管理**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-149">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>

::: zone-end

2. <span data-ttu-id="eb7ca-150">[**構成プロファイル**] を選び、割り当てるプロファイルの [**担当**者] でリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-150">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="eb7ca-151">[**構成プロファイルへのデバイスの割り当て**] ウィンドウで、割り当てるデバイスを検索して選びます。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-151">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="eb7ca-152">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb7ca-152">Click **Save**.</span></span>
