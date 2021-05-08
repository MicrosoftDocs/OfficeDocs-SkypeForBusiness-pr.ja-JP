---
title: Intune をTeamsして携帯電話とTeamsディスプレイをデプロイする
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
description: この記事では、ディスプレイでサポートされる機能と機能の概要Microsoft Teamsします。
ms.openlocfilehash: 178f8c594f8953c56a2d354806e86f4a19de028f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120779"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="1a31a-103">Intune をTeamsして携帯電話とTeamsディスプレイをデプロイする</span><span class="sxs-lookup"><span data-stu-id="1a31a-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="1a31a-104">この記事では、Intune を使用して携帯電話やディスプレイTeams展開Teams概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="1a31a-104">This article gives you an overview of how to deploy Teams phones and Teams displays using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="1a31a-105">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="1a31a-105">Conditional Access</span></span>

<span data-ttu-id="1a31a-106">条件付きアクセスはAzure Active Directory (Azure AD) 機能であり、Office 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されていることを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1a31a-106">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="1a31a-107">Teams サービスに条件付きアクセス ポリシーを適用する場合、Teams にアクセスする Android デバイス (Teams スマートフォンや Teams ディスプレイを含む) は Intune に登録する必要があります。その設定はポリシーに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a31a-107">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams need to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="1a31a-108">デバイスが Intune に登録されていない場合、またはデバイスが登録されているが、その設定がポリシーに準拠しない場合、条件付きアクセスでは、ユーザーがデバイスで Teams アプリにサインインまたは使用できません。</span><span class="sxs-lookup"><span data-stu-id="1a31a-108">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="1a31a-109">通常、Intune 内で定義されたコンプライアンス ポリシーは、ユーザーのグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="1a31a-109">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="1a31a-110">つまり、android コンプライアンス ポリシーを user@contoso.com に割り当てると、そのポリシーは Android スマートフォンと、サインインする Android ベースの Teams デバイスにも同様 user@contoso.com 適用されます。</span><span class="sxs-lookup"><span data-stu-id="1a31a-110">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="1a31a-111">Intune 登録を適用する必要がある条件付きアクセスを使用する場合、組織では、Intune 登録を正常に行うには、次の 2 つの設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="1a31a-111">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="1a31a-112">**Intune ライセンス** デバイスにサインインするユーザー Teams Intune のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="1a31a-112">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="1a31a-113">Teams デバイスが有効な Intune ライセンスを持つユーザー アカウントにサインインしている限り、デバイスはサインイン プロセスの一環として Microsoft Intune に自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="1a31a-113">As long as the Teams device are signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="1a31a-114">**Intune の構成** Android デバイス管理者登録用に適切に構成された Intune テナントが設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a31a-114">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="1a31a-115">Android ベースのデバイスにTeams Intune を構成する</span><span class="sxs-lookup"><span data-stu-id="1a31a-115">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="1a31a-116">TeamsAndroid ベースのデバイスは、Android デバイス管理者 (DA) 管理を介して Intune で管理されます。</span><span class="sxs-lookup"><span data-stu-id="1a31a-116">Teams Android-based devices are managed by in Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="1a31a-117">デバイスを Intune に登録する前に、いくつかの基本的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a31a-117">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="1a31a-118">Intune でデバイスを既に管理している場合は、既にこれらすべてのことを行っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1a31a-118">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="1a31a-119">ない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1a31a-119">If not, here’s what to do:</span></span>

1. <span data-ttu-id="1a31a-120">Intune MDM (モバイル デバイス管理) 機関を設定します。</span><span class="sxs-lookup"><span data-stu-id="1a31a-120">Set Intune MDM (mobile device management) Authority.</span></span>  <span data-ttu-id="1a31a-121">Intune を使用したことがない場合は、デバイスを登録する前に MDM 機関を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a31a-121">If you’re never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="1a31a-122">詳細については、「モバイル デバイス管理 [機関を設定する」を参照してください](/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="1a31a-122">For more information, see [Set the mobile device management authority](/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="1a31a-123">これは、新しい Intune テナントを作成するときに実行する必要がある 1 回の手順です。</span><span class="sxs-lookup"><span data-stu-id="1a31a-123">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
2. <span data-ttu-id="1a31a-124">Android デバイス管理者登録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="1a31a-124">Enable Android device administrator enrollment.</span></span> <span data-ttu-id="1a31a-125">Android ベースのTeamsは、Intune を使用してデバイス管理者デバイスとして管理されます。</span><span class="sxs-lookup"><span data-stu-id="1a31a-125">Android-based Teams device are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="1a31a-126">新しく作成されたテナントでは、デバイス管理者の登録は既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="1a31a-126">Device administrator enrollment is off by default for newly created tenants.</span></span>  <span data-ttu-id="1a31a-127">詳細については、「Android デバイス管理者 [の登録」を参照してください](/intune/enrollment/android-enroll-device-administrator)。</span><span class="sxs-lookup"><span data-stu-id="1a31a-127">For more information, see [Android device administrator enrollment](/intune/enrollment/android-enroll-device-administrator).</span></span>
3. <span data-ttu-id="1a31a-128">ユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="1a31a-128">Assign licenses to users.</span></span> <span data-ttu-id="1a31a-129">Intune にTeamsデバイスのユーザーには、有効な Intune ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a31a-129">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="1a31a-130">詳細については、「ユーザーが Intune にデバイスを [登録できるようライセンスをユーザーに割り当てる」を参照してください](/intune/fundamentals/licenses-assign)。</span><span class="sxs-lookup"><span data-stu-id="1a31a-130">For more information, see [Assign licenses to users so they can enroll devices in Intune](/intune/fundamentals/licenses-assign).</span></span>
4. <span data-ttu-id="1a31a-131">デバイス管理者のコンプライアンス ポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="1a31a-131">Assign Device Administrator compliance policies.</span></span>  <span data-ttu-id="1a31a-132">Android デバイス管理者のコンプライアンス ポリシーを作成し、Azure Active Directory デバイスにサインインするユーザーを含む Teams グループに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="1a31a-132">Create an Android Device Administrator compliance policy and assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="1a31a-133">詳細については、「コンプライアンス ポリシーを使用して Intune で管理するデバイスのルール [を設定する」を参照してください](/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="1a31a-133">For more information, see [Use compliance policies to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="1a31a-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a31a-134">See also</span></span>

[<span data-ttu-id="1a31a-135">Teams 対応の電話機</span><span class="sxs-lookup"><span data-stu-id="1a31a-135">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="1a31a-136">Microsoft Teams 認定 IP 電話</span><span class="sxs-lookup"><span data-stu-id="1a31a-136">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="1a31a-137">Teams表示</span><span class="sxs-lookup"><span data-stu-id="1a31a-137">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="1a31a-138">Teams でのデバイスの管理</span><span class="sxs-lookup"><span data-stu-id="1a31a-138">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="1a31a-139">Teams Marketplace</span><span class="sxs-lookup"><span data-stu-id="1a31a-139">Teams Marketplace</span></span>](https://office.com/teamsdevices)