---
title: 会議を呼び出す Teams ポリシーベースの記録&概要
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
description: 会議への通話用の Teams ポリシーベースの記録&する
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
ms.openlocfilehash: b37fcadb89c0ae88e48c20ab669aa91aef6d2f02
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757772"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="f9921-103">会議の通話に対する Teams ポリシーベースの記録&概要</span><span class="sxs-lookup"><span data-stu-id="f9921-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="f9921-104">ポリシーベースの記録を使用すると、通話および会議に Microsoft Teams を採用する組織は、関連する企業ポリシーまたは規制ポリシーの必要に応じて、通話とオンライン会議を自動的に記録して保持するために、管理ポリシーを使用して、その後の処理と保持のために自動的に記録およびキャプチャする必要がある場合に、管理ポリシーを使用して規定することができます。</span><span class="sxs-lookup"><span data-stu-id="f9921-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="f9921-105">Teams は、Teams の通信を構成、管理、記録、保存、分析するためのエンドツーエンド ソリューションを提供するために必要なプラットフォームの機能、ユーザー エクスペリエンス、管理インターフェイスなど、サードパーティのレコーディング ソリューションの統合をサポートするために強化されました。</span><span class="sxs-lookup"><span data-stu-id="f9921-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="f9921-106">強化された機能には、通信プラットフォーム API と記録のためのイベントが含まれます。次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f9921-106">Enhancements include communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="f9921-107">デバイス間でのシームレスで高品質なメディア キャプチャと、オーディオ、ビデオ、画面共有、チャットでサポートされるすべてのエンドポイント。</span><span class="sxs-lookup"><span data-stu-id="f9921-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="f9921-108">Teams ユーザーとサポートされる通話エンドポイント (Teams、Teams Mobile、Skype for Business、PSTN) 間の対話キャプチャのサポート</span><span class="sxs-lookup"><span data-stu-id="f9921-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="f9921-109">既存の Teams の管理通話ツールや会議ツールとポリシーとの統合など、コンプライアンス記録の新しい管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="f9921-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="f9921-110">コンプライアンス記録は、Microsoft 365 A3/A5/E3/E5/Business Premium および Office 365 A3/A5/E3/E5 ユーザーで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f9921-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="f9921-111">コンプライアンス記録ソリューション統合機能は、コンプライアンス記録と Microsoft Teams セッションの Ignite 2019 [<span class="underline">でも確認されました</span>](https://myignite.microsoft.com/archives/IG19-VCE40)。</span><span class="sxs-lookup"><span data-stu-id="f9921-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.microsoft.com/archives/IG19-VCE40).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="f9921-112">Teams の対話記録の概要</span><span class="sxs-lookup"><span data-stu-id="f9921-112">Teams interaction recording overview</span></span>

<span data-ttu-id="f9921-113">操作記録の使用例は、画像に示すように、記録機能の主な 4 つのカテゴリ (便利、機能、組織、および合法な切片) に効果的に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="f9921-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="f9921-114">![操作が何と理由を記録したのかを示すスクリーンショット。](media/recording-taxonomy.png "画像は記録カテゴリを示しています。")</span><span class="sxs-lookup"><span data-stu-id="f9921-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="f9921-115">各カテゴリには、レコーディングの開始方法、記録の記録方法、レコーディングの保存場所、通知を受け取るユーザー、アクセスを制御するユーザー、保持の処理方法に関するさまざまな要件が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f9921-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="f9921-116">種類</span><span class="sxs-lookup"><span data-stu-id="f9921-116">Type</span></span>                   | <span data-ttu-id="f9921-117">利便性 (通常の Teams レコーディング)</span><span class="sxs-lookup"><span data-stu-id="f9921-117">Convenience (Regular Teams Recording)</span></span> | <span data-ttu-id="f9921-118">組織 - 規制 (コンプライアンス記録)</span><span class="sxs-lookup"><span data-stu-id="f9921-118">Org - Regulated (Compliance Recording)</span></span> |
| ---------------------- | ------------------ | --------------- |
| <span data-ttu-id="f9921-119">[開始側]</span><span class="sxs-lookup"><span data-stu-id="f9921-119">Initiator</span></span>              | <span data-ttu-id="f9921-120">ユーザー</span><span class="sxs-lookup"><span data-stu-id="f9921-120">User</span></span>               | <span data-ttu-id="f9921-121">管理者 (システム)</span><span class="sxs-lookup"><span data-stu-id="f9921-121">Admin (system)</span></span>  |
| <span data-ttu-id="f9921-122">Target</span><span class="sxs-lookup"><span data-stu-id="f9921-122">Target</span></span>                 | <span data-ttu-id="f9921-123">1 回の通話/会議</span><span class="sxs-lookup"><span data-stu-id="f9921-123">Per-call / meeting</span></span> | <span data-ttu-id="f9921-124">ユーザーごと</span><span class="sxs-lookup"><span data-stu-id="f9921-124">Per-user</span></span>        |
| <span data-ttu-id="f9921-125">ストレージ所有者</span><span class="sxs-lookup"><span data-stu-id="f9921-125">Storage owner</span></span>          | <span data-ttu-id="f9921-126">ユーザー</span><span class="sxs-lookup"><span data-stu-id="f9921-126">User</span></span>               | <span data-ttu-id="f9921-127">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="f9921-127">Compliance</span></span>      |
| <span data-ttu-id="f9921-128">通知が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="f9921-128">Notification required?</span></span> | <span data-ttu-id="f9921-129">はい</span><span class="sxs-lookup"><span data-stu-id="f9921-129">Yes</span></span>                | <span data-ttu-id="f9921-130">はい</span><span class="sxs-lookup"><span data-stu-id="f9921-130">Yes</span></span>             |
| <span data-ttu-id="f9921-131">Access の所有者</span><span class="sxs-lookup"><span data-stu-id="f9921-131">Access Owner</span></span>           | <span data-ttu-id="f9921-132">ユーザー</span><span class="sxs-lookup"><span data-stu-id="f9921-132">User</span></span>               | <span data-ttu-id="f9921-133">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="f9921-133">Compliance</span></span>      |
| <span data-ttu-id="f9921-134">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="f9921-134">Retention Policy?</span></span>      | <span data-ttu-id="f9921-135">省略可能</span><span class="sxs-lookup"><span data-stu-id="f9921-135">Optional</span></span>           | <span data-ttu-id="f9921-136">はい</span><span class="sxs-lookup"><span data-stu-id="f9921-136">Yes</span></span>             |

<span data-ttu-id="f9921-137">Teams は、会議やライブ イベント [<span class="underline">に便利</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) で機能的に記録するさまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f9921-137">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="f9921-138">組織の記録とは、通話と会議に Teams を採用する組織が、関連する企業ポリシーまたは規制ポリシーの必要に応じて、通話とオンライン会議を自動的に記録および取得して、その後の処理と保持のために管理ポリシーを使用して示す機能を有効に意味します。</span><span class="sxs-lookup"><span data-stu-id="f9921-138">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="f9921-139">このポリシーの下のユーザーは、Teams とのデジタル対話が記録されているが、記録を無効にできないので、操作が完了すると記録にアクセスできないという認識を受け取る。</span><span class="sxs-lookup"><span data-stu-id="f9921-139">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="f9921-140">記録は、電子情報開示、法的保持、その他の企業保持の使用に関するコンプライアンス担当者や法務担当者が利用できる組織のアーカイブの一部になります。</span><span class="sxs-lookup"><span data-stu-id="f9921-140">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="f9921-141">ユーザーニーズの例</span><span class="sxs-lookup"><span data-stu-id="f9921-141">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="f9921-142"><strong>ペルシャ</strong></span><span class="sxs-lookup"><span data-stu-id="f9921-142"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="f9921-143"><strong>ニーズ</strong></span><span class="sxs-lookup"><span data-stu-id="f9921-143"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f9921-144">記録されたユーザー</span><span class="sxs-lookup"><span data-stu-id="f9921-144">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="f9921-145">記録中に通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="f9921-145">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="f9921-146">ポリシーまたは記録エラーが呼び出し動作の変更を引き起こしている場合は、通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="f9921-146">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f9921-147">コミュニケーション管理者</span><span class="sxs-lookup"><span data-stu-id="f9921-147">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="f9921-148">記録ポリシーを Teams ユーザー/エンドポイントに適用/適用する理由と方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="f9921-148">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="f9921-149">組織の Teams 記録ポリシーを構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="f9921-149">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="f9921-150">Teams の通話と会議に関する記録関連の問題を監視およびトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="f9921-150">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="f9921-151">使用、品質、信頼性に関する運用分析を行う内部法令遵守責任者をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f9921-151">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f9921-152">法令遵守責任者</span><span class="sxs-lookup"><span data-stu-id="f9921-152">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="f9921-153">適切な地域の境界でコンプライアンス義務を満たすために必要な方法で、すべての Teams 通信を収集します。</span><span class="sxs-lookup"><span data-stu-id="f9921-153">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="f9921-154">コミュニケーション関連のメタデータまたは対話コンテンツに基づいて対話を検索します。</span><span class="sxs-lookup"><span data-stu-id="f9921-154">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="f9921-155">一般的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f9921-155">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="f9921-156"><strong>メタデータ</strong> - 参加者、時刻、方向、ダイヤルされた番号、発信元番号、カスタム ビジネス データ</span><span class="sxs-lookup"><span data-stu-id="f9921-156"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="f9921-157"><strong>コンテンツ</strong> – トランスクリプション、感情、ルク、関連する相互作用</span><span class="sxs-lookup"><span data-stu-id="f9921-157"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="f9921-158">収集される対話を監視する機能など、収集された通信を分析してやり取りします。</span><span class="sxs-lookup"><span data-stu-id="f9921-158">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="f9921-159">収集された通信のセキュリティを確保し、すべての段階で改ざんを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="f9921-159">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="f9921-160">ソリューション アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="f9921-160">Solution architecture overview</span></span>

<span data-ttu-id="f9921-161">コンプライアンス記録ソリューションは、次の図に示すように Teams と統合されています。</span><span class="sxs-lookup"><span data-stu-id="f9921-161">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="f9921-162">![チームのカスタム アプリの設定を示すスクリーンショット](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "画像は、Teams 会議または通話が送信および受信された場合のフローを示しています。")</span><span class="sxs-lookup"><span data-stu-id="f9921-162">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="f9921-163">Recorder</span><span class="sxs-lookup"><span data-stu-id="f9921-163">Recorder</span></span>

<span data-ttu-id="f9921-164">コンプライアンス記録ソリューションの主要コンポーネントは、レコーダーです。</span><span class="sxs-lookup"><span data-stu-id="f9921-164">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="f9921-165">記録者は、Microsoft の通信プラットフォームを利用し [<span class="underline">、Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) Graph でアプリケーションとして登録するスケーラブル Azure ベースのサービス (ボット) として構築されています。</span><span class="sxs-lookup"><span data-stu-id="f9921-165">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="f9921-166">記録機能は、Teams の呼び出しおよび会議コミュニケーション プラットフォーム [<span class="underline">API</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) との直接のやり取りを提供し、メディアインジェストのエンドポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="f9921-166">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="f9921-167">ボット [<span class="underline">の構成方法、</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) アプリ インスタンスの作成方法、コンプライアンス ポリシーの割り当て方法を示すサンプル コンプライアンス 記録アプリケーションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f9921-167">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="f9921-168">このサンプルには、着信通話ルーティングの処理、記録状態の変更、記録[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)されているユーザーの削除[<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)など、特定の対話を記録するための API の使用方法の例も[<span class="underline">示します</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。</span><span class="sxs-lookup"><span data-stu-id="f9921-168">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="f9921-169">[<span class="underline">UpdateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http)と incomingContext については、特定の API に関する Graph ドキュメントを[<span class="underline">参照してください</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0)。</span><span class="sxs-lookup"><span data-stu-id="f9921-169">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="f9921-170">レコーダー サービスの正確な実装はパートナーによって異なりますが、Teams からレコーダーへの遅延を減らすために、展開の高可用性と地理的分布を実現するには、複数のレコーダーをサポートするように設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9921-170">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="f9921-171">さらに、レコーダー自体は回復性と冗長性を念頭に置いて設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9921-171">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="f9921-172">パートナーは、コンプライアンス記録統合のすべての要件を確実にサポートするために、認定のためのソリューションを提出する前に、Microsoft と Microsoft Graph 通信 API および SDK の最小必須リリース バージョンを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9921-172">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="f9921-173">コンプライアンス記録シナリオの基本である 2 つの特定の要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f9921-173">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="f9921-174">レコーダー ボットは Azure に展開する必要があります</span><span class="sxs-lookup"><span data-stu-id="f9921-174">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="f9921-175">レコーダー ボットは Azure の Windows VM で実行する必要があります</span><span class="sxs-lookup"><span data-stu-id="f9921-175">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="f9921-176">Azure と Windows VM の要件は Teams Bot コンポーネントにのみ適用されます。つまり、パートナーは、コンプライアンス記録に関する関連するパフォーマンスと機能の要件を満たしている場合に、選択したプラットフォームの残りの部分を実装できます。</span><span class="sxs-lookup"><span data-stu-id="f9921-176">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="f9921-177">コンプライアンス記録ポリシーの割り当てとプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="f9921-177">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="f9921-178">IT 管理者は、コンプライアンス記録ポリシーを作成して割り当て、記録するユーザーと、各ユーザーに使用する記録者を決定できます。</span><span class="sxs-lookup"><span data-stu-id="f9921-178">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="f9921-179">記録者は、通信操作が行われたときに、これらのポリシーの構成に基づいて会話に参加するために自動的に招待されます。</span><span class="sxs-lookup"><span data-stu-id="f9921-179">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="f9921-180">コンプライアンス記録ポリシーは [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) を使用して管理され、組織ごとにテナント、ユーザー単位、セキュリティ グループ レベルで適用できます。</span><span class="sxs-lookup"><span data-stu-id="f9921-180">Compliance recording policies are managed using [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="f9921-181">会議ポリシー、通話ポリシー、グループ ポリシー[<span class="underline"></span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)に関する Microsoft Docs[<span class="underline">の詳細については</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy)、以下を[<span class="underline">参照してください</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="f9921-181">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams), [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy) and  [<span class="underline">group policies</span>](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="f9921-182">テナントにアプリケーション インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9921-182">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="f9921-183">コンプライアンス記録ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9921-183">Create a Compliance Recording policy.</span></span>

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

   [<span data-ttu-id="f9921-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="f9921-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="f9921-185">コンプライアンス記録ポリシーをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="f9921-185">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="f9921-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="f9921-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="f9921-187">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="f9921-187">User experiences</span></span>

<span data-ttu-id="f9921-188">通知のサポートは、Teams クライアント エクスペリエンスを使用して有効になります。</span><span class="sxs-lookup"><span data-stu-id="f9921-188">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="f9921-189">エクスペリエンスには、視覚的またはオーディオを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9921-189">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="f9921-190">**Teams クライアント - 視覚的な通知**</span><span class="sxs-lookup"><span data-stu-id="f9921-190">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="f9921-191">デスクトップ/Web</span><span class="sxs-lookup"><span data-stu-id="f9921-191">Desktop/web</span></span>
- <span data-ttu-id="f9921-192">モバイル (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="f9921-192">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="f9921-193">Teams の電話</span><span class="sxs-lookup"><span data-stu-id="f9921-193">Teams phones</span></span>
- <span data-ttu-id="f9921-194">Teams のルーム</span><span class="sxs-lookup"><span data-stu-id="f9921-194">Teams rooms</span></span>

<span data-ttu-id="f9921-195">**その他のエンドポイント - 音声に関する通知**</span><span class="sxs-lookup"><span data-stu-id="f9921-195">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="f9921-196">SIP 電話機</span><span class="sxs-lookup"><span data-stu-id="f9921-196">SIP phones</span></span>
- <span data-ttu-id="f9921-197">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f9921-197">Skype for Business</span></span>
- <span data-ttu-id="f9921-198">電話会議</span><span class="sxs-lookup"><span data-stu-id="f9921-198">Audio conferencing</span></span>
- <span data-ttu-id="f9921-199">PSTN 発信者</span><span class="sxs-lookup"><span data-stu-id="f9921-199">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="f9921-200">Teams 認定プログラムのコンプライアンス記録</span><span class="sxs-lookup"><span data-stu-id="f9921-200">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="f9921-201">一般に公開されている API を公開することで、パートナーは CCaaS ソリューションを Teams と開発して統合できるほか、Microsoft Teams 認定プログラムのコンプライアンス記録を開発し、参加している各パートナーのソリューションがテストされ、Microsoft ソリューションから期待される品質、互換性、信頼性を提供することを保証する保証を顧客に提供しています。</span><span class="sxs-lookup"><span data-stu-id="f9921-201">In addition to publishing publicly available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="f9921-202">次のパートナーは、Microsoft Teams のソリューションを認定しています。</span><span class="sxs-lookup"><span data-stu-id="f9921-202">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="f9921-203">パートナー</span><span class="sxs-lookup"><span data-stu-id="f9921-203">Partner</span></span>|<span data-ttu-id="f9921-204">ソリューションの Web サイト</span><span class="sxs-lookup"><span data-stu-id="f9921-204">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="f9921-205">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="f9921-205">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|<span data-ttu-id="f9921-206">NICE</span><span class="sxs-lookup"><span data-stu-id="f9921-206">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="f9921-207">次のパートナーは、Microsoft Teams のソリューションを認定中です。</span><span class="sxs-lookup"><span data-stu-id="f9921-207">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="f9921-208">パートナー</span><span class="sxs-lookup"><span data-stu-id="f9921-208">Partner</span></span>|<span data-ttu-id="f9921-209">ソリューションの Web サイト</span><span class="sxs-lookup"><span data-stu-id="f9921-209">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="f9921-210">ASC テクノロジ</span><span class="sxs-lookup"><span data-stu-id="f9921-210">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="f9921-211">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="f9921-211">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="f9921-212">Dubber</span><span class="sxs-lookup"><span data-stu-id="f9921-212">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="f9921-213">Landis Technologies</span><span class="sxs-lookup"><span data-stu-id="f9921-213">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="f9921-214">Luware</span><span class="sxs-lookup"><span data-stu-id="f9921-214">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="f9921-215">Numonix</span><span class="sxs-lookup"><span data-stu-id="f9921-215">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="f9921-216">オーナの革新</span><span class="sxs-lookup"><span data-stu-id="f9921-216">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="f9921-217">赤いボックス</span><span class="sxs-lookup"><span data-stu-id="f9921-217">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="f9921-218">Verint</span><span class="sxs-lookup"><span data-stu-id="f9921-218">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="f9921-219">このリストは、パートナーが参加して認定条件を満たしたときに更新されます。</span><span class="sxs-lookup"><span data-stu-id="f9921-219">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f9921-220">次の手順</span><span class="sxs-lookup"><span data-stu-id="f9921-220">Next steps</span></span>

<span data-ttu-id="f9921-221">認定プログラムへの参加を希望しているベンダーの場合は、認定プログラムに<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com。</a></span><span class="sxs-lookup"><span data-stu-id="f9921-221">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
