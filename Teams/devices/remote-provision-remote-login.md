---
title: Android デバイスのリモート プロビジョニングTeamsサインイン
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Android デバイスのリモート プロビジョニングとサインインを行うTeams説明します
ms.openlocfilehash: f39b93a048cee84cf6890d063e272edbef5edb4e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059191"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="639ca-103">Android デバイスのリモート プロビジョニングTeamsサインイン</span><span class="sxs-lookup"><span data-stu-id="639ca-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="639ca-104">IT 管理者は、リモートでプロビジョニングし、Teams Android デバイスにサインインできます。</span><span class="sxs-lookup"><span data-stu-id="639ca-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="639ca-105">デバイスをリモートでプロビジョニングするには、管理者がプロビジョニングするデバイスの MAC の ID をアップロードし、確認コードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="639ca-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="639ca-106">プロセス全体は、管理センターからリモートTeams完了できます。</span><span class="sxs-lookup"><span data-stu-id="639ca-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="639ca-107">サポートされているデバイスを確認する</span><span class="sxs-lookup"><span data-stu-id="639ca-107">Review the supported devices</span></span>

<span data-ttu-id="639ca-108">次の一覧は、Android デバイスのファームウェア要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="639ca-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="639ca-109">デバイス カテゴリ</span><span class="sxs-lookup"><span data-stu-id="639ca-109">Device category</span></span>|<span data-ttu-id="639ca-110">デバイス モデル</span><span class="sxs-lookup"><span data-stu-id="639ca-110">Device model</span></span>|<span data-ttu-id="639ca-111">ファームウェアのバージョン</span><span class="sxs-lookup"><span data-stu-id="639ca-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="639ca-112">Teams電話</span><span class="sxs-lookup"><span data-stu-id="639ca-112">Teams phones</span></span>|<span data-ttu-id="639ca-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="639ca-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="639ca-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="639ca-114">58.15.0.124</span></span>|
|<span data-ttu-id="639ca-115">Teams電話</span><span class="sxs-lookup"><span data-stu-id="639ca-115">Teams phones</span></span>|<span data-ttu-id="639ca-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="639ca-116">Yealink VP59</span></span>|<span data-ttu-id="639ca-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="639ca-117">91.15.0.58</span></span>|
|<span data-ttu-id="639ca-118">Teams電話</span><span class="sxs-lookup"><span data-stu-id="639ca-118">Teams phones</span></span>|<span data-ttu-id="639ca-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="639ca-119">Yealink CP960</span></span>|<span data-ttu-id="639ca-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="639ca-120">73.15.0.117</span></span>|
|<span data-ttu-id="639ca-121">Teams電話</span><span class="sxs-lookup"><span data-stu-id="639ca-121">Teams phones</span></span>|<span data-ttu-id="639ca-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="639ca-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="639ca-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="639ca-123">122.15.0.36</span></span>|
|<span data-ttu-id="639ca-124">Teams電話</span><span class="sxs-lookup"><span data-stu-id="639ca-124">Teams phones</span></span>|<span data-ttu-id="639ca-125">クレスロン UC-2</span><span class="sxs-lookup"><span data-stu-id="639ca-125">Crestron UC-2</span></span>|<span data-ttu-id="639ca-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="639ca-126">1.0.3.52</span></span>|
|<span data-ttu-id="639ca-127">Teams電話</span><span class="sxs-lookup"><span data-stu-id="639ca-127">Teams phones</span></span>|  <span data-ttu-id="639ca-128">Poly Trio C60</span><span class="sxs-lookup"><span data-stu-id="639ca-128">Poly Trio C60</span></span>|  <span data-ttu-id="639ca-129">7.0.2.1071</span><span class="sxs-lookup"><span data-stu-id="639ca-129">7.0.2.1071</span></span>|
|<span data-ttu-id="639ca-130">Teams電話</span><span class="sxs-lookup"><span data-stu-id="639ca-130">Teams phones</span></span>|  <span data-ttu-id="639ca-131">CCX400/CCX500/CCX600</span><span class="sxs-lookup"><span data-stu-id="639ca-131">CCX400/CCX500/CCX600</span></span>    |<span data-ttu-id="639ca-132">7.0.2.1072</span><span class="sxs-lookup"><span data-stu-id="639ca-132">7.0.2.1072</span></span>|
|<span data-ttu-id="639ca-133">Teams電話</span><span class="sxs-lookup"><span data-stu-id="639ca-133">Teams phones</span></span>|  <span data-ttu-id="639ca-134">オーディオ コード C448HD/C450HD/C470HD</span><span class="sxs-lookup"><span data-stu-id="639ca-134">Audio Codes C448HD/C450HD/C470HD</span></span>|   <span data-ttu-id="639ca-135">1.10.120</span><span class="sxs-lookup"><span data-stu-id="639ca-135">1.10.120</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="639ca-136">デバイスの MAC アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="639ca-136">Add a device MAC address</span></span>

<span data-ttu-id="639ca-137">新しいデバイスをプロビジョニングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="639ca-137">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="639ca-138">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="639ca-138">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="639ca-139">[デバイス] **を展開します**。</span><span class="sxs-lookup"><span data-stu-id="639ca-139">Expand **Devices**.</span></span>
3. <span data-ttu-id="639ca-140">[アクション **] タブから [新しい** デバイスのプロビジョニング **] を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="639ca-140">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="639ca-141">[新 **しいデバイスのプロビジョニング]** ウィンドウで、MAC アドレスを手動で追加するか、ファイルをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="639ca-141">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="639ca-142">デバイスの MAC アドレスを手動で追加する</span><span class="sxs-lookup"><span data-stu-id="639ca-142">Manually add a device MAC address</span></span>

1. <span data-ttu-id="639ca-143">[アクティブ化 **を待っている] タブで\*\*\*\*、[MAC ID の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="639ca-143">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![デバイスの Mac アドレスを手動で追加する](../media/remote-provision-6.png)

1. <span data-ttu-id="639ca-145">MAC ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="639ca-145">Enter the MAC ID.</span></span>
1. <span data-ttu-id="639ca-146">場所を入力します。これは、技術者がデバイスをインストールする場所を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="639ca-146">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="639ca-147">完了したら **、[適用** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="639ca-147">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="639ca-148">アップロード MAC アドレスを追加するファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="639ca-148">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="639ca-149">[アクティブ **化を待っている]** タブで、[MAC **アップロード を選択します**。</span><span class="sxs-lookup"><span data-stu-id="639ca-149">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="639ca-150">ファイル テンプレートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="639ca-150">Download the file template.</span></span>
3. <span data-ttu-id="639ca-151">MAC ID と場所を入力し、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="639ca-151">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="639ca-152">**ファイル を選択** し、[ファイル]**をアップロード。**</span><span class="sxs-lookup"><span data-stu-id="639ca-152">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="639ca-153">確認コードを生成する</span><span class="sxs-lookup"><span data-stu-id="639ca-153">Generate a verification code</span></span>

<span data-ttu-id="639ca-154">デバイスの確認コードが必要です。</span><span class="sxs-lookup"><span data-stu-id="639ca-154">You need a verification code for the devices.</span></span> <span data-ttu-id="639ca-155">確認コードは、一括またはデバイス レベルで生成され、24 時間有効です。</span><span class="sxs-lookup"><span data-stu-id="639ca-155">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="639ca-156">[アクティブ **化を待っている] タブ** で、既存の MAC ID を選択します。</span><span class="sxs-lookup"><span data-stu-id="639ca-156">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="639ca-157">MAC アドレスのパスワードが作成され、[確認コード] 列 **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="639ca-157">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="639ca-158">MAC の一覧と確認コードを現場の技術者に提供します。</span><span class="sxs-lookup"><span data-stu-id="639ca-158">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="639ca-159">ファイル内の詳細を直接エクスポートし、実際のインストール作業を行っている技術者とファイルを共有できます。</span><span class="sxs-lookup"><span data-stu-id="639ca-159">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="639ca-160">デバイスをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="639ca-160">Provision the device</span></span>

<span data-ttu-id="639ca-161">デバイスの電源が入り、ネットワークに接続されると、技術者がデバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="639ca-161">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="639ca-162">これらの手順は、デバイスのTeamsされます。</span><span class="sxs-lookup"><span data-stu-id="639ca-162">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="639ca-163">技術者が[デバイスの **プロビジョニング] を\*\*\*\*選択設定。**</span><span class="sxs-lookup"><span data-stu-id="639ca-163">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![[アクション] タブから新しいデバイス オプションをプロビジョニングする](../media/provision-device1.png)
  
2. <span data-ttu-id="639ca-165">技術者は、指定された入力フィールドにデバイス固有の確認コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="639ca-165">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![新しいデバイス検証をプロビジョニングする](../media/provision-device-verification1.png)

   <span data-ttu-id="639ca-167">デバイスが正常にプロビジョニングされると、テナント名がサインイン ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="639ca-167">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![サインイン ページのテナント名](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="639ca-169">リモートでサインインする</span><span class="sxs-lookup"><span data-stu-id="639ca-169">Sign in remotely</span></span>

<span data-ttu-id="639ca-170">プロビジョニングされたデバイスが [サインイン待ち] **タブに表示** されます。個々のデバイスを選択して、リモート サインイン プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="639ca-170">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="639ca-171">[サインイン待ち] **タブからデバイスを選択** します。</span><span class="sxs-lookup"><span data-stu-id="639ca-171">Select a device from the **Awaiting sign in** tab.</span></span>

   ![サインインできるデバイスの一覧が表示されたウィンドウ。](../media/remote-device1.png)

2. <span data-ttu-id="639ca-173">「ユーザーにサインインする」 **の指示に従って、[** 閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="639ca-173">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![個々のデバイスの [ユーザーのサインイン] ウィンドウ](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="639ca-175">関連記事</span><span class="sxs-lookup"><span data-stu-id="639ca-175">Related article</span></span>

- [<span data-ttu-id="639ca-176">Teams でのデバイスの管理</span><span class="sxs-lookup"><span data-stu-id="639ca-176">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="639ca-177">デバイスTeamsをリモートで更新する</span><span class="sxs-lookup"><span data-stu-id="639ca-177">Update Teams devices remotely</span></span>](remote-update.md)
