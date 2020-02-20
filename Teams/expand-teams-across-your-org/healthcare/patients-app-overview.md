---
title: 'Teams 管理者用の患者アプリ '
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
description: Teams 管理者用の患者アプリ
ms.openlocfilehash: 4c4eaced1b7e3c328d589906ac50cfb8ac805ea3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153789"
---
# <a name="patients-app-overview"></a><span data-ttu-id="e0341-103">患者アプリの概要</span><span class="sxs-lookup"><span data-stu-id="e0341-103">Patients app overview</span></span>

<span data-ttu-id="e0341-104">患者アプリケーションは、Microsoft Teams ストアアプリで、すべての Teams ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="e0341-104">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="e0341-105">このアプリを使用すると、患者の治療チーム (看護師、医師、社会員など) が患者の一覧を表示して、ラウンドやアプリの会議から一般的な患者の監視まで、患者のリストを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e0341-105">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>

<span data-ttu-id="e0341-106">このアプリには、次の2つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="e0341-106">The app has two modes:</span></span>

- <span data-ttu-id="e0341-107">Emr から FHIR に接続する EMR 接続モード。</span><span class="sxs-lookup"><span data-stu-id="e0341-107">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="e0341-108">EMR 接続モードのアプリはプライベートプレビューのままであり、ユーザーまたは管理者は、Office 365 テナントに関する情報を使用して[teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)に Microsoft をドロップして、アプリへのアクセスを要求することがあります。</span><span class="sxs-lookup"><span data-stu-id="e0341-108">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) with information about their Office 365 tenant.</span></span>
- <span data-ttu-id="e0341-109">治療チームが患者情報を手動で追加/取り込みできる手動モード。</span><span class="sxs-lookup"><span data-stu-id="e0341-109">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="e0341-110">アプリケーションは、Teams app store で利用可能で、エンドユーザーはプライベートプレビューでダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0341-110">The application is available in the Teams app store for end users to download in private preview.</span></span> <span data-ttu-id="e0341-111">アプリは、Teams の[アプリセットアップポリシー](../../teams-app-setup-policies.md)を使用して、ユーザーの特定のセクションに制限することができます。</span><span class="sxs-lookup"><span data-stu-id="e0341-111">The app can be restricted to certain sections of users using [app setup policies](../../teams-app-setup-policies.md) in Teams.</span></span> <span data-ttu-id="e0341-112">アプリへのアクセスを取得するには、テナントがテクノロジ導入プログラムに含まれている必要があります (タップ)。</span><span class="sxs-lookup"><span data-stu-id="e0341-112">To get access to the app, your tenant needs to be part of the Technology Adoption Program (TAP).</span></span> <span data-ttu-id="e0341-113">[Teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)でメールを削除して、アクセス権を要求するプロセスを開始してください。</span><span class="sxs-lookup"><span data-stu-id="e0341-113">Please drop us an email at [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) to start the process to request access.</span></span>

## <a name="usage-example"></a><span data-ttu-id="e0341-114">使用例</span><span class="sxs-lookup"><span data-stu-id="e0341-114">Usage example</span></span>

<span data-ttu-id="e0341-115">医療 wards の各シフトでの丸めセッション中に、clinicians は nursing ステーションで収集して、の患者との進行状況に関する最新の更新について話し合うことができます。</span><span class="sxs-lookup"><span data-stu-id="e0341-115">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="e0341-116">また、重要な指標 (医療、患者の医療記録での明示的なものではありません) を強調表示し、お客様の診断に基づいて患者が適切なグライドパス上にいることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0341-116">They highlight the key critical metrics (not necessarily medical or that its explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="e0341-117">このような患者を丸めるために、クレジットの追加により、すべての clinicians が追加され、患者リストに患者が追加されるようになります。</span><span class="sxs-lookup"><span data-stu-id="e0341-117">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="e0341-118">ラウンドでは、患者との間の看護師とその他のケア givers によって、モバイルデバイス上の Microsoft Teams と患者アプリの情報が更新され、お客様のデバイスに関連する患者情報が更新され、ケアチーム内の他の参加者に対してそれらの更新とメモを表示することができます。常に同期します。1日に2回、シフトの開始時と終了時には、患者リストを超えて患者の一覧を表示し、患者のアプリを使って患者の顔を見ながら、大きなディスプレイ画面で患者のアプリを使って情報を共有することができます。</span><span class="sxs-lookup"><span data-stu-id="e0341-118">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-disciplinary team meetings to go over the patient list and use the Patients app to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="e0341-119">場合によっては、特定の clinicians が、それらのチーム会議にリモートでダイヤルインしても、ディスカッションの一部となることがあります。</span><span class="sxs-lookup"><span data-stu-id="e0341-119">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span>

## <a name="configure-patients-app"></a><span data-ttu-id="e0341-120">患者のアプリを設定する</span><span class="sxs-lookup"><span data-stu-id="e0341-120">Configure Patients app</span></span>

<span data-ttu-id="e0341-121">EMR モードの患者アプリを使用するように環境を準備する方法について詳しくは、「 [Microsoft Teams への電子医療記録の統合](patients-app.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e0341-121">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="e0341-122">また、組織で患者のアプリを有効にするには、「 [Microsoft Teams でアプリセットアップポリシーを管理](../../teams-app-setup-policies.md)する」を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0341-122">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<span data-ttu-id="e0341-123">エンドユーザーが患者アプリにアクセスして、所有または管理しているチームにインストールする方法については、「 [Microsoft Teams の使用を開始](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0341-123">For information on how your end users can access and install the Patients App to a team that they own or manage, see [Get started with Microsoft Teams Patients](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)</span></span> 

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a><span data-ttu-id="e0341-124">よく寄せられる質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="e0341-124">Frequently asked questions (FAQ)</span></span>

<span data-ttu-id="e0341-125">**患者のアプリデータはどこに保存されますか?**</span><span class="sxs-lookup"><span data-stu-id="e0341-125">**Where is the Patients app data stored?**</span></span>

<span data-ttu-id="e0341-126">エンドユーザーによって [患者] アプリに入力されたすべてのデータ (たとえば、列/フィールドスキーマ、リストとリストアイテム (患者) に入力された実際のデータ) は、セキュリティで保護された、互換性のある Exchange Online インフラストラクチャに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e0341-126">All of the data entered by end users into the Patients app, including the column/field schema, the actual data entered into the list and list items (i.e. patients), is stored in the secure and compliant Exchange Online infrastructure.</span></span> <span data-ttu-id="e0341-127">すべてのデータは、チームに関連付けられているグループメールボックスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e0341-127">All of the data is stored in the group mailbox that's associated with the team.</span></span> <span data-ttu-id="e0341-128">このアーキテクチャにより、患者アプリは、データ常駐サービス、行政機関向けクラウドサポート (将来の予定)、および eDiscovery サポートなどのその他のコンプライアンス/情報保護機能を簡単に満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="e0341-128">This architecture enables the Patients App to easily fulfill data residency, government cloud support (coming in the future) and other compliance/information protection features like eDiscovery support.</span></span> <span data-ttu-id="e0341-129">患者アプリは、チームのスコープで動作します。</span><span class="sxs-lookup"><span data-stu-id="e0341-129">The Patients app operates in a team scope.</span></span> <span data-ttu-id="e0341-130">チームごとにアプリのインスタンスをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0341-130">You will need to install an instance of the app per team.</span></span>

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

<span data-ttu-id="e0341-131">**患者アプリの入手方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="e0341-131">**Where can I acquire the Patients App from?**</span></span>

<span data-ttu-id="e0341-132">管理者によって、自分の組織に対して患者のアプリが有効になっている場合、すべてのエンドユーザーは Teams app store にアクセスして、自分がメンバーになっているチームに患者アプリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e0341-132">If the Patients app is enabled for their organization by their admin, any end user can go to the Teams app store and add the Patients app to a team they are a member of.</span></span> <span data-ttu-id="e0341-133">詳細については、「 [Microsoft Teams でアプリセットアップポリシーを管理](../../teams-app-setup-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0341-133">For more information, see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md).</span></span>

<span data-ttu-id="e0341-134">**自分のワード/ユニットの動作によって、チーム内に複数のインスタンスを含めることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="e0341-134">**Can I have multiple instances of the Patients app in a team because that's how my ward/unit operates?**</span></span>

<span data-ttu-id="e0341-135">現時点では、特定のチームに対してのみ、または [全般] チャネルにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e0341-135">Currently, you can only install one instance of the Patients app for a given team, and only in the general channel.</span></span> <span data-ttu-id="e0341-136">ただし、アプリ内では、複数のチャネルまたは分離シナリオに対応するために複数のリストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e0341-136">However, within the app, multiple lists can be created to address multi-channel or isolation/separation scenarios.</span></span> <span data-ttu-id="e0341-137">既定では、チームのすべてのメンバーは、[全般] チャネルの [患者] タブにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e0341-137">By default, all members of the team will have access to the Patients tab in the general channel.</span></span> 

<span data-ttu-id="e0341-138">**患者アプリからすべてのデータをエクスポートすることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="e0341-138">**Can I export all of the data from the Patients app?**</span></span>
<span data-ttu-id="e0341-139">現時点ではできませんが、この機能は近日中に公開されます。</span><span class="sxs-lookup"><span data-stu-id="e0341-139">Not right now, but this feature is coming soon.</span></span> 

<span data-ttu-id="e0341-140">**このアプリは PHI に対応しているため、不正アクセスや規制への準拠を防ぐ監査もありますか?**</span><span class="sxs-lookup"><span data-stu-id="e0341-140">**Since this app accommodates PHI, is there auditing to prevent unauthorized access or compliance with regulations?**</span></span>

<span data-ttu-id="e0341-141">はい、あります。</span><span class="sxs-lookup"><span data-stu-id="e0341-141">Yes, there is.</span></span> <span data-ttu-id="e0341-142">患者のアプリで Microsoft Teams ユーザーによって実行されるすべての UI 操作が監査され、セキュリティ/コンプライアンスセンターで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="e0341-142">Every single UI action performed by a Microsoft Teams user on the Patients app is audited and available in the security and compliance center.</span></span> <span data-ttu-id="e0341-143">詳細については、こちらの記事を参照して[ください](patients-audit.md)。</span><span class="sxs-lookup"><span data-stu-id="e0341-143">The details are explained in the article [here](patients-audit.md)</span></span>

## <a name="related-topics"></a><span data-ttu-id="e0341-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e0341-144">Related topics</span></span>

[<span data-ttu-id="e0341-145">電子医療記録を Microsoft Teams に統合する</span><span class="sxs-lookup"><span data-stu-id="e0341-145">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
