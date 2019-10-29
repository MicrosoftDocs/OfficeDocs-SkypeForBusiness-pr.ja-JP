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
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749559"
---
# <a name="patients-app-overview"></a><span data-ttu-id="57ebe-103">Patients アプリの概要</span><span class="sxs-lookup"><span data-stu-id="57ebe-103">Patients app overview</span></span>

<span data-ttu-id="57ebe-104">患者アプリケーションは、Microsoft Teams ストアアプリで、すべての Teams ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="57ebe-104">The Patients application is a Microsoft Teams store app available to all Teams users.</span></span> <span data-ttu-id="57ebe-105">このアプリを使用すると、患者の治療チーム (看護師、医師、社会員など) が患者の一覧を表示して、ラウンドやアプリの会議から一般的な患者の監視まで、患者のリストを確認できます。</span><span class="sxs-lookup"><span data-stu-id="57ebe-105">The app enables patient care teams consisting of clinical workers (e.g. Nurses, physicians, social workers) can curate and review lists of patients for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span>   

<span data-ttu-id="57ebe-106">このアプリには、次の2つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="57ebe-106">The app has two modes:</span></span> 

- <span data-ttu-id="57ebe-107">Emr から FHIR に接続する EMR 接続モード。</span><span class="sxs-lookup"><span data-stu-id="57ebe-107">The EMR Connected mode that connects to EMRs through FHIR.</span></span> <span data-ttu-id="57ebe-108">EMR 接続モードのアプリはプライベートプレビューのままであり、ユーザーまたは管理者は、Office 365 テナントに関する情報を使用して teamsforhealthcare@service.microsoft.com に Microsoft をドロップして、アプリへのアクセスを要求することがあります。</span><span class="sxs-lookup"><span data-stu-id="57ebe-108">The EMR Connected mode app stays in private preview and interested customers or admins may request access to the app by dropping Microsoft an email at teamsforhealthcare@service.microsoft.com with information about their Office 365 tenant.</span></span> 
- <span data-ttu-id="57ebe-109">治療チームが患者情報を手動で追加/取り込みできる手動モード。</span><span class="sxs-lookup"><span data-stu-id="57ebe-109">The manual mode that enables care teams to manually add/bring in patient information.</span></span> <span data-ttu-id="57ebe-110">このアプリケーションは、Teams app store で利用できます。これは、エンドユーザーが既定でダウンロードするためであり、パブリックプレビューに含まれています。</span><span class="sxs-lookup"><span data-stu-id="57ebe-110">The application is available in the Teams app store for end users to download by default and is in public preview.</span></span> <span data-ttu-id="57ebe-111">[Microsoft Teams のアプリセットアップポリシー](../../teams-app-setup-policies.md)を使用するユーザーの特定のセクションにアプリを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="57ebe-111">The app can be restricted to certain sections of users using [app setup policies in Microsoft Teams](../../teams-app-setup-policies.md)</span></span>



## <a name="usage-example"></a><span data-ttu-id="57ebe-112">使用例</span><span class="sxs-lookup"><span data-stu-id="57ebe-112">Usage example</span></span>

<span data-ttu-id="57ebe-113">医療 wards の各シフトでの丸めセッション中に、clinicians は nursing ステーションで収集して、の患者との進行状況に関する最新の更新について話し合うことができます。</span><span class="sxs-lookup"><span data-stu-id="57ebe-113">During rounding sessions on every shift in medical wards, clinicians gather at the nursing station to discuss the latest updates on the progress with patients in the ward.</span></span>  <span data-ttu-id="57ebe-114">また、重要な指標 (医療、患者の医療記録での明示的なものではありません) を強調表示し、お客様の診断に基づいて患者が適切なグライドパス上にいることを確認します。</span><span class="sxs-lookup"><span data-stu-id="57ebe-114">They highlight the key critical metrics (not necessarily medical or that its explicit on the patients’ medical records) and ensure the patient is on the right glide path to discharge based on their diagnosis.</span></span> <span data-ttu-id="57ebe-115">このような患者を丸めるために、クレジットの追加により、すべての clinicians が追加され、患者リストに患者が追加されるようになります。</span><span class="sxs-lookup"><span data-stu-id="57ebe-115">In order to round around these patients, the charge nurse sets up the patient app in a team where all the clinicians are added and adds patients to a patient list.</span></span> <span data-ttu-id="57ebe-116">ラウンドでは、患者との間の看護師とその他のケア givers によって、モバイルデバイス上の Microsoft Teams と患者アプリの情報が更新され、お客様のデバイスに関連する患者情報が更新され、ケアチーム内の他の参加者に対してそれらの更新とメモを表示することができます。常に同期します。1日に2回、シフトの開始時と終了時には、マルチ displicinary のチーム会議も用意されています。これには、患者リストを経由して患者の一覧を表示したり、患者のアプリを使って患者の情報を共有したりできます。</span><span class="sxs-lookup"><span data-stu-id="57ebe-116">During the rounds, the nurses and the other care givers for the patient access Microsoft Teams and the Patients app on their mobile devices and update relevant patient information on their device and then everyone else in the care team can see those updates and notes and stay in sync. Twice a day, at the start and end of a shift, they also have multi-displicinary team meetings to go over the patient list and use the Patients App to ground themselves and share information about each patient using the Patients app on a large display screen.</span></span> <span data-ttu-id="57ebe-117">場合によっては、特定の clinicians が、それらのチーム会議にリモートでダイヤルインしても、ディスカッションの一部となることがあります。</span><span class="sxs-lookup"><span data-stu-id="57ebe-117">Often times, certain clinicians may also dial in to these Teams meetings remotely and still be part of the discussion.</span></span> 

## <a name="configure-patients-app"></a><span data-ttu-id="57ebe-118">患者のアプリを設定する</span><span class="sxs-lookup"><span data-stu-id="57ebe-118">Configure Patients app</span></span>

<span data-ttu-id="57ebe-119">EMR モードの患者アプリを使用するように環境を準備する方法について詳しくは、「 [Microsoft Teams への電子医療記録の統合](patients-app.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="57ebe-119">For information on how to prepare your environment to use the EMR mode Patients app, see [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md).</span></span> <span data-ttu-id="57ebe-120">また、組織で患者のアプリを有効にするには、「 [Microsoft Teams でアプリセットアップポリシーを管理](../../teams-app-setup-policies.md)する」を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57ebe-120">You will also need to see [Manage app setup policies in Microsoft Teams](../../teams-app-setup-policies.md) to enable Patients app for your organization.</span></span>

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a><span data-ttu-id="57ebe-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="57ebe-121">Related topics</span></span>

[<span data-ttu-id="57ebe-122">電子医療記録を Microsoft Teams に統合する</span><span class="sxs-lookup"><span data-stu-id="57ebe-122">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
