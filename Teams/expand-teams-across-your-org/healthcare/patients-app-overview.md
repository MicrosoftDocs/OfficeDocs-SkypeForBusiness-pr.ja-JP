---
title: 'Teams 管理者用の患者アプリ '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: Teams 管理者用の患者アプリ
ms.openlocfilehash: 85f0d382de11b9259c6839aa8d0e556ad2512f5a
ms.sourcegitcommit: 2064c94eae82a5453674d38f0b28dcd6dc5c370e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "37885501"
---
# <a name="patients-app-overview"></a><span data-ttu-id="374b9-103">患者アプリの概要</span><span class="sxs-lookup"><span data-stu-id="374b9-103">Patients app overview</span></span>

<span data-ttu-id="374b9-104">患者アプリケーションは、Microsoft Teams ストアアプリで、すべての Teams ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="374b9-104">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="374b9-105">このアプリを使用すると、患者の治療チーム (看護師、医師、社会員など) が患者の一覧を表示して、ラウンドやアプリの会議から一般的な患者の監視まで、患者のリストを確認できます。</span><span class="sxs-lookup"><span data-stu-id="374b9-105">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>   

<span data-ttu-id="374b9-106">このアプリには、次の2つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="374b9-106">The app has two modes:</span></span> 

- <span data-ttu-id="374b9-107">Emr から FHIR に接続する EMR 接続モード。</span><span class="sxs-lookup"><span data-stu-id="374b9-107">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="374b9-108">EMR 接続モードのアプリはプライベートプレビューのままであり、ユーザーまたは管理者は、Office 365 テナントに関する情報を使用して teamsforhealthcare@service.microsoft.com に Microsoft をドロップして、アプリへのアクセスを要求することがあります。</span><span class="sxs-lookup"><span data-stu-id="374b9-108">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at teamsforhealthcare@service.microsoft.com with information about their Office 365 tenant.</span></span> 
- <span data-ttu-id="374b9-109">治療チームが患者情報を手動で追加/取り込みできる手動モード。</span><span class="sxs-lookup"><span data-stu-id="374b9-109">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="374b9-110">このアプリケーションは、Teams app store で利用できます。これは、エンドユーザーが既定でダウンロードするためであり、パブリックプレビューに含まれています。</span><span class="sxs-lookup"><span data-stu-id="374b9-110">The application is available in the Teams app store for end users to download by default and is in public preview.</span></span> <span data-ttu-id="374b9-111">[Microsoft Teams のアプリセットアップポリシー](../../teams-app-setup-policies.md)を使用するユーザーの特定のセクションにアプリを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="374b9-111">The app can be restricted to certain sections of users using [app setup policies in Microsoft Teams](../../teams-app-setup-policies.md)</span></span>



## <a name="usage-example"></a><span data-ttu-id="374b9-112">使用例</span><span class="sxs-lookup"><span data-stu-id="374b9-112">Usage example</span></span>

<span data-ttu-id="374b9-113">医療 wards の各シフトでの丸めセッション中に、clinicians は nursing ステーションで収集して、の患者との進行状況に関する最新の更新について話し合うことができます。</span><span class="sxs-lookup"><span data-stu-id="374b9-113">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="374b9-114">また、重要な指標 (医療、患者の医療記録での明示的なものではありません) を強調表示し、お客様の診断に基づいて患者が適切なグライドパス上にいることを確認します。</span><span class="sxs-lookup"><span data-stu-id="374b9-114">They highlight the key critical metrics (not necessarily medical or that its explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="374b9-115">このような患者を丸めるために、クレジットの追加により、すべての clinicians が追加され、患者リストに患者が追加されるようになります。</span><span class="sxs-lookup"><span data-stu-id="374b9-115">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="374b9-116">ラウンドでは、患者との間の看護師とその他のケア givers によって、モバイルデバイス上の Microsoft Teams と患者アプリの情報が更新され、お客様のデバイスに関連する患者情報が更新され、ケアチーム内の他の参加者に対してそれらの更新とメモを表示することができます。常に同期します。1日に2回、シフトの開始時と終了時には、マルチ displicinary のチーム会議も用意されています。これには、患者リストを経由して患者の一覧を表示したり、患者のアプリを使って患者の情報を共有したりできます。</span><span class="sxs-lookup"><span data-stu-id="374b9-116">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-displicinary team meetings to go over the patient list and use the Patients App to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="374b9-117">場合によっては、特定の clinicians が、それらのチーム会議にリモートでダイヤルインしても、ディスカッションの一部となることがあります。</span><span class="sxs-lookup"><span data-stu-id="374b9-117">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span> 

## <a name="configure-patients-app"></a><span data-ttu-id="374b9-118">患者のアプリを設定する</span><span class="sxs-lookup"><span data-stu-id="374b9-118">Configure Patients app</span></span>

<span data-ttu-id="374b9-119">EMR モードの患者アプリを使用するように環境を準備する方法について詳しくは、「 [Microsoft Teams への電子医療記録の統合](patients-app.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="374b9-119">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="374b9-120">また、組織で患者のアプリを有効にするには、「 [Microsoft Teams でアプリセットアップポリシーを管理](../../teams-app-setup-policies.md)する」を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="374b9-120">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a><span data-ttu-id="374b9-121">よく寄せられる質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="374b9-121">Frequently asked questions (FAQ)</span></span>

<span data-ttu-id="374b9-122">**患者のアプリデータはどこに保存されますか?**</span><span class="sxs-lookup"><span data-stu-id="374b9-122">**Where is the Patients app data stored?**</span></span>

<span data-ttu-id="374b9-123">エンドユーザーによって [患者] アプリに入力されたすべてのデータ (たとえば、列/フィールドスキーマ、リストとリストアイテム (患者) に入力された実際のデータ) は、セキュリティで保護された、互換性のある Exchange Online インフラストラクチャに格納されます。</span><span class="sxs-lookup"><span data-stu-id="374b9-123">All of the data entered by end users into the Patients App, including the column/field schema, the actual data entered into the list and list items (i.e. patients), is stored in the secure and compliant Exchange Online infrastructure.</span></span> <span data-ttu-id="374b9-124">すべてのデータは、チームに関連付けられているグループメールボックスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="374b9-124">All of the data is stored in the group mailbox that's associated with the team.</span></span> <span data-ttu-id="374b9-125">このアーキテクチャにより、患者アプリは、データ常駐サービス、行政機関向けクラウドサポート (将来の予定)、および eDiscovery サポートなどのその他のコンプライアンス/情報保護機能を簡単に満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="374b9-125">This architecture enables the Patients App to easily fulfill data residency, government cloud support (coming in the future) and other compliance/information protection features like eDiscovery support.</span></span> <span data-ttu-id="374b9-126">患者アプリは、チームのスコープで動作します。</span><span class="sxs-lookup"><span data-stu-id="374b9-126">The Patients app operates in a team scope.</span></span> <span data-ttu-id="374b9-127">チームごとにアプリのインスタンスをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="374b9-127">You will need to install an instance of the app per team.</span></span>

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

<span data-ttu-id="374b9-128">**患者アプリの入手方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="374b9-128">**Where can I acquire the Patients App from?**</span></span>

<span data-ttu-id="374b9-129">管理者によって、自分の組織に対して患者のアプリが有効になっている場合、すべてのエンドユーザーは Teams app store にアクセスして、自分がメンバーになっているチームに患者アプリを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="374b9-129">If the Patients app is enabled for their organization by their admin, any end user can go to the Teams app store and add the Patients app to a team they are a member of.</span></span> <span data-ttu-id="374b9-130">詳細については、「 [Microsoft Teams でアプリセットアップポリシーを管理](../../teams-app-setup-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="374b9-130">For more information, see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md).</span></span>

<span data-ttu-id="374b9-131">**自分のワード/ユニットの動作によって、チーム内に複数のインスタンスを含めることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="374b9-131">**Can I have multiple instances of the Patients app in a team because that's how my ward/unit operates?**</span></span>

<span data-ttu-id="374b9-132">現時点では、特定のチームに対してのみ、または [全般] チャネルにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="374b9-132">Currently, you can only install one instance of the Patients app for a given team, and only in the general channel.</span></span> <span data-ttu-id="374b9-133">ただし、アプリ内では、複数のチャネルまたは分離シナリオに対応するために複数のリストを作成できます。</span><span class="sxs-lookup"><span data-stu-id="374b9-133">However, within the app, multiple lists can be created to address multi-channel or isolation/separation scenarios.</span></span> <span data-ttu-id="374b9-134">既定では、チームのすべてのメンバーは、[全般] チャネルの [患者] タブにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="374b9-134">By default, all members of the team will have access to the Patients tab in the general channel.</span></span> 

<span data-ttu-id="374b9-135">**患者アプリからすべてのデータをエクスポートすることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="374b9-135">**Can I export all of the data from the Patients app?**</span></span>
<span data-ttu-id="374b9-136">現時点ではできませんが、この機能は近日中に公開されます。</span><span class="sxs-lookup"><span data-stu-id="374b9-136">Not right now, but this feature is coming soon.</span></span> 

<span data-ttu-id="374b9-137">**このアプリは PHI に対応しているため、不正アクセスや規制への準拠を防ぐ監査もありますか?**</span><span class="sxs-lookup"><span data-stu-id="374b9-137">**Since this app accommodates PHI, is there auditing to prevent unauthorized access or compliance with regulations?**</span></span>

<span data-ttu-id="374b9-138">はい、あります。</span><span class="sxs-lookup"><span data-stu-id="374b9-138">Yes, there is.</span></span> <span data-ttu-id="374b9-139">患者のアプリで Microsoft Teams ユーザーによって実行されるすべての UI 操作が監査され、セキュリティ/コンプライアンスセンターで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="374b9-139">Every single UI action performed by a Microsoft Teams user on the Patients app is audited and available in the security and compliance center.</span></span> <span data-ttu-id="374b9-140">詳細については、こちらの記事を参照して[ください](patients-audit.md)。</span><span class="sxs-lookup"><span data-stu-id="374b9-140">The details are explained in the article [here](patients-audit.md)</span></span>


## <a name="related-topics"></a><span data-ttu-id="374b9-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="374b9-141">Related topics</span></span>

[<span data-ttu-id="374b9-142">電子医療記録を Microsoft Teams に統合する</span><span class="sxs-lookup"><span data-stu-id="374b9-142">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
