---
title: 会議をTeamsする場合のポリシーベースの記録の&概要
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
description: 会議のTeamsのポリシーベースの記録について&する
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
ms.openlocfilehash: ba99e49aa546a57d412492737cae8f6520a9eb84
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308366"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="7db7b-103">会議のTeamsに対するポリシーベースの記録の&概要</span><span class="sxs-lookup"><span data-stu-id="7db7b-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="7db7b-104">ポリシー ベースの記録を使用すると、通話と会議に Microsoft Teams を採用する組織は、関連する企業または規制ポリシーの要求に応じて、通話とオンライン会議を自動的に記録して保持する必要がある場合に、管理ポリシーを使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="7db7b-105">Teamsは、Teams 通信を構成、管理、記録、保存、分析するためのエンド to エンド ソリューションを提供するために必要なプラットフォーム機能、ユーザー エクスペリエンス、管理インターフェイスなど、サード パーティ製の記録ソリューションの統合をサポートするために強化されました。</span><span class="sxs-lookup"><span data-stu-id="7db7b-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="7db7b-106">機能強化には、通信プラットフォーム API と記録用のイベントが含まれます。次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-106">Enhancements include communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="7db7b-107">デバイス間およびオーディオ、ビデオ、画面共有、チャットでサポートされているすべてのエンドポイントで、シームレスで高品質のメディア キャプチャ。</span><span class="sxs-lookup"><span data-stu-id="7db7b-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="7db7b-108">ユーザーとサポートされている呼び出しTeamsエンドポイント (Teams、Teams Mobile、Skype for Business PSTN) 間の対話キャプチャのサポート</span><span class="sxs-lookup"><span data-stu-id="7db7b-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="7db7b-109">コンプライアンス記録用の新しい管理ポリシー (既存の通話および会議ツールTeamsポリシーとの統合を含む)</span><span class="sxs-lookup"><span data-stu-id="7db7b-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="7db7b-110">コンプライアンス記録は、Microsoft 365 A3/A5/E3/E5/Business プレミアム および Office 365 A3/A5/E3/E5 ユーザーで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="7db7b-111">コンプライアンス記録ソリューションの統合機能は、コンプライアンス記録セッションの Ignite 2019 [Microsoft Teamsされました](https://myignite.microsoft.com/archives/IG19-VCE40)。</span><span class="sxs-lookup"><span data-stu-id="7db7b-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [Compliance Recording and Microsoft Teams session](https://myignite.microsoft.com/archives/IG19-VCE40).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="7db7b-112">Teams記録の概要</span><span class="sxs-lookup"><span data-stu-id="7db7b-112">Teams interaction recording overview</span></span>

<span data-ttu-id="7db7b-113">対話記録の使用例は、画像に示すように、便利、機能、組織、および法律上のインターセプトの 4 つの主要な記録機能カテゴリに効果的に分けることができます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7db7b-114">![操作の記録の理由と理由を示すスクリーンショット。](media/recording-taxonomy.png "画像には、記録カテゴリが表示されます。")</span><span class="sxs-lookup"><span data-stu-id="7db7b-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="7db7b-115">各カテゴリには、レコーディングの開始方法、記録の記録方法、記録の保存場所、通知を受け取るユーザー、アクセス権を制御するユーザー、保持の処理方法に関するさまざまな要件が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="7db7b-116">種類</span><span class="sxs-lookup"><span data-stu-id="7db7b-116">Type</span></span>                   | <span data-ttu-id="7db7b-117">利便性 (通常のTeams記録)</span><span class="sxs-lookup"><span data-stu-id="7db7b-117">Convenience (Regular Teams Recording)</span></span> | <span data-ttu-id="7db7b-118">組織 - 規制対象 (コンプライアンス記録)</span><span class="sxs-lookup"><span data-stu-id="7db7b-118">Org - Regulated (Compliance Recording)</span></span> |
| ---------------------- | ------------------ | --------------- |
| <span data-ttu-id="7db7b-119">イニシエーター</span><span class="sxs-lookup"><span data-stu-id="7db7b-119">Initiator</span></span>              | <span data-ttu-id="7db7b-120">ユーザー</span><span class="sxs-lookup"><span data-stu-id="7db7b-120">User</span></span>               | <span data-ttu-id="7db7b-121">管理者 (システム)</span><span class="sxs-lookup"><span data-stu-id="7db7b-121">Admin (system)</span></span>  |
| <span data-ttu-id="7db7b-122">Target</span><span class="sxs-lookup"><span data-stu-id="7db7b-122">Target</span></span>                 | <span data-ttu-id="7db7b-123">通話/会議ごとに</span><span class="sxs-lookup"><span data-stu-id="7db7b-123">Per-call / meeting</span></span> | <span data-ttu-id="7db7b-124">ユーザーごと</span><span class="sxs-lookup"><span data-stu-id="7db7b-124">Per-user</span></span>        |
| <span data-ttu-id="7db7b-125">Storage所有者</span><span class="sxs-lookup"><span data-stu-id="7db7b-125">Storage owner</span></span>          | <span data-ttu-id="7db7b-126">ユーザー</span><span class="sxs-lookup"><span data-stu-id="7db7b-126">User</span></span>               | <span data-ttu-id="7db7b-127">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="7db7b-127">Compliance</span></span>      |
| <span data-ttu-id="7db7b-128">通知が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="7db7b-128">Notification required?</span></span> | <span data-ttu-id="7db7b-129">はい</span><span class="sxs-lookup"><span data-stu-id="7db7b-129">Yes</span></span>                | <span data-ttu-id="7db7b-130">はい</span><span class="sxs-lookup"><span data-stu-id="7db7b-130">Yes</span></span>             |
| <span data-ttu-id="7db7b-131">アクセス所有者</span><span class="sxs-lookup"><span data-stu-id="7db7b-131">Access Owner</span></span>           | <span data-ttu-id="7db7b-132">ユーザー</span><span class="sxs-lookup"><span data-stu-id="7db7b-132">User</span></span>               | <span data-ttu-id="7db7b-133">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="7db7b-133">Compliance</span></span>      |
| <span data-ttu-id="7db7b-134">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="7db7b-134">Retention Policy?</span></span>      | <span data-ttu-id="7db7b-135">省略可能</span><span class="sxs-lookup"><span data-stu-id="7db7b-135">Optional</span></span>           | <span data-ttu-id="7db7b-136">はい</span><span class="sxs-lookup"><span data-stu-id="7db7b-136">Yes</span></span>             |

<span data-ttu-id="7db7b-137">Teamsは、会議やライブ イベントに[便利](./cloud-recording.md)で機能的な記録を行うさまざまな機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="7db7b-137">Teams provides various capabilities for [convenient](./cloud-recording.md) and functional recording for meetings and live events.</span></span> <span data-ttu-id="7db7b-138">組織記録とは、関連する企業または規制ポリシーで必要に応じて、通話とオンライン会議を自動的に記録して保持する必要がある場合に、管理ポリシーを使用して、通話と会議に Teams を導入する組織が自動的に記録およびキャプチャを行う必要がある場合に有効にするためのものです。</span><span class="sxs-lookup"><span data-stu-id="7db7b-138">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="7db7b-139">このポリシーの下のユーザーは、Teams とのデジタル対話が記録されているが、記録を無効にできないので、対話が完了すると記録にアクセスできないという認識を受け取る。</span><span class="sxs-lookup"><span data-stu-id="7db7b-139">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="7db7b-140">記録は、電子情報開示、法的保持、その他の企業保有の使用に関するコンプライアンス担当者および法務担当者が利用できる組織のアーカイブの一部になります。</span><span class="sxs-lookup"><span data-stu-id="7db7b-140">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="7db7b-141">ユーザーニーズの例</span><span class="sxs-lookup"><span data-stu-id="7db7b-141">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="7db7b-142">ペルシャ</span><span class="sxs-lookup"><span data-stu-id="7db7b-142">Persona</span></span></th>
<th><span data-ttu-id="7db7b-143">ニーズ</span><span class="sxs-lookup"><span data-stu-id="7db7b-143">Needs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7db7b-144">記録されたユーザー</span><span class="sxs-lookup"><span data-stu-id="7db7b-144">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="7db7b-145">記録が進行中のときに通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="7db7b-145">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="7db7b-146">ポリシーやレコーダーのエラーが呼び出し動作の変更を引き起こしている場合は、通知を受け取る。</span><span class="sxs-lookup"><span data-stu-id="7db7b-146">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7db7b-147">コミュニケーション管理者</span><span class="sxs-lookup"><span data-stu-id="7db7b-147">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="7db7b-148">ユーザー/エンドポイントに記録ポリシーを適用/適用する理由Teams理解します。</span><span class="sxs-lookup"><span data-stu-id="7db7b-148">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="7db7b-149">組織のTeams記録ポリシーを構成および管理します。</span><span class="sxs-lookup"><span data-stu-id="7db7b-149">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="7db7b-150">通話や会議の記録に関連する問題Teamsトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="7db7b-150">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="7db7b-151">使用状況、品質、信頼性に関する運用分析で内部コンプライアンス責任者をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7db7b-151">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7db7b-152">コンプライアンス責任者</span><span class="sxs-lookup"><span data-stu-id="7db7b-152">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="7db7b-153">適切な地域Teamsコンプライアンス義務を満たすために必要な方法で、すべての情報通信を収集します。</span><span class="sxs-lookup"><span data-stu-id="7db7b-153">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="7db7b-154">コミュニケーション関連のメタデータまたは対話コンテンツに基づいて対話を検索します。</span><span class="sxs-lookup"><span data-stu-id="7db7b-154">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="7db7b-155">一般的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7db7b-155">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="7db7b-156"><strong>メタデータ</strong> - 参加者、時間、方向、ダイヤルされた番号、発信元番号、カスタム ビジネス データ</span><span class="sxs-lookup"><span data-stu-id="7db7b-156"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="7db7b-157"><strong>コンテンツ</strong> – 文字起こし、センチメント、音声、関連する対話</span><span class="sxs-lookup"><span data-stu-id="7db7b-157"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="7db7b-158">収集される通信を監視する機能など、収集された通信を分析して操作します。</span><span class="sxs-lookup"><span data-stu-id="7db7b-158">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="7db7b-159">収集された通信のセキュリティを確保し、すべての段階で改ざんを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="7db7b-159">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="7db7b-160">ソリューション アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="7db7b-160">Solution architecture overview</span></span>

<span data-ttu-id="7db7b-161">コンプライアンス記録ソリューションは、次の図Teamsと統合されています。</span><span class="sxs-lookup"><span data-stu-id="7db7b-161">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7db7b-162">![チームのカスタム アプリ設定を示すスクリーンショット](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "画像は、会議または通話がTeams受信した場合のフローを示しています。")</span><span class="sxs-lookup"><span data-stu-id="7db7b-162">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="7db7b-163">レコーダー</span><span class="sxs-lookup"><span data-stu-id="7db7b-163">Recorder</span></span>

<span data-ttu-id="7db7b-164">コンプライアンス記録ソリューションのコア コンポーネントは、レコーダーです。</span><span class="sxs-lookup"><span data-stu-id="7db7b-164">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="7db7b-165">レコーダーは、Microsoft の通信プラットフォームを活用し[、Microsoft](/graph/cloud-communications-concept-overview) Graph にアプリケーションとして登録するスケーラブルな Azure ベースのサービス (ボット) として構築されています。</span><span class="sxs-lookup"><span data-stu-id="7db7b-165">Recorders are built as scalable Azure-based services (bots) that [leverage Microsoft’s communications platform](/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="7db7b-166">レコーダーは、通話や会議の通信プラットフォーム API Teams直接やり[](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)取りし、メディア インジェストのエンドポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="7db7b-166">The recorder provides the direct interaction with the Teams calls and meetings [communications platform APIs](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="7db7b-167">ボット [の構成、アプリ](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) インスタンスの作成、コンプライアンス ポリシーの割り当て方法を示すサンプル コンプライアンス 記録アプリケーションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-167">A [sample compliance recorder application is available](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="7db7b-168">このサンプルには、着信通話ルーティングの処理、録音状態の変更、記録[](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)されているユーザーの削除[](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)など、特定の対話を記録するための API 使用法の例も[示されています](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126)。</span><span class="sxs-lookup"><span data-stu-id="7db7b-168">The sample also has examples on API usage for recording specific interactions such as handling [incoming call](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [changing recording states](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [removing the user who is being recorded](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="7db7b-169">Graph API の詳細については[、updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0)と incomingContext に関するページ[を参照してください](/graph/api/resources/incomingcontext?view=graph-rest-1.0)。</span><span class="sxs-lookup"><span data-stu-id="7db7b-169">Graph documentation on the specific APIs can be found here for [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) and [incomingContext](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="7db7b-170">レコーダー サービスの正確な実装はパートナーによって異なりますが、Teams からレコーダーへの待機時間を短縮するために、デプロイの高可用性と地理的分散を実現するために、複数のレコーダーをサポートするように設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7db7b-170">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="7db7b-171">さらに、回復性と冗長性を念頭に置いてレコーダー自体を設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7db7b-171">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="7db7b-172">パートナーは、コンプライアンス記録統合のすべての要件がサポートされるのを確認するために、認定のためのソリューションを提出する前に、Microsoft Graph 通信 API と SDK の最小必須リリース バージョンを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7db7b-172">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="7db7b-173">コンプライアンス記録シナリオの基本である 2 つの具体的な要件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7db7b-173">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="7db7b-174">レコーダー ボットを Azure にデプロイする必要があります</span><span class="sxs-lookup"><span data-stu-id="7db7b-174">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="7db7b-175">レコーダー ボットは、Azure 内の Windows VM 上で実行する必要があります</span><span class="sxs-lookup"><span data-stu-id="7db7b-175">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="7db7b-176">Azure および Windows VM の要件は Teams Bot コンポーネントにのみ適用されます。つまり、パートナーは、コンプライアンス記録に関する関連するパフォーマンス要件と機能要件を満たしている場合に、選択したプラットフォームの残りの部分を実装できます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-176">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="7db7b-177">コンプライアンス記録ポリシーの割り当てとプロビジョニング</span><span class="sxs-lookup"><span data-stu-id="7db7b-177">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="7db7b-178">IT 管理者は、コンプライアンス記録ポリシーを作成して割り当てると、どのユーザーを記録し、どのレコーダーを各ユーザーに使用されるかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-178">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="7db7b-179">記録者は、通信操作が行われたときに、これらのポリシーの構成に基づいて会話に参加するために自動的に招待されます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-179">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="7db7b-180">コンプライアンス記録ポリシーは [Microsoft PowerShell](./teams-powershell-overview.md) を使用して管理され、テナント、ユーザー単位、およびセキュリティ グループ レベルで組織ごとに適用できます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-180">Compliance recording policies are managed using [Microsoft PowerShell](./teams-powershell-overview.md) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="7db7b-181">会議ポリシー、通話ポリシー、グループ[ポリシーに](./meeting-policies-in-teams.md)関する[](./teams-calling-policy.md)Microsoft Docs の詳細[については、 を参照してください](./assign-policies.md#assign-a-policy-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="7db7b-181">You can find more information on Microsoft Docs for [Meeting policies](./meeting-policies-in-teams.md), [calling policies](./teams-calling-policy.md) and  [group policies](./assign-policies.md#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="7db7b-182">テナントにアプリケーション インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7db7b-182">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="7db7b-183">コンプライアンス記録ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7db7b-183">Create a Compliance Recording policy.</span></span>

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

   <span data-ttu-id="7db7b-184">[「Set-CsTeamsComplianceRecordingPolicy」を参照してください](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7db7b-184">See [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="7db7b-185">コンプライアンス記録ポリシーをユーザーに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="7db7b-185">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   <span data-ttu-id="7db7b-186">[Grant-CsTeamsComplianceRecordingPolicy に関するページを参照してください](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7db7b-186">See [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps).</span></span>

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="7db7b-187">ユーザー エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="7db7b-187">User experiences</span></span>

<span data-ttu-id="7db7b-188">通知のサポートは、クライアント エクスペリエンスのTeams使用して有効になります。</span><span class="sxs-lookup"><span data-stu-id="7db7b-188">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="7db7b-189">エクスペリエンスには、視覚的またはオーディオを使用できます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-189">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="7db7b-190">**Teams クライアント - 視覚的な通知**</span><span class="sxs-lookup"><span data-stu-id="7db7b-190">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="7db7b-191">デスクトップ/Web</span><span class="sxs-lookup"><span data-stu-id="7db7b-191">Desktop/web</span></span>
- <span data-ttu-id="7db7b-192">モバイル (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="7db7b-192">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="7db7b-193">Teams電話</span><span class="sxs-lookup"><span data-stu-id="7db7b-193">Teams phones</span></span>
- <span data-ttu-id="7db7b-194">Teamsルーム</span><span class="sxs-lookup"><span data-stu-id="7db7b-194">Teams rooms</span></span>

<span data-ttu-id="7db7b-195">**その他のエンドポイント - 音声に関する通知**</span><span class="sxs-lookup"><span data-stu-id="7db7b-195">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="7db7b-196">SIP 電話</span><span class="sxs-lookup"><span data-stu-id="7db7b-196">SIP phones</span></span>
- <span data-ttu-id="7db7b-197">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7db7b-197">Skype for Business</span></span>
- <span data-ttu-id="7db7b-198">電話会議</span><span class="sxs-lookup"><span data-stu-id="7db7b-198">Audio conferencing</span></span>
- <span data-ttu-id="7db7b-199">PSTN 発信者</span><span class="sxs-lookup"><span data-stu-id="7db7b-199">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="7db7b-200">認定プログラムのTeams記録</span><span class="sxs-lookup"><span data-stu-id="7db7b-200">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="7db7b-201">公開されている API を公開することで、パートナーは CCaaS ソリューションを開発して Teams と統合できるほか、microsoft ソリューションから期待される品質、互換性、信頼性を提供するために、参加している各パートナーのソリューションがテストおよび検証されたという保証を顧客に提供するために、Microsoft Teams 認定プログラムのコンプライアンス記録を開発しました。</span><span class="sxs-lookup"><span data-stu-id="7db7b-201">In addition to publishing publicly available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="7db7b-202">次のパートナーは、パートナーのソリューションを認定Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7db7b-202">The following partners have certified their solution for Microsoft Teams.</span></span><br/><br/>

|<span data-ttu-id="7db7b-203">パートナー</span><span class="sxs-lookup"><span data-stu-id="7db7b-203">Partner</span></span>|<span data-ttu-id="7db7b-204">ソリューションの Web サイト</span><span class="sxs-lookup"><span data-stu-id="7db7b-204">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="7db7b-205">ASC テクノロジ</span><span class="sxs-lookup"><span data-stu-id="7db7b-205">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="7db7b-206">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="7db7b-206">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|<span data-ttu-id="7db7b-207">ダバー</span><span class="sxs-lookup"><span data-stu-id="7db7b-207">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="7db7b-208">NICE</span><span class="sxs-lookup"><span data-stu-id="7db7b-208">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="7db7b-209">Numonix</span><span class="sxs-lookup"><span data-stu-id="7db7b-209">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="7db7b-210">Verint</span><span class="sxs-lookup"><span data-stu-id="7db7b-210">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|<span data-ttu-id="7db7b-211">Theta Lake</span><span class="sxs-lookup"><span data-stu-id="7db7b-211">Theta Lake</span></span> |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|<span data-ttu-id="7db7b-212">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="7db7b-212">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |

<br/>
<span data-ttu-id="7db7b-213">次のパートナーは、ソリューションを認定するプロセスをMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="7db7b-213">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span><br/><br/>

|<span data-ttu-id="7db7b-214">パートナー</span><span class="sxs-lookup"><span data-stu-id="7db7b-214">Partner</span></span>|<span data-ttu-id="7db7b-215">ソリューションの Web サイト</span><span class="sxs-lookup"><span data-stu-id="7db7b-215">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="7db7b-216">Landis Technologies</span><span class="sxs-lookup"><span data-stu-id="7db7b-216">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="7db7b-217">Luware</span><span class="sxs-lookup"><span data-stu-id="7db7b-217">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="7db7b-218">Oak Innovation</span><span class="sxs-lookup"><span data-stu-id="7db7b-218">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="7db7b-219">赤いボックス</span><span class="sxs-lookup"><span data-stu-id="7db7b-219">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |

<span data-ttu-id="7db7b-220">このリストは、パートナーが参加して認定条件を満たしたときに更新されます。</span><span class="sxs-lookup"><span data-stu-id="7db7b-220">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7db7b-221">次の手順</span><span class="sxs-lookup"><span data-stu-id="7db7b-221">Next steps</span></span>

<span data-ttu-id="7db7b-222">認定プログラムへの参加を希望しているベンダーの場合は、 にメール<a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com。</a></span><span class="sxs-lookup"><span data-stu-id="7db7b-222">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
