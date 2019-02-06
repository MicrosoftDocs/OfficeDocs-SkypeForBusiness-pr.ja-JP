---
title: Microsoft Teams でのデバイスを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: kelsawi
f1keywords: ms.teamsadmincenter.devicemanagement.overview
description: 組織のチームと共同で使用するデバイスを管理する方法について説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb306930b4adca9c50e46ad1515324bbac2a2e2d
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754196"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="be51f-103">Microsoft Teams でのデバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="be51f-103">Manage your devices in Microsoft Teams</span></span>

 <span data-ttu-id="be51f-104">管理者としては、マイクロソフトのチームの管理センターから、組織のチームで使用されるすべてのデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="be51f-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams admin center.</span></span> <span data-ttu-id="be51f-105">表示し、組織のデバイスのインベントリを管理し、更新、再起動、デバイスのモニター診断などのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="be51f-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="be51f-106">作成し、デバイスまたはデバイスのグループに構成プロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="be51f-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="be51f-107">どのようなデバイスを管理することができますか。</span><span class="sxs-lookup"><span data-stu-id="be51f-107">What devices can you manage?</span></span>
<span data-ttu-id="be51f-108">デバイスは、チームの認定し、チームに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be51f-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="be51f-109">デバイスでは、初めてのユーザーが署名チームに、デバイス上に自動的に登録が。</span><span class="sxs-lookup"><span data-stu-id="be51f-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="be51f-110">管理可能な認定済みのデバイスのリストは、[会議電話](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16)と[デスクの電話](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be51f-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34).</span></span>

> [!NOTE]
> <span data-ttu-id="be51f-111">Microsoft Intune があれば、デバイスは自動的に Intune に登録します。</span><span class="sxs-lookup"><span data-stu-id="be51f-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="be51f-112">デバイスを登録すると後、デバイスのコンプライアンスを確認し、条件付きのアクセス ポリシーは、デバイスに適用します。</span><span class="sxs-lookup"><span data-stu-id="be51f-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="be51f-113">チーム内のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="be51f-113">Manage devices in Teams</span></span>

<span data-ttu-id="be51f-114">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="be51f-114">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="be51f-115">左側のナビゲーションでは、**デバイス**に移動 > **デバイスの管理**です。</span><span class="sxs-lookup"><span data-stu-id="be51f-115">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="be51f-116">**すべてのデバイス**を選択します。</span><span class="sxs-lookup"><span data-stu-id="be51f-116">Select **All devices**.</span></span>  

 <span data-ttu-id="be51f-117">ここでは、表示し、組織内のチームに登録されているすべてのデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="be51f-117">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="be51f-118">デバイスごとに表示される情報には、デバイス名、製造元、モデル、ユーザー、状態、アクション、最後の表示、および履歴が含まれています。</span><span class="sxs-lookup"><span data-stu-id="be51f-118">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="be51f-119">お客様のニーズに合った情報を表示するビューをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="be51f-119">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="be51f-120">組織内のチームのデバイスを管理する方法のいくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="be51f-120">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="be51f-121">これを行う.</span><span class="sxs-lookup"><span data-stu-id="be51f-121">To do this...</span></span>  |<span data-ttu-id="be51f-122">この操作を行う</span><span class="sxs-lookup"><span data-stu-id="be51f-122">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="be51f-123">デバイスの情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="be51f-123">Change device information</span></span>   | <span data-ttu-id="be51f-124">デバイス _gt が**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="be51f-124">Select a device > **Edit**.</span></span> <span data-ttu-id="be51f-125">デバイス名、ユーザー情報、資産タグなどの詳細を編集し、メモを追加できます。</span><span class="sxs-lookup"><span data-stu-id="be51f-125">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="be51f-126">ソフトウェア更新プログラムを管理します。</span><span class="sxs-lookup"><span data-stu-id="be51f-126">Manage software updates</span></span>   |<span data-ttu-id="be51f-127">デバイス _gt**更新プログラム**を選択します。</span><span class="sxs-lookup"><span data-stu-id="be51f-127">Select a device > **Update**.</span></span> <span data-ttu-id="be51f-128">デバイスで利用できるソフトウェアおよびファームウェアの更新の一覧を表示し、インストールする更新プログラムを選択できます。</span><span class="sxs-lookup"><span data-stu-id="be51f-128">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="be51f-129">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="be51f-129">Restart a device</span></span>   |<span data-ttu-id="be51f-130">デバイス _gt が**再起動**を選択します。</span><span class="sxs-lookup"><span data-stu-id="be51f-130">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="be51f-131">デバイスの履歴を表示します</span><span class="sxs-lookup"><span data-stu-id="be51f-131">View device history</span></span>  | <span data-ttu-id="be51f-132">デバイス _gt**履歴**を選択します。</span><span class="sxs-lookup"><span data-stu-id="be51f-132">Select a device > **History**.</span></span> <span data-ttu-id="be51f-133">デバイスの更新履歴を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="be51f-133">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="be51f-134">診断を表示します。</span><span class="sxs-lookup"><span data-stu-id="be51f-134">View diagnostics</span></span>  | <span data-ttu-id="be51f-135">デバイス _gt**診断プログラム**を選択します。</span><span class="sxs-lookup"><span data-stu-id="be51f-135">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="be51f-136">構成プロファイルを使用して、チームで</span><span class="sxs-lookup"><span data-stu-id="be51f-136">Use configuration profiles in Teams</span></span>

<span data-ttu-id="be51f-137">構成プロファイルを使用すると、組織内のチームのデバイスの設定および機能を管理できます。</span><span class="sxs-lookup"><span data-stu-id="be51f-137">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="be51f-138">作成したり、設定、およびデバイスまたはデバイスのグループにプロファイルを割り当てるを有効または無効にする機能など、構成プロファイルをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="be51f-138">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="be51f-139">構成プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="be51f-139">Create a configuration profile</span></span>

<span data-ttu-id="be51f-140">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="be51f-140">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="be51f-141">左側のナビゲーションでは、**デバイス**に移動 > **デバイスの管理**です。</span><span class="sxs-lookup"><span data-stu-id="be51f-141">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="be51f-142">**構成プロファイル**を選択し、**新しい構成プロファイル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="be51f-142">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="be51f-143">プロファイルの名前を入力し、わかりやすい説明を追加する場合は、します。</span><span class="sxs-lookup"><span data-stu-id="be51f-143">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="be51f-144">プロファイルに使用設定を指定し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be51f-144">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="be51f-145">構成プロファイルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="be51f-145">Assign a configuration profile</span></span>

<span data-ttu-id="be51f-146">![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**</span><span class="sxs-lookup"><span data-stu-id="be51f-146">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="be51f-147">左側のナビゲーションでは、**デバイス**に移動 > **デバイスの管理**です。</span><span class="sxs-lookup"><span data-stu-id="be51f-147">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="be51f-148">**構成プロファイル**を選択し、割り当てるプロファイルの**割り当て先**] の下のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="be51f-148">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="be51f-149">**構成プロファイルにデバイスを割り当てる**ペインで、検索し、割り当てるデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="be51f-149">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="be51f-150">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be51f-150">Click **Save**.</span></span>
