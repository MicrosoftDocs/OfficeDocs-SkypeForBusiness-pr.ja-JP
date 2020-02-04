---
title: EDU 管理者向けの Microsoft Teams ポリシー パッケージ
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1.keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams でポリシーパッケージを使用および管理する方法について説明します。
ms.openlocfilehash: 922481747e83b8885641185b8a7e4fa65bb2a1bd
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708663"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a><span data-ttu-id="a976c-103">EDU 管理者向けの Microsoft Teams ポリシー パッケージ</span><span class="sxs-lookup"><span data-stu-id="a976c-103">Microsoft Teams policy packages for EDU admins</span></span>

<span data-ttu-id="a976c-104">Microsoft Teams のポリシーパッケージでは、組織内で同様の役割を持つユーザーに割り当てることができる定義済みのポリシーおよびポリシー設定を収集します。</span><span class="sxs-lookup"><span data-stu-id="a976c-104">A policy package in Microsoft Teams collects predefined policies and policy settings that you can assign to users with similar roles in your institution.</span></span> <span data-ttu-id="a976c-105">ポリシーパッケージは、ポリシーを管理する際の一貫性を高めるために簡素化、合理化、および支援します。</span><span class="sxs-lookup"><span data-stu-id="a976c-105">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="a976c-106">通常の方法では、各ユーザーにポリシーパッケージを割り当て、必要に応じて各パッケージのポリシーをそのユーザーグループのニーズに合わせて再定義します。</span><span class="sxs-lookup"><span data-stu-id="a976c-106">In normal practice, you assign each of your users a policy package, and as necessary redefine the policies in each package to suit the needs of that user group.</span></span> <span data-ttu-id="a976c-107">パッケージの設定を更新すると、そのパッケージに割り当てられているすべてのユーザーが一括更新として変更されます。</span><span class="sxs-lookup"><span data-stu-id="a976c-107">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="a976c-108">一般に教育機関には、学生の年齢と成熟度によって、固有のニーズを持つさまざまな種類のユーザーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a976c-108">Educational institutions in general have many user types with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="a976c-109">たとえば、学生やスタッフに Microsoft Teams へのフルアクセスを許可することもできますが、学生が安全で優先的な学習環境を奨励できるように Microsoft Teams の機能を制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a976c-109">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="a976c-110">ポリシーパッケージを使用して、学校コミュニティのさまざまな cohorts のニーズに基づいて設定を調整できます。</span><span class="sxs-lookup"><span data-stu-id="a976c-110">You can use policy packages to tailor settings based on the needs of different cohorts in your school community.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="a976c-111">ポリシーパッケージとは</span><span class="sxs-lookup"><span data-stu-id="a976c-111">What is a policy package?</span></span>

<span data-ttu-id="a976c-112">ポリシーパッケージを使用すると、microsoft teams の機能を制御し、組織内の特定のユーザーのセットに対して Microsoft Teams での使用を許可または制限することができます。</span><span class="sxs-lookup"><span data-stu-id="a976c-112">Policy packages let you control Microsoft Teams features that allow or restrict Microsoft Teams use for  specific sets of people in your organization.</span></span> <span data-ttu-id="a976c-113">各ポリシーパッケージは、ユーザーロールに基づいて設計されています。定義済みのポリシーとポリシー設定が含まれており、その役割の一般的なアクティビティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a976c-113">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span>

<span data-ttu-id="a976c-114">ポリシーパッケージは、次のためのポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="a976c-114">Policy packages predefine policies for:</span></span>
- <span data-ttu-id="a976c-115">メッセージング </span><span class="sxs-lookup"><span data-stu-id="a976c-115">Messaging</span></span>
- <span data-ttu-id="a976c-116">会議</span><span class="sxs-lookup"><span data-stu-id="a976c-116">Meetings</span></span>
- <span data-ttu-id="a976c-117">アプリのセットアップ</span><span class="sxs-lookup"><span data-stu-id="a976c-117">App Setup</span></span>
- <span data-ttu-id="a976c-118">通話</span><span class="sxs-lookup"><span data-stu-id="a976c-118">Calling</span></span>
- <span data-ttu-id="a976c-119">ライブ イベント</span><span class="sxs-lookup"><span data-stu-id="a976c-119">Live events</span></span>

<span data-ttu-id="a976c-120">Microsoft Teams には現在、次のポリシーパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a976c-120">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="a976c-121">Microsoft Teams 管理センターに一覧表示されたパッケージ名</span><span class="sxs-lookup"><span data-stu-id="a976c-121">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="a976c-122">最適な用途</span><span class="sxs-lookup"><span data-stu-id="a976c-122">Best used for</span></span>  |<span data-ttu-id="a976c-123">説明</span><span class="sxs-lookup"><span data-stu-id="a976c-123">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="a976c-124">Education_Teacher</span><span class="sxs-lookup"><span data-stu-id="a976c-124">Education_Teacher</span></span>| <span data-ttu-id="a976c-125">教員および職員</span><span class="sxs-lookup"><span data-stu-id="a976c-125">Educators and staff</span></span>| <span data-ttu-id="a976c-126">この一連のポリシーとポリシー設定を使用して、組織内の教育者やスタッフに、Microsoft Teams を通じてチャット、通話、会議へのフルアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="a976c-126">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="a976c-127">Education_PrimaryStudent</span><span class="sxs-lookup"><span data-stu-id="a976c-127">Education_PrimaryStudent</span></span> | <span data-ttu-id="a976c-128">学校のプライマリ学生</span><span class="sxs-lookup"><span data-stu-id="a976c-128">Primary school aged students</span></span>  | <span data-ttu-id="a976c-129">お客様の組織内で、学生の学校の期限が切れている生徒は、Microsoft Teams 内で制限を超える必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a976c-129">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="a976c-130">この一連のポリシーとポリシー設定を使用して、会議の作成と管理、チャット管理、プライベート通話などの機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="a976c-130">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="a976c-131">Education_SecondaryStudent</span><span class="sxs-lookup"><span data-stu-id="a976c-131">Education_SecondaryStudent</span></span>| <span data-ttu-id="a976c-132">学生が期限切れになった第2学校</span><span class="sxs-lookup"><span data-stu-id="a976c-132">Secondary school aged students</span></span> | <span data-ttu-id="a976c-133">お客様の組織内で期限切れになっている第1の学生は、Microsoft Teams 内で制限を超える必要があります。</span><span class="sxs-lookup"><span data-stu-id="a976c-133">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="a976c-134">この一連のポリシーとポリシー設定を使用して、会議の作成と管理、チャット管理、プライベート通話などの機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="a976c-134">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="a976c-135">Education_HigherEducationStudent</span><span class="sxs-lookup"><span data-stu-id="a976c-135">Education_HigherEducationStudent</span></span> | <span data-ttu-id="a976c-136">高等教育の学生</span><span class="sxs-lookup"><span data-stu-id="a976c-136">Higher education students</span></span> | <span data-ttu-id="a976c-137">Intuition のより高い教育機関では、お客さまの生徒よりも制限が少なくなります。ただし、いくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="a976c-137">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="a976c-138">この一連のポリシーとポリシー設定を使用して、組織内のチャット、通話、会議へのアクセス権を付与することができます。ただし、学生が外部の参加者と Microsoft Teams を使用する方法は制限されます。</span><span class="sxs-lookup"><span data-stu-id="a976c-138">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|||

<span data-ttu-id="a976c-139">個々のポリシーには、ポリシーパッケージの名前が割り当てられているため、ポリシーパッケージにリンクされたポリシーを簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="a976c-139">Each individual policy is given the name of the policy package so you can easily identify policies linked to a policy package.</span></span> <span data-ttu-id="a976c-140">たとえば、学校の教師に Education_Teacher ポリシーパッケージを割り当てると、Education_Teacher という名前のポリシーがパッケージ内の各ポリシーに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="a976c-140">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher ポリシーパッケージのスクリーンショット](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="a976c-142">教師と管理サポートスタッフがさまざまなポリシーを必要とする場合は、既存のパッケージを転用することができます。現在使用していないパッケージを特定し、そのグループに適した設定に変更します。</span><span class="sxs-lookup"><span data-stu-id="a976c-142">If you decide that teachers and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="a976c-143">どのグループにどのパッケージを所有しているのか、またパッケージを転用する唯一の障害となります。</span><span class="sxs-lookup"><span data-stu-id="a976c-143">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="why-use-policy-packages"></a><span data-ttu-id="a976c-144">ポリシーパッケージを使用する理由</span><span class="sxs-lookup"><span data-stu-id="a976c-144">Why use policy packages</span></span>

<span data-ttu-id="a976c-145">組織内のユーザー数が数百人以上の場合は、「1つのパッケージを割り当てるか、それともすべてのユーザーに割り当てる必要があるのはなぜですか?」とたずねられます。</span><span class="sxs-lookup"><span data-stu-id="a976c-145">If your institution has hundreds, or even thousands of users, you may be asking yourself: "Why take the time to assign one package or another to all those users?"</span></span>

<span data-ttu-id="a976c-146">数百ものユーザーにパッケージを割り当てることは、管理時間については問題ありません。</span><span class="sxs-lookup"><span data-stu-id="a976c-146">Assigning packages to hundreds of users is an investment in administrative time, without question.</span></span> <span data-ttu-id="a976c-147">投資に関する重要なことは、すぐにではなく、時間の経過と共に支払われることです。</span><span class="sxs-lookup"><span data-stu-id="a976c-147">An important thing about investments is that they pay off over time, rather than immediately.</span></span>

<span data-ttu-id="a976c-148">教育環境では、同じまたは類似した役割を持つユーザーが数多く存在します。</span><span class="sxs-lookup"><span data-stu-id="a976c-148">In an educational environment, there are many users with the same or similar roles.</span></span> <span data-ttu-id="a976c-149">同じ方法でユーザーエクスペリエンスを管理すると、時間の経過と共に手間がかかります。</span><span class="sxs-lookup"><span data-stu-id="a976c-149">You spend less effort over time when you manage their user experience the same way.</span></span> <span data-ttu-id="a976c-150">[パッケージ] 機関のさまざまな役割に固有の一連のポリシーをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="a976c-150">Packages group a set of policies specific to the various roles in the institution.</span></span> <span data-ttu-id="a976c-151">同じライセンスを持っているが、異なる役割を持つユーザーは、役割に基づいて関連性のあるポリシーを割り当てることができます。これは、個々のユーザーの調整ポリシーよりも効率的です。</span><span class="sxs-lookup"><span data-stu-id="a976c-151">Users with the same license, but different roles, can have relevant policies assigned based on their role, which is more efficient than tweaking policies for individual users.</span></span>

<span data-ttu-id="a976c-152">組織内のすべてのユーザーをグループに分類して、パッケージを適用すると、パッケージに割り当てられているすべてのユーザーについてパッケージ設定を1回変更するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="a976c-152">Once you have all users in the institution sorted into groups and have packages applied, managing them from then on is a matter of changing the package settings once for all users assigned to the package.</span></span> <span data-ttu-id="a976c-153">パッケージにユーザーを割り当てる前または後に、パッケージ内のポリシーを微調整することを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="a976c-153">You can choose to fine-tune the policies within a package before or after assigning users to the package.</span></span>

<span data-ttu-id="a976c-154">1人のユーザーにパッケージを割り当てる方法、複数のユーザーにパッケージを一括で割り当てる方法、各パッケージにリンクされたポリシーを管理および更新する方法については、「 [Microsoft Teams でポリシーパッケージを管理](manage-policy-packages.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a976c-154">See [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 20 users, and managing and updating the policies linked to each package.</span></span>
