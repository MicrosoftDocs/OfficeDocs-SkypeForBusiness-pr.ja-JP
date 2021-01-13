---
title: Intune を使用して Teams の電話と Teams のディスプレイを展開する
ms.author: v-cichur
author: cichur
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
description: この記事では、Microsoft Teams のディスプレイでサポートされる機能の概要と機能について説明します。
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825417"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="08861-103">Intune を使用して Teams の電話と Teams のディスプレイを展開する</span><span class="sxs-lookup"><span data-stu-id="08861-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="08861-104">この記事では、Intune を使用して Teams 電話機と Teams ディスプレイを展開する方法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="08861-104">This article gives you an overview of how to deploy Teams phones and Teams displays using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="08861-105">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="08861-105">Conditional Access</span></span>

<span data-ttu-id="08861-106">条件付きアクセスは Azure Active Directory (Azure AD) 機能であり、Office 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されていることを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="08861-106">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="08861-107">Teams サービスに条件付きアクセス ポリシーを適用する場合、Teams にアクセスする Android デバイス (Teams の携帯電話や Teams を含む) は Intune に登録する必要があります。また、その設定はポリシーに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08861-107">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams need to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="08861-108">デバイスが Intune に登録されていない場合、またはデバイスが登録されているが、その設定がポリシーに準拠しない場合、条件付きアクセスにより、ユーザーはデバイスで Teams アプリにサインインしたり使用したりできません。</span><span class="sxs-lookup"><span data-stu-id="08861-108">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="08861-109">通常、Intune 内で定義されたコンプライアンス ポリシーはユーザーのグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="08861-109">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="08861-110">つまり、Android コンプライアンス ポリシーを user@contoso.com に割り当てると、そのポリシーは Android スマートフォンと、サインインしている任意の Android ベースの Teams user@contoso.com適用されます。</span><span class="sxs-lookup"><span data-stu-id="08861-110">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="08861-111">Intune の登録を適用する必要がある条件付きアクセスを使用する場合は、組織で Intune の登録を正常に行うには、次の 2 つの設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="08861-111">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="08861-112">**Intune ライセンス** Teams デバイスにサインインするユーザーには、Intune のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="08861-112">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="08861-113">Teams デバイスが有効な Intune ライセンスを持つユーザー アカウントにサインインしている限り、デバイスはサインイン プロセスの一環として Microsoft Intune に自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="08861-113">As long as the Teams device are signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="08861-114">**Intune を構成する** Android デバイス管理者登録用に適切に構成された Intune テナントが必要です。</span><span class="sxs-lookup"><span data-stu-id="08861-114">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="08861-115">Teams Android ベースのデバイスを登録するために Intune を構成する</span><span class="sxs-lookup"><span data-stu-id="08861-115">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="08861-116">Teams Android ベースのデバイスは、Android デバイス管理者 (DA) 管理を介して Intune で管理されます。</span><span class="sxs-lookup"><span data-stu-id="08861-116">Teams Android-based devices are managed by in Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="08861-117">デバイスを Intune に登録する前に、いくつかの基本的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="08861-117">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="08861-118">Intune でデバイスを管理している場合は、既にこれらすべてのことを行っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08861-118">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="08861-119">表示されない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="08861-119">If not, here’s what to do:</span></span>

1. <span data-ttu-id="08861-120">Intune MDM (モバイル デバイス管理) 機関を設定します。</span><span class="sxs-lookup"><span data-stu-id="08861-120">Set Intune MDM (mobile device management) Authority.</span></span>  <span data-ttu-id="08861-121">Intune を使用したことがない場合は、デバイスを登録する前に MDM 機関を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08861-121">If you’re never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="08861-122">詳細については、「モバイル デバイス管理 [機関を設定する」を参照してください](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="08861-122">For more information, see [Set the mobile device management authority](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="08861-123">これは、新しい Intune テナントを作成する際に実行する必要がある 1 回の手順です。</span><span class="sxs-lookup"><span data-stu-id="08861-123">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
2. <span data-ttu-id="08861-124">Android デバイス管理者の登録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="08861-124">Enable Android device administrator enrollment.</span></span> <span data-ttu-id="08861-125">Android ベースの Teams デバイスは、Intune を使用してデバイス管理者デバイスとして管理されます。</span><span class="sxs-lookup"><span data-stu-id="08861-125">Android-based Teams device are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="08861-126">新しく作成されたテナントでは、デバイス管理者の登録は既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="08861-126">Device administrator enrollment is off by default for newly created tenants.</span></span>  <span data-ttu-id="08861-127">詳細については、Android デバイス管理者 [の登録を参照してください](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)。</span><span class="sxs-lookup"><span data-stu-id="08861-127">For more information, see [Android device administrator enrollment](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator).</span></span>
3. <span data-ttu-id="08861-128">ライセンスをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="08861-128">Assign licenses to users.</span></span> <span data-ttu-id="08861-129">Intune に登録している Teams デバイスのユーザーには、有効な Intune ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="08861-129">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="08861-130">詳細については、「Intune にデバイスを登録 [するためにライセンスをユーザーに割り当てる」を参照してください](https://docs.microsoft.com/intune/fundamentals/licenses-assign)。</span><span class="sxs-lookup"><span data-stu-id="08861-130">For more information, see [Assign licenses to users so they can enroll devices in Intune](https://docs.microsoft.com/intune/fundamentals/licenses-assign).</span></span>
4. <span data-ttu-id="08861-131">デバイス管理者のコンプライアンス ポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="08861-131">Assign Device Administrator compliance policies.</span></span>  <span data-ttu-id="08861-132">Android デバイス管理者コンプライアンス ポリシーを作成し、Teams デバイスにサインインするユーザーを含む Azure Active Directory グループに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="08861-132">Create an Android Device Administrator compliance policy and assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="08861-133">詳細については、「コンプライアンス ポリシーを使用して、Intune で管理するデバイスのルール [を設定する」を参照してください](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="08861-133">For more information, see [Use compliance policies to set rules for devices you manage with Intune](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="08861-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="08861-134">See also</span></span>

[<span data-ttu-id="08861-135">Teams 対応の電話機</span><span class="sxs-lookup"><span data-stu-id="08861-135">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="08861-136">Microsoft Teams 認定 IP 電話</span><span class="sxs-lookup"><span data-stu-id="08861-136">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="08861-137">Teams の表示</span><span class="sxs-lookup"><span data-stu-id="08861-137">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="08861-138">Teams でのデバイスの管理</span><span class="sxs-lookup"><span data-stu-id="08861-138">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="08861-139">Teams Marketplace</span><span class="sxs-lookup"><span data-stu-id="08861-139">Teams Marketplace</span></span>](https://office.com/teamsdevices)
