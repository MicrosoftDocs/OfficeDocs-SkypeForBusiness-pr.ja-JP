---
title: 'Teams 管理者向けの患者アプリ '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Teams 管理者向けの患者アプリの詳細
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2302f117564e1dd00a6f238ca23a8e36c63ae554
ms.sourcegitcommit: e6e6a2a85ff376f97a3af3548e13d1273fa84a52
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697844"
---
# <a name="patients-app-overview"></a><span data-ttu-id="0cfb0-103">患者アプリの概要</span><span class="sxs-lookup"><span data-stu-id="0cfb0-103">Patients app overview</span></span>

> [!NOTE]
> <span data-ttu-id="0cfb0-104">2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="0cfb0-105">患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="0cfb0-106">患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="0cfb0-107">ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="0cfb0-108">リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="0cfb0-109">開始するには、リストの患者テンプレートを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="0cfb0-110">組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="0cfb0-111">患者アプリケーションは、すべての Teams ユーザーが利用できる Microsoft Teams ストア アプリです。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-111">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="0cfb0-112">このアプリを使用すると、臨床従事者 (看護師、医師、ソーシャル ワーカーなど) で構成される患者医療チームが、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで、患者のリストをキュレートして確認できます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-112">The app enables patient health teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>

<span data-ttu-id="0cfb0-113">アプリには 2 つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-113">The app has two modes:</span></span>

- <span data-ttu-id="0cfb0-114">FHIR を介して EMR に接続する EMR 接続モード。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-114">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="0cfb0-115">EMR 接続モード アプリはプライベート プレビューであり、関心のある顧客または管理者は、Microsoft 365 組織に関する情報を記載したメールを [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) にドロップすることにより、アプリへのアクセスを要求できます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-115">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) with information about their Microsoft 365 organization.</span></span>
- <span data-ttu-id="0cfb0-116">医療チームが患者情報を手動で追加/取り込むことができる手動モード。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-116">The manual mode that enables health teams to manually add/bring in patient information.</span></span> <span data-ttu-id="0cfb0-117">アプリケーションは、Teams アプリ ストアで入手し、エンド ユーザーがプライベート プレビューでダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-117">The application is available in the Teams app store for end users to download in private preview.</span></span> <span data-ttu-id="0cfb0-118">Teams で[アプリのセットアップ ポリシー](../../teams-app-setup-policies.md)を使用すると、アプリをユーザーの特定のセクションに制限できます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-118">The app can be restricted to certain sections of users using [app setup policies](../../teams-app-setup-policies.md) in Teams.</span></span> <span data-ttu-id="0cfb0-119">アプリにアクセスするには、テナントがテクノロジ採用プログラム (TAP) に参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-119">To get access to the app, your tenant needs to be part of the Technology Adoption Program (TAP).</span></span> <span data-ttu-id="0cfb0-120">アクセスを要求するプロセスを開始するには、[teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) にメールをお送りください。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-120">Please drop us an email at [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) to start the process to request access.</span></span>

## <a name="usage-example"></a><span data-ttu-id="0cfb0-121">使用例</span><span class="sxs-lookup"><span data-stu-id="0cfb0-121">Usage example</span></span>

<span data-ttu-id="0cfb0-122">病棟のシフトごとのラウンド セッション中に、臨床医が看護ステーションに集まり、病棟の患者と現在の進行状況について話し合います。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-122">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="0cfb0-123">重要な測定基準 (必ずしも医学的である必要はなく、患者の医療記録において明示的である必要はありません) を強調表示し、患者が診断に基づいて退院するための正しいグライド パスにいることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-123">They highlight the key critical metrics (not necessarily medical or that it's explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="0cfb0-124">これらの患者をラウンドするために、担当看護師はチームに患者アプリを設定し、そこにすべての臨床医が追加され、患者は患者リストに追加されます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-124">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="0cfb0-125">ラウンド中、患者の看護師やその他の介護者は、モバイル デバイスで Microsoft Teams と患者アプリにアクセスし、デバイスで関連する患者情報を更新します。その後、医療チームの他の全員がそれらの更新とメモを確認して、 同期します。1 日 2 回、シフトの開始時と終了時に、患者リストを確認し、患者アプリを使用して、現状を把握し、大きなディスプレイ画面の患者アプリを使用して各患者に関する情報を共有する、学際的なチーム会議もあります。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-125">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the health team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-disciplinary team meetings to go over the patient list and use the Patients app to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="0cfb0-126">しばしば、特定の臨床医は、これらの Teams の会議にリモートでダイヤルインして、ディスカッションに参加することもあります。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-126">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span>

## <a name="configure-patients-app"></a><span data-ttu-id="0cfb0-127">患者アプリを構成する</span><span class="sxs-lookup"><span data-stu-id="0cfb0-127">Configure Patients app</span></span>

<span data-ttu-id="0cfb0-128">組織[で Patients アプリを有効にするには、「Microsoft Teams](../../teams-app-setup-policies.md)のアプリ セットアップ ポリシーの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-128">See [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<span data-ttu-id="0cfb0-129">エンド ユーザーが患者アプリにアクセスして、所有または管理するチームにインストールする方法については、「[Microsoft Teams 患者アプリの使用を開始する](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-129">For information on how your end users can access and install the Patients App to a team that they own or manage, see [Get started with Microsoft Teams Patients](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).</span></span>

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a><span data-ttu-id="0cfb0-130">よく寄せられる質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="0cfb0-130">Frequently asked questions (FAQ)</span></span>

<span data-ttu-id="0cfb0-131">**患者アプリのデータはどこに保存されますか?**</span><span class="sxs-lookup"><span data-stu-id="0cfb0-131">**Where is the Patients app data stored?**</span></span>

<span data-ttu-id="0cfb0-132">列/フィールド スキーマ、リストおよびリスト アイテム (患者など) に入力された実際のデータを含む、エンド ユーザーが患者アプリに入力したすべてのデータは、安全で準拠した Exchange Online インフラストラクチャに保存されます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-132">All of the data entered by end users into the Patients app, including the column/field schema, the actual data entered into the list and list items (i.e. patients), is stored in the secure and compliant Exchange Online infrastructure.</span></span> <span data-ttu-id="0cfb0-133">すべてのデータは、チームに関連付けられているグループ メールボックスに保存されます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-133">All of the data is stored in the group mailbox that's associated with the team.</span></span> <span data-ttu-id="0cfb0-134">このアーキテクチャにより、患者アプリは、データの常駐、政府のクラウド サポート (将来的に予定)、および電子情報開示サポートなどの他のコンプライアンス/情報保護機能を簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-134">This architecture enables the Patients App to easily fulfill data residency, government cloud support (coming in the future) and other compliance/information protection features like eDiscovery support.</span></span> <span data-ttu-id="0cfb0-135">患者アプリはチームの範囲で動作します。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-135">The Patients app operates in a team scope.</span></span> <span data-ttu-id="0cfb0-136">チームごとにアプリのインスタンスをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-136">You will need to install an instance of the app per team.</span></span>

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

<span data-ttu-id="0cfb0-137">**患者アプリはどこから入手できますか?**</span><span class="sxs-lookup"><span data-stu-id="0cfb0-137">**Where can I acquire the Patients App from?**</span></span>

<span data-ttu-id="0cfb0-138">管理者が患者アプリを組織で有効にしている場合、すべてのエンド ユーザーは Teams アプリ ストアにアクセスして、患者アプリをメンバーのチームに追加できます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-138">If the Patients app is enabled for their organization by their admin, any end user can go to the Teams app store and add the Patients app to a team they are a member of.</span></span> <span data-ttu-id="0cfb0-139">詳細については、「[Microsoft Teams でアプリのセットアップ ポリシーを管理する](../../teams-app-setup-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-139">For more information, see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md).</span></span>

<span data-ttu-id="0cfb0-140">**病棟/ユニットの運用方法として、チームに患者アプリの複数のインスタンスを含めることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="0cfb0-140">**Can I have multiple instances of the Patients app in a team because that's how my ward/unit operates?**</span></span>

<span data-ttu-id="0cfb0-141">現在、与えられたチームにインストールできるのは、患者アプリのインスタンス 1 つだけで、全般チャネルにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-141">Currently, you can only install one instance of the Patients app for a given team, and only in the general channel.</span></span> <span data-ttu-id="0cfb0-142">ただし、アプリ内で複数のリストを作成して、マルチチャネルまたは分離/区分のシナリオに対応できます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-142">However, within the app, multiple lists can be created to address multi-channel or isolation/separation scenarios.</span></span> <span data-ttu-id="0cfb0-143">既定では、チームのすべてのメンバーが全般チャネルの [患者] タブにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-143">By default, all members of the team will have access to the Patients tab in the general channel.</span></span> 

<span data-ttu-id="0cfb0-144">**患者アプリからすべてのデータをエクスポートできますか?**</span><span class="sxs-lookup"><span data-stu-id="0cfb0-144">**Can I export all of the data from the Patients app?**</span></span>
<span data-ttu-id="0cfb0-145">現在はありませんが、この機能はまもなく登場します。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-145">Not right now, but this feature is coming soon.</span></span> 

<span data-ttu-id="0cfb0-146">**このアプリは PHI に対応しているので、不正アクセスを防ぎ、規制に準拠するための監査はありますか?**</span><span class="sxs-lookup"><span data-stu-id="0cfb0-146">**Since this app accommodates PHI, is there auditing to prevent unauthorized access or compliance with regulations?**</span></span>

<span data-ttu-id="0cfb0-147">はい、あります。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-147">Yes, there is.</span></span> <span data-ttu-id="0cfb0-148">Microsoft Teams ユーザーが患者アプリで実行するすべての UI アクションは監査され、セキュリティ/コンプライアンス センターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-148">Every single UI action performed by a Microsoft Teams user on the Patients app is audited and available in the security and compliance center.</span></span> <span data-ttu-id="0cfb0-149">詳細は、「[患者アプリの監査ログ](patients-audit.md)」で説明されています。</span><span class="sxs-lookup"><span data-stu-id="0cfb0-149">The details are explained in [Audit logs for Patients app](patients-audit.md).</span></span>

