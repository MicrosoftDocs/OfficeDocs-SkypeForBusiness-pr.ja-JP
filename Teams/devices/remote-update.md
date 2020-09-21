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
ms.openlocfilehash: e57ca3f357deeb005f845d37a17c4b20db5d2035
ms.sourcegitcommit: b255db7ef816d1884c9c71af86a901bd83a1d9ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962888"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="7bc68-103">Microsoft Teams デバイスをリモートで更新する</span><span class="sxs-lookup"><span data-stu-id="7bc68-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="7bc68-104">Microsoft Teams 管理センターを使用すると、スマートフォンやコラボレーションバーなどのチームデバイスをリモートで更新したり、デバイスファームウェアの自動更新動作を選択したりできます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as phones and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="7bc68-105">Teams 管理センターを使って、デバイスで次の情報を更新できます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="7bc68-106">Teams アプリと teams 管理者エージェント</span><span class="sxs-lookup"><span data-stu-id="7bc68-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="7bc68-107">会社ポータルアプリ</span><span class="sxs-lookup"><span data-stu-id="7bc68-107">Company portal app</span></span>
- <span data-ttu-id="7bc68-108">OEM エージェントアプリ</span><span class="sxs-lookup"><span data-stu-id="7bc68-108">OEM agent app</span></span>
- <span data-ttu-id="7bc68-109">デバイスのファームウェア</span><span class="sxs-lookup"><span data-stu-id="7bc68-109">Device firmware</span></span>

<span data-ttu-id="7bc68-110">デバイスのファームウェアの更新は、自動で適用するか、または将来の日付と時刻に対してスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="7bc68-111">利用可能なその他のデバイス更新プログラムは自動的には適用されませんが、手動で適用することも、将来の日付と時刻に対してスケジュールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="7bc68-112">デバイスのファームウェアの更新をスケジュール設定することはできますが、スケジュールされた日付と時刻が、構成されている30または90日の遅延後に発生した場合は、最大遅延に達するとファームウェアの更新が適用されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="7bc68-113">スケジュールされた日付と時刻は無視されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-113">The scheduled date and time are ignored.</span></span> <span data-ttu-id="7bc68-114">さらに、Microsoft Teams デバイスのリモート更新は、米国政府のクラウドテナント (GCC-高) でまだ利用できない機能です。</span><span class="sxs-lookup"><span data-stu-id="7bc68-114">Additionally, updating Microsoft Teams devices remotely is a feature not yet available on US Government Cloud tenants (GCC-High).</span></span>

<span data-ttu-id="7bc68-115">デバイスを管理するには、グローバル管理者、Teams サービス管理者、または Teams デバイス管理者である必要があります。管理者ロールの詳細については、「 [Microsoft teams 管理者ロールを使用してチームを管理する](../using-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bc68-115">To manage devices, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="7bc68-116">自動デバイスファームウェア更新動作を選ぶ</span><span class="sxs-lookup"><span data-stu-id="7bc68-116">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="7bc68-117">デバイスファームウェアの更新プログラムが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-117">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="7bc68-118">更新プログラムをリリースするとすぐに適用するかどうかを決めることができます (このオプションを選択した場合は、更新プログラムのリリース後に最初の週末に更新プログラムが適用されます)。または、更新プログラムがリリースされてから30日または90日後に更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="7bc68-118">You can decide whether to apply updates as soon as one is released (if you choose this option, updates are applied on the first weekend after an update is released), or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="7bc68-119">既定では、デバイスファームウェアの更新は30日リリースされています。</span><span class="sxs-lookup"><span data-stu-id="7bc68-119">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7bc68-120">最新のファームウェア更新プログラムのリリースは、Teams デバイスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="7bc68-120">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="7bc68-121">代わりに、デバイスで自動的に適用される更新プログラムが1つのバージョンで遅延されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-121">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="7bc68-122">たとえば、デバイスのバージョンが "10" に設定されていて、バージョン "11" がリリースされているとします。</span><span class="sxs-lookup"><span data-stu-id="7bc68-122">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="7bc68-123">バージョン "11" はまだ適用されません。</span><span class="sxs-lookup"><span data-stu-id="7bc68-123">Version "11" won't be applied yet.</span></span> <span data-ttu-id="7bc68-124">代わりに、バージョン "12" がリリースされた後にのみ、デバイスはバージョン "11" に更新されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-124">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

> [!NOTE]
> <span data-ttu-id="7bc68-125">一部のデバイスでは、自動ファームウェア更新がまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7bc68-125">Some devices don't support automatic firmware update yet.</span></span> <span data-ttu-id="7bc68-126">自動更新をサポートしていないデバイスで自動ファームウェアの更新設定を適用しても、これらのデバイスに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="7bc68-126">Applying automatic firmware update settings on devices that don't support automatic updates won't have any affect on those devices.</span></span> <span data-ttu-id="7bc68-127">デバイスが自動ファームウェア更新をサポートするかどうかについては、お使いのデバイスの製造元にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7bc68-127">For questions about whether your device will support automatic firmware updates, contact your device manufacturer.</span></span>

<span data-ttu-id="7bc68-128">デバイスの自動更新動作を選択するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7bc68-128">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="7bc68-129">アクセスして、Microsoft Teams 管理センターにサインインします。 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7bc68-129">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="7bc68-130">スマート**Devices**  >  **フォン**または**グループ作業バー**のデバイス間の移動</span><span class="sxs-lookup"><span data-stu-id="7bc68-130">Navigate **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="7bc68-131">1つ以上のデバイスを選択し、[**更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bc68-131">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="7bc68-132">[ **ファームウェアの自動更新**] で、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="7bc68-132">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="7bc68-133">**利用可能** になったら第2のデバイスファームウェアの更新プログラムがリリースされた後の最初の週末に最新のデバイスファームウェアが適用されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-133">**As soon as available** Second-newest device firmware update is applied on the first weekend after the latest update is released.</span></span>
    - <span data-ttu-id="7bc68-134">**30 日間の遅延** 第2のデバイスファームウェア更新プログラムは、最新の更新プログラムがリリースされてから30日後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-134">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="7bc68-135">**90 日間の延期** 第2のデバイスファームウェア更新プログラムは、最新の更新プログラムがリリースされてから90日後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-135">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="7bc68-136">[**更新**] を選ぶ</span><span class="sxs-lookup"><span data-stu-id="7bc68-136">Select **Update**</span></span>

<span data-ttu-id="7bc68-137">何らかの理由でデバイスファームウェアの更新を元に戻す必要がある場合は、デバイスを出荷時の設定にリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bc68-137">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="7bc68-138">製造元の指示に従って、デバイスをリセットします。</span><span class="sxs-lookup"><span data-stu-id="7bc68-138">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="7bc68-139">リモートデバイスを手動で更新する</span><span class="sxs-lookup"><span data-stu-id="7bc68-139">Manually update remote devices</span></span>

<span data-ttu-id="7bc68-140">管理センターを使用して1つ以上のデバイスを更新する場合は、デバイスをすぐに更新するか、または将来の日付と時刻の更新をスケジュールするかを決めることができます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-140">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="7bc68-141">リモートデバイスを手動で更新するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7bc68-141">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="7bc68-142">アクセスして、Microsoft Teams 管理センターにサインインします。 https://admin.teams.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="7bc68-142">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com</span></span>
2. <span data-ttu-id="7bc68-143">スマート**Devices**  >  **フォン**または**グループ作業バー**のデバイス間の移動</span><span class="sxs-lookup"><span data-stu-id="7bc68-143">Navigate  **Devices** > **Phones** or **Collaboration bars**</span></span>
3. <span data-ttu-id="7bc68-144">1つ以上のデバイスを選択し、[**更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bc68-144">Select one or more devices and then select **Update**</span></span>
4. <span data-ttu-id="7bc68-145">[ **手動更新**] で、将来の日付と時刻の更新をスケジュールする場合は、[ **スケジュール** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bc68-145">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="7bc68-146">更新は、 **timezone**で選択されたタイムゾーンの日付と時刻に適用されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-146">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="7bc68-147">表示される内容は、1つまたは複数のデバイスが選択されているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="7bc68-147">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="7bc68-148">下の左の図は、複数のデバイスが選択されている状態を示しています。右の画像は、1つのデバイスを選択しています。</span><span class="sxs-lookup"><span data-stu-id="7bc68-148">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="[デバイスの更新状態] ウィンドウに表示される1つまたは複数のデバイスビュー":::

<span data-ttu-id="7bc68-150">複数のデバイスを選択する場合は、選択した各デバイスに適用する更新の種類を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-150">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="7bc68-151">適用する更新の種類を選択して、[ **更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bc68-151">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="7bc68-152">1つのデバイスを選択すると、デバイスで利用可能な更新プログラムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-152">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="7bc68-153">デバイスで複数の更新の種類が利用できる場合は、適用する更新の種類をそれぞれ選びます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-153">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="7bc68-154">デバイスに適用されている **現在のバージョン** と適用される **新しいバージョン** を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-154">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="7bc68-155">適用する更新プログラムを選択して、[ **更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7bc68-155">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="7bc68-156">[ **更新**] を選択すると、更新プログラムをスケジュールしたときに選択した日付と時刻に、更新がデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-156">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="7bc68-157">将来の日付と時刻を選択しなかった場合は、数分以内に更新プログラムがデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="7bc68-157">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
