---
title: 会議への & 会議を発信するためのチームポリシーベースのレコーディングの概要
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: 会議への & 通話に関するチームポリシーベースのレコーディングについて
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61fbce79fc528f4b69baed9c08a8dabc9d40ed4a
ms.sourcegitcommit: 76fc38fe1fbbd93bf2815c57e66fc479df34d929
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002199"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="949ba-103">通話 & 会議用の Teams ポリシーベースのレコーディングの概要</span><span class="sxs-lookup"><span data-stu-id="949ba-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="949ba-104">ポリシーベースのレコーディングでは、管理ポリシーを使用して、通話や会議に Microsoft Teams を採用した組織が、関連する企業または規制ポリシーによって要求された後の処理および保存のために、通話やオンライン会議を自動的に記録してキャプチャする必要がある場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="949ba-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="949ba-105">Teams では、チームの通信を構成、管理、記録、保存、および分析するためのエンドツーエンドソリューションを提供するために必要なプラットフォーム機能、ユーザーエクスペリエンス、管理インターフェイスなど、サードパーティの記録ソリューションの統合をサポートするように強化されています。</span><span class="sxs-lookup"><span data-stu-id="949ba-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="949ba-106">これには、通信プラットフォーム Api と記録するイベントが含まれます。次の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="949ba-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="949ba-107">オーディオ、ビデオ、画面共有、およびチャットのための、デバイス間およびサポートされているすべてのエンドポイントにわたるシームレスな高品質メディアのキャプチャ。</span><span class="sxs-lookup"><span data-stu-id="949ba-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="949ba-108">Teams ユーザーとサポートされている通話エンドポイント (Teams、Teams Mobile、Skype for Business、PSTN) の間での操作のキャプチャのサポート</span><span class="sxs-lookup"><span data-stu-id="949ba-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="949ba-109">既存のチーム管理者との統合、会議のツールとポリシーの統合など、コンプライアンスの記録用の新しい管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="949ba-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="949ba-110">コンプライアンス記録を有効にするには、Microsoft 365 A3/A5/E3/E5/ビジネス Premium および Office 365 A3/A5/E3 ユーザーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="949ba-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="949ba-111">コンプライアンス記録ソリューションの統合機能も、 [<span class="underline">コンプライアンス記録と Microsoft Teams セッション</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions)の Ignite 2019 でレビューされています。</span><span class="sxs-lookup"><span data-stu-id="949ba-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="949ba-112">チームの対話式記録の概要</span><span class="sxs-lookup"><span data-stu-id="949ba-112">Teams interaction recording overview</span></span>

<span data-ttu-id="949ba-113">相互作用記録ユースケースは、画像に示すように、便利、機能、組織、合法的なの4つの主要なカテゴリに実質的に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="949ba-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="949ba-114">![操作の記録とその理由を示すスクリーンショット。](media/recording-taxonomy.png "この画像は録音カテゴリを示しています。")</span><span class="sxs-lookup"><span data-stu-id="949ba-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="949ba-115">各カテゴリには、レコーディングの開始方法、記録される内容、レコーディングの保存場所、通知するユーザー、アクセスを制御するユーザー、および保持の処理方法について、さまざまな要件があります。</span><span class="sxs-lookup"><span data-stu-id="949ba-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="949ba-116">種類</span><span class="sxs-lookup"><span data-stu-id="949ba-116">Type</span></span>                   | <span data-ttu-id="949ba-117">効率</span><span class="sxs-lookup"><span data-stu-id="949ba-117">Convenience</span></span>        | <span data-ttu-id="949ba-118">機能</span><span class="sxs-lookup"><span data-stu-id="949ba-118">Functional</span></span>         | <span data-ttu-id="949ba-119">組織-一般</span><span class="sxs-lookup"><span data-stu-id="949ba-119">Org - General</span></span>      | <span data-ttu-id="949ba-120">組織規制</span><span class="sxs-lookup"><span data-stu-id="949ba-120">Org - Regulated</span></span> | <span data-ttu-id="949ba-121">合法的な切片</span><span class="sxs-lookup"><span data-stu-id="949ba-121">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="949ba-122">・</span><span class="sxs-lookup"><span data-stu-id="949ba-122">Initiator</span></span>              | <span data-ttu-id="949ba-123">ユーザー</span><span class="sxs-lookup"><span data-stu-id="949ba-123">User</span></span>               | <span data-ttu-id="949ba-124">アプリ/ソリューション</span><span class="sxs-lookup"><span data-stu-id="949ba-124">App/Solution</span></span>       | <span data-ttu-id="949ba-125">管理 (システム)</span><span class="sxs-lookup"><span data-stu-id="949ba-125">Admin (system)</span></span>     | <span data-ttu-id="949ba-126">管理 (システム)</span><span class="sxs-lookup"><span data-stu-id="949ba-126">Admin (system)</span></span>  | <span data-ttu-id="949ba-127">LEA</span><span class="sxs-lookup"><span data-stu-id="949ba-127">LEA</span></span>                |
| <span data-ttu-id="949ba-128">Target</span><span class="sxs-lookup"><span data-stu-id="949ba-128">Target</span></span>                 | <span data-ttu-id="949ba-129">電話ごと/会議</span><span class="sxs-lookup"><span data-stu-id="949ba-129">Per-call / meeting</span></span> | <span data-ttu-id="949ba-130">電話ごと/会議</span><span class="sxs-lookup"><span data-stu-id="949ba-130">Per-call / meeting</span></span> | <span data-ttu-id="949ba-131">電話ごと/会議</span><span class="sxs-lookup"><span data-stu-id="949ba-131">Per-call / meeting</span></span> | <span data-ttu-id="949ba-132">ユーザーごと</span><span class="sxs-lookup"><span data-stu-id="949ba-132">Per-user</span></span>        | <span data-ttu-id="949ba-133">エンドポイント/DID</span><span class="sxs-lookup"><span data-stu-id="949ba-133">Per-endpoint / DID</span></span> |
| <span data-ttu-id="949ba-134">記憶域の所有者</span><span class="sxs-lookup"><span data-stu-id="949ba-134">Storage owner</span></span>          | <span data-ttu-id="949ba-135">ユーザー</span><span class="sxs-lookup"><span data-stu-id="949ba-135">User</span></span>               | <span data-ttu-id="949ba-136">アプリ</span><span class="sxs-lookup"><span data-stu-id="949ba-136">App</span></span>                | <span data-ttu-id="949ba-137">同期</span><span class="sxs-lookup"><span data-stu-id="949ba-137">Admin</span></span>              | <span data-ttu-id="949ba-138">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="949ba-138">Compliance</span></span>      | <span data-ttu-id="949ba-139">LEA</span><span class="sxs-lookup"><span data-stu-id="949ba-139">LEA</span></span>                |
| <span data-ttu-id="949ba-140">通知が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="949ba-140">Notification required?</span></span> | <span data-ttu-id="949ba-141">はい</span><span class="sxs-lookup"><span data-stu-id="949ba-141">Yes</span></span>                | <span data-ttu-id="949ba-142">はい</span><span class="sxs-lookup"><span data-stu-id="949ba-142">Yes</span></span>                | <span data-ttu-id="949ba-143">はい</span><span class="sxs-lookup"><span data-stu-id="949ba-143">Yes</span></span>                | <span data-ttu-id="949ba-144">はい</span><span class="sxs-lookup"><span data-stu-id="949ba-144">Yes</span></span>             | <span data-ttu-id="949ba-145">いいえ</span><span class="sxs-lookup"><span data-stu-id="949ba-145">No</span></span>                 |
| <span data-ttu-id="949ba-146">Access の所有者</span><span class="sxs-lookup"><span data-stu-id="949ba-146">Access Owner</span></span>           | <span data-ttu-id="949ba-147">ユーザー</span><span class="sxs-lookup"><span data-stu-id="949ba-147">User</span></span>               | <span data-ttu-id="949ba-148">アプリ</span><span class="sxs-lookup"><span data-stu-id="949ba-148">App</span></span>                | <span data-ttu-id="949ba-149">同期</span><span class="sxs-lookup"><span data-stu-id="949ba-149">Admin</span></span>              | <span data-ttu-id="949ba-150">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="949ba-150">Compliance</span></span>      | <span data-ttu-id="949ba-151">LEA</span><span class="sxs-lookup"><span data-stu-id="949ba-151">LEA</span></span>                |
| <span data-ttu-id="949ba-152">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="949ba-152">Retention Policy?</span></span>      | <span data-ttu-id="949ba-153">省略可能</span><span class="sxs-lookup"><span data-stu-id="949ba-153">Optional</span></span>           | <span data-ttu-id="949ba-154">はい</span><span class="sxs-lookup"><span data-stu-id="949ba-154">Yes</span></span>                | <span data-ttu-id="949ba-155">はい</span><span class="sxs-lookup"><span data-stu-id="949ba-155">Yes</span></span>                | <span data-ttu-id="949ba-156">はい</span><span class="sxs-lookup"><span data-stu-id="949ba-156">Yes</span></span>             | <span data-ttu-id="949ba-157">はい</span><span class="sxs-lookup"><span data-stu-id="949ba-157">Yes</span></span>                |

<span data-ttu-id="949ba-158">Teams には、会議やライブイベントに関する [<span class="underline">便利</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) で機能的な記録のためのさまざまな機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="949ba-158">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="949ba-159">組織の記録とは、管理ポリシーを利用して、通話や会議のためのチームを採用する組織を、関連する企業または規制ポリシーによって要求された後の処理および保持のために自動的に記録し、キャプチャする必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="949ba-159">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="949ba-160">このポリシーの下のユーザーは、チームとのデジタル操作が記録されているが、操作が完了するとレコーディングへのアクセスが許可されていないことを認識します。</span><span class="sxs-lookup"><span data-stu-id="949ba-160">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="949ba-161">レコーディングは、電子情報開示、法的保持、およびその他の企業留保の使用について、コンプライアンスおよび法務担当者が利用できる組織アーカイブの一部になります。</span><span class="sxs-lookup"><span data-stu-id="949ba-161">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="949ba-162">ユーザーニーズの例</span><span class="sxs-lookup"><span data-stu-id="949ba-162">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="949ba-163"><strong>代表</strong></span><span class="sxs-lookup"><span data-stu-id="949ba-163"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="949ba-164"><strong>不要</strong></span><span class="sxs-lookup"><span data-stu-id="949ba-164"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="949ba-165">記録されたユーザー</span><span class="sxs-lookup"><span data-stu-id="949ba-165">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="949ba-166">レコーディングの進行中に通知されます。</span><span class="sxs-lookup"><span data-stu-id="949ba-166">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="949ba-167">ポリシーまたはレコーダーエラーが原因で、呼び出し動作の変更が発生した場合に通知されます。</span><span class="sxs-lookup"><span data-stu-id="949ba-167">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="949ba-168">通信管理者</span><span class="sxs-lookup"><span data-stu-id="949ba-168">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="949ba-169">記録ポリシーを Teams ユーザー/エンドポイントに適用/適用する理由とその方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="949ba-169">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="949ba-170">組織のチーム記録ポリシーを構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="949ba-170">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="949ba-171">チームの通話と会議に関するレコーディング関連の問題を監視してトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="949ba-171">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="949ba-172">利用状況、品質、信頼性についての運用分析によって、社内の法令遵守責任者をサポートします。</span><span class="sxs-lookup"><span data-stu-id="949ba-172">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="949ba-173">法令遵守責任者</span><span class="sxs-lookup"><span data-stu-id="949ba-173">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="949ba-174">適切な地域境界でコンプライアンス義務を満たすために必要な方法で、すべてのチームの通信を収集します。</span><span class="sxs-lookup"><span data-stu-id="949ba-174">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="949ba-175">コミュニケーション関連のメタデータまたは操作の内容に基づいて、相互作用を検索します。</span><span class="sxs-lookup"><span data-stu-id="949ba-175">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="949ba-176">一般的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="949ba-176">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="949ba-177"><strong>メタデータ</strong> - 参加者、時刻、方向、ダイヤル番号、発信者番号、カスタムビジネスデータ</span><span class="sxs-lookup"><span data-stu-id="949ba-177"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="949ba-178"><strong>コンテンツ</strong> –議事録、感情、ふりがな、関連する操作</span><span class="sxs-lookup"><span data-stu-id="949ba-178"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="949ba-179">収集された通信を監視して、収集された通信を監視する機能など、収集された通信を分析し、操作します。</span><span class="sxs-lookup"><span data-stu-id="949ba-179">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="949ba-180">収集された通信のセキュリティを確保し、すべての段階で改ざんされないようにします。</span><span class="sxs-lookup"><span data-stu-id="949ba-180">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="949ba-181">ソリューションアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="949ba-181">Solution architecture overview</span></span>

<span data-ttu-id="949ba-182">コンプライアンス記録ソリューションは、次の図に示すように Teams に統合されています。</span><span class="sxs-lookup"><span data-stu-id="949ba-182">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="949ba-183">![チームのカスタムアプリの設定を示すスクリーンショット](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "画像は、Teams 会議または通話の送受信が行われたときのフローを示します。")</span><span class="sxs-lookup"><span data-stu-id="949ba-183">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="949ba-184">記録</span><span class="sxs-lookup"><span data-stu-id="949ba-184">Recorder</span></span>

<span data-ttu-id="949ba-185">コンプライアンス記録ソリューションのコアコンポーネントは記録ツールです。</span><span class="sxs-lookup"><span data-stu-id="949ba-185">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="949ba-186">レコーダーは、 [<span class="underline">microsoft の通信プラットフォームを利用</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) し、microsoft Graph でアプリケーションを登録する、スケーラブルな Azure ベースのサービス (ボット) として構築されます。</span><span class="sxs-lookup"><span data-stu-id="949ba-186">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="949ba-187">レコーダーは、Teams の通話と会議 [<span class="underline">通信プラットフォーム api</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) との直接操作を提供し、メディアの取り込みのエンドポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="949ba-187">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="949ba-188">[ [<span class="underline">コンプライアンス記録のサンプル] アプリケーションを使用</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) すると、ボットの構成、アプリインスタンスの作成、コンプライアンスポリシーの割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="949ba-188">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="949ba-189">また、このサンプルには、 [<span class="underline">着信通話</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) ルーティングの処理、 [<span class="underline">記録状態の変更</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)、記録されている [<span class="underline">ユーザーの削除</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)など、特定の操作を記録するための API の使用例も用意されています。</span><span class="sxs-lookup"><span data-stu-id="949ba-189">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="949ba-190">[<span class="underline">UpdateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http)と[<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)については、特定の api に関するグラフドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="949ba-190">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="949ba-191">レコーダーサービスの正確な実装はパートナーによって異なりますが、展開の高可用性と地理的分布を実現するために、複数のレコーダーをサポートするように設計する必要があります。これは、チームの待機時間を削減するためです。</span><span class="sxs-lookup"><span data-stu-id="949ba-191">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="949ba-192">また、復元性と冗長性を考慮して設計されていることが想定されています。</span><span class="sxs-lookup"><span data-stu-id="949ba-192">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="949ba-193">パートナーは、コンプライアンスの記録統合の要件がすべてサポートされていることを確認するために、認定のために microsoft Graph communications Api と Sdk の最低限必要なリリースバージョンを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="949ba-193">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="949ba-194">コンプライアンス記録シナリオの基本として、次の2つの要件があります。</span><span class="sxs-lookup"><span data-stu-id="949ba-194">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="949ba-195">レコーダーボットは Azure に展開する必要があります</span><span class="sxs-lookup"><span data-stu-id="949ba-195">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="949ba-196">レコーダーボットは Azure の Windows VM で実行する必要があります</span><span class="sxs-lookup"><span data-stu-id="949ba-196">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="949ba-197">Azure と Windows の VM の要件は、Teams ボットコンポーネントにのみ適用されます。つまり、パートナーは、コンプライアンスの記録に関連するパフォーマンスと機能要件を満たすことができる、選択肢のその他のプラットフォームを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="949ba-197">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="949ba-198">コンプライアンス記録ポリシーの割り当てとプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="949ba-198">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="949ba-199">IT 管理者は、コンプライアンス記録ポリシーを作成して割り当てることによって、どのユーザーを記録し、各ユーザーにどのような記録を使用するかを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="949ba-199">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="949ba-200">レコーダーは、通信操作が行われたときに、これらのポリシーの構成に基づいて、会話に参加するために自動的に招待されます。</span><span class="sxs-lookup"><span data-stu-id="949ba-200">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="949ba-201">コンプライアンス記録ポリシーは、 [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) を使用して管理され、各組織のテナント、ユーザーごと、セキュリティグループのレベルで適用できます。</span><span class="sxs-lookup"><span data-stu-id="949ba-201">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="949ba-202">[<span class="underline">会議ポリシー</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)、[<span class="underline">通話ポリシー</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) 、[<span class="underline">グループポリシー</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)の詳細については、Microsoft ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="949ba-202">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="949ba-203">テナントでアプリケーションインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="949ba-203">Create an application instance in your tenant.</span></span>

   ```powershell
   PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

   RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
   ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
   TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   UserPrincipalName : cr.instance@contoso.onmicrosoft.com
   ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
   DisplayName       : ComplianceRecordingBotInstance
   PhoneNumber       :
   ```

   ```powershell
   PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
   ```

2. <span data-ttu-id="949ba-204">コンプライアンスの記録ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="949ba-204">Create a Compliance Recording policy.</span></span>

   ```powershell
   PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

   Identity                        : Global
   ComplianceRecordingApplications : {}
   Enabled                         : True
   WarnUserOnRemoval               : True
   Description                     : Test policy created by tenant admin
   ```

   ```powershell
   PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
   -ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
   ```

   [<span data-ttu-id="949ba-205"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="949ba-205"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="949ba-206">コンプライアンスの記録ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="949ba-206">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="949ba-207"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="949ba-207"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="949ba-208">ユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="949ba-208">User experiences</span></span>

<span data-ttu-id="949ba-209">チームクライアントエクスペリエンスを使用して、通知のサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="949ba-209">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="949ba-210">エクスペリエンスは、ビジュアルとオーディオのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="949ba-210">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="949ba-211">**チームクライアント-視覚的な通知**</span><span class="sxs-lookup"><span data-stu-id="949ba-211">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="949ba-212">デスクトップ/web</span><span class="sxs-lookup"><span data-stu-id="949ba-212">Desktop/web</span></span>
- <span data-ttu-id="949ba-213">モバイル (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="949ba-213">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="949ba-214">Teams 電話</span><span class="sxs-lookup"><span data-stu-id="949ba-214">Teams phones</span></span>
- <span data-ttu-id="949ba-215">Teams のルーム</span><span class="sxs-lookup"><span data-stu-id="949ba-215">Teams rooms</span></span>

<span data-ttu-id="949ba-216">**その他のエンドポイント-音声通知**</span><span class="sxs-lookup"><span data-stu-id="949ba-216">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="949ba-217">SIP 電話</span><span class="sxs-lookup"><span data-stu-id="949ba-217">SIP phones</span></span>
- <span data-ttu-id="949ba-218">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="949ba-218">Skype for Business</span></span>
- <span data-ttu-id="949ba-219">電話会議</span><span class="sxs-lookup"><span data-stu-id="949ba-219">Audio conferencing</span></span>
- <span data-ttu-id="949ba-220">PSTN 発信者</span><span class="sxs-lookup"><span data-stu-id="949ba-220">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="949ba-221">Teams 認定プログラムのコンプライアンス記録</span><span class="sxs-lookup"><span data-stu-id="949ba-221">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="949ba-222">一般に公開されている Api を公開することにより、パートナーは CCaaS ソリューションの開発とチームとの統合を行うことができるようになりました。 Microsoft Teams 認定プログラムのコンプライアンス記録が開発され、お客様が Microsoft ソリューションに期待する品質、互換性、および信頼性を提供できることを保証しています。</span><span class="sxs-lookup"><span data-stu-id="949ba-222">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="949ba-223">以下のパートナーは、Microsoft Teams のソリューションを認定しています。</span><span class="sxs-lookup"><span data-stu-id="949ba-223">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="949ba-224">パートナー</span><span class="sxs-lookup"><span data-stu-id="949ba-224">Partner</span></span>|<span data-ttu-id="949ba-225">ソリューションの Web サイト</span><span class="sxs-lookup"><span data-stu-id="949ba-225">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="949ba-226">すばらしい</span><span class="sxs-lookup"><span data-stu-id="949ba-226">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="949ba-227">以下のパートナーは、Microsoft Teams のソリューションを認定するプロセスを担当しています。</span><span class="sxs-lookup"><span data-stu-id="949ba-227">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="949ba-228">パートナー</span><span class="sxs-lookup"><span data-stu-id="949ba-228">Partner</span></span>|<span data-ttu-id="949ba-229">ソリューションの Web サイト</span><span class="sxs-lookup"><span data-stu-id="949ba-229">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="949ba-230">ASC テクノロジ</span><span class="sxs-lookup"><span data-stu-id="949ba-230">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="949ba-231">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="949ba-231">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="949ba-232">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="949ba-232">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="949ba-233">Dubber</span><span class="sxs-lookup"><span data-stu-id="949ba-233">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="949ba-234">Landis Technologies</span><span class="sxs-lookup"><span data-stu-id="949ba-234">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="949ba-235">Luware</span><span class="sxs-lookup"><span data-stu-id="949ba-235">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="949ba-236">Numonix</span><span class="sxs-lookup"><span data-stu-id="949ba-236">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="949ba-237">オークの革新</span><span class="sxs-lookup"><span data-stu-id="949ba-237">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="949ba-238">赤いボックス</span><span class="sxs-lookup"><span data-stu-id="949ba-238">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="949ba-239">Verint</span><span class="sxs-lookup"><span data-stu-id="949ba-239">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="949ba-240">このリストは、パートナーが参加して認定条件を満たしたときに更新されます。</span><span class="sxs-lookup"><span data-stu-id="949ba-240">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="949ba-241">次のステップ</span><span class="sxs-lookup"><span data-stu-id="949ba-241">Next steps</span></span>

<span data-ttu-id="949ba-242">認定プログラムに参加しようとしているベンダーの場合は、メール  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>してください。</span><span class="sxs-lookup"><span data-stu-id="949ba-242">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
