---
title: "Microsoft Teams での電話会議"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams での電話会議の展開についての実践的なガイダンスを提供します。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: cf50e6468bdf4fc96419d39fbc889c5b5a220a8d
ms.sourcegitcommit: e0efee5350da54a1f1ae1c317f8613652c820bc6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="e21cf-103">Microsoft Teams での電話会議</span><span class="sxs-lookup"><span data-stu-id="e21cf-103">Audio Conferencing in Microsoft Teams</span></span>
=====================================

> [!IMPORTANT]
> <span data-ttu-id="e21cf-104">電話会議はパブリック プレビュー版です。</span><span class="sxs-lookup"><span data-stu-id="e21cf-104">Audio conferencing is in Public Preview.</span></span> <span data-ttu-id="e21cf-105">電話会議は、アーリー アダプター (EA) とプレビュー カスタマーを対象とし、リリースまたは更新ごとに変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-105">It's available to Early Adopters (EA) and preview customers and could change as it is released or updated.</span></span>

<span data-ttu-id="e21cf-106">Office 365 の電話会議 (旧名: PSTN 会議) では、参加者はどの電話端末からでも会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-106">Audio Conferencing in Office 365 (formerly known as PSTN Conferencing) allows participants to join your meetings from any telephone.</span></span> <span data-ttu-id="e21cf-107">Microsoft Teams でもこの機能が利用できるようになりました。ユーザーは自分の電話端末を使用して Teams 会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-107">This feature is now available in Microsoft Teams, allowing users to join Teams meetings using their phones.</span></span> <span data-ttu-id="e21cf-108">この記事の実践的なガイダンスでは、Office 365 FastTrack カスタマーの電話会議の導入フレームワークについて、構想、参加、価値の創出というステップごとに説明します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-108">The practical guidance in this article steps you through the Office 365 FastTrack customer journey framework for Audio Conferencing - Envision, Onboard, and Drive value.</span></span>

<span data-ttu-id="e21cf-109">Office 365 の[電話会議](https://go.microsoft.com/fwlink/?linkid=858992)で利用できる機能を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-109">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="e21cf-110">電話会議は Teams と Skype for Business Online の両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e21cf-110">Audio Conferencing supports both Teams and Skype for Business Online.</span></span> <span data-ttu-id="e21cf-111">現時点では、既存の Skype for Business 管理センターとリモート PowerShell で電話会議の管理インターフェースを利用できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-111">Currently, the existing Skype for Business Admin center and remote PowerShell provide the administrative interfaces to manage Audio Conferencing.</span></span>


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

<span data-ttu-id="e21cf-112">構想 <a name="Envision_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="e21cf-112">Envision <a name="Envision_AudioConferencing"> </a></span></span>
=========

<span data-ttu-id="e21cf-113">構想の段階は Office 365 カスタマーによる導入の基礎であり、電話会議を含むすべてのワークロードに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-113">The Envision phase provides the foundation for the Office 365 customer journey and is applicable to all workloads such as Audio Conferencing.</span></span>

<span data-ttu-id="e21cf-114">この段階では、ビジネス目標を明確にするとともに関連するプロジェクト ステークホルダーを編成して、最終的に次のことを実現します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-114">In this phase, business goals are captured, with relevant project stakeholders assembled, to ultimately deliver:</span></span>

-   <span data-ttu-id="e21cf-115">ビジネス ユース ケース、主要ステークホルダー、目的と主要成果 (OKR)、主要成功指標 (KSI)、リスク、環境評価、導入の準備状況、運用計画を含む高度な成功計画。</span><span class="sxs-lookup"><span data-stu-id="e21cf-115">a high-level success plan that contains business use cases, key stakeholders, objectives and key results (OKRs), key success indicators (KSIs), risks, environmental assessment, adoption readiness, and operational plan.</span></span>

-   <span data-ttu-id="e21cf-116">さらに、理想の最終的な状態を実現する、電話会議の詳細な技術実装計画。</span><span class="sxs-lookup"><span data-stu-id="e21cf-116">and subsequently, a detailed Audio Conferencing technical implementation plan to achieve the desired end state.</span></span>

<a name="define-business-use-cases-for-audio-conferencing"></a><span data-ttu-id="e21cf-117">電話会議のビジネス ユース ケースを定義する</span><span class="sxs-lookup"><span data-stu-id="e21cf-117">Define business use cases for Audio Conferencing</span></span>
------------------------------------------------

<span data-ttu-id="e21cf-118">電話会議により、会議の参加者は従来の電話回線、PBX、携帯電話を使用したダイヤルインで PSTN を介して参加できるため、組織は予約済みの会議への追加のエントリ ポイントを確保できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-118">Audio Conferencing provides organizations with additional entry points to any scheduled meetings by allowing meeting participants to join via PSTN by dialing in using traditional landline, PBX, or mobile phones.</span></span>

<span data-ttu-id="e21cf-119">これは、開催者や参加者がコンピューターにアクセスしていない場合、データ接続が利用できない場合、モバイル データの対応エリアにムラがあるリモート エリアでの接続や帯域幅が制限された無料の公共 Wi-Fi サービスへの接続など音声通信をサポートするには信頼性が不十分である場合、会議の参加者がすぐに利用できるテレフォニー エンドポイントを使用して会議にダイアルインすることを希望する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e21cf-119">This is useful when the organizer or participants are not in front of a computer, or when data connections are unavailable or unreliable to support voice communications—such as when in a remote area with spotty mobile data coverage, or if connected to a free, public Wi-Fi service with limited bandwidth, or when meeting participants prefer to dial in to the meeting using telephony endpoint readily accessible to them.</span></span>

<span data-ttu-id="e21cf-120">このステップでは、重要なプロジェクト ステークホルダーが電話会議の実装をサポートするビジネス ユース ケースを定義します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-120">In this step, core project stakeholders will define business use cases that support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="e21cf-121">ビジネス ユース ケースは、予期される測定可能なビジネス成果を定義、文書化することを目的としたもので、次の項目を含みます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-121">Business use cases are meant to define and document the expected and measurable business outcomes, and include the following:</span></span>

-   <span data-ttu-id="e21cf-122">現在のビジネス プロセスの説明。</span><span class="sxs-lookup"><span data-stu-id="e21cf-122">Description of current business process.</span></span>

-   <span data-ttu-id="e21cf-123">定義された既存のビジネス プロセスにおける課題。</span><span class="sxs-lookup"><span data-stu-id="e21cf-123">Challenges with existing business process defined.</span></span>

-   <span data-ttu-id="e21cf-124">課題の克服に向けたテクノロジーの有効性。</span><span class="sxs-lookup"><span data-stu-id="e21cf-124">How technology can help overcome these challenges.</span></span>

-   <span data-ttu-id="e21cf-125">課題を克服したときに予期される測定可能なビジネス成果。</span><span class="sxs-lookup"><span data-stu-id="e21cf-125">The expected and measurable business outcome if these challenges are overcome.</span></span>

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><span data-ttu-id="e21cf-126"><strong>現在のビジネス プロセスの説明</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-126"><strong>Description of current business process</strong></span></span></p>
<p><span data-ttu-id="e21cf-127">現在、Contoso 社は地元のテレフォニー プロバイダが提供する PSTN 会議サービスを利用しています。このサービスでは社内会議または外部関係者との会議に対して分単位の料金が発生しています。</span><span class="sxs-lookup"><span data-stu-id="e21cf-127">Contoso currently relies on PSTN conferencing services provided by the incumbent local telephony provider chargeable by meeting minutes for internal meetings and meetings involving external parties.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><span data-ttu-id="e21cf-128"><strong>既存のビジネス プロセスにおける課題</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-128"><strong>Challenges with existing business process</strong></span></span></p>
<p><span data-ttu-id="e21cf-129">Contoso 社は現在の PSTN 会議サービスに対して年間約 100 万ドルを費やしています。これは社内会議で発生するコストの 75％ を占めています。</span><span class="sxs-lookup"><span data-stu-id="e21cf-129">Contoso spends roughly USD 1 million per year for the current PSTN conferencing service, with 75% of the cost incurred for internal meetings.</span></span></p>
<p><span data-ttu-id="e21cf-130">PSTN 会議サービスによってホストされる従来のテレフォニー エンドポイントを使用した会議への参加は、最新の通信およびコラボレーション プラットフォームとして Teams を導入する組織の計画とは方向性が異なります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-130">The use of traditional telephony endpoints to join the meetings hosted by the PSTN conferencing service is not aligned with the plan for the organization to adopt Teams as modern communications and collaboration platform.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><span data-ttu-id="e21cf-131"><strong>課題の克服に向けたテクノロジーの有効性</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-131"><strong>How technology can overcome these challenges</strong></span></span></p>
<p><span data-ttu-id="e21cf-132">Microsoft Teams を最新の通信およびコラボレーション プラットフォームとして導入することで、内部ユーザーは最適なヘッドセットを備えた PC や会議室のデバイスを主に使用して会議に参加することが予測されます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-132">With the adoption of Microsoft Teams as modern communications and collaboration platform, internal users are expected to primarily join meetings using their PCs equipped with optimized headsets and meeting room devices.</span></span> <span data-ttu-id="e21cf-133">外部の参加者に対応する場合や、内部の参加者による PC の音声機能の使用が推奨されない状況に対応する場合にも、電話会議サービスを利用することが可能です。</span><span class="sxs-lookup"><span data-stu-id="e21cf-133">Audio Conferencing service will be available to support external participants or to support situations where the use of PC audio is not favorable for the internal participants.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><span data-ttu-id="e21cf-134"><strong>予期される測定可能なビジネス成果</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-134"><strong>Expected, measurable, business outcomes</strong></span></span></p>
<p><span data-ttu-id="e21cf-135">最新の通信およびコラボレーション プラットフォームとして位置付けられた Teams に移行し、電話会議サービスと連携させることにより、Contoso 社は PSTN 会議サービスを提供するためのコストを既存の PSTN 会議サービスの約 20％ にまで年間コストを大幅に削減できることが予期されます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-135">The move to Teams as modern communications and collaboration platform, combined with Audio Conferencing service, will greatly reduce the cost to deliver the PSTN conferencing service to the point that Contoso is expected to only spend approximately 20% of the annual cost of the existing PSTN conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-136">_表 1 ビジネス ユース ケースの例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-136">_Table 1 Business use case example_</span></span>


<span data-ttu-id="e21cf-137">このステップで、ビジネス ユース ケースの定義に加え、組織範囲とプロジェクト タイムラインを明確にすることで「構想」段階の次のステップへの移行が容易になります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-137">In addition to defining the business use cases, having a clarity around the organizational scope and project timelines at this step helps move onto the next step of the Envision phase.</span></span>

<a name="identify-key-stakeholders"></a><span data-ttu-id="e21cf-138">主要なステークホルダーを特定する</span><span class="sxs-lookup"><span data-stu-id="e21cf-138">Identify key stakeholders</span></span>
-------------------------

<span data-ttu-id="e21cf-139">上記のステップで定義したビジネス ユース ケースには、電話会議の実装についての組織範囲も含まれます。この組織範囲に基づいて、プロジェクトに関与する適任者を編成し、包括的なステークホルダー マトリックスを完成することができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-139">The business use cases defined in the previous step will include organizational scope of Audio Conferencing implementation, and based on that, the comprehensive stakeholder matrix can be completed to include the right people to be involved in the project.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-140">役割</span><span class="sxs-lookup"><span data-stu-id="e21cf-140">Role</span></span></th>
<th align="left"><span data-ttu-id="e21cf-141">説明</span><span class="sxs-lookup"><span data-stu-id="e21cf-141">Description</span></span></th>
<th align="left"><span data-ttu-id="e21cf-142">名前、連絡先情報、場所</span><span class="sxs-lookup"><span data-stu-id="e21cf-142">Name, contact information, location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-143"><strong>プロジェクト エグゼクティブ スポンサー</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-143"><strong>Project Executive Sponsor</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-144">プロジェクトおよびプロジェクトの目的実現に関する最終的な権限と説明責任</span><span class="sxs-lookup"><span data-stu-id="e21cf-144">Ultimate authority and accountability for the project and delivery on project objectives</span></span></li>
<li><span data-ttu-id="e21cf-145">プロジェクト リードによって報告された問題の解決を支援する</span><span class="sxs-lookup"><span data-stu-id="e21cf-145">Help resolve issues escalated by Project Lead</span></span></li>
<li><span data-ttu-id="e21cf-146">社内でのプロジェクトの目標についてのスポンサーとの意思疎通</span><span class="sxs-lookup"><span data-stu-id="e21cf-146">Sponsors communication within the company about project goals</span></span></li>
<li><span data-ttu-id="e21cf-147">主要な戦略決定に対する責任</span><span class="sxs-lookup"><span data-stu-id="e21cf-147">Responsible for making key strategic decisions</span></span></li>
<li><span data-ttu-id="e21cf-148">必要なリソースおよび予算の利用可能性に対する責任</span><span class="sxs-lookup"><span data-stu-id="e21cf-148">Responsible for availability of required resources and budget</span></span></p>
<li><span data-ttu-id="e21cf-149">主要な四半期ごとのビジネス レビュー (QBR)</span><span class="sxs-lookup"><span data-stu-id="e21cf-149">Leading Quarterly Business Reviews (QBR)</span></span></li>
<li><span data-ttu-id="e21cf-150">啓発キャンペーンの取り組みへの支援とサポート</span><span class="sxs-lookup"><span data-stu-id="e21cf-150">Buy-In and support of awareness campaign effort</span></span></li>
<li><span data-ttu-id="e21cf-151">プログラム ロールアウトのプロジェクト スポンサーとしての役割</span><span class="sxs-lookup"><span data-stu-id="e21cf-151">Serving as the Project Sponsor to the program rollout</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-152">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-152">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-153"><strong>プロジェクト リード</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-153"><strong>Project Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-154">プロジェクト チームの管理と指導</span><span class="sxs-lookup"><span data-stu-id="e21cf-154">Managing and leading project team</span></span></li>
<li><span data-ttu-id="e21cf-155">プロジェクトに関与するパートナーと作業チームを調整する</span><span class="sxs-lookup"><span data-stu-id="e21cf-155">Coordinates partners and working teams engaged in the project</span></span></li>
<li><span data-ttu-id="e21cf-156">四半期ごとの主要成果を実現するためのプロジェクト計画の作成と管理に対する責任</span><span class="sxs-lookup"><span data-stu-id="e21cf-156">Accountable for creating and managing project plans to meet quarterly key results</span></span></li>
<li><span data-ttu-id="e21cf-157">部門横断的な課題の解決</span><span class="sxs-lookup"><span data-stu-id="e21cf-157">Resolving cross-functional issues</span></span></li>
<li><span data-ttu-id="e21cf-158">プロジェクト スポンサーへの定期的な更新の提供</span><span class="sxs-lookup"><span data-stu-id="e21cf-158">Providing regular updates to the project sponsors</span></span></li>
<li><span data-ttu-id="e21cf-159">導入の状況を総合的なプロジェクト計画に取り入れる</span><span class="sxs-lookup"><span data-stu-id="e21cf-159">Incorporating Adoption aspects into the all-up project plan</span></span></li>
<li><span data-ttu-id="e21cf-160">月次ビジネスおよび運用レビュー (MBR) の指揮による四半期ごとのビジネス レビューへの貢献</span><span class="sxs-lookup"><span data-stu-id="e21cf-160">Leading Monthly Business and Operational Reviews (MBR), contributing to Quarterly Business Reviews</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-161">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-161">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-162"><strong>コラボレーション リード/アーキテクト</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-162"><strong>Collaboration Lead/Architect</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-163">企業の幹部によって定義されたコラボレーション戦略の実行に対する責任</span><span class="sxs-lookup"><span data-stu-id="e21cf-163">Responsible for execution on collaboration strategy defined by company executives</span></span></li>
<li><span data-ttu-id="e21cf-164">ビジネス目標を満たす企業向けコラボレーション製品の分析と選択</span><span class="sxs-lookup"><span data-stu-id="e21cf-164">Analyzing and choosing collaboration products for the company that meets business goals</span></span></li>
<li><span data-ttu-id="e21cf-165">コラボレーション製品の運用設計に対する責任</span><span class="sxs-lookup"><span data-stu-id="e21cf-165">Responsible for the design of the operations for collaboration products</span></span></li>
<li><span data-ttu-id="e21cf-166">運用とサポート モデルを定義する</span><span class="sxs-lookup"><span data-stu-id="e21cf-166">Defines operation and support model</span></span></li>
<li><span data-ttu-id="e21cf-167">月次および四半期ごとのビジネス レビューのへの貢献</span><span class="sxs-lookup"><span data-stu-id="e21cf-167">Contributing to Monthly and Quarterly Business Reviews</span></span></li><ul></td>
<td align="left"><span data-ttu-id="e21cf-168">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-168">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-169"><strong>コンサルタント</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-169"><strong>Consultant</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-170">構成サービスに対する責任</span><span class="sxs-lookup"><span data-stu-id="e21cf-170">Responsible for configuration services</span></span></li>
<li><span data-ttu-id="e21cf-171">全体的なソリューション アーキテクチャに貢献する</span><span class="sxs-lookup"><span data-stu-id="e21cf-171">Contributes in overall solution architecture</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-172">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-172">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-173"><strong>プロジェクト マネージャー</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-173"><strong>Project Manager</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-174">プロジェクト計画の作成と保守</span><span class="sxs-lookup"><span data-stu-id="e21cf-174">Developing and maintaining project plan</span></span></li>
<li><span data-ttu-id="e21cf-175">プロジェクト計画と予算に見合ったプロジェクト成果の管理</span><span class="sxs-lookup"><span data-stu-id="e21cf-175">Managing project deliverables in line with project plan and budget</span></span></li>
<li><span data-ttu-id="e21cf-176">報告を含む、プロジェクトの問題の記録と管理</span><span class="sxs-lookup"><span data-stu-id="e21cf-176">Recording and managing project issues, including escalations</span></span></li>
<li><span data-ttu-id="e21cf-177">週次スタンド アップ コールの実施</span><span class="sxs-lookup"><span data-stu-id="e21cf-177">Conducting weekly stand up calls</span></span></li>
<li><span data-ttu-id="e21cf-178">プロジェクト エグゼクティブ スポンサーと連携する、プロジェクト エグゼクティブ スポンサーに更新を提供する</span><span class="sxs-lookup"><span data-stu-id="e21cf-178">Liaises with, and provides updates to project executive sponsors</span></span></li>
<li><span data-ttu-id="e21cf-179">アーキテクトとの協力による変更管理およびコミュニケーション プランの定義</span><span class="sxs-lookup"><span data-stu-id="e21cf-179">Working with the Architect to define the Change Management approach and Communication Plans</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-180">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-180">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-181"><strong>変更管理/導入の専門家</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-181"><strong>Change Management/Adoption Specialist</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-182">検出段階から導入およびトレーニング プロセスへの移行に関する意見を提供する</span><span class="sxs-lookup"><span data-stu-id="e21cf-182">Provide input on Discovery phase into adoption and training processes</span></span></li>
<li><span data-ttu-id="e21cf-183">導入戦略ワークショップに参加する</span><span class="sxs-lookup"><span data-stu-id="e21cf-183">Participate in adoption strategy workshop</span></span></li>
<li><span data-ttu-id="e21cf-184">導入戦略の策定と導入戦略に対する責任</span><span class="sxs-lookup"><span data-stu-id="e21cf-184">Developing and responsible for adoption strategy</span></span></li>
<li><span data-ttu-id="e21cf-185">コミュニケーション プランの作成と実行</span><span class="sxs-lookup"><span data-stu-id="e21cf-185">Developing and executing communication plan</span></span></li>
<li><span data-ttu-id="e21cf-186">エンド ユーザーへのトレーニングの提供に対する責任</span><span class="sxs-lookup"><span data-stu-id="e21cf-186">Responsible for delivering trainings to end users</span></span></li>
<li><span data-ttu-id="e21cf-187">フィードバックを収集し、調査を実施する</span><span class="sxs-lookup"><span data-stu-id="e21cf-187">Collect feedback and conduct surveys</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-188">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-188">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-189"><strong>ネットワーク リード</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-189"><strong>Network Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-190">検出段階からネットワーク設計への移行に関する意見を提供する</span><span class="sxs-lookup"><span data-stu-id="e21cf-190">Providing input on Discovery phase into network design</span></span></li>
<li><span data-ttu-id="e21cf-191">構想ワークショップでの計画作成への参加</span><span class="sxs-lookup"><span data-stu-id="e21cf-191">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="e21cf-192">プロジェクト実行時のネットワーク チームの作業を調整する</span><span class="sxs-lookup"><span data-stu-id="e21cf-192">Coordinates work of networking team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-193">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-193">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-194"><strong>セキュリティ リード</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-194"><strong>Security Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-195">検出段階からセキュリティ設計およびプロセスへの移行に関する意見を提供する</span><span class="sxs-lookup"><span data-stu-id="e21cf-195">Providing input on Discovery phase into security design and processes</span></span></li>
<li><span data-ttu-id="e21cf-196">構想ワークショップでの計画作成への参加</span><span class="sxs-lookup"><span data-stu-id="e21cf-196">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="e21cf-197">プロジェクト実行時のセキュリティ チームの作業を調整する</span><span class="sxs-lookup"><span data-stu-id="e21cf-197">Coordinates work of security team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-198">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-198">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-199"><strong>テレフォニー リード</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-199"><strong>Telephony Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-200">検出段階からテレフォニー設計への移行に関する意見を提供する</span><span class="sxs-lookup"><span data-stu-id="e21cf-200">Providing input on Discovery phase into telephony design</span></span></li>
<li><span data-ttu-id="e21cf-201">構想ワークショップでの計画作成への参加</span><span class="sxs-lookup"><span data-stu-id="e21cf-201">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="e21cf-202">プロジェクト実行時のテレフォニー チームの作業を調整する</span><span class="sxs-lookup"><span data-stu-id="e21cf-202">Coordinates work of telephony team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-203">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-203">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-204"><strong>デスクトップ リード</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-204"><strong>Desktop Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-205">検出段階からクライアントおよび更新プロセスへの移行に関する意見を提供する</span><span class="sxs-lookup"><span data-stu-id="e21cf-205">Providing input on Discovery phase into clients and update process</span></span></li>
<li><span data-ttu-id="e21cf-206">構想ワークショップでの計画作成への参加</span><span class="sxs-lookup"><span data-stu-id="e21cf-206">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="e21cf-207">プロジェクト実行時のデスクトップ チームの作業を調整する</span><span class="sxs-lookup"><span data-stu-id="e21cf-207">Coordinates work of desktop team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-208">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-208">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-209"><strong>サポート/ヘルプ デスク リード</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-209"><strong>Support/Help Desk Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-210">検出段階から運用およびサポート モデルへの移行に関する意見を提供する</span><span class="sxs-lookup"><span data-stu-id="e21cf-210">Providing input on Discovery phase into operational and support model</span></span></li>
<li><span data-ttu-id="e21cf-211">構想ワークショップでの計画作成への参加</span><span class="sxs-lookup"><span data-stu-id="e21cf-211">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="e21cf-212">サポート モデルの計画への参加</span><span class="sxs-lookup"><span data-stu-id="e21cf-212">Participating into support model planning</span></span></li>
<li><span data-ttu-id="e21cf-213">プロジェクト実行時のサポート チーム/リソースの作業を調整する</span><span class="sxs-lookup"><span data-stu-id="e21cf-213">Coordinates work of support teams/resources during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-214">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-214">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-215"><strong>ビジネス ユニットの代表者</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-215"><strong>Business Unit Representatives</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-216">エンド ユーザーを対象とした導入ガイドと資料の作成に貢献する</span><span class="sxs-lookup"><span data-stu-id="e21cf-216">Contribute in End User based adoption guides and materials</span></span></li>
<li><span data-ttu-id="e21cf-217">ビジネス ユース ケースへの貢献とレビュー</span><span class="sxs-lookup"><span data-stu-id="e21cf-217">Contribute to and review Business Use Cases</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-218">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-218">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-219"><strong>展開リード</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-219"><strong>Deployment Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-220">展開の前提条件が満たされていることを確認する</span><span class="sxs-lookup"><span data-stu-id="e21cf-220">Ensure that deployment prerequisites are met</span></span></li>
<li><span data-ttu-id="e21cf-221">準備および展開段階のアクティビティに必要なカスタマー リソースを手配する</span><span class="sxs-lookup"><span data-stu-id="e21cf-221">Engage customer resources to engage on prepare and deploy stage activities</span></span></li>
<li><span data-ttu-id="e21cf-222">準備および展開の状況をレビューする会議に参加する</span><span class="sxs-lookup"><span data-stu-id="e21cf-222">Participate in meetings to review prepare and deploy status</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-223">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-223">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-224"><strong>IT 管理者</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-224"><strong>IT Admins</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-225">テストの計画と実施を支援する責任がある IT 専門家</span><span class="sxs-lookup"><span data-stu-id="e21cf-225">IT Pros responsible for assistance with test planning and execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-226">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-226">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-227"><strong>サービス所有者</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-227"><strong>Service Owner</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-228">電話会議サービス全般の運用に対する責任</span><span class="sxs-lookup"><span data-stu-id="e21cf-228">Is responsible for the operation of the Audio Conferencing service all up</span></span></li>
<li><span data-ttu-id="e21cf-229">電話会議サービスの所有者</span><span class="sxs-lookup"><span data-stu-id="e21cf-229">Owner of Audio Conferencing service</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-230">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-230">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-231"><strong>品質チャンピオン</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-231"><strong>Quality Champion</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-232">品質、信頼性を向上し、ユーザー フィードバックを促進する</span><span class="sxs-lookup"><span data-stu-id="e21cf-232">Drives quality, reliability and user feedback</span></span></li>
<li><span data-ttu-id="e21cf-233">品質の傾向を特定し、該当チームによる修正を促す</span><span class="sxs-lookup"><span data-stu-id="e21cf-233">Identifies the quality trends and drive remediation with the respective teams</span></span></li>
<li><span data-ttu-id="e21cf-234">運営委員会を介してリーダーシップに報告する</span><span class="sxs-lookup"><span data-stu-id="e21cf-234">Reports through the steering committee back to leadership</span></span></li>
<li><span data-ttu-id="e21cf-235">「Rate My Call (通話を評価する)」および「Net Promoter Score (ネット プロモーター スコア)」を使用して品質、信頼性、ユーザーの感想を報告する</span><span class="sxs-lookup"><span data-stu-id="e21cf-235">Reports on quality, reliability, and user sentiment through Rate My Call and Net Promoter Score</span></span></li></ul></td>
<td align="left"><span data-ttu-id="e21cf-236">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-236">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-237">_表 2 ステークホルダー マトリックス テンプレートの例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-237">_Table 2 Stakeholder matrix template example_</span></span>


> [!NOTE]
> <span data-ttu-id="e21cf-238">上記の例の表およびこのドキュメント内の以降の表はテンプレートとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-238">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="e21cf-239">「TBA」(今後追加される予定) と記載されている箇所には、計画プロセスを遂行する上で満たす必要のある情報が入ります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-239">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a><span data-ttu-id="e21cf-240">目的、主要成果、主要成功指標、およびリスクについて定義する</span><span class="sxs-lookup"><span data-stu-id="e21cf-240">Define objectives and key results, key success indicators, and risks</span></span>
--------------------------------------------------------------------

<span data-ttu-id="e21cf-241">プロジェクト ステークホルダーの編成が完了すると、ビジネス ユース ケース、組織範囲、プロジェクト タイムラインを目的と主要成果 (OKR) に変換し、プロジェクトの成功の測定方法を主要成功指標 (KSI) の一覧として定義できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-241">With the project stakeholders assembled, business use cases, organizational scope and project timelines can be translated into objectives and key results (OKRs) and the measures of project success can be defined into a list of key success indicators (KSIs).</span></span>

<span data-ttu-id="e21cf-242">プロジェクト ステークホルダーは、OKR と KSI の定義に完全に参加することで、プロジェクトに対するオーナーシップを感じることができ、組織のビジネス要件に同調することができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-242">Full participation from project stakeholders when defining the OKRs and KSIs will ensure sense of ownership and they are aligned to organizational business requirements.</span></span>

<span data-ttu-id="e21cf-243">OKR には、プロジェクトの開始段階で設定した目的の一覧、四半期ごとに定義した測定可能な主要成果が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-243">OKRs will contain the list of objectives set in the beginning of the project, with measurable key results defined in a quarterly basis.</span></span> <span data-ttu-id="e21cf-244">主要成果は毎月レビューを行ってプロジェクト全体の状況を追跡し、必要な場合は状況に応じて四半期計画を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-244">The key results are reviewed monthly to track status of the overall project, and based on progress, adjustment to the quarterly plans can be made as needed.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><p><span data-ttu-id="e21cf-245"><strong>ビジョン</strong>: Office 365 への投資を最大化して生産性を向上</span><span class="sxs-lookup"><span data-stu-id="e21cf-245"><strong>Vision</strong>: Increase productivity by maximizing Office 365 investments</span></span></p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-246"><strong>目的</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-246"><strong>Objectives</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-247"><strong>主要成果</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-247"><strong>Key Results</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-248"><strong>やるべきこと</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-248"><strong>To Do</strong></span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-249">2018 年度末までに Teams での電話会議を展開する</span><span class="sxs-lookup"><span data-stu-id="e21cf-249">Deploy Audio Conferencing in Teams by end of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="e21cf-250">18 年度第 1 四半期: Teams での電話会議をグローバルに展開する</span><span class="sxs-lookup"><span data-stu-id="e21cf-250">FY18Q1: Deploy Audio Conferencing in Teams globally</span></span></td>
<td align="left"><p><span data-ttu-id="e21cf-251">構想</span><span class="sxs-lookup"><span data-stu-id="e21cf-251">Envision</span></span></p>
<ul><li><span data-ttu-id="e21cf-252">成功計画を作成する</span><span class="sxs-lookup"><span data-stu-id="e21cf-252">Create success plan</span></span></li>
<li><span data-ttu-id="e21cf-253">詳細な技術実装計画を作成する</span><span class="sxs-lookup"><span data-stu-id="e21cf-253">Create detailed technical implementation plan</span></span></li></ul>
<p><span data-ttu-id="e21cf-254">参加</span><span class="sxs-lookup"><span data-stu-id="e21cf-254">Onboard</span></span></p>
<ul><li><span data-ttu-id="e21cf-255">成功計画を実施する</span><span class="sxs-lookup"><span data-stu-id="e21cf-255">Execute success plan</span></span></li>
<li><span data-ttu-id="e21cf-256">技術実装計画を実施する</span><span class="sxs-lookup"><span data-stu-id="e21cf-256">Execute technical implementation plan</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-257">2018 年度半ばまでに旧 PSTN 会議をグローバルで廃止する</span><span class="sxs-lookup"><span data-stu-id="e21cf-257">Decommission legacy PSTN Conferencing service globally by mid of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="e21cf-258">18 年度第 2 四半期: 旧 PSTN 会議サービスをグローバルで廃止する</span><span class="sxs-lookup"><span data-stu-id="e21cf-258">FY18Q2: Decommission legacy PSTN Conferencing service globally</span></span></td>
<td align="left"><p><span data-ttu-id="e21cf-259">価値の創出</span><span class="sxs-lookup"><span data-stu-id="e21cf-259">Drive Value</span></span></p>
<ul><li><span data-ttu-id="e21cf-260">ユーザー エンゲージメントを推進し、導入を促進する</span><span class="sxs-lookup"><span data-stu-id="e21cf-260">Boost user engagement and drive adoption</span></span></li>
<li><span data-ttu-id="e21cf-261">変更の管理と用意を行う</span><span class="sxs-lookup"><span data-stu-id="e21cf-261">Manage and prepare for change</span></span></li>
<li><span data-ttu-id="e21cf-262">成功を測定、共有して、反復する</span><span class="sxs-lookup"><span data-stu-id="e21cf-262">Measure, share success, and iterate</span></span></li></ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-263">_表 3 OKR の例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-263">_Table 3 Example of OKRs_</span></span>


<span data-ttu-id="e21cf-264">KSI は主要成果の質と成功を測定し、良い結果と悪い結果を詳細に示すことで OKR に関する 2 つの特性 (達成または未達成) を補足します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-264">KSIs measure quality and success of the key results and complement the binary nature of OKRs (achieved or not achieved), by detailing the good and/or bad results.</span></span> <span data-ttu-id="e21cf-265">KSI を定義するときには、SMART (具体的な、測定可能な、割り当て可能な、現実的な、適時の ) 条件を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e21cf-265">When defining KSIs, we recommend leveraging the “specific, measurable, assignable, realistic, time-related” or SMART criteria.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-266">種類</span><span class="sxs-lookup"><span data-stu-id="e21cf-266">Type</span></span></th>
<th align="left"><p><span data-ttu-id="e21cf-267">KSI 質問 &amp;</span><span class="sxs-lookup"><span data-stu-id="e21cf-267">KSI questions &amp;</span></span></p>
<p><span data-ttu-id="e21cf-268">条件</span><span class="sxs-lookup"><span data-stu-id="e21cf-268">criteria</span></span></p></th>
<th align="left"><span data-ttu-id="e21cf-269">測定方法</span><span class="sxs-lookup"><span data-stu-id="e21cf-269">How measured</span></span></th>
<th align="left"><span data-ttu-id="e21cf-270">成功の条件</span><span class="sxs-lookup"><span data-stu-id="e21cf-270">Success criteria</span></span></th>
<th align="left"><span data-ttu-id="e21cf-271">測定済み</span><span class="sxs-lookup"><span data-stu-id="e21cf-271">Measured</span></span></th>
<th align="left"><span data-ttu-id="e21cf-272">責任</span><span class="sxs-lookup"><span data-stu-id="e21cf-272">Responsible</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-273"><strong>使用例/導入</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-273"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-274">通話の品質は以前のソリューションに比べて同等以上である</span><span class="sxs-lookup"><span data-stu-id="e21cf-274">Call quality is equal to or better than the previous solution</span></span></td>
<td align="left"><span data-ttu-id="e21cf-275">アンケート</span><span class="sxs-lookup"><span data-stu-id="e21cf-275">Survey page</span></span></td>
<td align="left"><span data-ttu-id="e21cf-276">ユーザーの 80% が同意または強く同意している</span><span class="sxs-lookup"><span data-stu-id="e21cf-276">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="e21cf-277">有効化後および四半期ごと</span><span class="sxs-lookup"><span data-stu-id="e21cf-277">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="e21cf-278">情報技術チーム</span><span class="sxs-lookup"><span data-stu-id="e21cf-278">Information Technology team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-279"><strong>使用例/導入</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-279"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-280">Teams の導入により通信プロセスが簡易化された</span><span class="sxs-lookup"><span data-stu-id="e21cf-280">Teams made the communication process easier</span></span></td>
<td align="left"><span data-ttu-id="e21cf-281">アンケート</span><span class="sxs-lookup"><span data-stu-id="e21cf-281">Survey page</span></span></td>
<td align="left"><span data-ttu-id="e21cf-282">ユーザーの 80% が同意または強く同意している</span><span class="sxs-lookup"><span data-stu-id="e21cf-282">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="e21cf-283">有効化後および四半期ごと</span><span class="sxs-lookup"><span data-stu-id="e21cf-283">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="e21cf-284">変更管理チーム</span><span class="sxs-lookup"><span data-stu-id="e21cf-284">Change Management team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-285"><strong>使用例/導入</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-285"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-286">ユーザーが積極的にソリューションを利用している</span><span class="sxs-lookup"><span data-stu-id="e21cf-286">Users actively use the solution</span></span></td>
<td align="left"><span data-ttu-id="e21cf-287">Office 365 レポート、通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="e21cf-287">Office 365 reports, Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-288">ユーザーの 80% が毎日使用するアクティブ ユーザーである</span><span class="sxs-lookup"><span data-stu-id="e21cf-288">80% of users are active daily users</span></span></td>
<td align="left"><span data-ttu-id="e21cf-289">毎日</span><span class="sxs-lookup"><span data-stu-id="e21cf-289">Daily</span></span></td>
<td align="left"><span data-ttu-id="e21cf-290">変更管理チーム</span><span class="sxs-lookup"><span data-stu-id="e21cf-290">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-291"><strong>使用例/品質</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-291"><strong>Usage/quality</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-292">低い通話品質/会議品質の割合を最低限に抑える</span><span class="sxs-lookup"><span data-stu-id="e21cf-292">Percentage of poor calls/conferences should be minimal</span></span></td>
<td align="left"><span data-ttu-id="e21cf-293">通話品質ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="e21cf-293">Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-294">&lt; 毎月 5% の低品質通話</span><span class="sxs-lookup"><span data-stu-id="e21cf-294">&lt; 5% of poor calls per month</span></span></td>
<td align="left"><span data-ttu-id="e21cf-295">毎日</span><span class="sxs-lookup"><span data-stu-id="e21cf-295">Daily</span></span></td>
<td align="left"><span data-ttu-id="e21cf-296">情報技術チーム</span><span class="sxs-lookup"><span data-stu-id="e21cf-296">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-297"><strong>使用例/サポート</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-297"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-298">テクニカル サポートの受け方を知っている</span><span class="sxs-lookup"><span data-stu-id="e21cf-298">I know how to get technical support</span></span></td>
<td align="left"><span data-ttu-id="e21cf-299">アンケート</span><span class="sxs-lookup"><span data-stu-id="e21cf-299">Survey page</span></span></td>
<td align="left"><span data-ttu-id="e21cf-300">ユーザーの 90% が同意または強く同意している</span><span class="sxs-lookup"><span data-stu-id="e21cf-300">90% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="e21cf-301">有効化後および四半期ごと</span><span class="sxs-lookup"><span data-stu-id="e21cf-301">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="e21cf-302">変更管理チーム</span><span class="sxs-lookup"><span data-stu-id="e21cf-302">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-303"><strong>使用例/サポート</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-303"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-304">テクニカル サポートの品質に満足している</span><span class="sxs-lookup"><span data-stu-id="e21cf-304">I am satisfied with the quality of technical support</span></span></td>
<td align="left"><span data-ttu-id="e21cf-305">アンケート</span><span class="sxs-lookup"><span data-stu-id="e21cf-305">Survey page</span></span></td>
<td align="left"><span data-ttu-id="e21cf-306">ユーザーの 80% が同意または強く同意している</span><span class="sxs-lookup"><span data-stu-id="e21cf-306">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="e21cf-307">各インシデント後</span><span class="sxs-lookup"><span data-stu-id="e21cf-307">After each incident</span></span></td>
<td align="left"><span data-ttu-id="e21cf-308">情報技術チーム</span><span class="sxs-lookup"><span data-stu-id="e21cf-308">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-309"><strong>財務</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-309"><strong>Financial</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-310">旧会議手段の時間 (分) の削減</span><span class="sxs-lookup"><span data-stu-id="e21cf-310">Reduction of legacy conferencing minutes</span></span></td>
<td align="left"><span data-ttu-id="e21cf-311">財務システム</span><span class="sxs-lookup"><span data-stu-id="e21cf-311">Financial system</span></span></td>
<td align="left"><span data-ttu-id="e21cf-312">定義された ROI を達成する</span><span class="sxs-lookup"><span data-stu-id="e21cf-312">Meet defined ROI</span></span></td>
<td align="left"><span data-ttu-id="e21cf-313">ROI に基づく</span><span class="sxs-lookup"><span data-stu-id="e21cf-313">Based on ROI</span></span></td>
<td align="left"><span data-ttu-id="e21cf-314">変更管理チーム</span><span class="sxs-lookup"><span data-stu-id="e21cf-314">Change Management team</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-315">_表 4 KSI の例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-315">_Table 4 Example of KSIs_</span></span>


<span data-ttu-id="e21cf-316">この演習の一環としてビジネス リスクを特定し、特定した各リスクについて軽減計画を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-316">You need to identify business risks as part of this exercise and define a mitigation plan for each identified risk.</span></span> <span data-ttu-id="e21cf-317">この情報はリスク計画に取り入れることができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-317">This information can be captured into a risk plan.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-318">リスク</span><span class="sxs-lookup"><span data-stu-id="e21cf-318">Risk</span></span></th>
<th align="left"><span data-ttu-id="e21cf-319">可能性</span><span class="sxs-lookup"><span data-stu-id="e21cf-319">Likelihood</span></span></th>
<th align="left"><span data-ttu-id="e21cf-320">影響</span><span class="sxs-lookup"><span data-stu-id="e21cf-320">Impact</span></span></th>
<th align="left"><span data-ttu-id="e21cf-321">全体</span><span class="sxs-lookup"><span data-stu-id="e21cf-321">Overall</span></span></th>
<th align="left"><span data-ttu-id="e21cf-322">軽減計画</span><span class="sxs-lookup"><span data-stu-id="e21cf-322">Mitigation plan</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-323">予定されている合併により最大で 1,000 人の追加が見込まれる</span><span class="sxs-lookup"><span data-stu-id="e21cf-323">Upcoming merger will add up to 1,000 people</span></span></td>
<td align="left"><span data-ttu-id="e21cf-324">高</span><span class="sxs-lookup"><span data-stu-id="e21cf-324">High availability</span></span></td>
<td align="left"><span data-ttu-id="e21cf-325">高</span><span class="sxs-lookup"><span data-stu-id="e21cf-325">High availability</span></span></td>
<td align="left"><span data-ttu-id="e21cf-326">高</span><span class="sxs-lookup"><span data-stu-id="e21cf-326">High availability</span></span></td>
<td align="left"><p><span data-ttu-id="e21cf-327">合併される会社については、独自のプロセス (構想、参加、価値の創出) で OKR を分離する</span><span class="sxs-lookup"><span data-stu-id="e21cf-327">For merged companies, separate OKR with own process (Envision, Onboard, Drive Value)</span></span></p>
<p><span data-ttu-id="e21cf-328">既存の OKR に含めない</span><span class="sxs-lookup"><span data-stu-id="e21cf-328">Do not include them in existing OKRs</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-329">電話番号の移行のためプロジェクトの完了が遅れる</span><span class="sxs-lookup"><span data-stu-id="e21cf-329">Telephone number porting will delay project completion</span></span></td>
<td align="left"><span data-ttu-id="e21cf-330">高</span><span class="sxs-lookup"><span data-stu-id="e21cf-330">High availability</span></span></td>
<td align="left"><span data-ttu-id="e21cf-331">高</span><span class="sxs-lookup"><span data-stu-id="e21cf-331">High availability</span></span></td>
<td align="left"><span data-ttu-id="e21cf-332">高</span><span class="sxs-lookup"><span data-stu-id="e21cf-332">High availability</span></span></td>
<td align="left"><p><span data-ttu-id="e21cf-333">電話番号の移行をサポートするために必要なすべての情報 (カスタマー サービス レコード、請求書の詳細、承認状など) を事前に用意する</span><span class="sxs-lookup"><span data-stu-id="e21cf-333">Prepare all the required information to support telephone number porting ahead of time (i.e.: customer service record, billing details, Letter of Authorization)</span></span></p>
<p><span data-ttu-id="e21cf-334">電話番号の移行の所要時間に対応するためプロジェクト タイムラインを調整する</span><span class="sxs-lookup"><span data-stu-id="e21cf-334">Adjust project timeline to accommodate turnaround time of telephone number porting execution</span></span></p>
<p><span data-ttu-id="e21cf-335">新しいダイヤルイン会議番号の使用を外部の参加者に伝える</span><span class="sxs-lookup"><span data-stu-id="e21cf-335">Communicate the use of new dial-in conferencing numbers to external participants</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-336">計画されたネットワーク再設計</span><span class="sxs-lookup"><span data-stu-id="e21cf-336">Planned network redesign</span></span></td>
<td align="left"><span data-ttu-id="e21cf-337">高</span><span class="sxs-lookup"><span data-stu-id="e21cf-337">High availability</span></span></td>
<td align="left"><span data-ttu-id="e21cf-338">中</span><span class="sxs-lookup"><span data-stu-id="e21cf-338">Medium</span></span></td>
<td align="left"><span data-ttu-id="e21cf-339">中</span><span class="sxs-lookup"><span data-stu-id="e21cf-339">Medium</span></span></td>
<td align="left"><span data-ttu-id="e21cf-340">最新の通信およびコラボレーション プラットフォームとして Teams を実装する前に、プロジェクトの範囲においてサイトに対する Network Readiness Assessment を実行します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-340">Before implementing Teams as modern communications and collaboration platform, run network readiness assessment for sites in scope of the project</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-341">_表 5 リスク計画の例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-341">_Table 5 Risk plan example_</span></span>


<a name="assess-environment-and-evaluate-adoption-readiness"></a><span data-ttu-id="e21cf-342">環境の評価と、導入の準備状況の評価を行う</span><span class="sxs-lookup"><span data-stu-id="e21cf-342">Assess environment and evaluate adoption readiness</span></span>
--------------------------------------------------

<span data-ttu-id="e21cf-343">設定した OKR を達成するため、ソリューションの高度アーキテクチャを定義しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-343">To achieve the intended OKRs, you may have to define the high-level architecture of the solution.</span></span> <span data-ttu-id="e21cf-344">その場合は、環境を検出して、IT とテレフォニーのインフラストラクチャ、ネットワーキング、運用に関連するすべての側面を評価します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-344">It takes environmental discovery to evaluate all aspects relating to IT and telephony infrastructure, networking, and operations.</span></span>

<span data-ttu-id="e21cf-345">環境の検出には、電話会議のビジネス ユース ケースをサポートするための PC およびモバイル デバイスの準備状況 (ハードウェア要件からソフトウェア要件まで) の評価など、エンドユーザー コンピューティングに関連するすべての事項が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-345">All matters related to end-user computing, such as readiness assessment of the personal computers and mobile devices to support Audio Conferencing business use cases, from hardware requirements to software requirements, will be included as part of the environmental discovery.</span></span>

<span data-ttu-id="e21cf-346">環境の検出では、[電話番号を Microsoft に移行する](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e)必要があるかどうかも明らかになります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-346">Environmental discovery can also uncover if there are requirements to [transfer phone numbers to Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span> <span data-ttu-id="e21cf-347">これによって、組織は必要性の有無に応じてプロジェクト計画を調整し、番号の移行に必要な情報を準備することができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-347">This will help your organization to adjust the project plan accordingly and prepare the necessary information required for number porting.</span></span> <span data-ttu-id="e21cf-348">次の[アンケート](https://go.microsoft.com/fwlink/?linkid=858995)を活用して環境の検出を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-348">You can perform environmental discovery by leveraging the following [questionnaire](https://go.microsoft.com/fwlink/?linkid=858995).</span></span>

<span data-ttu-id="e21cf-349">環境の検出では、Network Readiness Assessment を実行して、電話会議サービスの実装をサポートする準備がネットワークで整っているかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-349">Environmental discovery must include network readiness assessment to ensure the network is ready to support the implementation of the Audio Conferencing service.</span></span>

<span data-ttu-id="e21cf-350">電話会議サービスをサポートするためのネットワークの準備状況は、環境の検出で [My Advisor Network Planner ツール](https://go.microsoft.com/fwlink/?linkid=858999) に取得した情報 (インターネット接続性や WAN トポロジ、サイト リンク、利用可能な帯域幅、ペルソナ分析データ (各ワークロードについて予期される使用方法に変換可能)) を活用して判断できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-350">Network readiness to support the Audio Conferencing service can be determined by leveraging the information captured through the environmental discovery (such as details of internet connectivity and WAN topology, site links, available bandwidth, and persona analysis data (that can be translated into an expected usage of each workload) into the [My Advisor Network Planner tool](https://go.microsoft.com/fwlink/?linkid=858999).</span></span> <span data-ttu-id="e21cf-351">ネットワークの準備状況をさらに深く確認する場合は、[Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) または [Network Readiness Assessment ツール パートナー](https://go.microsoft.com/fwlink/?linkid=859003)によって提供されるソリューションを使用してリアルタイムのメディア トラフィック シミュレーションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-351">To further confirm network readiness, real-time media traffic simulation can be performed using the solutions provided by [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) or by [Network Readiness Assessment tools partners](https://go.microsoft.com/fwlink/?linkid=859003).</span></span>

<span data-ttu-id="e21cf-352">Network Readiness Assessment の結果により、必要なネットワーク最適化、または電話会議の実装を成功させるために必要な修復が明確になります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-352">The results of the Network Readiness Assessment will paint a clearer picture of the required network optimization or remediation required for the success of Audio Conferencing implementation.</span></span>

<span data-ttu-id="e21cf-353">導入の準備状況は、ペルソナ分析を行い、電話会議サービスの実装の対象とする組織内のペルソナの一覧を作成することで評価できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-353">Adoption readiness can be evaluated by executing persona analysis to come up with a list of personas in the organization who can be targeted for the implementation of Audio Conferencing service.</span></span> <span data-ttu-id="e21cf-354">ペルソナ分析には、設定したビジネス成果を実現するために必要な追加の周辺機器やデバイスの特定も含まれます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-354">The persona analysis includes the identification of additional peripherals or devices required to realize the intended business outcomes.</span></span>

<span data-ttu-id="e21cf-355">ペルソナ分析を行う場合は、[Persona Alignment (ペルソナ調整)](https://go.microsoft.com/fwlink/?linkid=859005) ワークショップ デッキと [Persona Feature Matrix (ペルソナ機能マトリックス)](https://go.microsoft.com/fwlink/?linkid=859006) を活用して関連するプロジェクト ステークホルダーが参加するワークショップを開催できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-355">To perform persona analysis, you can conduct a workshop by involving relevant project stakeholders, leveraging the [Persona Alignment](https://go.microsoft.com/fwlink/?linkid=859005) workshop deck and [Persona Feature Matrix](https://go.microsoft.com/fwlink/?linkid=859006).</span></span> <span data-ttu-id="e21cf-356">ペルソナ分析ワークショップの結果は [Persona Analysis Report (ペルソナ分析レポート)](https://go.microsoft.com/fwlink/?linkid=859007) テンプレートを使用してレポートにまとめることができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-356">The result of persona analysis workshop can be summarized into a report using the [Persona Analysis Report](https://go.microsoft.com/fwlink/?linkid=859007) template.</span></span>


> [!NOTE]
> <span data-ttu-id="e21cf-357">Discovery Questionnaire (検出アンケート) と Persona Analysis (ペルソナ分析)の例は Skype for Business Online 用に作成されたものですが、その内容の大部分は Teams にも関連します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-357">While the Discovery Questionnaire and Persona Analysis examples were initially written for Skype for Business Online, a majority of the content is relevant to Teams.</span></span> <span data-ttu-id="e21cf-358">プロジェクトの目標に関連しない項目は自由に変更または削除してください。</span><span class="sxs-lookup"><span data-stu-id="e21cf-358">Feel free to modify and remove items that are not relevant to the project goals.</span></span>


<span data-ttu-id="e21cf-359">環境の評価と導入の準備状況の評価の一環として、技術的なリスクを特定し、特定した各リスクについて軽減計画を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-359">You can identify technical risks as part of an environmental assessment and adoption readiness evaluation and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="e21cf-360">この情報はリスク計画の一部として取り入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-360">This information should be incorporated as part of the risk plan.</span></span>

<a name="map-operational-roles"></a><span data-ttu-id="e21cf-361">運用の役割をマッピングする</span><span class="sxs-lookup"><span data-stu-id="e21cf-361">Map operational roles</span></span>
---------------------

<span data-ttu-id="e21cf-362">最初のパイロット ユーザーを有効にした時点で運用を開始する必要があるため、運用の計画と電話会議サービスを運用するチームの特定は重要なステップです。</span><span class="sxs-lookup"><span data-stu-id="e21cf-362">Planning for operations and identifying the teams that will operate the Audio Conferencing service is an important step, as operations must start when the first pilot users are enabled.</span></span> <span data-ttu-id="e21cf-363">特定された各チームは、指定されたタスクと責任を確認して同意し、電話会議サービスを運用するための準備に取りかかる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-363">Each identified team must review and agree on the tasks and responsibilities identified and start the preparation to operate the Audio Conferencing service.</span></span> <span data-ttu-id="e21cf-364">この準備には、トレーニングや用意、スタッフの追加、サービスを提供するために必要な外部プロバイダの設定などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-364">The preparation might include training and readiness, additional staffing, or ensuring external providers are set up to deliver the service.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-365">運用の役割</span><span class="sxs-lookup"><span data-stu-id="e21cf-365">Operational Role</span></span></th>
<th align="left"><span data-ttu-id="e21cf-366">説明</span><span class="sxs-lookup"><span data-stu-id="e21cf-366">Description</span></span></th>
<th align="left"><span data-ttu-id="e21cf-367">チーム</span><span class="sxs-lookup"><span data-stu-id="e21cf-367">Team Member</span></span></th>
<th align="left"><span data-ttu-id="e21cf-368">連絡先の詳細</span><span class="sxs-lookup"><span data-stu-id="e21cf-368">Contact Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-369">サービス所有者</span><span class="sxs-lookup"><span data-stu-id="e21cf-369">Service Owner</span></span></td>
<td align="left"><span data-ttu-id="e21cf-370">サービス所有者、ビジネス部門へのインターフェース、戦略</span><span class="sxs-lookup"><span data-stu-id="e21cf-370">Service owner, interface to business divisions, strategy</span></span></td>
<td align="left"><span data-ttu-id="e21cf-371">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-371">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-372">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-372">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-373">電話会議の運用</span><span class="sxs-lookup"><span data-stu-id="e21cf-373">Audio Conferencing Operations</span></span></td>
<td align="left"><span data-ttu-id="e21cf-374">日常的な運用、ユーザーとデバイス アカウントの移動/追加/変更、監視</span><span class="sxs-lookup"><span data-stu-id="e21cf-374">Daily operations, user and device account move/add/change, monitoring</span></span></td>
<td align="left"><span data-ttu-id="e21cf-375">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-375">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-376">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-376">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-377">テナント管理者</span><span class="sxs-lookup"><span data-stu-id="e21cf-377">Office 365 Tenant Admin</span></span></td>
<td align="left"><span data-ttu-id="e21cf-378">テナント全体の設定の変更、新しい機能の有効化</span><span class="sxs-lookup"><span data-stu-id="e21cf-378">Change tenant-wide settings, enable new features</span></span></td>
<td align="left"><span data-ttu-id="e21cf-379">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-379">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-380">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-380">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-381">ヘルプ デスク</span><span class="sxs-lookup"><span data-stu-id="e21cf-381">Help Desk.</span></span></td>
<td align="left"><span data-ttu-id="e21cf-382">エンドユーザーがサポートを受けるためのインターフェース</span><span class="sxs-lookup"><span data-stu-id="e21cf-382">Interface for end-users to get support</span></span></td>
<td align="left"><span data-ttu-id="e21cf-383">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-383">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-384">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-384">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-385">ネットワークの運用</span><span class="sxs-lookup"><span data-stu-id="e21cf-385">Network Operations</span></span></td>
<td align="left"><span data-ttu-id="e21cf-386">LAN、WAN、Wi-Fi、インターネット アクセスを実装する</span><span class="sxs-lookup"><span data-stu-id="e21cf-386">Runs LAN, WAN, Wi-Fi, and Internet Access</span></span></td>
<td align="left"><span data-ttu-id="e21cf-387">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-387">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-388">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-388">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-389">Client &amp; Endpoints チーム</span><span class="sxs-lookup"><span data-stu-id="e21cf-389">Client &amp; Endpoints Team</span></span></td>
<td align="left"><span data-ttu-id="e21cf-390">デスクトップの展開を管理する</span><span class="sxs-lookup"><span data-stu-id="e21cf-390">Manage desktop deployments</span></span></td>
<td align="left"><span data-ttu-id="e21cf-391">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-391">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-392">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-392">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-393">ID の運用</span><span class="sxs-lookup"><span data-stu-id="e21cf-393">Identity Operations</span></span></td>
<td align="left"><span data-ttu-id="e21cf-394">ID インフラストラクチャを管理する (AD、ADFS、Azure AD)</span><span class="sxs-lookup"><span data-stu-id="e21cf-394">Manage identity infrastructure (AD, ADFS, Azure AD)</span></span></td>
<td align="left"><span data-ttu-id="e21cf-395">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-395">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-396">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-396">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-397">導入/変更管理</span><span class="sxs-lookup"><span data-stu-id="e21cf-397">Adoption/change management</span></span></td>
<td align="left"><span data-ttu-id="e21cf-398">ソリューションの啓発、トレーニング、導入を管理する</span><span class="sxs-lookup"><span data-stu-id="e21cf-398">Manage awareness, training and adoption for the solution</span></span></td>
<td align="left"><span data-ttu-id="e21cf-399">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-399">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-400">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-400">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-401">Exchange の運用</span><span class="sxs-lookup"><span data-stu-id="e21cf-401">Exchange Operations</span></span></td>
<td align="left"><span data-ttu-id="e21cf-402">Exchange 環境を管理する</span><span class="sxs-lookup"><span data-stu-id="e21cf-402">Manages the Exchange environment</span></span></td>
<td align="left"><span data-ttu-id="e21cf-403">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-403">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-404">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-404">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-405">_表 6 運用の役割のマッピングの例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-405">_Table 6 Example of operational roles mapping_</span></span>


<span data-ttu-id="e21cf-406">運用の役割のマッピングを、各役割に関するタスクの情報を含むより詳細なものにする場合は、[Operational Role Mapping Workbook (運用の役割マッピング ワークブック)](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) を使用すると、電話会議サービスをサポートするための役割と責任を明確にする詳細な情報を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-406">To facilitate a more detailed operational roles mapping, including the tasks associated with each operational role, you can use the [Operational Role Mapping Workbook](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) to capture the details that will provide the clarity around roles and responsibilities to support Audio Conferencing service.</span></span>

<a name="document-success-plan"></a><span data-ttu-id="e21cf-407">成功計画を文書化する</span><span class="sxs-lookup"><span data-stu-id="e21cf-407">Document success plan</span></span>
---------------------

<span data-ttu-id="e21cf-408">成功計画は構想段階で作成する文書で、ビジネス ケース、サービスの準備状況、導入計画、運用計画で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-408">A success plan is the documentation created in the Envision phase that consists of business case, service readiness, adoption plan, and operational plan.</span></span>

<span data-ttu-id="e21cf-409">成功計画は、FastTrack や展開パートナーを含むプロジェクト チームに対して、電話会議サービスにより組織の目標を実現する上で十分な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-409">The success plan will provide the project team, which can include FastTrack or deployment partner, with sufficient information to realize the organization’s goals with Audio Conferencing service.</span></span>

<span data-ttu-id="e21cf-410">一般的に、成功計画は以下の主なセクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-410">In general, a success plan will contain the following main sections:</span></span>

-   <span data-ttu-id="e21cf-411">ビジネス ケース</span><span class="sxs-lookup"><span data-stu-id="e21cf-411">Business case</span></span>

-   <span data-ttu-id="e21cf-412">サービスの準備状況</span><span class="sxs-lookup"><span data-stu-id="e21cf-412">Service readiness</span></span>

-   <span data-ttu-id="e21cf-413">導入計画</span><span class="sxs-lookup"><span data-stu-id="e21cf-413">Adoption plan</span></span>

-   <span data-ttu-id="e21cf-414">運用計画</span><span class="sxs-lookup"><span data-stu-id="e21cf-414">Operational plan</span></span>

### <a name="business-case"></a><span data-ttu-id="e21cf-415">ビジネス ケース</span><span class="sxs-lookup"><span data-stu-id="e21cf-415">Business case</span></span>

<span data-ttu-id="e21cf-416">一般的に、ビジネス ケースに必要な主な情報には、ビジネス ユース ケース、ステークホルダー、OKR と KSI、リスク、プロジェクト タイムラインがあります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-416">Business use cases, stakeholders, OKRs and KSIs, risks, and project timelines typically make up the bulk of information required for a business case.</span></span> <span data-ttu-id="e21cf-417">成功計画の一部として、こうした情報を文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-417">You need to document them as part of the success plan.</span></span>

### <a name="service-readiness"></a><span data-ttu-id="e21cf-418">サービスの準備状況</span><span class="sxs-lookup"><span data-stu-id="e21cf-418">Service readiness</span></span>

<span data-ttu-id="e21cf-419">環境の評価では、電話会議の実装に向けた組織の技術的な準備状況を判断するために必要な初期情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-419">Environmental assessment provides the initial information required to determine technical readiness for the organization to implement Audio Conferencing.</span></span>

<span data-ttu-id="e21cf-420">ここでは、環境の評価で検出された、修復が必要な領域に対処する計画も示されます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-420">Included here is the plan to address areas needing remediation discovered through environmental assessment.</span></span> <span data-ttu-id="e21cf-421">成功計画の一部としてサービスの準備状況の評価と修復計画を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-421">You need to include the service readiness assessment and remediation plan as part of the success plan.</span></span>

### <a name="adoption-plan"></a><span data-ttu-id="e21cf-422">導入計画</span><span class="sxs-lookup"><span data-stu-id="e21cf-422">Adoption plan</span></span>

<span data-ttu-id="e21cf-423">導入の準備状況の評価に続き、より詳細な計画を完成させて、プロジェクト チームが通信計画、トレーニング計画、立ち上げ前/立ち上げ時/立ち上げ後に関する包括的な導入アクティビティを導き出せるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-423">Following an adoption readiness assessment, further detailed planning must be completed for the project team to come up with a comprehensive set of communication plans, training plan, and pre-launch, at-launch, and post-launch adoption activities.</span></span>

<span data-ttu-id="e21cf-424">このステップでは、チラシ、ウェルカム メール、トレーニング資料といった導入アクティビティをサポートするリソースを特定し、さらに組織の要件を満たすために必要なカスタマイズを特定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-424">Resources to support adoption activities such as flyers, welcome emails, and training materials are identified at this step, along with any customizations needed to meet organizational requirements.</span></span>

<span data-ttu-id="e21cf-425">導入アクティビティのテンプレートは[こちら](https://www.microsoft.com/download/details.aspx?id=54244)で入手できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-425">The templates for adoption activities are available [here](https://www.microsoft.com/download/details.aspx?id=54244).</span></span>

### <a name="operational-plan"></a><span data-ttu-id="e21cf-426">運用計画</span><span class="sxs-lookup"><span data-stu-id="e21cf-426">Operational plan</span></span>

<span data-ttu-id="e21cf-427">運用の役割のマッピングに関する演習では、役割と責任、電話会議の実装をサポートする運用の各役割に割り当てるチームを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-427">Operational roles mapping exercise will establish the roles and responsibilities, and the teams assigned to each operational role to support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="e21cf-428">ソリューションの運用準備を確実に行うため、この作業を完了させて、成功計画の一部として運用計画を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-428">You need to complete this and include the operational plan as part of the success plan to ensure operational readiness of the solution.</span></span>

<span data-ttu-id="e21cf-429">Teams での電話会議の計画  <a name="Planning_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="e21cf-429">Planning for Audio Conferencing in Teams  <a name="Planning_AudioConferencing"> </a></span></span>
========================================

<span data-ttu-id="e21cf-430">Teams での電話会議の実装を計画するには、ビジネス要件を満たすソリューションの実装に向けて組織が十分な準備を行うことができるよう、事前に一連の意思決定を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-430">To plan for the implementation of Audio Conferencing in Teams, a series of decisions must be made ahead of time to better prepare your organization to implement a solution that meets business requirements.</span></span> <span data-ttu-id="e21cf-431">この意思決定は技術実装計画で文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-431">These decisions will be documented into a technical implementation plan.</span></span>

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a><span data-ttu-id="e21cf-432">電話会議の利用可否</span><span class="sxs-lookup"><span data-stu-id="e21cf-432">Availability of Audio Conferencing</span></span>

<span data-ttu-id="e21cf-433">電話会議は以下の[国と地域](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US)で利用できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-433">Audio Conferencing is available in these [countries and regions](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e21cf-434">法的な規制により、多国間組織での電話会議の利用には、電話会議サービスが提供されている国や地域から Office 365 サブスクリプションの契約が提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-434">Due to legal constraints, for Audio Conferencing to be available to multinational organizations, the contract for Office 365 subscriptions must be sourced from countries and regions covered by Audio Conferencing service.</span></span>

<span data-ttu-id="e21cf-435">組織が電話会議サービスの利用資格を有していることが確認できたら、利用可能な国と地域のリストに基づいて、電話会議サービスを実装するユーザーの場所やオフィスのリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-435">After confirming your organization’s eligibility for obtaining the Audio Conferencing service, compile the list of user locations or offices where Audio Conferencing service will be implemented based on the list of available countries and regions.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="e21cf-436">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="e21cf-436">Decision Points</span></span></td>
<td align="left"><p><span data-ttu-id="e21cf-437">電話会議サービスを実装するユーザーの場所またはオフィスを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-437">Decide which user locations or offices will implement the Audio Conferencing service.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="e21cf-438">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e21cf-438">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="e21cf-439">電話会議サービスを有効にするユーザーの場所とオフィスを文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-439">Document the user locations or offices to be enabled for the Audio Conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-440">オフィス</span><span class="sxs-lookup"><span data-stu-id="e21cf-440">Office</span></span></th>
<th align="left"><span data-ttu-id="e21cf-441">場所</span><span class="sxs-lookup"><span data-stu-id="e21cf-441">Location</span></span></th>
<th align="left"><span data-ttu-id="e21cf-442">PSTN 会議サービス</span><span class="sxs-lookup"><span data-stu-id="e21cf-442">PSTN Conference Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-443">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-443">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-444">オーストラリア</span><span class="sxs-lookup"><span data-stu-id="e21cf-444">Australia</span></span></td>
<td align="left"><span data-ttu-id="e21cf-445">電話会議</span><span class="sxs-lookup"><span data-stu-id="e21cf-445">Audio conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-446">100 Cyberport Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-446">100 Cyberport Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-447">香港特別自治区</span><span class="sxs-lookup"><span data-stu-id="e21cf-447">Hong Kong SAR</span></span></td>
<td align="left"><span data-ttu-id="e21cf-448">旧 PSTN 会議</span><span class="sxs-lookup"><span data-stu-id="e21cf-448">Legacy PSTN Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-449">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="e21cf-449">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-450">シンガポール</span><span class="sxs-lookup"><span data-stu-id="e21cf-450">Singapore</span></span></td>
<td align="left"><span data-ttu-id="e21cf-451">電話会議</span><span class="sxs-lookup"><span data-stu-id="e21cf-451">Audio conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-452">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="e21cf-452">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="e21cf-453">イギリス</span><span class="sxs-lookup"><span data-stu-id="e21cf-453">United Kingdom</span></span></td>
<td align="left"><span data-ttu-id="e21cf-454">電話会議</span><span class="sxs-lookup"><span data-stu-id="e21cf-454">Audio conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-455">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="e21cf-455">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="e21cf-456">フランス</span><span class="sxs-lookup"><span data-stu-id="e21cf-456">France</span></span></td>
<td align="left"><span data-ttu-id="e21cf-457">電話会議</span><span class="sxs-lookup"><span data-stu-id="e21cf-457">Audio conferencing</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-458">_表 7 電話会議サービス サイト有効化リストの例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-458">_Table 7 Example of Audio Conferencing service site enablement list_</span></span>


## <a name="licensing-for-audio-conferencing"></a><span data-ttu-id="e21cf-459">電話会議のライセンス</span><span class="sxs-lookup"><span data-stu-id="e21cf-459">Licensing for Audio Conferencing</span></span>

<span data-ttu-id="e21cf-460">[電話会議ライセンス](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US) (旧名: Skype for Business PSTN 会議ライセンス) は、Office 365 E5 サブスクリプション プランの一部、または Office 365 E1 や Office 365 E3 サブスクリプション プランへのアドオンとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-460">[Audio Conferencing license](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), formerly known as Skype for Business PSTN Conferencing license, is available as part of Office 365 E5 subscription plans, or as an add-on to Office 365 E1 or Office 365 E3 subscription plans.</span></span>

> [!NOTE]
> <span data-ttu-id="e21cf-461">Teams での PSTN またはダイヤルイン会議は、サードパーティ<sup></sup>の電話会議プロバイダー (ACP) をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="e21cf-461">PSTN or dial-in conferencing in Teams does not support 3<sup>rd</sup>-party Audio Conferencing Providers (ACPs).</span></span>
> <br><span data-ttu-id="e21cf-462">Skype for Business Online PSTN 会議を使用している場合は、Teams ですぐに電話会議を利用できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-462">If you already use Skype for Business Online PSTN Conferencing today, you can immediately take advantage of Audio Conferencing in Teams.</span></span>

<span data-ttu-id="e21cf-463">無料電話の会議ブリッジ電話番号を提供したり、国際電話番号への会議ダイヤルアウトをサポートするには、組織の[通信クレジット](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059)を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-463">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to International phone numbers, you need to setup [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) for your organization.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="e21cf-464">一部の国では通話無料の会議ブリッジ電話番号でのみサービスが提供されます。こうした国でダイヤルインをサポートするには、通信クレジットの使用が必須になります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-464">Some countries are serviced by toll-free conference bridge phone numbers only, and in this case the use of Communications Credits is a mandatory requirement to support dial in for such countries.</span></span>

<span data-ttu-id="e21cf-465">通信クレジットを実装するには、最初に初回購入金額を決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-465">The first consideration to make when implementing Communications Credits is to decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="e21cf-466">推奨される金額については、[Communications Credits (通信クレジット)](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e21cf-466">Recommended funding amounts can be referenced from the [Communications Credits](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span>

<span data-ttu-id="e21cf-467">[Communications Credits (通信クレジット)](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) のドキュメントには、組織が自動リチャージを使用する場合のリチャージ実行 (資金の最小金額) の推奨金額も記載されています。</span><span class="sxs-lookup"><span data-stu-id="e21cf-467">If your organization chooses to use auto-recharge, a recommendation on the trigger (lowest amount of funds) is also included in the [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span> <span data-ttu-id="e21cf-468">自動リチャージの金額は実際の使用量に応じて決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-468">Auto-recharge amount needs to be determined by the actual usage.</span></span> <span data-ttu-id="e21cf-469">通信クレジットの使用量を経時的に監視して、必要に応じてリチャージの金額を調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-469">Communications Credits usage should be monitored over time and the recharge amount needs to be adjusted as required.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="e21cf-470">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="e21cf-470">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-471">組織が必要な電話会議ライセンスをまだ購入していない場合は、電話会議ライセンスの取得方法を既存の Office 365 サブスクリプションからステップ アップするか、電話会議アドオンを入手するかのいずれかに決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-471">If your organization has not already purchased the required Audio Conferencing licensing, decide whether Audio Conferencing licenses will be acquired by stepping up existing Office 365 subscriptions or by acquiring Audio Conferencing add-ons.</span></span></li>
<li><span data-ttu-id="e21cf-472">電話会議の実装で通信クレジットが必要であるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-472">Decide if Communications Credits is required for Audio Conferencing implementation.</span></span> <span data-ttu-id="e21cf-473">必要な場合は、初回購入金額を決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-473">If so, decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="e21cf-474">該当する場合は、リチャージを実行する金額と自動リチャージする金額を決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-474">Where applicable, decide the trigger amount and auto-recharge amount.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="e21cf-475">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e21cf-475">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-476">電話会議ライセンスを割り当てるユーザーを文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-476">Document the users that will be assigned Audio Conferencing license.</span></span></li>
<li><span data-ttu-id="e21cf-477">通信クレジット計画 (初回購入金額、リチャージを実行する金額、自動リチャージする金額) を文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-477">Document the Communications Credits plan (initial amount, trigger amount, auto-recharge amount).</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-478">ユーザー</span><span class="sxs-lookup"><span data-stu-id="e21cf-478">User</span></span></th>
<th align="left"><span data-ttu-id="e21cf-479">オフィス</span><span class="sxs-lookup"><span data-stu-id="e21cf-479">Office</span></span></th>
<th align="left"><span data-ttu-id="e21cf-480">Office 365 ライセンス</span><span class="sxs-lookup"><span data-stu-id="e21cf-480">Office 365 License</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-481">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="e21cf-481">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="e21cf-482">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-482">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-483">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e21cf-483">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-484">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="e21cf-484">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="e21cf-485">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-485">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-486">Office 365 E3、電話会議アドオン</span><span class="sxs-lookup"><span data-stu-id="e21cf-486">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-487">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="e21cf-487">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="e21cf-488">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-488">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-489">Office 365 E3、電話会議アドオン</span><span class="sxs-lookup"><span data-stu-id="e21cf-489">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-490">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="e21cf-490">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="e21cf-491">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="e21cf-491">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-492">Office 365 E3、電話会議アドオン</span><span class="sxs-lookup"><span data-stu-id="e21cf-492">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-493">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="e21cf-493">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="e21cf-494">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="e21cf-494">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-495">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e21cf-495">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-496">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="e21cf-496">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="e21cf-497">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="e21cf-497">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-498">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e21cf-498">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-499">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="e21cf-499">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="e21cf-500">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="e21cf-500">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="e21cf-501">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e21cf-501">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-502">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="e21cf-502">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="e21cf-503">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="e21cf-503">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="e21cf-504">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e21cf-504">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-505">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="e21cf-505">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="e21cf-506">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="e21cf-506">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="e21cf-507">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e21cf-507">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-508">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="e21cf-508">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="e21cf-509">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="e21cf-509">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="e21cf-510">Office 365 E3、電話会議アドオン</span><span class="sxs-lookup"><span data-stu-id="e21cf-510">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-511">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="e21cf-511">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="e21cf-512">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="e21cf-512">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="e21cf-513">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e21cf-513">Office 365 Enterprise E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-514">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="e21cf-514">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="e21cf-515">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="e21cf-515">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="e21cf-516">Office 365 E3、電話会議アドオン</span><span class="sxs-lookup"><span data-stu-id="e21cf-516">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-517">_表 8 電話会議の開催者のライセンス割り当てリストの例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-517">_Table 8 Example of license assignment list for Audio Conferencing meeting organizers_</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-518">初回購入金額</span><span class="sxs-lookup"><span data-stu-id="e21cf-518">Initial amount</span></span></th>
<td align="left"><span data-ttu-id="e21cf-519">$ 1,000</span><span class="sxs-lookup"><span data-stu-id="e21cf-519">$ 1,000</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-520">リチャージを実行する金額</span><span class="sxs-lookup"><span data-stu-id="e21cf-520">Trigger amount</span></span></th>
<td align="left"><span data-ttu-id="e21cf-521">$ 400</span><span class="sxs-lookup"><span data-stu-id="e21cf-521">$ 400</span></span></td>
</tr>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-522">自動リチャージする金額</span><span class="sxs-lookup"><span data-stu-id="e21cf-522">Auto-recharge amount</span></span></th>
<td align="left"><span data-ttu-id="e21cf-523">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-523">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-524">_表 9 通信クレジットの計画番号の例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-524">_Table 9 Example of Communications Credits planning numbers_</span></span>


## <a name="conference-bridge-phone-numbers"></a><span data-ttu-id="e21cf-525">会議ブリッジ電話番号</span><span class="sxs-lookup"><span data-stu-id="e21cf-525">Conference bridge phone numbers</span></span>

<span data-ttu-id="e21cf-526">Office 365 の電話会議サービスには次が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-526">The Audio Conferencing service in Office 365 includes:</span></span>

-   <span data-ttu-id="e21cf-527">複数の種類の会議ブリッジ電話番号 (有料電話と無料電話)</span><span class="sxs-lookup"><span data-stu-id="e21cf-527">Multiple types of conference bridge phone numbers (Toll and Toll-Free)</span></span>

-   <span data-ttu-id="e21cf-528">複数のカテゴリの電話番号 (専用と共有)</span><span class="sxs-lookup"><span data-stu-id="e21cf-528">Multiple categories of the phone number (dedicated and shared)</span></span>

-   <span data-ttu-id="e21cf-529">会議ブリッジでの複数言語のサポート (プライマリとセカンダリ)</span><span class="sxs-lookup"><span data-stu-id="e21cf-529">Support for multiple languages for the conference bridge (primary and secondary)</span></span>

-   <span data-ttu-id="e21cf-530">テナントの既定の電話番号</span><span class="sxs-lookup"><span data-stu-id="e21cf-530">A default phone number for the tenant.</span></span>

<span data-ttu-id="e21cf-531">提供される機能の詳細な説明については、「[Skype for Business のダイヤルインまたは PSTN 会議をセットアップする](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US)」と「[ダイヤルイン会議の電話番号](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)」**をご覧ください。**</span><span class="sxs-lookup"><span data-stu-id="e21cf-531">Full description of the included capabilities can be referenced from [Set up dial-in or PSTN conferencing for Skype for Business](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) and [Phone numbers for dial-in conferencing](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span></span>

> [!NOTE]
> <span data-ttu-id="e21cf-532">専用の会議ブリッジ電話番号は、「[Skype for Business サービスの電話番号を取得する](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734)」で説明されている適用可能なライセンス数に応じた、テナントごとに取得可能な電話番号の制限にカウントされます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-532">Dedicated conference bridge phone numbers are counted towards the limit of phone numbers that can be acquired per tenant, based on the number of applicable licenses as described in [Getting Skype for Business service phone numbers](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span></span> <span data-ttu-id="e21cf-533">無料電話の会議ブリッジ電話番号では通信クレジットが必要になります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-533">Toll-free conference bridge phone numbers require Communications Credits.</span></span>

<span data-ttu-id="e21cf-534">電話会議サービスに移行する必要のある既存の会議ブリッジ電話番号が存在する場合は、国固有の要件を満たしているという前提の上で既存の会議ブリッジ電話番号を Microsoft に移行できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-534">If there are existing conference bridge phone numbers that must be transferred to the Audio Conferencing service, assuming they are meeting the country-specific requirements, then the existing conference bridge phone numbers can be transferred to Microsoft.</span></span>


> [!NOTE]
> <span data-ttu-id="e21cf-535">Microsoft への電話番号の移行における複雑さは、国や地域、キャリヤ、関与する回路の数、その他多くの関連する要因によって大きく左右されます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-535">Complexity of transferring phone numbers to Microsoft varies greatly based on the countries or regions, carriers, the number of circuits involved, and many other contributing factors.</span></span> <span data-ttu-id="e21cf-536">電話番号の移行を計画する場合は、「[Number Porting Guide (番号の移行ガイド)](https://go.microsoft.com/fwlink/?linkid=859011)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e21cf-536">To plan for phone number porting, check out the [Number Porting Guide](https://go.microsoft.com/fwlink/?linkid=859011).</span></span>

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

<span data-ttu-id="e21cf-537">電話会議サービスへの電話番号の移行について詳しくは、「[Transfer phone numbers to Skype for Business Online (Skype for Business Online への電話番号の移行)](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e21cf-537">Additional details on transferring phone numbers to Audio Conferencing service can be found in [Transfer phone numbers to Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="e21cf-538">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="e21cf-538">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-539">組織で専用の会議ブリッジ電話番号が必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-539">Decide whether the organization requires dedicated conference bridge phone numbers</span></span></li>
<li><span data-ttu-id="e21cf-540">電話会議の実装においてユーザーの場所またはオフィスに対して会議ブリッジ電話番号を取得する方法 (Microsoft から取得または既存の電話番号の移行) を決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-540">Decide how the dedicated conference bridge phone numbers will be obtained for user locations or offices in-scope for the Audio Conferencing implementation (obtain from Microsoft or transfer existing phone numbers)</span></span></li>
<li><span data-ttu-id="e21cf-541">Microsoft から取得する場合は、電話会議の実装の範囲内のユーザーの場所またはオフィスに対して電話番号を取得する方法 (フォーム提出または自動) を決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-541">If you choose to obtain from Microsoft, decide the method to obtain phone numbers (form submission or automated) for user locations or offices in-scope for the Audio Conferencing implementation</span></span></li>
<li><span data-ttu-id="e21cf-542">それぞれの専用会議ブリッジ電話番号に設定する言語設定を決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-542">Decide the language preferences to be set up for each dedicated conference bridge phone number</span></span></li>
<li><span data-ttu-id="e21cf-543">テナントの既定の会議ブリッジ電話番号を決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-543">Decide the tenant default conference bridge phone number</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="e21cf-544">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e21cf-544">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-545">電話会議の実装の範囲内のそれぞれのユーザーの場所またはオフィスに対して電話番号を取得する方法を詳しく記述する電話番号取得のマスタープランを文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-545">Document the master plan for phone numbers acquisition, detailing how phone numbers will be obtained for each user location or office in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="e21cf-546">該当する場合は、場所またはオフィスごとに <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">New Telephone Number Request (新規電話番号要求)</a> フォームを入力します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-546">If applicable, complete <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">the New Telephone Number Request form</a>, one form for each location or office</span></span></li>
<li><span data-ttu-id="e21cf-547">既存の電話番号を移行する場合は、「<a href="https://go.microsoft.com/fwlink/?linkid=859011">Number Porting Guide (番号の移行ガイド)</a>」を参照して、電話会議の実装タイムラインを調整してください。</span><span class="sxs-lookup"><span data-stu-id="e21cf-547">If you choose to transfer existing phone numbers, check out the <a href="https://go.microsoft.com/fwlink/?linkid=859011">Number Porting Guide</a> to plan it and adjust Audio Conferencing implementation timeline accordingly.</span></span></li>
<li><span data-ttu-id="e21cf-548">詳細な会議ブリッジ番号構成 (共有および専用の会議ブリッジ電話番号、それぞれの専用会議ブリッジ電話番号の言語設定、テナントの既定の会議ブリッジ電話番号) を文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-548">Document the detailed conference bridge phone number configurations (shared and dedicated conference bridge phone numbers, language preferences for each dedicated conference bridge phone number, tenant default conference bridge phone number)</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-549">オフィス</span><span class="sxs-lookup"><span data-stu-id="e21cf-549">Office</span></span></th>
<th align="left"><span data-ttu-id="e21cf-550">ブリッジ番号の取得とブリッジの種類</span><span class="sxs-lookup"><span data-stu-id="e21cf-550">Bridge Number Acquisition and Bridge Type</span></span></th>
<th align="left"><span data-ttu-id="e21cf-551">ブリッジ番号</span><span class="sxs-lookup"><span data-stu-id="e21cf-551">Bridge Number</span></span></th>
<th align="left"><span data-ttu-id="e21cf-552">ブリッジの言語</span><span class="sxs-lookup"><span data-stu-id="e21cf-552">Bridge Language</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-553">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-553">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-554">新規に取得、専用</span><span class="sxs-lookup"><span data-stu-id="e21cf-554">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="e21cf-555">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-555">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-556">英語 (オーストラリア)</span><span class="sxs-lookup"><span data-stu-id="e21cf-556">en-AU – English (Australia)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-557">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="e21cf-557">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-558">新規に取得、共有</span><span class="sxs-lookup"><span data-stu-id="e21cf-558">Acquire new, shared</span></span></td>
<td align="left"><span data-ttu-id="e21cf-559">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-559">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-560">英語 (米国)、中国語 (簡体字、PRC)</span><span class="sxs-lookup"><span data-stu-id="e21cf-560">English (United States), Chinese (Simplified, PRC)</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-561">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="e21cf-561">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="e21cf-562">既存のポート、専用</span><span class="sxs-lookup"><span data-stu-id="e21cf-562">Port existing, dedicated</span></span></td>
<td align="left"><span data-ttu-id="e21cf-563">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="e21cf-563">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="e21cf-564">英語 (英国)</span><span class="sxs-lookup"><span data-stu-id="e21cf-564">en-GB – English (United Kingdom)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-565">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="e21cf-565">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="e21cf-566">新規に取得、専用</span><span class="sxs-lookup"><span data-stu-id="e21cf-566">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="e21cf-567">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-567">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-568">フランス語 (フランス)、英語 (英国)</span><span class="sxs-lookup"><span data-stu-id="e21cf-568">French (France), English (United Kingdom)</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-569">_表 10 会議ブリッジの詳細の例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-569">_Table 10 Example of conference bridge details_</span></span>


> [!NOTE]
> <span data-ttu-id="e21cf-570">上記の例の表およびこのドキュメント内の以降の表はテンプレートとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-570">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="e21cf-571">「TBA」(今後追加される予定) と記載されている箇所には、計画プロセスを遂行する上で満たす必要のある情報が入ります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-571">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

## <a name="conference-bridge-settings"></a><span data-ttu-id="e21cf-572">会議ブリッジの設定</span><span class="sxs-lookup"><span data-stu-id="e21cf-572">Conference bridge settings</span></span>

<span data-ttu-id="e21cf-573">電話会議への参加に関する操作と表示 (会議の参加および退出に関する通知、発信者名の記録)、会議の開催者の PIN の長さ、電子メール通知といった組織全体の構成オプションをエンドユーザーのエクスペリエンスに応じて細かく調整できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-573">Organization-wide configuration options around Audio Conferencing meeting join experience (meeting entry and exit notification and caller name recording), meeting organizer’s PIN length, and email notification are available to further tailor the end-user experience.</span></span>

-   <span data-ttu-id="e21cf-574">会議の参加と退出に関する通知は、記録された名前、電話番号、効果音の形式で利用できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-574">Meeting entry and exit notifications are available in the form of recorded name, phone number, and tones.</span></span>

-   <span data-ttu-id="e21cf-575">PIN の長さは 4～12 桁です。既定は 5 桁の PIN です。</span><span class="sxs-lookup"><span data-stu-id="e21cf-575">PIN length is configurable from 4 to 12 digits, with a 5-digit PIN as the default.</span></span>

-   <span data-ttu-id="e21cf-576">電話会議ライセンスが有効になるときや、管理者による変更時に送信される通知メールは、既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-576">Notification emails upon enablement of Audio Conferencing license or any other admin-driven changes are enabled by default.</span></span> <span data-ttu-id="e21cf-577">この機能は無効にすることができます。無効にすることで組織のエンドユーザーの通信を制御できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-577">You can disable this feature and take control of your organization’s end-user communications.</span></span>

<span data-ttu-id="e21cf-578">電話会議ライセンスが割り当てられたユーザーの場合、電話会議の調整に表示される既定の有料/無料電話番号は次のいずれかに構成して使用できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-578">For users who are assigned an Audio Conferencing license, the default toll/toll-free numbers, shown in the Audio Conferencing coordinates, are configurable to use:</span></span>

-   <span data-ttu-id="e21cf-579">テナントレベルの既定の番号</span><span class="sxs-lookup"><span data-stu-id="e21cf-579">the tenant-level default, or</span></span>

-   <span data-ttu-id="e21cf-580">自動的に割り当てられる会議ブリッジ電話番号</span><span class="sxs-lookup"><span data-stu-id="e21cf-580">the automatically-assigned conference bridge phone numbers, or</span></span>

-   <span data-ttu-id="e21cf-581">各ユーザーに対して手動で定義する会議ブリッジ電話番号</span><span class="sxs-lookup"><span data-stu-id="e21cf-581">manually defined conference bridge phone numbers for each user.</span></span>

<span data-ttu-id="e21cf-582">通常、ユーザー固有の会議ブリッジ電話番号は、ユーザーが地理的に分散され、会議の招待状に既定の会議ブリッジ電話番号として市内番号を指定する必要がある国際的または全国的な組織にとって便利です。</span><span class="sxs-lookup"><span data-stu-id="e21cf-582">User-specific conference bridge phone numbers are typically useful in global or nationwide organizations where users are distributed and must provide local numbers as the default conference bridge phone numbers in the meeting invites.</span></span>

<span data-ttu-id="e21cf-583">他の都市や海外から参加する参加者は、テナントレベルで構成された追加の番号を検索することができます。ただし、この番号は会議の招待状には直接表示されません。</span><span class="sxs-lookup"><span data-stu-id="e21cf-583">Participants joining from different cities or overseas can look up additional numbers configured at the tenant-level, but these numbers do not appear directly in the meeting invites.</span></span> <span data-ttu-id="e21cf-584">会議の招待状には、参加者を [Teams Conference Dial-in Numbers (Teams の会議ダイヤルイン番号)] ページに導くリンクが記載されています。このページでは、参加者の場所から最も近い会議ブリッジ電話番号を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-584">The meeting invites provide a link that will take participants to the Teams Conference Dial-in Numbers page for them to lookup the closest conference bridge phone numbers available from their location.</span></span>

<span data-ttu-id="e21cf-585">さらに、会議の各開催者は未認証の発信者の処理方法を構成することもできます。未認証の発信者の参加を許可する前に開催者が会議を開始する必要があるかどうか、会議を開始する当たって開催者が未認証の発信者を許可する必要があるかどうかを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-585">You can also configure how unauthenticated callers are handled by each individual meeting organizer, whether to require meeting organizer to start the meeting before unauthenticated callers are admitted, or to allow unauthenticated callers to start a meeting.</span></span>

<span data-ttu-id="e21cf-586">各ユーザーに適用可能な追加の構成を使用して、無料電話の会議ブリッジ電話番号の使用や会議からのダイヤルアウトを制御できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-586">Additional configurations that can be applied for each user are available to control the use of toll-free conference bridge phone numbers and dial-out from a conference.</span></span>

> [!NOTE]
> <span data-ttu-id="e21cf-587">現時点では、料金に関連するこれらの制御はプレビュー カスタマーのみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-587">These cost-related controls are currently available for preview customers only.</span></span> <span data-ttu-id="e21cf-588">組織は [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013) でプレビュー プログラムに登録できます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-588">You can enroll your organization in the preview program from [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).</span></span>

<span data-ttu-id="e21cf-589">これらの制御を使用すると、会議の開催者は開催する会議で無料電話の会議ブリッジ電話番号を提供するかどうかを決めたり、参加者が会議からダイヤルアウトできるかどうかを制御したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-589">With these controls, you can decide whether meeting organizers can provide toll-free conference bridge phone numbers for meetings organized by them, and to control whether participants can dial out from the meetings organized by them.</span></span> <span data-ttu-id="e21cf-590">ダイヤルアウトの制御には、ダイヤルアウトの禁止、国内番号にのみダイヤルアウトを許可、国内および国際番号の両方にダイヤルアウトを許可があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-590">The level of dial-out control spans from disallowing dial out, only allowing dial out to domestic numbers, to allowing dial out to both domestic and international numbers.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="e21cf-591">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="e21cf-591">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-592">組織で会議の参加と退出の通知が必要かどうかを決定し、必要な場合は実装する通知の種類 (効果音、電話番号または記録された名前) を決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-592">Decide whether the organization requires entry and exit notifications, and if yes, the type of notification to be implemented (tones, phone number, or recorded name).</span></span></li>
<li><span data-ttu-id="e21cf-593">組織のセキュリティ要件に合った電話会議の PIN の長さを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-593">Decide the Audio Conferencing PIN length that meets the organizational security requirements.</span></span></li>
<li><span data-ttu-id="e21cf-594">組織で電話会議サービスに関連するエンドユーザーの通信を制御するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-594">Decide if the organization wants to take control of end-user communications related to Audio Conferencing service.</span></span></li>
<li><span data-ttu-id="e21cf-595">会議ブリッジ電話番号を各会議の開催者に割り当てるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-595">Decide the conference bridge phone numbers to be assigned to each meeting organizer.</span></span></li>
<li><span data-ttu-id="e21cf-596">一部の会議の開催者について、会議に無料電話の会議ブリッジ電話番号の使用が必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-596">Decide whether some meeting organizers require the ability to use toll-free conference bridge phone numbers for their meeings</span></span></li>
<li><span data-ttu-id="e21cf-597">一部の会議の開催者について、会議を開始する前に未認証の発信者を許可する機能が必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-597">Decide whether some meeting organizers require the ability to allow unauthenticated callers to start a meeting.</span></span></li>
<li><span data-ttu-id="e21cf-598">一部の会議の開催者について、会議ダイヤルアウトを制御する機能が必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-598">Decide whether some meeting organizers require conference dial out to be controlled.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="e21cf-599">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e21cf-599">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-600">詳細な会議ブリッジ設定 (参加および退出の通知、PIN 長さ、構成変更メール通知) を文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-600">Document the detailed conference bridge settings (entry and exit notifications, PIN length, configuration change email notification).</span></span></li>
<li><span data-ttu-id="e21cf-601">各会議の開催者に割り当てる会議ブリッジ電話番号、さらに未認証の発信者のポリシー、無料電話、ダイヤルアウトの制御に対する設定を文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-601">Document the conference bridge phone numbers to be assinged to each meeting organizer and the corresponding setting to control unauthenticated caller’s policy, and toll-free and dial out controls.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="e21cf-602"><strong>会議の参加および退出の通知を有効にする</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-602"><strong>Enable meeting entry and exit notifications</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-603">有効</span><span class="sxs-lookup"><span data-stu-id="e21cf-603">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="e21cf-604"><strong>参加/退出のアナウンスのタイプ</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-604"><strong>Entry/exit announcement type</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-605">効果音</span><span class="sxs-lookup"><span data-stu-id="e21cf-605">Tones</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="e21cf-606"><strong>会議に参加する前に名前を記録するように発信者に求める</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-606"><strong>Ask callers to record their name before joining the meeting</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-607">無効</span><span class="sxs-lookup"><span data-stu-id="e21cf-607">Disabled.</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="e21cf-608"><strong>PIN の長さ</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-608"><strong>PIN length</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-609">5</span><span class="sxs-lookup"><span data-stu-id="e21cf-609">Example 5</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="e21cf-610"><strong>ユーザーのダイヤルイン設定の変更時にそのユーザーに自動的にメールを送信する</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-610"><strong>Automatically send emails to users if their dial-in settings change</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-611">無効</span><span class="sxs-lookup"><span data-stu-id="e21cf-611">Disabled.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-612">_表 11 会議ブリッジ設定の例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-612">_Table 11 Example of conference bridge settings_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-613">ユーザー</span><span class="sxs-lookup"><span data-stu-id="e21cf-613">User</span></span></th>
<th align="left"><span data-ttu-id="e21cf-614">オフィス</span><span class="sxs-lookup"><span data-stu-id="e21cf-614">Office</span></span></th>
<th align="left"><span data-ttu-id="e21cf-615">既定の有料電話番号</span><span class="sxs-lookup"><span data-stu-id="e21cf-615">Default toll number</span></span></th>
<th align="left"><span data-ttu-id="e21cf-616">既定の無料電話番号</span><span class="sxs-lookup"><span data-stu-id="e21cf-616">Default toll-free number</span></span></th>
<th align="left"><span data-ttu-id="e21cf-617">無料電話を許可する</span><span class="sxs-lookup"><span data-stu-id="e21cf-617">Allow toll-free</span></span></th>
<th align="left"><span data-ttu-id="e21cf-618">未認証の発信者のバイパス ロビー</span><span class="sxs-lookup"><span data-stu-id="e21cf-618">PSTN callers bypass lobby</span></span></th>
<th align="left"><span data-ttu-id="e21cf-619">会議ダイヤルアウト</span><span class="sxs-lookup"><span data-stu-id="e21cf-619">Conference dial out</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-620">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="e21cf-620">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="e21cf-621">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-621">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-622">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-622">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-623">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-623">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-624">はい</span><span class="sxs-lookup"><span data-stu-id="e21cf-624">Yes</span></span></td>
<td align="left"><span data-ttu-id="e21cf-625">有効</span><span class="sxs-lookup"><span data-stu-id="e21cf-625">Enabled</span></span></td>
<td align="left"><span data-ttu-id="e21cf-626">国際および国内</span><span class="sxs-lookup"><span data-stu-id="e21cf-626">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-627">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="e21cf-627">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="e21cf-628">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-628">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-629">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-629">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-630">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-630">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-631">いいえ</span><span class="sxs-lookup"><span data-stu-id="e21cf-631">No</span></span></td>
<td align="left"><span data-ttu-id="e21cf-632">無効</span><span class="sxs-lookup"><span data-stu-id="e21cf-632">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="e21cf-633">許可されていない</span><span class="sxs-lookup"><span data-stu-id="e21cf-633">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-634">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="e21cf-634">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="e21cf-635">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-635">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-636">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-636">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-637">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-637">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-638">いいえ</span><span class="sxs-lookup"><span data-stu-id="e21cf-638">No</span></span></td>
<td align="left"><span data-ttu-id="e21cf-639">無効</span><span class="sxs-lookup"><span data-stu-id="e21cf-639">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="e21cf-640">許可されていない</span><span class="sxs-lookup"><span data-stu-id="e21cf-640">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-641">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="e21cf-641">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="e21cf-642">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="e21cf-642">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-643">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-643">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-644">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-644">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-645">はい</span><span class="sxs-lookup"><span data-stu-id="e21cf-645">Yes</span></span></td>
<td align="left"><span data-ttu-id="e21cf-646">無効</span><span class="sxs-lookup"><span data-stu-id="e21cf-646">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="e21cf-647">国内</span><span class="sxs-lookup"><span data-stu-id="e21cf-647">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-648">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="e21cf-648">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="e21cf-649">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="e21cf-649">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-650">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-650">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-651">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-651">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-652">はい</span><span class="sxs-lookup"><span data-stu-id="e21cf-652">Yes</span></span></td>
<td align="left"><span data-ttu-id="e21cf-653">有効</span><span class="sxs-lookup"><span data-stu-id="e21cf-653">Enabled</span></span></td>
<td align="left"><span data-ttu-id="e21cf-654">国内</span><span class="sxs-lookup"><span data-stu-id="e21cf-654">Domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-655">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="e21cf-655">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="e21cf-656">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="e21cf-656">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-657">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-657">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-658">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-658">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-659">はい</span><span class="sxs-lookup"><span data-stu-id="e21cf-659">Yes</span></span></td>
<td align="left"><span data-ttu-id="e21cf-660">有効</span><span class="sxs-lookup"><span data-stu-id="e21cf-660">Enabled</span></span></td>
<td align="left"><span data-ttu-id="e21cf-661">国内</span><span class="sxs-lookup"><span data-stu-id="e21cf-661">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-662">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="e21cf-662">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="e21cf-663">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="e21cf-663">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="e21cf-664">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="e21cf-664">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="e21cf-665">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-665">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-666">はい</span><span class="sxs-lookup"><span data-stu-id="e21cf-666">Yes</span></span></td>
<td align="left"><span data-ttu-id="e21cf-667">有効</span><span class="sxs-lookup"><span data-stu-id="e21cf-667">Enabled</span></span></td>
<td align="left"><span data-ttu-id="e21cf-668">許可されていない</span><span class="sxs-lookup"><span data-stu-id="e21cf-668">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-669">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="e21cf-669">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="e21cf-670">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="e21cf-670">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="e21cf-671">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="e21cf-671">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="e21cf-672">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-672">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-673">はい</span><span class="sxs-lookup"><span data-stu-id="e21cf-673">Yes</span></span></td>
<td align="left"><span data-ttu-id="e21cf-674">無効</span><span class="sxs-lookup"><span data-stu-id="e21cf-674">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="e21cf-675">許可されていない</span><span class="sxs-lookup"><span data-stu-id="e21cf-675">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-676">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="e21cf-676">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="e21cf-677">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="e21cf-677">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="e21cf-678">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="e21cf-678">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="e21cf-679">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-679">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-680">はい</span><span class="sxs-lookup"><span data-stu-id="e21cf-680">Yes</span></span></td>
<td align="left"><span data-ttu-id="e21cf-681">無効</span><span class="sxs-lookup"><span data-stu-id="e21cf-681">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="e21cf-682">許可されていない</span><span class="sxs-lookup"><span data-stu-id="e21cf-682">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-683">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="e21cf-683">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="e21cf-684">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="e21cf-684">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="e21cf-685">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-685">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-686">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-686">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-687">いいえ</span><span class="sxs-lookup"><span data-stu-id="e21cf-687">No</span></span></td>
<td align="left"><span data-ttu-id="e21cf-688">無効</span><span class="sxs-lookup"><span data-stu-id="e21cf-688">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="e21cf-689">国内</span><span class="sxs-lookup"><span data-stu-id="e21cf-689">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-690">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="e21cf-690">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="e21cf-691">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="e21cf-691">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="e21cf-692">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-692">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-693">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-693">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-694">はい</span><span class="sxs-lookup"><span data-stu-id="e21cf-694">Yes</span></span></td>
<td align="left"><span data-ttu-id="e21cf-695">有効</span><span class="sxs-lookup"><span data-stu-id="e21cf-695">Enabled</span></span></td>
<td align="left"><span data-ttu-id="e21cf-696">国際および国内</span><span class="sxs-lookup"><span data-stu-id="e21cf-696">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-697">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="e21cf-697">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="e21cf-698">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="e21cf-698">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="e21cf-699">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-699">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-700">TBA</span><span class="sxs-lookup"><span data-stu-id="e21cf-700">TBA</span></span></td>
<td align="left"><span data-ttu-id="e21cf-701">いいえ</span><span class="sxs-lookup"><span data-stu-id="e21cf-701">No</span></span></td>
<td align="left"><span data-ttu-id="e21cf-702">無効</span><span class="sxs-lookup"><span data-stu-id="e21cf-702">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="e21cf-703">国内</span><span class="sxs-lookup"><span data-stu-id="e21cf-703">Domestic</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-704">_表 12 会議ブリッジ設定の割り当ての例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-704">_Table 12 Example of conference bridge settings assignments_</span></span>


## <a name="dial-plans"></a><span data-ttu-id="e21cf-705">ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-705">Dial plans</span></span>

<span data-ttu-id="e21cf-706">Office 365 の電話システム機能である[ダイヤル プラン](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b)は、通話の認証およびルーティングの目的で、ダイヤルされた電話番号を代替形式 (通常、[E.164](https://go.microsoft.com/fwlink/?linkid=859014) 形式) に変換する正規化ルールです。</span><span class="sxs-lookup"><span data-stu-id="e21cf-706">A [Dial Plan](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), a Phone System feature of Office 365, is a set of normalization rules that translates dialed phone numbers into an alternate format (typically [E.164](https://go.microsoft.com/fwlink/?linkid=859014) format) for call authorization and call routing.</span></span> <span data-ttu-id="e21cf-707">電話会議サービスは、この電話システムで使用されるものと同じ機能を使用して、会議ダイヤルアウトのシナリオでダイヤルされた電話番号を変換します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-707">Audio Conferencing service leverages the same capabilities used by Phone System to translate dialed phone numbers in conference dial out scenarios.</span></span>

<span data-ttu-id="e21cf-708">ダイヤル プランでは、ユーザーは従来の使い慣れた方法で電話番号をダイヤルできます (市内通話の場合に市外局番を省略、国内通話の場合に国番号を省略、会議ダイヤルアウト実行時に短い桁をダイヤル)。</span><span class="sxs-lookup"><span data-stu-id="e21cf-708">A dial plan allows users to dial phone numbers the way they are accustomed to, such as omitting area code for local calls, omitting country code for domestic calls, or even using short digit dialing when performing conference dial out.</span></span>

<span data-ttu-id="e21cf-709">Office 365 の電話システム機能には、次の 2 種類のダイヤル プランがあります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-709">Within the Phone System feature of Office 365, there are two types of dial plans:</span></span>

-   <span data-ttu-id="e21cf-710">**サービス ダイヤル プラン**: </span><span class="sxs-lookup"><span data-stu-id="e21cf-710">**Service dial plan**.</span></span> <span data-ttu-id="e21cf-711">既定のダイヤル プランで、Office 365 の使用場所に基づいてユーザーに適用されます。変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="e21cf-711">This is the default dial plan and applied to users based on Office 365 usage location, and it cannot be modified.</span></span>

<!-- -->

-   <span data-ttu-id="e21cf-712">**テナント ダイヤル プラン**: </span><span class="sxs-lookup"><span data-stu-id="e21cf-712">**Tenant dial plan**.</span></span> <span data-ttu-id="e21cf-713">テナント内のカスタマイズ可能なダイヤル プランです。さらに 2 つのタイプに分類されます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-713">This is a customizable dial plan within a tenant, and further divided into two types:</span></span>

    -   <span data-ttu-id="e21cf-714">**テナント - グローバル ダイヤル プラン** - テナント内のすべてのユーザーに適用されるダイヤル プラン。</span><span class="sxs-lookup"><span data-stu-id="e21cf-714">**Tenant-global dial plan**—the dial plan applies to all users within the tenant.</span></span>

    -   <span data-ttu-id="e21cf-715">**テナント - ユーザー ダイヤル プラン** - 特定のユーザーにのみ適用されるダイヤル プラン。</span><span class="sxs-lookup"><span data-stu-id="e21cf-715">**Tenant-user dial plan**—the dial plan applies only to specific users.</span></span>


> [!NOTE]
> <span data-ttu-id="e21cf-716">詳細と例については、「[Office 365 Calling Plan dial plans (Office 365 通話プランのダイヤル プラン)](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e21cf-716">Check out the [Office 365 Calling Plan dial plans](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) documentation for further details and examples.</span></span>

<span data-ttu-id="e21cf-717">ユーザーに有効なダイヤル プランを割り当てるには、サービス ダイヤル プラン (ユーザーが Office 365 を使用する場所に基づく) とテナント ダイヤル プラン (テナント - グローバル ダイヤル プランまたはテナント - ユーザー ダイヤル プランのいずれか) を組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-717">The effective dial plan assigned to users is the combination of service dial plan (based on user’s Office 365 usage location) and tenant dial plan (can be either tenant-global dial plan or tenant-user dial plan).</span></span>

![](media/audio_conferencing_image8.png)

<span data-ttu-id="e21cf-718">各テナント ダイヤル プランには最大で 25 の正規化ルールがあります。このため、サービス ダイヤル プランの一部として既に利用可能な正規化ルールとの重複を回避する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-718">There is a maximum of 25 normalization rules in each tenant dial plan, and thus duplication with normalization rules already available as part of service dial plan needs to be avoided.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="e21cf-719">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="e21cf-719">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-720">カスタマイズしたダイヤル プラン (ビジネス要件、導入要件など) が組織で必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-720">Decide if your organization requires customized dial plans (business requirements, adoption requirements, etc.).</span></span></li>
<li><span data-ttu-id="e21cf-721">該当する場合は、カスタマイズしたダイヤル プランの要件を満たすテナント ダイヤル プランの範囲 (テナント - グローバルまたはテナント - ユーザー) を決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-721">If applicable, decide the scope of tenant dial plan (tenant-global or tenant-user) to support the requirements for customized dial plans.</span></span></li>
<li><span data-ttu-id="e21cf-722">該当する場合は、電話会議の実装の範囲内のユーザーの場所とオフィスをサポートするために作成するテナント ダイヤル プランを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-722">If applicable, decide the tenant dial plans that will be created to support user locations or offices in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="e21cf-723">該当する場合は、カスタマイズしたダイヤル プランが必要なユーザー、各ユーザーに割り当てるテナント ダイヤル プランを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-723">If applicable, decide which user require customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="e21cf-724">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e21cf-724">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="e21cf-725">カスタマイズしたダイヤル プランと、電話会議の実装の一環として構成される関連した正規化ルールを文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-725">Document the customized dial plans and the associated normalization rules to be configured as part of Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="e21cf-726">カスタマイズしたダイヤル プランが必要なユーザー、各ユーザーに割り当てるテナント ダイヤル プランを文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-726">Document the users to be assigned with customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-727">テナント ダイヤル プランの名前/説明</span><span class="sxs-lookup"><span data-stu-id="e21cf-727">Tenant Dial Plan Name/Description</span></span></th>
<th align="left"><span data-ttu-id="e21cf-728">正規化ルールの名前/説明</span><span class="sxs-lookup"><span data-stu-id="e21cf-728">Normalization Rules Name/Description</span></span></th>
<th align="left"><span data-ttu-id="e21cf-729">パターン</span><span class="sxs-lookup"><span data-stu-id="e21cf-729">IPv6 Pattern</span></span></th>
<th align="left"><span data-ttu-id="e21cf-730">変換</span><span class="sxs-lookup"><span data-stu-id="e21cf-730">Translation</span></span></th>
<th align="left"><span data-ttu-id="e21cf-731">IsInternalExtension</span><span class="sxs-lookup"><span data-stu-id="e21cf-731">IsInternalExtension</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e21cf-732"><strong>AU-NSW-NorthRyde-OER</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-732"><strong>AU-NSW-NorthRyde-OER</strong></span></span></p>
<p><span data-ttu-id="e21cf-733"><em>One Epping Road North Ryde、NSW、AU ダイヤル プラン</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-733"><em>One Epping Road North Ryde, NSW, AU Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="e21cf-734"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-734"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span></span></p>
<p><span data-ttu-id="e21cf-735"><em>One Epping Road オフィスの内部番号 (x7000 - x7999)、North Ryde、NSW、オーストラリア</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-735"><em>Internal number (x7000 - x7999) for One Epping Road office, North Ryde, NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="e21cf-736">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="e21cf-736">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="e21cf-737">+6125550$1</span><span class="sxs-lookup"><span data-stu-id="e21cf-737">+6125550$1</span></span></td>
<td align="left"><span data-ttu-id="e21cf-738">True</span><span class="sxs-lookup"><span data-stu-id="e21cf-738">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="e21cf-739"><strong>AU-NSW-Local</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-739"><strong>AU-NSW-Local</strong></span></span></p>
<p><span data-ttu-id="e21cf-740"><em>NSW、オーストラリアの市内番号の正規化</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-740"><em>Local number normalization for NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="e21cf-741">^([2-9]\d{7})$</span><span class="sxs-lookup"><span data-stu-id="e21cf-741">^([2-9]\d{7})$</span></span></td>
<td align="left"><span data-ttu-id="e21cf-742">+612$1</span><span class="sxs-lookup"><span data-stu-id="e21cf-742">+612$1</span></span></td>
<td align="left"><span data-ttu-id="e21cf-743">False</span><span class="sxs-lookup"><span data-stu-id="e21cf-743">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="e21cf-744"><strong>AU-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-744"><strong>AU-TollFree</strong></span></span></p>
<p><span data-ttu-id="e21cf-745"><em>オーストラリアの無料電話番号の正規化</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-745"><em>Toll Free number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="e21cf-746">^(1[38]\d{4,8})\d*$</span><span class="sxs-lookup"><span data-stu-id="e21cf-746">^(1[38]\d{4,8})\d*$</span></span></td>
<td align="left"><span data-ttu-id="e21cf-747">+61$1</span><span class="sxs-lookup"><span data-stu-id="e21cf-747">+61$1</span></span></td>
<td align="left"><span data-ttu-id="e21cf-748">False</span><span class="sxs-lookup"><span data-stu-id="e21cf-748">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="e21cf-749"><strong>AU-Service</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-749"><strong>AU-Service</strong></span></span></p>
<p><span data-ttu-id="e21cf-750"><em>オーストラリアのサービス番号の正規化</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-750"><em>Service number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="e21cf-751">^(000|1[0125]\d{1,8})$</span><span class="sxs-lookup"><span data-stu-id="e21cf-751">^(000|1[0125]\d{1,8})$</span></span></td>
<td align="left"><span data-ttu-id="e21cf-752">$1</span><span class="sxs-lookup"><span data-stu-id="e21cf-752">$1</span></span></td>
<td align="left"><span data-ttu-id="e21cf-753">False</span><span class="sxs-lookup"><span data-stu-id="e21cf-753">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e21cf-754"><strong>SG-Singapore-OMB</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-754"><strong>SG-Singapore-OMB</strong></span></span></p>
<p><span data-ttu-id="e21cf-755"><em>OMB Singapore、SG ダイヤル プラン</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-755"><em>OMB Singapore, SG Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="e21cf-756"><strong>SG-OMB-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-756"><strong>SG-OMB-Internal</strong></span></span></p>
<p><span data-ttu-id="e21cf-757"><em>OMB オフィスの内部番号 (x8000 – x8999)、シンガポール</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-757"><em>Internal number (x8000 – x8999) for OMB office, Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="e21cf-758">^(8\d{3})$</span><span class="sxs-lookup"><span data-stu-id="e21cf-758">^(8\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="e21cf-759">+656888$1</span><span class="sxs-lookup"><span data-stu-id="e21cf-759">+656888$1</span></span></td>
<td align="left"><span data-ttu-id="e21cf-760">True</span><span class="sxs-lookup"><span data-stu-id="e21cf-760">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="e21cf-761"><strong>SG-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-761"><strong>SG-TollFree</strong></span></span></p>
<p><span data-ttu-id="e21cf-762"><em>シンガポールの無料電話番号の正規化</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-762"><em>Toll Free number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="e21cf-763">^(1?800\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="e21cf-763">^(1?800\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="e21cf-764">+65$1</span><span class="sxs-lookup"><span data-stu-id="e21cf-764">+65$1</span></span></td>
<td align="left"><span data-ttu-id="e21cf-765">False</span><span class="sxs-lookup"><span data-stu-id="e21cf-765">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="e21cf-766"><strong>SG-Service</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-766"><strong>SG-Service</strong></span></span></p>
<p><span data-ttu-id="e21cf-767"><em>シンガポールのサービス番号の正規化</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-767"><em>Service number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="e21cf-768">^(1\d{3,4}|9\d{2})$</span><span class="sxs-lookup"><span data-stu-id="e21cf-768">^(1\d{3,4}|9\d{2})$</span></span></td>
<td align="left"><span data-ttu-id="e21cf-769">$1</span><span class="sxs-lookup"><span data-stu-id="e21cf-769">$1</span></span></td>
<td align="left"><span data-ttu-id="e21cf-770">False</span><span class="sxs-lookup"><span data-stu-id="e21cf-770">False</span></span></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e21cf-771"><strong>FR-Paris-Issy-39qdPR</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-771"><strong>FR-Paris-Issy-39qdPR</strong></span></span></p>
<p><span data-ttu-id="e21cf-772"><em>39 quai du Président Roosevelt Issy-les-Moulineaux、フランスのダイヤル プラン</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-772"><em>39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="e21cf-773"><strong>FR-39qdPR-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-773"><strong>FR-39qdPR-Internal</strong></span></span></p>
<p><span data-ttu-id="e21cf-774"><em>39 quai du Président Roosevelt オフィスの内部番号 (x7000 – x7999)、Issy-les-Moulineaux、フランス</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-774"><em>Internal number (x7000 – x7999) for 39 quai du Président Roosevelt office, Issy-les-Moulineaux, France</em></span></span></p></td>
<td align="left"><span data-ttu-id="e21cf-775">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="e21cf-775">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="e21cf-776">+3319999$1</span><span class="sxs-lookup"><span data-stu-id="e21cf-776">+3319999$1</span></span></td>
<td align="left"><span data-ttu-id="e21cf-777">True</span><span class="sxs-lookup"><span data-stu-id="e21cf-777">True</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="e21cf-778"><strong>FR-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-778"><strong>FR-TollFree</strong></span></span></p>
<p><span data-ttu-id="e21cf-779"><em>フランスの無料電話番号の正規化</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-779"><em>Toll Free number normalization for France</em></span></span></p></td>
<td align="left"><span data-ttu-id="e21cf-780">^0?(80\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="e21cf-780">^0?(80\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="e21cf-781">+33$1</span><span class="sxs-lookup"><span data-stu-id="e21cf-781">+33$1</span></span></td>
<td align="left"><span data-ttu-id="e21cf-782">False</span><span class="sxs-lookup"><span data-stu-id="e21cf-782">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="e21cf-783"><strong>FR-Service</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-783"><strong>FR-Service</strong></span></span></p>
<p><span data-ttu-id="e21cf-784"><em>フランスのサービス番号の正規化</em></span><span class="sxs-lookup"><span data-stu-id="e21cf-784"><em>Service number normalization for France</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="e21cf-785">^(1\d{1,2}|11[68]\d{3}|</span><span class="sxs-lookup"><span data-stu-id="e21cf-785">^(1\d{1,2}|11[68]\d{3}|</span></span></p>
<p><span data-ttu-id="e21cf-786">10\d{2}|3\d{3})$</span><span class="sxs-lookup"><span data-stu-id="e21cf-786">10\d{2}|3\d{3})$</span></span></p></td>
<td align="left"><span data-ttu-id="e21cf-787">$1</span><span class="sxs-lookup"><span data-stu-id="e21cf-787">$1</span></span></td>
<td align="left"><span data-ttu-id="e21cf-788">False</span><span class="sxs-lookup"><span data-stu-id="e21cf-788">False</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-789">_表 13 テナント ダイヤル プランの例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-789">_Table 13 Example of tenant dial plans_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e21cf-790">ユーザー</span><span class="sxs-lookup"><span data-stu-id="e21cf-790">User</span></span></th>
<th align="left"><span data-ttu-id="e21cf-791">オフィス</span><span class="sxs-lookup"><span data-stu-id="e21cf-791">Office</span></span></th>
<th align="left"><span data-ttu-id="e21cf-792">ダイヤル プランの種類</span><span class="sxs-lookup"><span data-stu-id="e21cf-792">Dial Plan Type</span></span></th>
<th align="left"><span data-ttu-id="e21cf-793">ダイヤル プランの名前</span><span class="sxs-lookup"><span data-stu-id="e21cf-793">Dial Plan Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-794">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="e21cf-794">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="e21cf-795">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-795">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-796">テナント ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-796">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-797">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="e21cf-797">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-798">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="e21cf-798">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="e21cf-799">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-799">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-800">テナント ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-800">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-801">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="e21cf-801">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-802">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="e21cf-802">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="e21cf-803">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="e21cf-803">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="e21cf-804">テナント ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-804">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-805">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="e21cf-805">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-806">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="e21cf-806">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="e21cf-807">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="e21cf-807">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-808">テナント ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-808">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-809">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="e21cf-809">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-810">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="e21cf-810">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="e21cf-811">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="e21cf-811">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-812">テナント ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-812">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-813">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="e21cf-813">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-814">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="e21cf-814">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="e21cf-815">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="e21cf-815">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="e21cf-816">テナント ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-816">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-817">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="e21cf-817">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-818">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="e21cf-818">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="e21cf-819">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="e21cf-819">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="e21cf-820">サービス ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-820">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-821">該当なし</span><span class="sxs-lookup"><span data-stu-id="e21cf-821">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-822">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="e21cf-822">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="e21cf-823">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="e21cf-823">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="e21cf-824">サービス ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-824">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-825">該当なし</span><span class="sxs-lookup"><span data-stu-id="e21cf-825">N/A</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-826">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="e21cf-826">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="e21cf-827">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="e21cf-827">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="e21cf-828">サービス ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-828">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-829">該当なし</span><span class="sxs-lookup"><span data-stu-id="e21cf-829">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-830">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="e21cf-830">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="e21cf-831">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="e21cf-831">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="e21cf-832">テナント ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-832">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-833">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="e21cf-833">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-834">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="e21cf-834">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="e21cf-835">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="e21cf-835">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="e21cf-836">テナント ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-836">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-837">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="e21cf-837">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="e21cf-838">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="e21cf-838">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="e21cf-839">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="e21cf-839">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="e21cf-840">テナント ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-840">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="e21cf-841">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="e21cf-841">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-842">_表 14 ダイヤル プランの割り当ての例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-842">_Table 14 Example of dial plan assignments_</span></span>


## <a name="microsoft-teams-configurations"></a><span data-ttu-id="e21cf-843">Microsoft Teams の構成</span><span class="sxs-lookup"><span data-stu-id="e21cf-843">Microsoft Teams configurations</span></span>

<span data-ttu-id="e21cf-844">電話会議は予約済みの会議にのみ利用できるため、会議の予約 (プライベート会議およびチャネル会議) を制御するテナントレベルの構成を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e21cf-844">Since Audio Conferencing is only available for scheduled meetings, tenant-level configurations that govern meeting scheduling (private and channel meetings) must be enabled.</span></span>


> [!NOTE]
> <span data-ttu-id="e21cf-845">すべての会議のディスカッションを検出可能にするというコンプライアンス要件が組織に対して課せられている場合、会議の開催者が Exchange オンプレミス メールボックスを利用しているならば、プライベート会議を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e21cf-845">Currently, if your organization has compliance requirements to ensure all meeting discussions are discoverable, you should disable private meetings if the organizer has an Exchange on-premises mailbox.</span></span><br><br>
> <span data-ttu-id="e21cf-846">組織のすべての会議が<strong>招待されたユーザー</strong>にのみ表示される必要がある場合は、<strong>チャネル</strong>で会議を予約する機能を無効にして、招待されていないユーザーに情報が公開されないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e21cf-846">In another use case, if all meetings in the organization must be visible <strong>to invited parties</strong> only, to avoid disclosing meeting information to uninvited parties, we recommend that you disable the ability to schedule meetings in <strong>channels</strong>.</span></span>

<span data-ttu-id="e21cf-847">テナントレベルの構成の一部であるこれらの設定は、組織のすべてのユーザーに適用され、電話会議を**使った** Teams の会議だけでなく、Teams でのすべての会議の予約に影響を及ぼします。</span><span class="sxs-lookup"><span data-stu-id="e21cf-847">The settings, available as tenant-level configurations, are applicable to all users in the organization, and will impact all meeting scheduling in Teams, not specific to Teams meetings **with** Audio Conferencing.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="e21cf-848">判断ポイント</span><span class="sxs-lookup"><span data-stu-id="e21cf-848">Decision Point</span></span></td>
<td align="left"><p><span data-ttu-id="e21cf-849">組織でプライベート会議の予約を有効または無効にする必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-849">Decide if the organization requires to enable or disable scheduling of private meetings.</span></span></p>
<p><span data-ttu-id="e21cf-850">組織でチャネル会議の予約を有効または無効にする必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-850">Decide if the organization requires to enable or disable scheduling of channel meetings.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="e21cf-851">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e21cf-851">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="e21cf-852">Teams の会議予約の構成を文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-852">Document the meeting scheduling configurations for Teams.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="e21cf-853"><strong>プライベート会議の予約を許可する</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-853"><strong>Allow scheduling for private meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-854">有効</span><span class="sxs-lookup"><span data-stu-id="e21cf-854">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><span data-ttu-id="e21cf-855"><strong>チャネル会議の予約を許可する</strong></span><span class="sxs-lookup"><span data-stu-id="e21cf-855"><strong>Allow scheduling for channel meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="e21cf-856">無効</span><span class="sxs-lookup"><span data-stu-id="e21cf-856">Disabled.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="e21cf-857">_表 15 Microsoft Teams の会議の構成の例_</span><span class="sxs-lookup"><span data-stu-id="e21cf-857">_Table 15 Example of Microsoft Teams meetings configurations_</span></span>


## <a name="document-technical-implementation-plan"></a><span data-ttu-id="e21cf-858">技術実装計画を文書化する</span><span class="sxs-lookup"><span data-stu-id="e21cf-858">Document technical implementation plan</span></span>

<span data-ttu-id="e21cf-859">上記の判断ポイントを参考にして、技術実装計画を文書化します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-859">Use the decision points above to document your technical implementation plan.</span></span>

<span data-ttu-id="e21cf-860">この技術実装計画は、FastTrack または展開パートナーを含むプロジェクト チームに対して、電話会議の実装における技術面での参加を行うために必要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e21cf-860">This technical implementation plan will provide the project team, which can include FastTrack or a deployment partner, with the information required to execute the technical onboarding for the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="e21cf-861">一般的に、技術実装計画は以下の主なセクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e21cf-861">In general, a technical implementation plan will contain the following main sections:</span></span>

-   <span data-ttu-id="e21cf-862">電話会議サービス サイト有効化リスト</span><span class="sxs-lookup"><span data-stu-id="e21cf-862">Audio Conferencing service site enablement list</span></span>

-   <span data-ttu-id="e21cf-863">電話会議の開催者のライセンス割り当てリスト</span><span class="sxs-lookup"><span data-stu-id="e21cf-863">License assignment list for Audio Conferencing meeting organizers</span></span>

-   <span data-ttu-id="e21cf-864">通信クレジットの計画番号</span><span class="sxs-lookup"><span data-stu-id="e21cf-864">Communications Credits planning numbers</span></span>

-   <span data-ttu-id="e21cf-865">会議ブリッジの詳細</span><span class="sxs-lookup"><span data-stu-id="e21cf-865">Conference bridge details</span></span>

-   <span data-ttu-id="e21cf-866">会議ブリッジの設定</span><span class="sxs-lookup"><span data-stu-id="e21cf-866">Conference bridge settings</span></span>

-   <span data-ttu-id="e21cf-867">会議ブリッジの設定の割り当て</span><span class="sxs-lookup"><span data-stu-id="e21cf-867">Conference bridge settings assignments</span></span>

-   <span data-ttu-id="e21cf-868">テナント ダイヤル プラン</span><span class="sxs-lookup"><span data-stu-id="e21cf-868">Tenant dial plans</span></span>

-   <span data-ttu-id="e21cf-869">ダイヤル プランの割り当て</span><span class="sxs-lookup"><span data-stu-id="e21cf-869">Dial plan assignments</span></span>

-   <span data-ttu-id="e21cf-870">Microsoft Teams の会議の構成</span><span class="sxs-lookup"><span data-stu-id="e21cf-870">Microsoft Teams meetings configurations</span></span>

<span data-ttu-id="e21cf-871">成功計画と技術実装計画を完成することにより、組織では Office 365 カスタマーの次の導入ステップに進む準備が整います。</span><span class="sxs-lookup"><span data-stu-id="e21cf-871">With the completion of success plan and technical implementation plan, you are now ready to take your organization to the next steps along the Office 365 customer journey.</span></span>

<a name="onboard"></a><span data-ttu-id="e21cf-872">参加</span><span class="sxs-lookup"><span data-stu-id="e21cf-872">Onboard</span></span>
=======

<span data-ttu-id="e21cf-873">*準備中*</span><span class="sxs-lookup"><span data-stu-id="e21cf-873">*Coming Soon*</span></span>

<a name="drive-value"></a><span data-ttu-id="e21cf-874">価値の創出</span><span class="sxs-lookup"><span data-stu-id="e21cf-874">Drive Value</span></span>
===========

<span data-ttu-id="e21cf-875">*準備中*</span><span class="sxs-lookup"><span data-stu-id="e21cf-875">*Coming Soon*</span></span>



### <a name="see-also"></a><span data-ttu-id="e21cf-876">関連項目</span><span class="sxs-lookup"><span data-stu-id="e21cf-876">See also</span></span>
[<span data-ttu-id="e21cf-877">Skype for Business のダイヤルインまたは PSTN 会議をセットアップする</span><span class="sxs-lookup"><span data-stu-id="e21cf-877">Set up dial-in or PSTN conferencing for Skype for Business</span></span>](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)
