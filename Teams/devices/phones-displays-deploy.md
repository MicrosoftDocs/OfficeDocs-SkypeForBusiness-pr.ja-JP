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
ms.openlocfilehash: ee5b536aaadaf458b6edf9b32dea299a3ecad9a0
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420822"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="85f28-103">Intune をTeamsして携帯電話とTeamsディスプレイをデプロイする</span><span class="sxs-lookup"><span data-stu-id="85f28-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="85f28-104">この記事では、デプロイ方法の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="85f28-104">This article gives you an overview of how to deploy.</span></span> <span data-ttu-id="85f28-105">Teams Intune を使用してTeams表示する。</span><span class="sxs-lookup"><span data-stu-id="85f28-105">Teams phones and Teams display using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="85f28-106">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="85f28-106">Conditional Access</span></span>

<span data-ttu-id="85f28-107">条件付きアクセスはAzure Active Directory (Azure AD) 機能であり、Office 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されていることを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="85f28-107">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="85f28-108">Teams サービスに条件付きアクセス ポリシーを適用する場合、Teams にアクセスする Android デバイス (Teams スマートフォンや Teams ディスプレイを含む) は Intune に登録する必要があります。設定はポリシーに準拠する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85f28-108">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams needs to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="85f28-109">デバイスが Intune に登録されていない場合、またはデバイスが登録されているが、その設定がポリシーに準拠しない場合、条件付きアクセスでは、ユーザーがデバイスで Teams アプリにサインインまたは使用できません。</span><span class="sxs-lookup"><span data-stu-id="85f28-109">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="85f28-110">通常、Intune 内で定義されたコンプライアンス ポリシーは、ユーザーのグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="85f28-110">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="85f28-111">つまり、android コンプライアンス ポリシーを user@contoso.com に割り当てると、そのポリシーは Android スマートフォンと、サインインする Android ベースの Teams デバイスにも同様 user@contoso.com 適用されます。</span><span class="sxs-lookup"><span data-stu-id="85f28-111">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="85f28-112">Intune 登録を適用する必要がある条件付きアクセスを使用する場合、組織では、Intune 登録を正常に行うには、次の 2 つの設定が必要です。</span><span class="sxs-lookup"><span data-stu-id="85f28-112">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="85f28-113">**Intune ライセンス** デバイスにサインインするユーザー Teams Intune のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="85f28-113">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="85f28-114">Teams デバイスが有効な Intune ライセンスを持つユーザー アカウントにサインインしている限り、デバイスはサインイン プロセスの一環として Microsoft Intune に自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="85f28-114">As long as the Teams device is signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="85f28-115">**Intune の構成** Android デバイス管理者登録用に適切に構成された Intune テナントが設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="85f28-115">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="85f28-116">Android ベースのデバイスにTeams Intune を構成する</span><span class="sxs-lookup"><span data-stu-id="85f28-116">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="85f28-117">TeamsAndroid ベースのデバイスは、Android デバイス管理者 (DA) 管理を介して Intune によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="85f28-117">Teams Android-based devices are managed by Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="85f28-118">デバイスを Intune に登録する前に、いくつかの基本的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="85f28-118">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="85f28-119">Intune でデバイスを既に管理している場合は、既にこれらすべてのことを行っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="85f28-119">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="85f28-120">ない場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="85f28-120">If not, here’s what to do:</span></span>

> [!NOTE]
> - <span data-ttu-id="85f28-121">テナント管理者が共通領域の電話を Intune に登録する場合は、Intune ライセンスをアカウントに追加し、Intune 登録の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="85f28-121">If tenant admins want common area phones to be enrolled into Intune, they need to add an Intune license to the account and follow the steps for Intune enrollment.</span></span>
> - <span data-ttu-id="85f28-122">Teams デバイスへのサインインに使用したユーザー アカウントが Intune のライセンスを取得されていない場合は、Intune コンプライアンス ポリシーと登録制限をアカウントで無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="85f28-122">If the user account used to sign into a Teams device isn't licensed for Intune, Intune compliance policies and enrollment restrictions need to be disabled for the account.</span></span>



1. <span data-ttu-id="85f28-123">Intune MDM (モバイル デバイス管理) 機関を設定します。</span><span class="sxs-lookup"><span data-stu-id="85f28-123">Set Intune MDM (mobile device management) Authority.</span></span>  

   <span data-ttu-id="85f28-124">Intune を使用したことがない場合は、デバイスを登録する前に MDM 機関を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85f28-124">If you’ve never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="85f28-125">詳細については、「モバイル デバイス管理 [機関を設定する」を参照してください](/intune/fundamentals/mdm-authority-set)。</span><span class="sxs-lookup"><span data-stu-id="85f28-125">For more information, see [Set the mobile device management authority](/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="85f28-126">これは、新しい Intune テナントを作成するときに実行する必要がある 1 回の手順です。</span><span class="sxs-lookup"><span data-stu-id="85f28-126">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
1. <span data-ttu-id="85f28-127">Android デバイス管理者登録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="85f28-127">Enable Android device administrator enrollment.</span></span>
  
   <span data-ttu-id="85f28-128">Android ベースのTeamsデバイスは、Intune を使用してデバイス管理者デバイスとして管理されます。</span><span class="sxs-lookup"><span data-stu-id="85f28-128">Android-based Teams devices are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="85f28-129">新しく作成されたテナントでは、デバイス管理者の登録は既定でオフになっています。</span><span class="sxs-lookup"><span data-stu-id="85f28-129">Device administrator enrollment is off by default for newly created tenants.</span></span> <span data-ttu-id="85f28-130">「Android [デバイス管理者の登録」を参照してください](/intune/enrollment/android-enroll-device-administrator)。</span><span class="sxs-lookup"><span data-stu-id="85f28-130">See [Android device administrator enrollment](/intune/enrollment/android-enroll-device-administrator).</span></span>
1. <span data-ttu-id="85f28-131">ユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="85f28-131">Assign licenses to users.</span></span> 
 
   <span data-ttu-id="85f28-132">Intune にTeamsデバイスのユーザーには、有効な Intune ライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="85f28-132">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="85f28-133">詳細については、「ユーザーが Intune にデバイスを [登録できるようライセンスをユーザーに割り当てる」を参照してください](/intune/fundamentals/licenses-assign)。</span><span class="sxs-lookup"><span data-stu-id="85f28-133">For more information, see [Assign licenses to users so they can enroll devices in Intune](/intune/fundamentals/licenses-assign).</span></span>
1. <span data-ttu-id="85f28-134">デバイス管理者のコンプライアンス ポリシーを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="85f28-134">Assign Device Administrator compliance policies.</span></span>  

   <span data-ttu-id="85f28-135">a.</span><span class="sxs-lookup"><span data-stu-id="85f28-135">a.</span></span> <span data-ttu-id="85f28-136">Android デバイス管理者のコンプライアンス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="85f28-136">Create an Android Device Administrator compliance policy.</span></span>

   <span data-ttu-id="85f28-137">b.</span><span class="sxs-lookup"><span data-stu-id="85f28-137">b.</span></span> <span data-ttu-id="85f28-138">デバイスにサインインするAzure Active Directoryを含むグループに割り当Teamsします。</span><span class="sxs-lookup"><span data-stu-id="85f28-138">Assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="85f28-139">[「コンプライアンス ポリシーを使用して Intune で管理するデバイスのルールを設定する」を参照してください](/mem/intune/protect/device-compliance-get-started)。</span><span class="sxs-lookup"><span data-stu-id="85f28-139">See [Use compliance policies to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="85f28-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="85f28-140">See also</span></span>

[<span data-ttu-id="85f28-141">Teams 対応の電話機</span><span class="sxs-lookup"><span data-stu-id="85f28-141">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="85f28-142">Microsoft Teams 認定 IP 電話</span><span class="sxs-lookup"><span data-stu-id="85f28-142">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="85f28-143">Teams表示</span><span class="sxs-lookup"><span data-stu-id="85f28-143">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="85f28-144">Teams でのデバイスの管理</span><span class="sxs-lookup"><span data-stu-id="85f28-144">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="85f28-145">Teams Marketplace</span><span class="sxs-lookup"><span data-stu-id="85f28-145">Teams Marketplace</span></span>](https://office.com/teamsdevices)