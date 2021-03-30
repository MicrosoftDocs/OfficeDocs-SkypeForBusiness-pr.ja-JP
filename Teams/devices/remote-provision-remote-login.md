---
title: Teams Android デバイスのリモート プロビジョニングとサインイン
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
description: Teams Android デバイスのリモート プロビジョニングとサインインの方法について説明します。
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410357"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="9cf0b-103">Teams Android デバイスのリモート プロビジョニングとサインイン</span><span class="sxs-lookup"><span data-stu-id="9cf0b-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="9cf0b-104">IT 管理者は、リモートで Teams Android デバイスをプロビジョニングしてサインインできます。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="9cf0b-105">リモートでデバイスをプロビジョニングするには、管理者がプロビジョニングされているデバイスの MAC ID をアップロードし、確認コードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="9cf0b-106">Teams 管理センターからリモートでプロセス全体を完了できます。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="9cf0b-107">サポートされているデバイスを確認する</span><span class="sxs-lookup"><span data-stu-id="9cf0b-107">Review the supported devices</span></span>

<span data-ttu-id="9cf0b-108">次の一覧は、Android デバイスのファームウェア要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="9cf0b-109">デバイス カテゴリ</span><span class="sxs-lookup"><span data-stu-id="9cf0b-109">Device category</span></span>|<span data-ttu-id="9cf0b-110">デバイス モデル</span><span class="sxs-lookup"><span data-stu-id="9cf0b-110">Device model</span></span>|<span data-ttu-id="9cf0b-111">ファームウェアのバージョン</span><span class="sxs-lookup"><span data-stu-id="9cf0b-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="9cf0b-112">Teams の電話</span><span class="sxs-lookup"><span data-stu-id="9cf0b-112">Teams phones</span></span>|<span data-ttu-id="9cf0b-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="9cf0b-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="9cf0b-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="9cf0b-114">58.15.0.124</span></span>|
|<span data-ttu-id="9cf0b-115">Teams の電話</span><span class="sxs-lookup"><span data-stu-id="9cf0b-115">Teams phones</span></span>|<span data-ttu-id="9cf0b-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="9cf0b-116">Yealink VP59</span></span>|<span data-ttu-id="9cf0b-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="9cf0b-117">91.15.0.58</span></span>|
|<span data-ttu-id="9cf0b-118">Teams の電話</span><span class="sxs-lookup"><span data-stu-id="9cf0b-118">Teams phones</span></span>|<span data-ttu-id="9cf0b-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="9cf0b-119">Yealink CP960</span></span>|<span data-ttu-id="9cf0b-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="9cf0b-120">73.15.0.117</span></span>|
|<span data-ttu-id="9cf0b-121">Teams の電話</span><span class="sxs-lookup"><span data-stu-id="9cf0b-121">Teams phones</span></span>|<span data-ttu-id="9cf0b-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="9cf0b-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="9cf0b-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="9cf0b-123">122.15.0.36</span></span>|
|<span data-ttu-id="9cf0b-124">Teams の電話</span><span class="sxs-lookup"><span data-stu-id="9cf0b-124">Teams phones</span></span>|<span data-ttu-id="9cf0b-125">クレットロン UC-2</span><span class="sxs-lookup"><span data-stu-id="9cf0b-125">Crestron UC-2</span></span>|<span data-ttu-id="9cf0b-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="9cf0b-126">1.0.3.52</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="9cf0b-127">デバイスの MAC アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="9cf0b-127">Add a device MAC address</span></span>

<span data-ttu-id="9cf0b-128">新しいデバイスをプロビジョニングするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-128">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="9cf0b-129">Teams 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-129">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="9cf0b-130">[デバイス **] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-130">Expand **Devices**.</span></span>
3. <span data-ttu-id="9cf0b-131">[操作 **] タブから [新しい** デバイスのプロビジョニング **] を選択** します。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-131">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="9cf0b-132">[新 **しいデバイスのプロビジョニング** ] ウィンドウで、MAC アドレスを手動で追加するか、ファイルをアップロードできます。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-132">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="9cf0b-133">デバイスの MAC アドレスを手動で追加する</span><span class="sxs-lookup"><span data-stu-id="9cf0b-133">Manually add a device MAC address</span></span>

1. <span data-ttu-id="9cf0b-134">[ライセンス認証 **待ち] タブで\*\*\*\*、[MAC ID の追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-134">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![デバイスの Mac アドレスを手動で追加する](../media/remote-provision-6.png)

1. <span data-ttu-id="9cf0b-136">MAC ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-136">Enter the MAC ID.</span></span>
1. <span data-ttu-id="9cf0b-137">場所を入力すると、技術者がデバイスをインストールする場所を特定できます。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-137">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="9cf0b-138">完了 **したら [適用** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-138">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="9cf0b-139">ファイルをアップロードしてデバイスの MAC アドレスを追加する</span><span class="sxs-lookup"><span data-stu-id="9cf0b-139">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="9cf0b-140">[ライセンス **認証待ち]** タブで **、[MAC のアップロード] を選び、**</span><span class="sxs-lookup"><span data-stu-id="9cf0b-140">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="9cf0b-141">ファイル テンプレートをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-141">Download the file template.</span></span>
3. <span data-ttu-id="9cf0b-142">MAC ID と場所を入力し、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-142">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="9cf0b-143">**ファイルを選択し**、[アップロード] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-143">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="9cf0b-144">確認コードを生成する</span><span class="sxs-lookup"><span data-stu-id="9cf0b-144">Generate a verification code</span></span>

<span data-ttu-id="9cf0b-145">デバイスの確認コードが必要です。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-145">You need a verification code for the devices.</span></span> <span data-ttu-id="9cf0b-146">確認コードは、一括またはデバイス レベルで生成され、24 時間有効です。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-146">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="9cf0b-147">[ライセンス **認証待ち]** タブで、既存の MAC ID を選択します。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-147">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="9cf0b-148">MAC アドレスのパスワードが作成され、[確認コード] 列 **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-148">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="9cf0b-149">フィールド技術者に MAC の ID と確認コードの一覧を提供します。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-149">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="9cf0b-150">ファイルに詳細を直接エクスポートし、実際のインストール作業を行っている技術者とファイルを共有できます。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-150">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="9cf0b-151">デバイスをプロビジョニングする</span><span class="sxs-lookup"><span data-stu-id="9cf0b-151">Provision the device</span></span>

<span data-ttu-id="9cf0b-152">デバイスの電源が入り、ネットワークに接続されると、技術者がデバイスをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-152">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="9cf0b-153">これらの手順は、Teams デバイスで完了します。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-153">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="9cf0b-154">技術者が [設定] **から [プロビジョニング デバイス** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-154">The technician selects **Provision device** from the **Settings**.</span></span>  

   ![[操作] タブから新しいデバイス オプションをプロビジョニングする](../media/provision-device1.png)
  
2. <span data-ttu-id="9cf0b-156">技術者は、指定された入力フィールドにデバイス固有の確認コードを入力します。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-156">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![新しいデバイスの確認をプロビジョニングする](../media/provision-device-verification1.png)

   <span data-ttu-id="9cf0b-158">デバイスのプロビジョニングが正常に完了すると、テナント名がサインイン ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-158">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![サインイン ページのテナント名](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="9cf0b-160">リモートでサインインする</span><span class="sxs-lookup"><span data-stu-id="9cf0b-160">Sign in remotely</span></span>

<span data-ttu-id="9cf0b-161">プロビジョニングされたデバイスが [サインイン待ち **] タブに表示** されます。個々のデバイスを選択してリモート サインイン プロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-161">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="9cf0b-162">[サインイン待ち] タブ **からデバイスを選択** します。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-162">Select a device from the **Awaiting sign in** tab.</span></span>

   ![サインインできるデバイスの一覧が表示されたウィンドウ。](../media/remote-device1.png)

2. <span data-ttu-id="9cf0b-164">[サインイン] の指示 **に従ってユーザーをサインインし**、[閉じる] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="9cf0b-164">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![個々のデバイスのユーザー ウィンドウにサインインする](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="9cf0b-166">関連記事</span><span class="sxs-lookup"><span data-stu-id="9cf0b-166">Related article</span></span>

- [<span data-ttu-id="9cf0b-167">Teams でのデバイスの管理</span><span class="sxs-lookup"><span data-stu-id="9cf0b-167">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="9cf0b-168">Teams デバイスをリモートで更新する</span><span class="sxs-lookup"><span data-stu-id="9cf0b-168">Update Teams devices remotely</span></span>](remote-update.md)
