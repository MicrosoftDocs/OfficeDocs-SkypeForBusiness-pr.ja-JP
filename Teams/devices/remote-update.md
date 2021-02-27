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
description: Teams 管理センターを使用して、Microsoft Teams の電話、Teams パネル、コラボレーション バーをリモートで更新する
ms.openlocfilehash: 67b76d8330de5a801625a22c25cd1f9637048d05
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347888"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="40dec-103">Microsoft Teams デバイスをリモートで更新する</span><span class="sxs-lookup"><span data-stu-id="40dec-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="40dec-104">Microsoft Teams 管理センターを使用して、Teams の電話、Teams パネル、コラボレーション バーなどの Teams デバイスをリモートで更新し、デバイス ファームウェアの自動更新動作を選択できます。</span><span class="sxs-lookup"><span data-stu-id="40dec-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as Teams phones, Teams panels, and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="40dec-105">Teams 管理センターを使用して、デバイスで次の情報を更新できます。</span><span class="sxs-lookup"><span data-stu-id="40dec-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="40dec-106">Teams アプリとチームの管理エージェント</span><span class="sxs-lookup"><span data-stu-id="40dec-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="40dec-107">ポータル サイト アプリ</span><span class="sxs-lookup"><span data-stu-id="40dec-107">Company portal app</span></span>
- <span data-ttu-id="40dec-108">OEM エージェント アプリ</span><span class="sxs-lookup"><span data-stu-id="40dec-108">OEM agent app</span></span>
- <span data-ttu-id="40dec-109">デバイスファームウェア</span><span class="sxs-lookup"><span data-stu-id="40dec-109">Device firmware</span></span>

<span data-ttu-id="40dec-110">デバイス ファームウェアの更新プログラムは、自動的に適用するか、将来の日時にスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="40dec-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="40dec-111">その他の利用可能なデバイス更新プログラムは自動的に適用されませんが、手動で適用したり、将来の日時にスケジュールしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="40dec-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="40dec-112">デバイスのファームウェアの更新はスケジュール可能ですが、スケジュールされた日付と時刻が設定された最大 30 日または 90 日の遅延を超える場合は、最大遅延に達するとファームウェアの更新が適用されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="40dec-113">スケジュールされた日付と時刻は無視されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-113">The scheduled date and time are ignored.</span></span> <span data-ttu-id="40dec-114">また、Microsoft Teams デバイスをリモートで更新する機能は、米国 Government Cloud テナント (GCC-High) ではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="40dec-114">Additionally, updating Microsoft Teams devices remotely is a feature not yet available on US Government Cloud tenants (GCC-High).</span></span>

<span data-ttu-id="40dec-115">デバイスを管理するには、グローバル管理者、Teams サービス管理者、または Teams デバイス管理者である必要があります。管理者ロールの詳細については、「Microsoft Teams 管理者ロールを使用して Teams を [管理する」を参照してください](../using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="40dec-115">To manage devices, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="40dec-116">デバイスファームウェアの自動更新動作を選択する</span><span class="sxs-lookup"><span data-stu-id="40dec-116">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="40dec-117">デバイス ファームウェアの更新プログラムは自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-117">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="40dec-118">更新プログラムがリリースされるとすぐに適用するかどうかを決定できます (このオプションを選択した場合、更新プログラムがリリースされた後の最初の週末に適用されます)、または更新プログラムのリリースから 30 日または 90 日後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-118">You can decide whether to apply updates as soon as one is released (if you choose this option, updates are applied on the first weekend after an update is released), or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="40dec-119">既定では、デバイスファームウェアの更新プログラムは 30 日間リリースされます。</span><span class="sxs-lookup"><span data-stu-id="40dec-119">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40dec-120">最新のファームウェア更新プログラムリリースは、Teams デバイスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="40dec-120">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="40dec-121">代わりに、デバイスに自動的に適用される更新プログラムは、1 つのバージョンで遅延されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-121">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="40dec-122">たとえば、デバイスにバージョン "10" が適用され、バージョン "11" がリリースされるとします。</span><span class="sxs-lookup"><span data-stu-id="40dec-122">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="40dec-123">バージョン "11" はまだ適用されません。</span><span class="sxs-lookup"><span data-stu-id="40dec-123">Version "11" won't be applied yet.</span></span> <span data-ttu-id="40dec-124">代わりに、お使いのデバイスは、バージョン "12" がリリースされた後にのみバージョン "11" に更新されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-124">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

> [!NOTE]
> <span data-ttu-id="40dec-125">一部のデバイスでは、ファームウェアの自動更新がまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40dec-125">Some devices don't support automatic firmware update yet.</span></span> <span data-ttu-id="40dec-126">自動更新をサポートしないデバイスにファームウェアの自動更新設定を適用しても、それらのデバイスには影響を与え得ない。</span><span class="sxs-lookup"><span data-stu-id="40dec-126">Applying automatic firmware update settings on devices that don't support automatic updates won't have any affect on those devices.</span></span> <span data-ttu-id="40dec-127">お使いのデバイスがファームウェアの自動更新をサポートするかどうかに関する質問については、デバイスの製造元にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="40dec-127">For questions about whether your device will support automatic firmware updates, contact your device manufacturer.</span></span>

<span data-ttu-id="40dec-128">デバイスの自動更新動作を選択するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="40dec-128">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="40dec-129">Microsoft Teams 管理センターにアクセスしてサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="40dec-129">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="40dec-130">デバイス  >  **の IP 電話またはコラボレーション バー** または Teams **パネル\*\*\*\*間を移動します**。</span><span class="sxs-lookup"><span data-stu-id="40dec-130">Navigate **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="40dec-131">1 つ以上のデバイスを選択し、[更新] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="40dec-131">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="40dec-132">[ **ファームウェアの自動更新] で**、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="40dec-132">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="40dec-133">**すぐに利用可能** 最新の更新プログラムがリリースされた後の最初の週末に、最新のデバイス ファームウェア更新プログラムが適用されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-133">**As soon as available** Second-newest device firmware update is applied on the first weekend after the latest update is released.</span></span>
    - <span data-ttu-id="40dec-134">**30 日延期** 最新のデバイス ファームウェア更新プログラムは、最新の更新プログラムがリリースされた 30 日後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-134">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="40dec-135">**90 日延期** 最新のデバイス ファームウェア更新プログラムは、最新の更新プログラムがリリースされた 90 日後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-135">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="40dec-136">[更新 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="40dec-136">Select **Update**.</span></span>

<span data-ttu-id="40dec-137">何らかの理由でデバイスのファームウェアの更新を元に戻す必要がある場合は、デバイスを出荷時の設定にリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="40dec-137">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="40dec-138">製造元の指示に従ってデバイスをリセットします。</span><span class="sxs-lookup"><span data-stu-id="40dec-138">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="40dec-139">リモート デバイスを手動で更新する</span><span class="sxs-lookup"><span data-stu-id="40dec-139">Manually update remote devices</span></span>

<span data-ttu-id="40dec-140">管理センターを使用して 1 つ以上のデバイスを更新する場合、デバイスをすぐに更新するか、将来の日時の更新をスケジュールするかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="40dec-140">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="40dec-141">リモート デバイスを手動で更新するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="40dec-141">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="40dec-142">Microsoft Teams 管理センターにアクセスしてサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="40dec-142">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="40dec-143">デバイス  >  **の IP 電話またはコラボレーション バー** または Teams **パネル\*\*\*\*間を移動します**。</span><span class="sxs-lookup"><span data-stu-id="40dec-143">Navigate  **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="40dec-144">1 つ以上のデバイスを選択し、[更新] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="40dec-144">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="40dec-145">[**手動更新]** で、今後の日付と時刻の更新をスケジュールする場合は、[スケジュール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="40dec-145">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="40dec-146">更新プログラムは、タイムゾーンで選択されたタイムゾーンの日付と時刻に **適用されます**。</span><span class="sxs-lookup"><span data-stu-id="40dec-146">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="40dec-147">表示される内容は、デバイスが選択されているデバイスか複数あるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="40dec-147">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="40dec-148">次の左側の画像は複数のデバイスを選択し、右側の画像は 1 つのデバイスを選択した場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="40dec-148">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="[デバイスの更新の状態] ウィンドウの 1 つのデバイス ビューと複数のデバイス ビュー":::

<span data-ttu-id="40dec-150">複数のデバイスを選択する場合は、選択した各デバイスに適用する更新の種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="40dec-150">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="40dec-151">適用する更新プログラムの種類を選択し、[更新] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="40dec-151">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="40dec-152">1 つのデバイスを選択すると、そのデバイスで利用可能な更新プログラムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-152">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="40dec-153">デバイスで複数の更新の種類を使用できる場合は、適用する各更新の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="40dec-153">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="40dec-154">デバイスに適用 **されている現在の** バージョンと適用される **新しいバージョン** を表示できます。</span><span class="sxs-lookup"><span data-stu-id="40dec-154">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="40dec-155">適用する更新プログラムを選択し、[更新] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="40dec-155">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="40dec-156">[更新] **を選択** すると、更新プログラムをスケジュールした場合に選択した日時に、デバイスに更新プログラムが適用されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-156">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="40dec-157">将来の日付と時刻を選択しなかった場合は、数分以内に更新プログラムがデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="40dec-157">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
