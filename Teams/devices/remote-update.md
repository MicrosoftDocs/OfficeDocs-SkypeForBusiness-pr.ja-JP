---
title: Microsoft Teams デバイスをリモートで更新する
ms.author: dstrome
author: dstrome
ms.reviewer: rahulmi
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Teams 管理センターを使用して、リモートで Microsoft Teams の電話とコラボレーションバーを更新する
ms.openlocfilehash: 7e47c9394eddfa73b8b55279b68ae59ff7b6de3d
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944107"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="d49de-103">Microsoft Teams デバイスをリモートで更新する</span><span class="sxs-lookup"><span data-stu-id="d49de-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="d49de-104">Microsoft Teams 管理センターを使用すると、スマートフォンやコラボレーションバーなどのチームデバイスをリモートで更新したり、デバイスファームウェアの自動更新動作を選択したりできます。</span><span class="sxs-lookup"><span data-stu-id="d49de-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as phones and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="d49de-105">Teams 管理センターを使って、デバイスで次の情報を更新できます。</span><span class="sxs-lookup"><span data-stu-id="d49de-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="d49de-106">Teams アプリと teams 管理者エージェント</span><span class="sxs-lookup"><span data-stu-id="d49de-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="d49de-107">会社ポータルアプリ</span><span class="sxs-lookup"><span data-stu-id="d49de-107">Company portal app</span></span>
- <span data-ttu-id="d49de-108">OEM エージェントアプリ</span><span class="sxs-lookup"><span data-stu-id="d49de-108">OEM agent app</span></span>
- <span data-ttu-id="d49de-109">デバイスのファームウェア</span><span class="sxs-lookup"><span data-stu-id="d49de-109">Device firmware</span></span>

<span data-ttu-id="d49de-110">デバイスのファームウェアの更新は、自動で適用するか、または将来の日付と時刻に対してスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="d49de-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="d49de-111">利用可能なその他のデバイス更新プログラムは自動的には適用されませんが、手動で適用することも、将来の日付と時刻に対してスケジュールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d49de-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="d49de-112">デバイスのファームウェアの更新をスケジュール設定することはできますが、スケジュールされた日付と時刻が、構成されている30または90日の遅延後に発生した場合は、最大遅延に達するとファームウェアの更新が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="d49de-113">スケジュールされた日付と時刻は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-113">The scheduled date and time are ignored.</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="d49de-114">自動デバイスファームウェア更新動作を選ぶ</span><span class="sxs-lookup"><span data-stu-id="d49de-114">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="d49de-115">デバイスファームウェアの更新プログラムが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-115">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="d49de-116">更新プログラムがリリースされるとすぐに更新プログラムを適用するかどうかを決定することができます。更新プログラムがリリースされた後、30日または90日です。</span><span class="sxs-lookup"><span data-stu-id="d49de-116">You can decide whether to apply updates as soon as one is released, or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="d49de-117">既定では、デバイスファームウェアの更新は30日リリースされています。</span><span class="sxs-lookup"><span data-stu-id="d49de-117">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d49de-118">最新のファームウェア更新プログラムのリリースは、Teams デバイスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="d49de-118">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="d49de-119">代わりに、デバイスで自動的に適用される更新プログラムが1つのバージョンで遅延されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-119">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="d49de-120">たとえば、デバイスのバージョンが "10" に設定されていて、バージョン "11" がリリースされているとします。</span><span class="sxs-lookup"><span data-stu-id="d49de-120">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="d49de-121">バージョン "11" はまだ適用されません。</span><span class="sxs-lookup"><span data-stu-id="d49de-121">Version "11" won't be applied yet.</span></span> <span data-ttu-id="d49de-122">代わりに、バージョン "12" がリリースされた後にのみ、デバイスはバージョン "11" に更新されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-122">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

<span data-ttu-id="d49de-123">デバイスの自動更新動作を選択するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d49de-123">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="d49de-124">アクセスして、Microsoft Teams 管理センターにサインインします。https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d49de-124">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="d49de-125">スマート**Devices**  >  **フォン**または**グループ作業バー**のデバイス間の移動</span><span class="sxs-lookup"><span data-stu-id="d49de-125">Navigate **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="d49de-126">1つ以上のデバイスを選択し、[**更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d49de-126">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="d49de-127">[**ファームウェアの自動更新**] で、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="d49de-127">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="d49de-128">**利用可能**になったら第2のデバイスファームウェアの最新の更新プログラムは、最新の更新プログラムがリリースされた後、できるだけ早く適用されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-128">**As soon as available** Second-newest device firmware update is applied as soon as possible after the latest update is released.</span></span>
    - <span data-ttu-id="d49de-129">**30 日間の遅延**第2のデバイスファームウェア更新プログラムは、最新の更新プログラムがリリースされてから30日後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-129">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="d49de-130">**90 日間の延期**第2のデバイスファームウェア更新プログラムは、最新の更新プログラムがリリースされてから90日後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-130">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="d49de-131">[**更新**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="d49de-131">Select **Update**</span></span>

<span data-ttu-id="d49de-132">何らかの理由でデバイスファームウェアの更新を元に戻す必要がある場合は、デバイスを出荷時の設定にリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d49de-132">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="d49de-133">製造元の指示に従って、デバイスをリセットします。</span><span class="sxs-lookup"><span data-stu-id="d49de-133">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="d49de-134">リモートデバイスを手動で更新する</span><span class="sxs-lookup"><span data-stu-id="d49de-134">Manually update remote devices</span></span>

<span data-ttu-id="d49de-135">管理センターを使用して1つ以上のデバイスを更新する場合は、デバイスをすぐに更新するか、または将来の日付と時刻の更新をスケジュールするかを決めることができます。</span><span class="sxs-lookup"><span data-stu-id="d49de-135">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="d49de-136">リモートデバイスを手動で更新するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d49de-136">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="d49de-137">アクセスして、Microsoft Teams 管理センターにサインインします。https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d49de-137">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="d49de-138">スマート**Devices**  >  **フォン**または**グループ作業バー**のデバイス間の移動</span><span class="sxs-lookup"><span data-stu-id="d49de-138">Navigate  **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="d49de-139">1つ以上のデバイスを選択し、[**更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d49de-139">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="d49de-140">[**手動更新**] で、将来の日付と時刻の更新をスケジュールする場合は、[**スケジュール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d49de-140">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="d49de-141">更新は、 **timezone**で選択されたタイムゾーンの日付と時刻に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-141">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="d49de-142">表示される内容は、1つまたは複数のデバイスが選択されているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d49de-142">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="d49de-143">下の左の図は、複数のデバイスが選択されている状態を示しています。右の画像は、1つのデバイスを選択しています。</span><span class="sxs-lookup"><span data-stu-id="d49de-143">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="[デバイスの更新状態] ウィンドウに表示される1つまたは複数のデバイスビュー":::

<span data-ttu-id="d49de-145">複数のデバイスを選択する場合は、選択した各デバイスに適用する更新の種類を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="d49de-145">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="d49de-146">適用する更新の種類を選択して、[**更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d49de-146">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="d49de-147">1つのデバイスを選択すると、デバイスで利用可能な更新プログラムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-147">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="d49de-148">デバイスで複数の更新の種類が利用できる場合は、適用する更新の種類をそれぞれ選びます。</span><span class="sxs-lookup"><span data-stu-id="d49de-148">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="d49de-149">デバイスに適用されている**現在のバージョン**と適用される**新しいバージョン**を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d49de-149">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="d49de-150">適用する更新プログラムを選択して、[**更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d49de-150">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="d49de-151">[**更新**] を選択すると、更新プログラムをスケジュールしたときに選択した日付と時刻に、更新がデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-151">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="d49de-152">将来の日付と時刻を選択しなかった場合は、数分以内に更新プログラムがデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d49de-152">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
