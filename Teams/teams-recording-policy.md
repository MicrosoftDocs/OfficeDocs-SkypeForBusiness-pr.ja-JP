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
ms.openlocfilehash: db0c7b0d151a12852adffafeda9d84475b82e055
ms.sourcegitcommit: c49698e03fa3bdd7c82496189b200ac6bb4e05a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48320792"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="2b854-103">通話 & 会議用の Teams ポリシーベースのレコーディングの概要</span><span class="sxs-lookup"><span data-stu-id="2b854-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="2b854-104">ポリシーベースのレコーディングでは、管理ポリシーを使用して、通話や会議に Microsoft Teams を採用した組織が、関連する企業または規制ポリシーによって要求された後の処理および保存のために、通話やオンライン会議を自動的に記録してキャプチャする必要がある場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="2b854-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="2b854-105">Teams では、チームの通信を構成、管理、記録、保存、および分析するためのエンドツーエンドソリューションを提供するために必要なプラットフォーム機能、ユーザーエクスペリエンス、管理インターフェイスなど、サードパーティの記録ソリューションの統合をサポートするように強化されています。</span><span class="sxs-lookup"><span data-stu-id="2b854-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="2b854-106">これには、通信プラットフォーム Api と記録するイベントが含まれます。次の情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2b854-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="2b854-107">オーディオ、ビデオ、画面共有、およびチャットのための、デバイス間およびサポートされているすべてのエンドポイントにわたるシームレスな高品質メディアのキャプチャ。</span><span class="sxs-lookup"><span data-stu-id="2b854-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="2b854-108">Teams ユーザーとサポートされている通話エンドポイント (Teams、Teams Mobile、Skype for Business、PSTN) の間での操作のキャプチャのサポート</span><span class="sxs-lookup"><span data-stu-id="2b854-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="2b854-109">既存のチーム管理者との統合、会議のツールとポリシーの統合など、コンプライアンスの記録用の新しい管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="2b854-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="2b854-110">コンプライアンス記録ソリューションの統合機能も、 [<span class="underline">コンプライアンス記録と Microsoft Teams セッション</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions)の Ignite 2019 でレビューされています。</span><span class="sxs-lookup"><span data-stu-id="2b854-110">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="2b854-111">チームの対話式記録の概要</span><span class="sxs-lookup"><span data-stu-id="2b854-111">Teams interaction recording overview</span></span>

<span data-ttu-id="2b854-112">相互作用記録ユースケースは、画像に示すように、便利、機能、組織、合法的なの4つの主要なカテゴリに実質的に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="2b854-112">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="2b854-113">![操作の記録とその理由を示すスクリーンショット。](media/recording-taxonomy.png "この画像は録音カテゴリを示しています。")</span><span class="sxs-lookup"><span data-stu-id="2b854-113">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="2b854-114">各カテゴリには、レコーディングの開始方法、記録される内容、レコーディングの保存場所、通知するユーザー、アクセスを制御するユーザー、および保持の処理方法について、さまざまな要件があります。</span><span class="sxs-lookup"><span data-stu-id="2b854-114">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

|                        | <span data-ttu-id="2b854-115">効率</span><span class="sxs-lookup"><span data-stu-id="2b854-115">Convenience</span></span>        | <span data-ttu-id="2b854-116">機能</span><span class="sxs-lookup"><span data-stu-id="2b854-116">Functional</span></span>         | <span data-ttu-id="2b854-117">組織-一般</span><span class="sxs-lookup"><span data-stu-id="2b854-117">Org - General</span></span>      | <span data-ttu-id="2b854-118">組織規制</span><span class="sxs-lookup"><span data-stu-id="2b854-118">Org - Regulated</span></span> | <span data-ttu-id="2b854-119">合法的な切片</span><span class="sxs-lookup"><span data-stu-id="2b854-119">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="2b854-120">・</span><span class="sxs-lookup"><span data-stu-id="2b854-120">Initiator</span></span>              | <span data-ttu-id="2b854-121">ユーザー</span><span class="sxs-lookup"><span data-stu-id="2b854-121">User</span></span>               | <span data-ttu-id="2b854-122">アプリ/ソリューション</span><span class="sxs-lookup"><span data-stu-id="2b854-122">App/Solution</span></span>       | <span data-ttu-id="2b854-123">管理 (システム)</span><span class="sxs-lookup"><span data-stu-id="2b854-123">Admin (system)</span></span>     | <span data-ttu-id="2b854-124">管理 (システム)</span><span class="sxs-lookup"><span data-stu-id="2b854-124">Admin (system)</span></span>  | <span data-ttu-id="2b854-125">LEA</span><span class="sxs-lookup"><span data-stu-id="2b854-125">LEA</span></span>                |
| <span data-ttu-id="2b854-126">Target</span><span class="sxs-lookup"><span data-stu-id="2b854-126">Target</span></span>                 | <span data-ttu-id="2b854-127">電話ごと/会議</span><span class="sxs-lookup"><span data-stu-id="2b854-127">Per-call / meeting</span></span> | <span data-ttu-id="2b854-128">電話ごと/会議</span><span class="sxs-lookup"><span data-stu-id="2b854-128">Per-call / meeting</span></span> | <span data-ttu-id="2b854-129">電話ごと/会議</span><span class="sxs-lookup"><span data-stu-id="2b854-129">Per-call / meeting</span></span> | <span data-ttu-id="2b854-130">ユーザーごと</span><span class="sxs-lookup"><span data-stu-id="2b854-130">Per-user</span></span>        | <span data-ttu-id="2b854-131">エンドポイント/DID</span><span class="sxs-lookup"><span data-stu-id="2b854-131">Per-endpoint / DID</span></span> |
| <span data-ttu-id="2b854-132">記憶域の所有者</span><span class="sxs-lookup"><span data-stu-id="2b854-132">Storage owner</span></span>          | <span data-ttu-id="2b854-133">ユーザー</span><span class="sxs-lookup"><span data-stu-id="2b854-133">User</span></span>               | <span data-ttu-id="2b854-134">アプリ</span><span class="sxs-lookup"><span data-stu-id="2b854-134">App</span></span>                | <span data-ttu-id="2b854-135">同期</span><span class="sxs-lookup"><span data-stu-id="2b854-135">Admin</span></span>              | <span data-ttu-id="2b854-136">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="2b854-136">Compliance</span></span>      | <span data-ttu-id="2b854-137">LEA</span><span class="sxs-lookup"><span data-stu-id="2b854-137">LEA</span></span>                |
| <span data-ttu-id="2b854-138">通知が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="2b854-138">Notification required?</span></span> | <span data-ttu-id="2b854-139">はい</span><span class="sxs-lookup"><span data-stu-id="2b854-139">Yes</span></span>                | <span data-ttu-id="2b854-140">はい</span><span class="sxs-lookup"><span data-stu-id="2b854-140">Yes</span></span>                | <span data-ttu-id="2b854-141">はい</span><span class="sxs-lookup"><span data-stu-id="2b854-141">Yes</span></span>                | <span data-ttu-id="2b854-142">はい</span><span class="sxs-lookup"><span data-stu-id="2b854-142">Yes</span></span>             | <span data-ttu-id="2b854-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="2b854-143">No</span></span>                 |
| <span data-ttu-id="2b854-144">Access の所有者</span><span class="sxs-lookup"><span data-stu-id="2b854-144">Access Owner</span></span>           | <span data-ttu-id="2b854-145">ユーザー</span><span class="sxs-lookup"><span data-stu-id="2b854-145">User</span></span>               | <span data-ttu-id="2b854-146">アプリ</span><span class="sxs-lookup"><span data-stu-id="2b854-146">App</span></span>                | <span data-ttu-id="2b854-147">同期</span><span class="sxs-lookup"><span data-stu-id="2b854-147">Admin</span></span>              | <span data-ttu-id="2b854-148">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="2b854-148">Compliance</span></span>      | <span data-ttu-id="2b854-149">LEA</span><span class="sxs-lookup"><span data-stu-id="2b854-149">LEA</span></span>                |
| <span data-ttu-id="2b854-150">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="2b854-150">Retention Policy?</span></span>      | <span data-ttu-id="2b854-151">省略可能</span><span class="sxs-lookup"><span data-stu-id="2b854-151">Optional</span></span>           | <span data-ttu-id="2b854-152">はい</span><span class="sxs-lookup"><span data-stu-id="2b854-152">Yes</span></span>                | <span data-ttu-id="2b854-153">はい</span><span class="sxs-lookup"><span data-stu-id="2b854-153">Yes</span></span>                | <span data-ttu-id="2b854-154">はい</span><span class="sxs-lookup"><span data-stu-id="2b854-154">Yes</span></span>             | <span data-ttu-id="2b854-155">はい</span><span class="sxs-lookup"><span data-stu-id="2b854-155">Yes</span></span>                |

<span data-ttu-id="2b854-156">Teams には、会議やライブイベントに関する [<span class="underline">便利</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) で機能的な記録のためのさまざまな機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="2b854-156">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="2b854-157">組織の記録とは、管理ポリシーを利用して、通話や会議のためのチームを採用する組織を、関連する企業または規制ポリシーによって要求された後の処理および保持のために自動的に記録し、キャプチャする必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2b854-157">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="2b854-158">このポリシーの下のユーザーは、チームとのデジタル操作が記録されているが、操作が完了するとレコーディングへのアクセスが許可されていないことを認識します。</span><span class="sxs-lookup"><span data-stu-id="2b854-158">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="2b854-159">レコーディングは、電子情報開示、法的保持、およびその他の企業留保の使用について、コンプライアンスおよび法務担当者が利用できる組織アーカイブの一部になります。</span><span class="sxs-lookup"><span data-stu-id="2b854-159">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="2b854-160">ユーザーニーズの例</span><span class="sxs-lookup"><span data-stu-id="2b854-160">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="2b854-161"><strong>代表</strong></span><span class="sxs-lookup"><span data-stu-id="2b854-161"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="2b854-162"><strong>不要</strong></span><span class="sxs-lookup"><span data-stu-id="2b854-162"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="2b854-163">記録されたユーザー</span><span class="sxs-lookup"><span data-stu-id="2b854-163">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="2b854-164">レコーディングの進行中に通知されます。</span><span class="sxs-lookup"><span data-stu-id="2b854-164">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="2b854-165">ポリシーまたはレコーダーエラーが原因で、呼び出し動作の変更が発生した場合に通知されます。</span><span class="sxs-lookup"><span data-stu-id="2b854-165">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="2b854-166">通信管理者</span><span class="sxs-lookup"><span data-stu-id="2b854-166">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="2b854-167">記録ポリシーを Teams ユーザー/エンドポイントに適用/適用する理由とその方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b854-167">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="2b854-168">組織のチーム記録ポリシーを構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="2b854-168">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="2b854-169">チームの通話と会議に関するレコーディング関連の問題を監視してトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="2b854-169">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="2b854-170">利用状況、品質、信頼性についての運用分析によって、社内の法令遵守責任者をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2b854-170">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="2b854-171">法令遵守責任者</span><span class="sxs-lookup"><span data-stu-id="2b854-171">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="2b854-172">適切な地域境界でコンプライアンス義務を満たすために必要な方法で、すべてのチームの通信を収集します。</span><span class="sxs-lookup"><span data-stu-id="2b854-172">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="2b854-173">コミュニケーション関連のメタデータまたは操作の内容に基づいて、相互作用を検索します。</span><span class="sxs-lookup"><span data-stu-id="2b854-173">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="2b854-174">一般的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b854-174">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b854-175"><strong>メタデータ</strong> - 参加者、時刻、方向、ダイヤル番号、発信者番号、カスタムビジネスデータ</span><span class="sxs-lookup"><span data-stu-id="2b854-175"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="2b854-176"><strong>コンテンツ</strong> –議事録、感情、ふりがな、関連する操作</span><span class="sxs-lookup"><span data-stu-id="2b854-176"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="2b854-177">収集された通信を監視して、収集された通信を監視する機能など、収集された通信を分析し、操作します。</span><span class="sxs-lookup"><span data-stu-id="2b854-177">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="2b854-178">収集された通信のセキュリティを確保し、すべての段階で改ざんされないようにします。</span><span class="sxs-lookup"><span data-stu-id="2b854-178">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="2b854-179">ソリューションアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="2b854-179">Solution architecture overview</span></span>

<span data-ttu-id="2b854-180">コンプライアンス記録ソリューションは、次の図に示すように Teams に統合されています。</span><span class="sxs-lookup"><span data-stu-id="2b854-180">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="2b854-181">![チームのカスタムアプリの設定を示すスクリーンショット](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "画像は、Teams 会議または通話の送受信が行われたときのフローを示します。")</span><span class="sxs-lookup"><span data-stu-id="2b854-181">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="2b854-182">記録</span><span class="sxs-lookup"><span data-stu-id="2b854-182">Recorder</span></span>

<span data-ttu-id="2b854-183">コンプライアンス記録ソリューションのコアコンポーネントは記録ツールです。</span><span class="sxs-lookup"><span data-stu-id="2b854-183">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="2b854-184">レコーダーは、 [<span class="underline">microsoft の通信プラットフォームを利用</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) し、microsoft Graph でアプリケーションを登録する、スケーラブルな Azure ベースのサービス (ボット) として構築されます。</span><span class="sxs-lookup"><span data-stu-id="2b854-184">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="2b854-185">レコーダーは、Teams の通話と会議 [<span class="underline">通信プラットフォーム api</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) との直接操作を提供し、メディアの取り込みのエンドポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="2b854-185">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="2b854-186">[ [<span class="underline">コンプライアンス記録のサンプル] アプリケーションを使用</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) すると、ボットの構成、アプリインスタンスの作成、コンプライアンスポリシーの割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b854-186">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="2b854-187">また、このサンプルには、[<span class="underline">着信通話</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   ルーティングの処理、[<span class="underline">記録状態の変更</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)、記録されている[<span class="underline">ユーザーの削除</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)など、特定の操作を記録するための API の使用例も用意されています。</span><span class="sxs-lookup"><span data-stu-id="2b854-187">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="2b854-188">[<span class="underline">UpdateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http)と[<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)については、特定の api に関するグラフドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b854-188">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="2b854-189">レコーダーサービスの正確な実装はパートナーによって異なりますが、展開の高可用性と地理的分布を実現するために、複数のレコーダーをサポートするように設計する必要があります。これは、チームの待機時間を削減するためです。</span><span class="sxs-lookup"><span data-stu-id="2b854-189">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="2b854-190">また、復元性と冗長性を考慮して設計されていることが想定されています。</span><span class="sxs-lookup"><span data-stu-id="2b854-190">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="2b854-191">パートナーは、コンプライアンスの記録統合の要件がすべてサポートされていることを確認するために、認定のために microsoft Graph communications Api と Sdk の最低限必要なリリースバージョンを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b854-191">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="2b854-192">コンプライアンス記録シナリオの基本として、次の2つの要件があります。</span><span class="sxs-lookup"><span data-stu-id="2b854-192">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="2b854-193">レコーダーボットは Azure に展開する必要があります</span><span class="sxs-lookup"><span data-stu-id="2b854-193">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="2b854-194">レコーダーボットは Azure の Windows VM で実行する必要があります</span><span class="sxs-lookup"><span data-stu-id="2b854-194">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="2b854-195">Azure と Windows の VM の要件は、Teams ボットコンポーネントにのみ適用されます。つまり、パートナーは、コンプライアンスの記録に関連するパフォーマンスと機能要件を満たすことができる、選択肢のその他のプラットフォームを実装することができます。</span><span class="sxs-lookup"><span data-stu-id="2b854-195">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="2b854-196">コンプライアンス記録ポリシーの割り当てとプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="2b854-196">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="2b854-197">IT 管理者は、コンプライアンス記録ポリシーを作成して割り当てることによって、どのユーザーを記録し、各ユーザーにどのような記録を使用するかを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="2b854-197">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="2b854-198">レコーダーは、通信操作が行われたときに、これらのポリシーの構成に基づいて、会話に参加するために自動的に招待されます。</span><span class="sxs-lookup"><span data-stu-id="2b854-198">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="2b854-199">コンプライアンス記録ポリシーは、 [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) を使用して管理され、各組織のテナント、ユーザーごと、セキュリティグループのレベルで適用できます。</span><span class="sxs-lookup"><span data-stu-id="2b854-199">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="2b854-200">[<span class="underline">会議ポリシー</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)、[<span class="underline">通話ポリシー</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) 、[<span class="underline">グループポリシー</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)の詳細については、Microsoft ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b854-200">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="2b854-201">テナントでアプリケーションインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b854-201">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="2b854-202">コンプライアンスの記録ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b854-202">Create a Compliance Recording policy.</span></span>

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

   [<span data-ttu-id="2b854-203"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="2b854-203"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="2b854-204">コンプライアンスの記録ポリシーをユーザーに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2b854-204">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="2b854-205"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="2b854-205"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="2b854-206">ユーザーエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="2b854-206">User experiences</span></span>

<span data-ttu-id="2b854-207">チームクライアントエクスペリエンスを使用して、通知のサポートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2b854-207">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="2b854-208">エクスペリエンスは、ビジュアルとオーディオのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="2b854-208">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="2b854-209">**チームクライアント-視覚的な通知**</span><span class="sxs-lookup"><span data-stu-id="2b854-209">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="2b854-210">デスクトップ/web</span><span class="sxs-lookup"><span data-stu-id="2b854-210">Desktop/web</span></span>
- <span data-ttu-id="2b854-211">モバイル (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="2b854-211">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="2b854-212">Teams 電話</span><span class="sxs-lookup"><span data-stu-id="2b854-212">Teams phones</span></span>
- <span data-ttu-id="2b854-213">Teams のルーム</span><span class="sxs-lookup"><span data-stu-id="2b854-213">Teams rooms</span></span>

<span data-ttu-id="2b854-214">**その他のエンドポイント-音声通知**</span><span class="sxs-lookup"><span data-stu-id="2b854-214">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="2b854-215">SIP 電話</span><span class="sxs-lookup"><span data-stu-id="2b854-215">SIP phones</span></span>
- <span data-ttu-id="2b854-216">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2b854-216">Skype for Business</span></span>
- <span data-ttu-id="2b854-217">電話会議</span><span class="sxs-lookup"><span data-stu-id="2b854-217">Audio conferencing</span></span>
- <span data-ttu-id="2b854-218">PSTN 発信者</span><span class="sxs-lookup"><span data-stu-id="2b854-218">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="2b854-219">Teams 認定プログラムのコンプライアンス記録</span><span class="sxs-lookup"><span data-stu-id="2b854-219">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="2b854-220">一般に公開されている Api を公開することにより、パートナーは CCaaS ソリューションの開発とチームとの統合を行うことができるようになりました。 Microsoft Teams 認定プログラムのコンプライアンス記録が開発され、お客様が Microsoft ソリューションに期待する品質、互換性、および信頼性を提供できることを保証しています。</span><span class="sxs-lookup"><span data-stu-id="2b854-220">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="2b854-221">以下のパートナーは、Microsoft Teams のソリューションを認定するプロセスを担当しています。</span><span class="sxs-lookup"><span data-stu-id="2b854-221">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>  

|<span data-ttu-id="2b854-222">パートナー</span><span class="sxs-lookup"><span data-stu-id="2b854-222">Partner</span></span>|<span data-ttu-id="2b854-223">ソリューションの Web サイト</span><span class="sxs-lookup"><span data-stu-id="2b854-223">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="2b854-224">ASC テクノロジ</span><span class="sxs-lookup"><span data-stu-id="2b854-224">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="2b854-225">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="2b854-225">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="2b854-226">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="2b854-226">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="2b854-227">すばらしい</span><span class="sxs-lookup"><span data-stu-id="2b854-227">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="2b854-228">Numonix</span><span class="sxs-lookup"><span data-stu-id="2b854-228">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="2b854-229">赤いボックス</span><span class="sxs-lookup"><span data-stu-id="2b854-229">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="2b854-230">Verint</span><span class="sxs-lookup"><span data-stu-id="2b854-230">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="2b854-231">このリストは、パートナーが参加して認定条件を満たしたときに更新されます。</span><span class="sxs-lookup"><span data-stu-id="2b854-231">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2b854-232">次のステップ</span><span class="sxs-lookup"><span data-stu-id="2b854-232">Next steps</span></span>

<span data-ttu-id="2b854-233">認定プログラムに参加しようとしているベンダーの場合は、メール  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>してください。</span><span class="sxs-lookup"><span data-stu-id="2b854-233">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
