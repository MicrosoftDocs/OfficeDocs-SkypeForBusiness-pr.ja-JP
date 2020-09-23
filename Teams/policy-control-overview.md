---
title: Microsoft Teams のポリシー制御の概要
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams のポリシー制御の概要。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3665f386f43d8e9b8c49a024663265c25ae96214
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136045"
---
# <a name="policy-control-overview-for-microsoft-teams"></a><span data-ttu-id="04301-103">Microsoft Teams のポリシー制御の概要</span><span class="sxs-lookup"><span data-stu-id="04301-103">Policy control overview for Microsoft Teams</span></span>

<span data-ttu-id="04301-104">Microsoft では、Microsoft 365 の一部である Microsoft Teams を使用する際にデータの収集方法と使用方法を選択するのに必要な情報とコントロールを提供するように努めています。</span><span class="sxs-lookup"><span data-stu-id="04301-104">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Teams, a part of Microsoft 365.</span></span>

<span data-ttu-id="04301-105">この記事は、次の領域のプライバシー制御に関する情報を提供することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="04301-105">This article is intended to provide you with information about privacy controls for the following areas:</span></span>

- <span data-ttu-id="04301-106">**診断データ** は、組織内で Windows を実行しているコンピューターで使用されている Teams と Office ソフトウェアについての診断データを収集し、Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="04301-106">**Diagnostic data** that is collected and sent to Microsoft about Teams and Office software being used on computers running Windows in your organization.</span></span>
- <span data-ttu-id="04301-107">**接続エクスペリエンス**は、クラウドベースの機能を使用し、強化された Teams と Office 機能をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="04301-107">**Connected experiences** that use cloud-based functionality to provide enhanced Teams and Office features to you and your users.</span></span>

<span data-ttu-id="04301-108">これらの変更の一部として、新規および更新されたユーザー インターフェイス (UI) 要素とポリシーの設定があります。</span><span class="sxs-lookup"><span data-stu-id="04301-108">As part of these changes, there are new and updated user interface (UI) elements and policy settings</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04301-109">詳細については、M365 の「[ポリシー管理の概要](https://docs.microsoft.com/deployoffice/privacy/overview-privacy-controls)」のコンテンツをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04301-109">For further reading, please review the [Policy Control Overview](https://docs.microsoft.com/deployoffice/privacy/overview-privacy-controls) content for M365.</span></span>

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a><span data-ttu-id="04301-110">Microsoft 365 Apps for enterprise から Microsoft に送信される診断データ</span><span class="sxs-lookup"><span data-stu-id="04301-110">Diagnostic data sent from Microsoft 365 Apps for enterprise to Microsoft</span></span>

<span data-ttu-id="04301-111">診断データは次の目的で使用されます。</span><span class="sxs-lookup"><span data-stu-id="04301-111">Diagnostic data is used to:</span></span>

- <span data-ttu-id="04301-112">Teams を安全かつ最新の状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="04301-112">Keep Teams secure and up-to-date.</span></span>
- <span data-ttu-id="04301-113">問題を検出、診断、修正します。</span><span class="sxs-lookup"><span data-stu-id="04301-113">Detect, diagnose and remediate problems.</span></span>
- <span data-ttu-id="04301-114">製品の改善を行います。</span><span class="sxs-lookup"><span data-stu-id="04301-114">Make product improvements.</span></span>

<span data-ttu-id="04301-115">収集されたデータの例は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="04301-115">An example of some of the collected data includes:</span></span>

- <span data-ttu-id="04301-116">アプリケーションの言語</span><span class="sxs-lookup"><span data-stu-id="04301-116">Application language</span></span>
- <span data-ttu-id="04301-117">ユーザーの種類</span><span class="sxs-lookup"><span data-stu-id="04301-117">User type</span></span>
- <span data-ttu-id="04301-118">OS のビルド バージョン</span><span class="sxs-lookup"><span data-stu-id="04301-118">Build version of the OS</span></span>

## <a name="clients-that-adhere-to-diagnostic-controls"></a><span data-ttu-id="04301-119">診断制御に準拠しているクライアント</span><span class="sxs-lookup"><span data-stu-id="04301-119">Clients that adhere to diagnostic controls</span></span>

<span data-ttu-id="04301-120">次のクライアントは、診断制御に準拠してデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="04301-120">The following clients adhere to diagnostic controls and will submit data:</span></span>

- <span data-ttu-id="04301-121">iOS</span><span class="sxs-lookup"><span data-stu-id="04301-121">iOS</span></span>
- <span data-ttu-id="04301-122">Android</span><span class="sxs-lookup"><span data-stu-id="04301-122">Android</span></span>
- <span data-ttu-id="04301-123">デスクトップ (win32 API を使用しているコンポーネントのみ)</span><span class="sxs-lookup"><span data-stu-id="04301-123">Desktop (only the component that is using the win32 API)</span></span>

<span data-ttu-id="04301-124">必要なモバイル データ診断については、「[モバイルのポリシー制御診断データ](policy-control-diagnostic-data-mobile.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04301-124">For required mobile data diagnostics, see [Policy control diagnostic data for mobile](policy-control-diagnostic-data-mobile.md).</span></span>

<span data-ttu-id="04301-125">必要なデスクトップ データ診断については、「[デスクトップのポリシー制御診断データ](policy-control-diagnostic-data-desktop.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="04301-125">For required desktop data diagnostics, see [Policy control diagnostic data for desktop](policy-control-diagnostic-data-desktop.md).</span></span>

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a><span data-ttu-id="04301-126">Teams アプリから Microsoft に送信された診断データ</span><span class="sxs-lookup"><span data-stu-id="04301-126">Diagnostic data sent from the Teams app to Microsoft</span></span>

<span data-ttu-id="04301-127">この、組織内の Windows を実行しているコンピューターで使用されている Teams ソフトウェアについての診断データは、収集されて Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="04301-127">This diagnostic data is collected and sent to Microsoft about Teams software being used on computers running Windows in your organization.</span></span>

<span data-ttu-id="04301-128">Teams ソフトウェアには、選択可能な 3 つのレベルの診断データがあります。</span><span class="sxs-lookup"><span data-stu-id="04301-128">There are three levels of diagnostic data for Teams software that you can choose from:</span></span>

- <span data-ttu-id="04301-129">**必須** Office をセキュリティで保護し、最新の状態を維持し、インストールされているデバイス上で正常に動作するために必要な最小限のデータ。</span><span class="sxs-lookup"><span data-stu-id="04301-129">**Required** The minimum data necessary to help keep Office secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>
- <span data-ttu-id="04301-130">**オプション** 製品の改良に役立ち、問題の検出、診断、修正に役立つ高度な情報を提供する追加データ。</span><span class="sxs-lookup"><span data-stu-id="04301-130">**Optional** Additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and remediate issues.</span></span>
- <span data-ttu-id="04301-131">**なし** ユーザーのデバイスで実行されている Teams ソフトウェアに関する診断データは収集されず、Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="04301-131">**Neither** No diagnostic data about Teams software running on the user’s device is collected and sent to us.</span></span> <span data-ttu-id="04301-132">ただし、このオプションはユーザーが Teams を使用しているときに発生する問題を検出、診断、および修正する機能を大幅に制限します。</span><span class="sxs-lookup"><span data-stu-id="04301-132">This option, however, significantly limits our ability to detect, diagnose, and remediate problems your users may encounter using Teams.</span></span>

<span data-ttu-id="04301-133">必須の診断データには、たとえば、デバイスにインストールされている Teams クライアントのバージョンに関する情報や、会議に参加しようとしたときに Teams アプリケーションがクラッシュすることを示す情報などがあります。</span><span class="sxs-lookup"><span data-stu-id="04301-133">Required diagnostic data could include, for example, information about the version of Teams client installed on the device, or include information that indicates that the Teams application is crashing when trying to join a meeting.</span></span> <span data-ttu-id="04301-134">オプションの診断データには、通話の開始にかかる時間に関する情報が含まれる場合があり、接続またはネットワーク パフォーマンスの問題を示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04301-134">Optional diagnostic data could include information about the time it takes to initiate a phone call, which could indicate an issue with connectivity or network performance.</span></span>

<span data-ttu-id="04301-135">オプションの診断データを送信するよう選択した場合は、必須の診断データも含まれています。</span><span class="sxs-lookup"><span data-stu-id="04301-135">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="04301-136">組織の管理者は、ポリシー設定を使用して Microsoft に送信する診断データのレベルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="04301-136">As an admin for your organization, you’ll be able to use a policy setting to choose which level of diagnostic data is sent to us.</span></span> <span data-ttu-id="04301-137">設定を変更しない限り、オプションの診断データが Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="04301-137">Optional diagnostic data will be sent to Microsoft unless you change the setting.</span></span> <span data-ttu-id="04301-138">オプションの診断データを提供することで、Microsoft の Office エンジニアリング チームは問題を検出、診断、および軽減し、組織への影響を少なくすることができます。</span><span class="sxs-lookup"><span data-stu-id="04301-138">Providing optional diagnostic data better enables the Office engineering team at Microsoft to detect, diagnose, and mitigate issues to reduce impacts to your organization.</span></span>

<span data-ttu-id="04301-139">組織の資格情報 (仕事用アカウントまたは学校用アカウントと呼ばれることもあります) を使用して Teams にサインインした場合、ユーザーは自分のデバイスの診断データのレベルを変更できません。</span><span class="sxs-lookup"><span data-stu-id="04301-139">Your users won’t be able to change the diagnostic data level for their devices if they are signed in to Teams with their organizational credentials, which is sometimes referred to as a work or school account.</span></span>

<span data-ttu-id="04301-140">この診断データには、ユーザーの名前、ユーザーの電子メール アドレス、または Office ファイルのコンテンツは含まれません。</span><span class="sxs-lookup"><span data-stu-id="04301-140">This diagnostic data doesn’t include names of users, their email addresses, or the content of their Office files.</span></span> <span data-ttu-id="04301-141">Microsoft のシステムでは、ユーザーの診断データに関連付ける一意の ID を作成しています。</span><span class="sxs-lookup"><span data-stu-id="04301-141">Our system creates a unique ID that it associates with your user’s diagnostic data.</span></span> <span data-ttu-id="04301-142">Teams アプリが 100 回クラッシュしたことを示す診断データを受信すると、この一意の ID によって、1 人のユーザーが 100 回クラッシュしたのか、100 人の異なるユーザーが 1 回ずつクラッシュしたかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="04301-142">When we receive diagnostic data showing that the Teams app crashed 100 times, this unique ID lets us determine if it was a single user who crashed 100 times or if it was 100 different users who each crashed once.</span></span> <span data-ttu-id="04301-143">この一意の ID を特定のユーザーの識別に使用することはありません。</span><span class="sxs-lookup"><span data-stu-id="04301-143">We don’t use this unique ID to identify a specific user.</span></span>

## <a name="required-service-data-for-connected-experiences"></a><span data-ttu-id="04301-144">接続エクスペリエンスに必要なサービス データ</span><span class="sxs-lookup"><span data-stu-id="04301-144">Required service data for connected experiences</span></span>

<span data-ttu-id="04301-145">必要なサービス データとは、ユーザーがクラウドベースの接続エクスペリエンスを提供できるようにし、エクスペリエンスをセキュリティで保護し、期待どおりに機能するようにするためのデータです。</span><span class="sxs-lookup"><span data-stu-id="04301-145">Required service data is data that enables us to deliver these cloud-based connected experiences and help make these experiences secure and perform as expected.</span></span> <span data-ttu-id="04301-146">次の 3 つの種類の情報が、必要なサービス データを構成します。</span><span class="sxs-lookup"><span data-stu-id="04301-146">Three types of information make up required service data.</span></span>

- <span data-ttu-id="04301-147">**お客様のコンテンツ**。Word 文書に入力したテキストなど、Office を使用して作成したコンテンツ。</span><span class="sxs-lookup"><span data-stu-id="04301-147">**Customer content**, which is content you create using Office, such as text typed in a Word document.</span></span>
- <span data-ttu-id="04301-148">**機能データ**。アプリの構成情報など、接続エクスペリエンスがタスクを実行するために必要な情報を含みます。</span><span class="sxs-lookup"><span data-stu-id="04301-148">**Functional data**, which includes information needed by a connected experience to perform its task, such as configuration information about the app.</span></span>
- <span data-ttu-id="04301-149">**サービス診断データ**。サービスをセキュリティで保護し、最新の状態に保ち、期待どおりに実行するために必要なデータ。</span><span class="sxs-lookup"><span data-stu-id="04301-149">**Service diagnostic data**, which is the data necessary to keep the service secure, up to date, and performing as expected.</span></span> <span data-ttu-id="04301-150">このデータは接続エクスペリエンスに厳密に関連しているため、必須またはオプションの診断データ レベルとは別になります。</span><span class="sxs-lookup"><span data-stu-id="04301-150">Because this data is strictly related to the connected experience, it is separate from required or optional diagnostic data levels.</span></span>

<span data-ttu-id="04301-151">この機能をユーザーに提供しないことを選択できます。その場合、この情報は、接続されたエクスペリエンスの機能をサポートするために Microsoft に提供されません。</span><span class="sxs-lookup"><span data-stu-id="04301-151">You can choose to not offer this functionality to your users, in which case this information will not be provided to Microsoft to support the functionality of connected experiences.</span></span> <span data-ttu-id="04301-152">[必要なサービス データ](https://docs.microsoft.com/deployoffice/privacy/required-service-data)の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="04301-152">You can learn more about [required service data](https://docs.microsoft.com/deployoffice/privacy/required-service-data).</span></span>

## <a name="essential-services-for-microsoft-teams"></a><span data-ttu-id="04301-153">Microsoft Teams の重要なサービス</span><span class="sxs-lookup"><span data-stu-id="04301-153">Essential services for Microsoft Teams</span></span>

<span data-ttu-id="04301-154">Microsoft 365 Apps for enterprise の機能に不可欠な一連のサービスもあります。これらを無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="04301-154">There are also a set of services that are essential to how Microsoft 365 Apps for enterprise functions and cannot be disabled.</span></span> <span data-ttu-id="04301-155">たとえば、Microsoft 365 Apps for enterprise を使用するためのライセンスを正しく取得しているかどうかを確認するライセンス サービスです。</span><span class="sxs-lookup"><span data-stu-id="04301-155">For example, the licensing service that confirms that you are properly licensed to use Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="04301-156">これらのサービスに関する必要なサービス データは、設定済みの他のポリシー設定に関係なく、収集されて Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="04301-156">Required service data about these services is collected and sent to Microsoft, regardless of any other policy settings that you have configured.</span></span>

<span data-ttu-id="04301-157">詳細については、 [Office の不可欠なサービス](https://docs.microsoft.com/deployoffice/privacy/essential-services)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04301-157">For more information, see [Essential services for Office](https://docs.microsoft.com/deployoffice/privacy/essential-services).</span></span>
