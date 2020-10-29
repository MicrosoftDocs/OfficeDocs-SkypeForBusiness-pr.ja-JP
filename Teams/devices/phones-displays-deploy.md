---
title: Intune を使用してチームの電話とチームの表示を展開する
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: この記事では、Microsoft Teams でサポートされている機能の概要について説明します。
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787638"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="b901b-103">Intune を使用してチームの電話とチームの表示を展開する</span><span class="sxs-lookup"><span data-stu-id="b901b-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="b901b-104">この記事では、Intune を使用して、チームの電話やチームの表示を展開する方法の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="b901b-104">This article gives you an overview of how to deploy Teams phones and Teams displays using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="b901b-105">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="b901b-105">Conditional Access</span></span>

<span data-ttu-id="b901b-106">条件付きアクセスは、Office 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されるようにするために、Azure Active Directory (Azure AD) の機能です。</span><span class="sxs-lookup"><span data-stu-id="b901b-106">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="b901b-107">条件付きアクセスポリシーを Teams サービスに適用すると、Access Teams は Intune に登録され、その設定がポリシーに準拠する必要があることを示す、Android デバイス (Teams の電話やチームの表示など) が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b901b-107">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams need to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="b901b-108">デバイスが Intune に登録されていない場合、または登録されているが、その設定がポリシーに準拠していない場合は、条件付きアクセスによって、ユーザーがデバイスで Teams アプリにサインインしたり、使用したりすることを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="b901b-108">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="b901b-109">通常、Intune で定義されているコンプライアンスポリシーは、ユーザーのグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b901b-109">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="b901b-110">つまり、Android のコンプライアンスポリシーを user@contoso.com に割り当てると、そのポリシーは Android スマートフォンと、user@contoso.com によってサインインされる Android ベースの Teams デバイスに同じように適用されます。</span><span class="sxs-lookup"><span data-stu-id="b901b-110">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="b901b-111">Intune の登録を適用する必要がある条件付きアクセスを使用する場合、組織では、Intune 登録が成功するためにセットアップする必要があることがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b901b-111">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="b901b-112">**Intune ライセンス** Teams デバイスにサインインしているユーザーは、Intune のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="b901b-112">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="b901b-113">チームデバイスが有効な Intune ライセンスを持っているユーザーアカウントにサインインしている限り、そのデバイスはサインイン処理の一環として Microsoft Intune に自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="b901b-113">As long as the Teams device are signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="b901b-114">**Intune を構成する** Android デバイス管理者登録用に、適切に設定された Intune テナントが必要です。</span><span class="sxs-lookup"><span data-stu-id="b901b-114">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="b901b-115">Teams Android ベースのデバイスを登録するように Intune を構成する</span><span class="sxs-lookup"><span data-stu-id="b901b-115">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="b901b-116">Teams Android ベースのデバイスは、Intune で Android デバイス管理者 (DA) 管理によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="b901b-116">Teams Android-based devices are managed by in Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="b901b-117">デバイスを Intune に登録する前に、いくつかの基本的な手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b901b-117">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="b901b-118">既に Intune でデバイスを管理している場合は、次のことを行っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b901b-118">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="b901b-119">そうでない場合は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="b901b-119">If not, here’s what to do:</span></span>

1. <span data-ttu-id="b901b-120">Intune MDM (モバイルデバイス管理) 権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="b901b-120">Set Intune MDM (mobile device management) Authority.</span></span>  <span data-ttu-id="b901b-121">まだ Intune を使用していない場合は、デバイスを登録する前に MDM の権限を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b901b-121">If you’re never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="b901b-122">詳細については、「 [モバイルデバイス管理機関を設定する](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b901b-122">For more information, see [Set the mobile device management authority](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="b901b-123">これは、新しい Intune テナントの作成時に行う必要がある1回限りの手順です。</span><span class="sxs-lookup"><span data-stu-id="b901b-123">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
2. <span data-ttu-id="b901b-124">Android デバイス管理者の登録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b901b-124">Enable Android device administrator enrollment.</span></span> <span data-ttu-id="b901b-125">Android ベースの Teams デバイスは、Intune でデバイス管理デバイスとして管理されます。</span><span class="sxs-lookup"><span data-stu-id="b901b-125">Android-based Teams device are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="b901b-126">新しく作成されたテナントの場合、デバイス管理者の登録は既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="b901b-126">Device administrator enrollment is off by default for newly created tenants.</span></span>  <span data-ttu-id="b901b-127">詳細については、「 [Android デバイス管理者の登録](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b901b-127">For more information, see [Android device administrator enrollment](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).</span></span>
3. <span data-ttu-id="b901b-128">ライセンスをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b901b-128">Assign licenses to users.</span></span> <span data-ttu-id="b901b-129">Intune に登録しているチームデバイスのユーザーには、有効な Intune ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b901b-129">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="b901b-130">詳細については、「 [ユーザーにライセンスを割り当てて、ユーザーが Intune にデバイスを登録できるようにする](https://docs.microsoft.com/intune/fundamentals/licenses-assign)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b901b-130">For more information, see [Assign licenses to users so they can enroll devices in Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).</span></span>
4. <span data-ttu-id="b901b-131">デバイス管理者のコンプライアンスポリシーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b901b-131">Assign Device Administrator compliance policies.</span></span>  <span data-ttu-id="b901b-132">Android デバイス管理者のコンプライアンスポリシーを作成して、チームデバイスにサインインするユーザーが含まれている Azure Active Directory グループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b901b-132">Create an Android Device Administrator compliance policy and assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="b901b-133">詳細については、「 [コンプライアンスポリシーを使用して、Intune で管理しているデバイスのルールを設定する](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b901b-133">For more information, see [Use compliance policies to set rules for devices you manage with Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="b901b-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="b901b-134">See also</span></span>

[<span data-ttu-id="b901b-135">Teams 対応の電話機</span><span class="sxs-lookup"><span data-stu-id="b901b-135">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="b901b-136">Microsoft Teams 認定 IP 電話</span><span class="sxs-lookup"><span data-stu-id="b901b-136">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="b901b-137">Teams の表示</span><span class="sxs-lookup"><span data-stu-id="b901b-137">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="b901b-138">Teams でのデバイスの管理</span><span class="sxs-lookup"><span data-stu-id="b901b-138">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="b901b-139">Teams Marketplace</span><span class="sxs-lookup"><span data-stu-id="b901b-139">Teams Marketplace</span></span>](https://office.com/teamsdevices)
