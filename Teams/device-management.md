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
ms.openlocfilehash: dff307b1bd4ede3e8999a78a5e6a8df36b8a1411
ms.sourcegitcommit: a378848c5aeb8e2b25300024318de792454d905b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/28/2018
ms.locfileid: "27458551"
---
# <a name="manage-your-devices-in-microsoft-teams"></a><span data-ttu-id="c9234-103">Microsoft Teams でのデバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="c9234-103">Manage your devices in Microsoft Teams</span></span>

 <span data-ttu-id="c9234-104">管理者としては、ビジネス管理センターのマイクロソフト チームと Skype から、組織内のチームで使用するすべてのデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="c9234-104">As an admin, you manage all devices used with Teams in your organization from the Microsoft Teams & Skype for Business admin center.</span></span> <span data-ttu-id="c9234-105">表示し、組織のデバイスのインベントリを管理し、更新、再起動、デバイスのモニター診断などのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9234-105">You can view and manage the device inventory for your organization and do tasks such as update, restart, and monitor diagnostics for devices.</span></span> <span data-ttu-id="c9234-106">作成し、デバイスまたはデバイスのグループに構成プロファイルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c9234-106">You can also create and assign configuration profiles to a device or groups of devices.</span></span> 

## <a name="what-devices-can-you-manage"></a><span data-ttu-id="c9234-107">どのようなデバイスを管理することができますか。</span><span class="sxs-lookup"><span data-stu-id="c9234-107">What devices can you manage?</span></span>
<span data-ttu-id="c9234-108">デバイスは、チームの認定し、チームに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9234-108">Devices must be certified for Teams and enrolled in Teams.</span></span> <span data-ttu-id="c9234-109">デバイスでは、初めてのユーザーが署名チームに、デバイス上に自動的に登録が。</span><span class="sxs-lookup"><span data-stu-id="c9234-109">A device is automatically enrolled the first time a user signs in to Teams on the device.</span></span> <span data-ttu-id="c9234-110">管理可能な認定済みのデバイスのリストは、[会議電話](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=ddb1bc66-7499-4823-8d2b-a2c6dbe4f716)と[デスクの電話](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=c6536b33-f554-4b55-bd3d-c98733ebc017&page=1&filters=)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9234-110">For a list of certified devices that can be managed, see [Conference phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=ddb1bc66-7499-4823-8d2b-a2c6dbe4f716) and [Desk phones](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?categoryid=c6536b33-f554-4b55-bd3d-c98733ebc017&page=1&filters=).</span></span>

> [!NOTE]
> <span data-ttu-id="c9234-111">Microsoft Intune があれば、デバイスは自動的に Intune に登録します。</span><span class="sxs-lookup"><span data-stu-id="c9234-111">If you have Microsoft Intune, devices are automatically enrolled in Intune.</span></span> <span data-ttu-id="c9234-112">デバイスを登録すると後、デバイスのコンプライアンスを確認し、条件付きのアクセス ポリシーは、デバイスに適用します。</span><span class="sxs-lookup"><span data-stu-id="c9234-112">After a device is enrolled, device compliance is confirmed and conditional access policies are applied to the device.</span></span> 

## <a name="manage-devices-in-teams"></a><span data-ttu-id="c9234-113">チーム内のデバイスを管理します。</span><span class="sxs-lookup"><span data-stu-id="c9234-113">Manage devices in Teams</span></span>

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="c9234-115">ビジネス管理センターの Microsoft のチームと Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9234-115">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="c9234-116">左側のナビゲーションでは、**デバイス**に移動 > **デバイスの管理**です。</span><span class="sxs-lookup"><span data-stu-id="c9234-116">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="c9234-117">**すべてのデバイス**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9234-117">Select **All devices**.</span></span>  

 <span data-ttu-id="c9234-118">ここでは、表示し、組織内のチームに登録されているすべてのデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c9234-118">From here, you can view and manage all devices enrolled in Teams in your organization.</span></span> <span data-ttu-id="c9234-119">デバイスごとに表示される情報には、デバイス名、製造元、モデル、ユーザー、状態、アクション、最後の表示、および履歴が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9234-119">Information that you'll see for each device includes device name, manufacturer, model, user, status, action, last seen, and history.</span></span> <span data-ttu-id="c9234-120">お客様のニーズに合った情報を表示するビューをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="c9234-120">You can customize the view to show the information that fits your needs.</span></span>

 <span data-ttu-id="c9234-121">組織内のチームのデバイスを管理する方法のいくつかの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c9234-121">Here's some examples of how you can manage Teams devices in your organization.</span></span>  
    
|<span data-ttu-id="c9234-122">これを行う.</span><span class="sxs-lookup"><span data-stu-id="c9234-122">To do this...</span></span>  |<span data-ttu-id="c9234-123">この操作を行う</span><span class="sxs-lookup"><span data-stu-id="c9234-123">Do this</span></span> |
|---------|---------|
|<span data-ttu-id="c9234-124">デバイスの情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="c9234-124">Change device information</span></span>   | <span data-ttu-id="c9234-125">デバイスを選択して >**編集**します。</span><span class="sxs-lookup"><span data-stu-id="c9234-125">Select a device > **Edit**.</span></span> <span data-ttu-id="c9234-126">デバイス名、ユーザー情報、資産タグなどの詳細を編集し、メモを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c9234-126">You can edit details such as device name, user information, asset tag, and add notes.</span></span>     |
|<span data-ttu-id="c9234-127">ソフトウェア更新プログラムを管理します。</span><span class="sxs-lookup"><span data-stu-id="c9234-127">Manage software updates</span></span>   |<span data-ttu-id="c9234-128">デバイスを選択 >**更新**します。</span><span class="sxs-lookup"><span data-stu-id="c9234-128">Select a device > **Update**.</span></span> <span data-ttu-id="c9234-129">デバイスで利用できるソフトウェアおよびファームウェアの更新の一覧を表示し、インストールする更新プログラムを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c9234-129">You can view the list of software and firmware updates available for the device and choose the updates to install.</span></span>    |
|<span data-ttu-id="c9234-130">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="c9234-130">Restart a device</span></span>   |<span data-ttu-id="c9234-131">デバイスを選択して >**を再起動**します。</span><span class="sxs-lookup"><span data-stu-id="c9234-131">Select a device > **Restart**.</span></span>          |
|<span data-ttu-id="c9234-132">デバイスの履歴を表示します</span><span class="sxs-lookup"><span data-stu-id="c9234-132">View device history</span></span>  | <span data-ttu-id="c9234-133">デバイスを選択 >**履歴**です。</span><span class="sxs-lookup"><span data-stu-id="c9234-133">Select a device > **History**.</span></span> <span data-ttu-id="c9234-134">デバイスの更新履歴を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c9234-134">You can view the update history for the device.</span></span>     |
|<span data-ttu-id="c9234-135">診断を表示します。</span><span class="sxs-lookup"><span data-stu-id="c9234-135">View diagnostics</span></span>  | <span data-ttu-id="c9234-136">デバイスを選択 >**診断**します。</span><span class="sxs-lookup"><span data-stu-id="c9234-136">Select a device > **Diagnostics**.</span></span>        |

## <a name="use-configuration-profiles-in-teams"></a><span data-ttu-id="c9234-137">構成プロファイルを使用して、チームで</span><span class="sxs-lookup"><span data-stu-id="c9234-137">Use configuration profiles in Teams</span></span>

<span data-ttu-id="c9234-138">構成プロファイルを使用すると、組織内のチームのデバイスの設定および機能を管理できます。</span><span class="sxs-lookup"><span data-stu-id="c9234-138">Use configuration profiles to manage settings and features for Teams devices in your organization.</span></span> <span data-ttu-id="c9234-139">作成したり、設定、およびデバイスまたはデバイスのグループにプロファイルを割り当てるを有効または無効にする機能など、構成プロファイルをアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="c9234-139">You can create or upload configuration profiles to include settings and features you want to enable or disable and then assign a profile to a device or groups of devices.</span></span> 

### <a name="create-a-configuration-profile"></a><span data-ttu-id="c9234-140">構成プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c9234-140">Create a configuration profile</span></span>

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="c9234-142">ビジネス管理センターの Microsoft のチームと Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9234-142">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="c9234-143">左側のナビゲーションでは、**デバイス**に移動 > **デバイスの管理**です。</span><span class="sxs-lookup"><span data-stu-id="c9234-143">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="c9234-144">**構成プロファイル**を選択し、**新しい構成プロファイル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9234-144">Select **Configuration profiles**, and then select **New configuration profile**.</span></span>
3. <span data-ttu-id="c9234-145">プロファイルの名前を入力し、わかりやすい説明を追加する場合は、します。</span><span class="sxs-lookup"><span data-stu-id="c9234-145">Enter a name for the profile and if you want, add a friendly description.</span></span>
4. <span data-ttu-id="c9234-146">プロファイルに使用設定を指定し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9234-146">Specify the settings you want for the profile, and then click **Save**.</span></span>

### <a name="assign-a-configuration-profile"></a><span data-ttu-id="c9234-147">構成プロファイルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="c9234-147">Assign a configuration profile</span></span>

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="c9234-149">ビジネス管理センターの Microsoft のチームと Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="c9234-149">Using the Microsoft Teams & Skype for Business admin center</span></span>

1. <span data-ttu-id="c9234-150">左側のナビゲーションでは、**デバイス**に移動 > **デバイスの管理**です。</span><span class="sxs-lookup"><span data-stu-id="c9234-150">In the left navigation, go to **Devices** > **Manage Devices**.</span></span>
2. <span data-ttu-id="c9234-151">**構成プロファイル**を選択し、割り当てるプロファイルの**割り当て先**] の下のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9234-151">Select **Configuration profile**, and then under **Assigned to** in the profile you want to assign, click the link.</span></span>  
3. <span data-ttu-id="c9234-152">**構成プロファイルにデバイスを割り当てる**ペインで、検索し、割り当てるデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9234-152">In the **Assign devices to a configuration profile** pane, search for and select the devices you want to assign.</span></span>
4. <span data-ttu-id="c9234-153">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9234-153">Click **Save**.</span></span>
