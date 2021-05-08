---
title: デバイスMicrosoft Teamsをリモートで更新する
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
description: Microsoft Teams管理センターを使用Teams電話、パネル、コラボレーション バーをリモートTeams更新する
ms.openlocfilehash: 67b76d8330de5a801625a22c25cd1f9637048d05
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347888"
---
# <a name="update-microsoft-teams-devices-remotely"></a><span data-ttu-id="8533e-103">デバイスMicrosoft Teamsをリモートで更新する</span><span class="sxs-lookup"><span data-stu-id="8533e-103">Update Microsoft Teams devices remotely</span></span>

<span data-ttu-id="8533e-104">Microsoft Teams 管理センターを使用して、Teams 電話、Teams パネル、コラボレーション バーなどの Teams デバイスをリモートで更新し、デバイス ファームウェアの自動更新動作を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8533e-104">Using the Microsoft Teams admin center, you can update your Teams devices, such as Teams phones, Teams panels, and collaboration bars, remotely, and you can choose device firmware automatic-update behavior.</span></span> <span data-ttu-id="8533e-105">次の情報は、デバイスの管理センターを使用Teams更新できます。</span><span class="sxs-lookup"><span data-stu-id="8533e-105">You can update the following on your devices using the Teams admin center:</span></span>

- <span data-ttu-id="8533e-106">Teamsチーム管理者エージェントを作成する</span><span class="sxs-lookup"><span data-stu-id="8533e-106">Teams app and teams admin agent</span></span>
- <span data-ttu-id="8533e-107">ポータル サイト アプリ</span><span class="sxs-lookup"><span data-stu-id="8533e-107">Company portal app</span></span>
- <span data-ttu-id="8533e-108">OEM エージェント アプリ</span><span class="sxs-lookup"><span data-stu-id="8533e-108">OEM agent app</span></span>
- <span data-ttu-id="8533e-109">デバイスファームウェア</span><span class="sxs-lookup"><span data-stu-id="8533e-109">Device firmware</span></span>

<span data-ttu-id="8533e-110">デバイス ファームウェアの更新プログラムは、自動的に適用するか、将来の日時にスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8533e-110">Device firmware updates can either be applied automatically or scheduled for a future date and time.</span></span> <span data-ttu-id="8533e-111">その他の利用可能なデバイスの更新プログラムは自動的には適用されませんが、手動で適用したり、将来の日時にスケジュールしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8533e-111">Other available device updates aren't applied automatically, but can be applied manually or scheduled for a future date and time.</span></span>

> [!NOTE]
> <span data-ttu-id="8533e-112">デバイスファームウェアの更新はスケジュール可能ですが、スケジュールされた日付と時刻が構成された最大 30 日または 90 日の遅延より後に達した場合、ファームウェアの更新は最大遅延に達すると適用されます。</span><span class="sxs-lookup"><span data-stu-id="8533e-112">While device firmware updates can be scheduled, if the scheduled date and time falls after the configured maximum 30 or 90 day delay, the firmware update is applied when the maximum delay is reached.</span></span> <span data-ttu-id="8533e-113">スケジュールされた日付と時刻は無視されます。</span><span class="sxs-lookup"><span data-stu-id="8533e-113">The scheduled date and time are ignored.</span></span> <span data-ttu-id="8533e-114">さらに、デバイスをリモートMicrosoft Teams更新する機能は、米国政府機関クラウド テナント (GCC-High) ではまだ利用できません。</span><span class="sxs-lookup"><span data-stu-id="8533e-114">Additionally, updating Microsoft Teams devices remotely is a feature not yet available on US Government Cloud tenants (GCC-High).</span></span>

<span data-ttu-id="8533e-115">デバイスを管理するには、グローバル管理者、サービス管理者Teams、またはデバイス管理者Teams必要があります。管理者ロールの詳細については、「管理者ロールを使用してMicrosoft Teams[を管理する」を](../using-admin-roles.md)Teams。</span><span class="sxs-lookup"><span data-stu-id="8533e-115">To manage devices, you need to be a Global admin, Teams Service admin, or Teams Device admin. For more information about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](../using-admin-roles.md).</span></span>

## <a name="choose-automatic-device-firmware-update-behavior"></a><span data-ttu-id="8533e-116">デバイス ファームウェアの自動更新動作を選択する</span><span class="sxs-lookup"><span data-stu-id="8533e-116">Choose automatic device firmware update behavior</span></span>

<span data-ttu-id="8533e-117">デバイス ファームウェアの更新プログラムは自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8533e-117">Device firmware updates are applied automatically.</span></span> <span data-ttu-id="8533e-118">更新プログラムがリリースされるとすぐに適用するか (このオプションを選択した場合、更新プログラムがリリースされた後の最初の週末に更新プログラムが適用されます)、または更新プログラムがリリースされた 30 日または 90 日後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8533e-118">You can decide whether to apply updates as soon as one is released (if you choose this option, updates are applied on the first weekend after an update is released), or 30 or 90 days after an update is released.</span></span> <span data-ttu-id="8533e-119">既定では、デバイス ファームウェアの更新プログラムは 30 日間リリースされます。</span><span class="sxs-lookup"><span data-stu-id="8533e-119">By default, device firmware updates are applied 30 days one released.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8533e-120">最新のファームウェア更新プログラム のリリースは、お使いのデバイスTeamsされません。</span><span class="sxs-lookup"><span data-stu-id="8533e-120">The latest firmware update release isn't applied on your Teams device.</span></span> <span data-ttu-id="8533e-121">代わりに、デバイスに自動的に適用される更新プログラムは、1 つのバージョンで遅延します。</span><span class="sxs-lookup"><span data-stu-id="8533e-121">Instead, the update that's automatically applied on your device is delayed by one version.</span></span> <span data-ttu-id="8533e-122">たとえば、デバイスにバージョン "10" が適用され、バージョン "11" がリリースされるとします。</span><span class="sxs-lookup"><span data-stu-id="8533e-122">For example, assume your device has version "10" applied, and version "11" is released.</span></span> <span data-ttu-id="8533e-123">バージョン "11" はまだ適用されません。</span><span class="sxs-lookup"><span data-stu-id="8533e-123">Version "11" won't be applied yet.</span></span> <span data-ttu-id="8533e-124">代わりに、バージョン "12" がリリースされた後、デバイスはバージョン "11" にのみ更新されます。</span><span class="sxs-lookup"><span data-stu-id="8533e-124">Instead your device will only be updated to version "11" after version "12" is released.</span></span>

> [!NOTE]
> <span data-ttu-id="8533e-125">一部のデバイスでは、ファームウェアの自動更新がまだサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8533e-125">Some devices don't support automatic firmware update yet.</span></span> <span data-ttu-id="8533e-126">自動更新をサポートしないデバイスにファームウェアの自動更新設定を適用しても、それらのデバイスには影響を及ぼされません。</span><span class="sxs-lookup"><span data-stu-id="8533e-126">Applying automatic firmware update settings on devices that don't support automatic updates won't have any affect on those devices.</span></span> <span data-ttu-id="8533e-127">デバイスがファームウェアの自動更新をサポートするかどうかについては、デバイスの製造元にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="8533e-127">For questions about whether your device will support automatic firmware updates, contact your device manufacturer.</span></span>

<span data-ttu-id="8533e-128">デバイスの自動更新動作を選択するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8533e-128">To choose the automatic update behavior for your devices, do the following:</span></span>

1. <span data-ttu-id="8533e-129">にアクセスして、Microsoft Teams 管理センターにサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="8533e-129">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="8533e-130">[**デバイス**  >  **IP 電話] または [** コラボレーション **バー]** パネルTeams **移動します**。</span><span class="sxs-lookup"><span data-stu-id="8533e-130">Navigate **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="8533e-131">1 つ以上のデバイスを選択し、[更新] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8533e-131">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="8533e-132">[ **ファームウェアの自動更新] で**、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="8533e-132">Under **Firmware auto-update**, select one of the following:</span></span>
    - <span data-ttu-id="8533e-133">**利用可能な場合は、すぐに** 最新のデバイス ファームウェアの更新プログラムは、最新の更新プログラムがリリースされた後の最初の週末に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8533e-133">**As soon as available** Second-newest device firmware update is applied on the first weekend after the latest update is released.</span></span>
    - <span data-ttu-id="8533e-134">**30 日延期** 最新のデバイス ファームウェア更新プログラムは、最新の更新プログラムがリリースされた 30 日後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8533e-134">**Defer 30 days** Second-newest device firmware update is applied 30 days after the latest update is released.</span></span>
    - <span data-ttu-id="8533e-135">**90 日延期** 最新のデバイス ファームウェア更新プログラムは、最新の更新プログラムがリリースされた 90 日後に適用されます。</span><span class="sxs-lookup"><span data-stu-id="8533e-135">**Defer 90 days** Second-newest device firmware update is applied 90 days after the latest update is released.</span></span>
5. <span data-ttu-id="8533e-136">[更新] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8533e-136">Select **Update**.</span></span>

<span data-ttu-id="8533e-137">何らかの理由でデバイスファームウェアの更新を元に戻す必要がある場合は、デバイスを出荷時の設定にリセットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8533e-137">If, for whatever reason, you need to revert a device firmware update, you need to reset your device to its factory settings.</span></span> <span data-ttu-id="8533e-138">製造元の指示に従ってデバイスをリセットします。</span><span class="sxs-lookup"><span data-stu-id="8533e-138">Reset your device using the instructions from its manufacturer.</span></span>  

## <a name="manually-update-remote-devices"></a><span data-ttu-id="8533e-139">リモート デバイスを手動で更新する</span><span class="sxs-lookup"><span data-stu-id="8533e-139">Manually update remote devices</span></span>

<span data-ttu-id="8533e-140">管理センターを使用して 1 つ以上のデバイスを更新する場合は、デバイスをすぐに更新するか、将来の日時の更新をスケジュールするかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="8533e-140">When you update one or more devices using the admin center, you can decide whether to update the devices immediately or schedule an update for a future date and time.</span></span>

<span data-ttu-id="8533e-141">リモート デバイスを手動で更新するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8533e-141">To manually update remote devices, do the following:</span></span>

1. <span data-ttu-id="8533e-142">にアクセスして、Microsoft Teams 管理センターにサインインします https://admin.teams.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="8533e-142">Sign in to Microsoft Teams admin center by visiting https://admin.teams.microsoft.com.</span></span>
2. <span data-ttu-id="8533e-143">[**デバイス**  >  **IP 電話] または [** コラボレーション **バー]** パネルTeams **移動します**。</span><span class="sxs-lookup"><span data-stu-id="8533e-143">Navigate  **Devices** > **IP phones** or **Collaboration bars** or **Teams panels**.</span></span>
3. <span data-ttu-id="8533e-144">1 つ以上のデバイスを選択し、[更新] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8533e-144">Select one or more devices and then select **Update**.</span></span>
4. <span data-ttu-id="8533e-145">[**手動更新]\*\*\*\*で、将来** の日付と時刻の更新をスケジュールする場合は、[スケジュール] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8533e-145">Under **Manual updates**, select **Schedule** if you want to schedule the update for a future date and time.</span></span> <span data-ttu-id="8533e-146">更新は、タイムゾーン で選択されたタイムゾーンの日付と時刻に **適用されます**。</span><span class="sxs-lookup"><span data-stu-id="8533e-146">The updates are applied at the date and time in the timezone selected in **Timezone**.</span></span>

<span data-ttu-id="8533e-147">表示される内容は、デバイスが 1 つ選択されているデバイスか複数のデバイスかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="8533e-147">What you'll see depends on whether you have one, or multiple, devices selected.</span></span> <span data-ttu-id="8533e-148">次の左側の画像は、選択されている複数のデバイスを示し、右側の画像には 1 つのデバイスが選択されています。</span><span class="sxs-lookup"><span data-stu-id="8533e-148">The left image below shows multiple devices selected while the image on the right shows a single device selected.</span></span>

:::image type="content" source="../media/device-update-status.png" alt-text="[デバイスの更新状態] ウィンドウの 1 つ以上のデバイス ビュー":::

<span data-ttu-id="8533e-150">複数のデバイスを選択すると、選択した各デバイスに適用する更新プログラムの種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8533e-150">When you select multiple devices, you can choose which update types to apply to each selected device.</span></span> <span data-ttu-id="8533e-151">適用する更新プログラムの種類を選択し、[更新] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8533e-151">Select the update types you want to apply and select **Update**.</span></span>

<span data-ttu-id="8533e-152">1 つのデバイスを選択すると、そのデバイスで使用できる更新プログラムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8533e-152">When you select a single device, updates that are available for the device are shown.</span></span> <span data-ttu-id="8533e-153">デバイスで複数の更新プログラムの種類を使用できる場合は、適用する各更新の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="8533e-153">If multiple update types are available for the device, select each update type to apply.</span></span> <span data-ttu-id="8533e-154">デバイスに適用されている **現在の** バージョンと適用される **[新しいバージョン** ] を表示できます。</span><span class="sxs-lookup"><span data-stu-id="8533e-154">You can view the **Current version** applied on the device and the **New version** that will be applied.</span></span> <span data-ttu-id="8533e-155">適用する更新プログラムを選択し、[更新] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8533e-155">Select the update(s) you want to apply and select **Update**.</span></span>

<span data-ttu-id="8533e-156">[更新] **を選択** すると、更新プログラムをスケジュールした場合に選択した日時に、更新プログラムがデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8533e-156">After you select **Update**, updates are applied to your devices at the date and time you selected if you scheduled an update.</span></span> <span data-ttu-id="8533e-157">将来の日付と時刻を選択しなかった場合、数分以内に更新プログラムがデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8533e-157">If you didn't select a future date and time, updates are applied to your devices within a few minutes.</span></span>
