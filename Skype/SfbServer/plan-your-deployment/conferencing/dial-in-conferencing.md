---
title: Skype for Business Server でのダイヤルイン会議の計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: '概要: Skype for Business Server でのダイヤルイン会議の計画については、このトピックを参照してください。'
ms.openlocfilehash: f78f5dcea5ce26bdfeb0ba52a6eeaf046ae6965b
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888546"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="2d449-103">Skype for Business Server でのダイヤルイン会議の計画</span><span class="sxs-lookup"><span data-stu-id="2d449-103">Plan for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="2d449-104">**概要:** このトピックでは、Skype for Business Server でのダイヤルイン会議の計画について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d449-104">**Summary:** Read this topic to learn about planning for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="2d449-105">ダイヤルイン会議は、会議出席者が電話から会議に参加することによって会議の音声部分に参加できるようにする、Skype for Business Server のオプションの機能です。</span><span class="sxs-lookup"><span data-stu-id="2d449-105">Dial-in conferencing is an optional feature of Skype for Business Server that allows meeting attendees to join the audio portion of a meeting by calling in to the meeting from a phone.</span></span> <span data-ttu-id="2d449-106">ダイヤルイン会議は音声会議のサブセットであり、追加構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="2d449-106">Dial-in conferencing is a subset of audio conferencing and requires additional configuration.</span></span> <span data-ttu-id="2d449-107">ここでは、組織のダイヤルイン会議を展開する前の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d449-107">This topic describes what you need to think about before deploying dial-in conferencing for your organization.</span></span> 
  
<span data-ttu-id="2d449-108">ダイヤルイン会議に必要なコンポーネントの一部は、ダイヤルイン会議に固有のものであり、一部はエンタープライズボイスコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="2d449-108">Some of the components required for dial-in conferencing are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="2d449-109">ダイヤルイン会議では、エンタープライズ VoIP で使用するのと同じコンポーネントをいくつか使用しますが、エンタープライズ VoIP を展開しない場合でも、ダイヤルイン会議を展開できます。</span><span class="sxs-lookup"><span data-stu-id="2d449-109">Although dial-in conferencing uses some of the same components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span> <span data-ttu-id="2d449-110">ここでは、ダイヤルイン会議に必要なコンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2d449-110">This section describes the components that are needed for dial-in conferencing.</span></span> <span data-ttu-id="2d449-111">完全なエンタープライズ Voip ソリューションの計画について詳しくは、「 [Skype For Business Server でのエンタープライズ voip ソリューションの計画](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2d449-111">For more information about planning a complete Enterprise Voice solution, see [Plan your Enterprise Voice solution in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).</span></span>
  
<span data-ttu-id="2d449-112">ダイヤルイン会議では、仲介サーバーを展開して公衆交換電話網 (PSTN) への接続を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d449-112">Dial-in conferencing requires that you provide connectivity to the public switched telephone network (PSTN) by deploying a Mediation Server.</span></span> <span data-ttu-id="2d449-113">組織でダイヤルイン会議を実現するには、仲介サーバーの展開に加えて、以下のことを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d449-113">In addition to deploying a Mediation Server, you need to consider the following to allow dial-in conferencing for your organization:</span></span>
  
- <span data-ttu-id="2d449-114">公衆交換電話網 (PSTN) への接続の計画</span><span class="sxs-lookup"><span data-stu-id="2d449-114">Your plan for connecting to the public switched telephone network (PSTN)</span></span>
    
- <span data-ttu-id="2d449-115">ダイヤル プラン、アクセス番号、および会議の地域の計画</span><span class="sxs-lookup"><span data-stu-id="2d449-115">Your plan for dial plans, access numbers, and conferencing regions</span></span>
    
- <span data-ttu-id="2d449-116">会議ディレクトリ作成の計画</span><span class="sxs-lookup"><span data-stu-id="2d449-116">Your plan for creating conferencing directories</span></span>
    
- <span data-ttu-id="2d449-117">ダイヤルイン アクセスを許可するための会議ポリシー</span><span class="sxs-lookup"><span data-stu-id="2d449-117">Your conferencing policy for allowing dial-in access</span></span>
    
- <span data-ttu-id="2d449-118">エンタープライズ ユーザーと匿名ユーザーのサポート</span><span class="sxs-lookup"><span data-stu-id="2d449-118">Support for enterprise and anonymous users</span></span>
    
> [!NOTE]
> <span data-ttu-id="2d449-119">ダイヤルイン会議を展開する場合は、Skype for Business Server 会議を展開するすべてのプールに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d449-119">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Skype for Business Server conferencing.</span></span> <span data-ttu-id="2d449-120">プールごとにアクセス番号 (会議に参加するために参加者が発信する番号) を割り当てる必要はありませんが、プールごとにダイヤルイン機能を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d449-120">You do not need to assign access numbers--the numbers participants call to join a conference--in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="2d449-121">この要件は、ユーザーが1つのプールのアクセス番号を呼び出して、別のプールで Skype for Business Server 会議に参加したときに記録された名前の機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2d449-121">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Skype for Business Server conference in a different pool.</span></span> 
  
## <a name="plan-for-pstn-connectivity"></a><span data-ttu-id="2d449-122">PSTN 接続の計画</span><span class="sxs-lookup"><span data-stu-id="2d449-122">Plan for PSTN connectivity</span></span>

<span data-ttu-id="2d449-123">ダイヤルイン会議には、少なくとも 1 つの仲介サーバーと少なくとも 1 つの公衆交換電話網 (PSTN) ゲートウェイが必要です。</span><span class="sxs-lookup"><span data-stu-id="2d449-123">Dial-in conferencing requires at least one Mediation Server and at least one public switched telephone network (PSTN) gateway.</span></span> 
  
<span data-ttu-id="2d449-124">仲介サーバーは、中央サイトまたはブランチ サイトに展開できます。</span><span class="sxs-lookup"><span data-stu-id="2d449-124">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="2d449-125">中央サイトでは、仲介サーバーをフロントエンド プールまたは Standard Edition サーバー上に併置するか、スタンドアロンのサーバー上またはプールに展開できます。</span><span class="sxs-lookup"><span data-stu-id="2d449-125">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="2d449-126">ブランチ サイトでは、仲介サーバーをスタンドアロンのサーバー上か、存続可能ブランチ アプライアンスのコンポーネントとして展開できます。</span><span class="sxs-lookup"><span data-stu-id="2d449-126">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>
  
<span data-ttu-id="2d449-p106">PSTN ゲートウェイは、中央サイトまたはブランチ サイトに展開できます。ブランチ サイトでは、PSTN ゲートウェイは、スタンドアロンの場合と存続可能ブランチ アプライアンスのコンポーネントの場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d449-p106">You can deploy a PSTN gateway in a central site or in a branch site. In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>
  
<span data-ttu-id="2d449-129">仲介サーバーと PSTN ゲートウェイの要件の詳細については、「skype for [Business server の仲介サーバーコンポーネント](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)」、「 [skype for Business Server のトポロジビルダーへの仲介サーバーの展開](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)」、「skype For [business server のトポロジビルダーでのゲートウェイの定義](../../deploy/deploy-enterprise-voice/define-a-gateway.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d449-129">For details about Mediation Server and PSTN gateway requirements, see [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), [Deploy a Mediation Server in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md), and [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a><span data-ttu-id="2d449-130">ダイヤル プラン、アクセス番号、および会議の地域を計画する</span><span class="sxs-lookup"><span data-stu-id="2d449-130">Plan for dial plans, access numbers, and conferencing regions</span></span>

<span data-ttu-id="2d449-p107">ダイヤルイン会議を構成するには、ダイヤル プランとダイヤルイン会議アクセス番号を作成します。また、ダイヤルイン会議アクセス番号とダイヤル プランを関連付ける、ダイヤルインの地域も指定します。具体的には、以下のような情報です。</span><span class="sxs-lookup"><span data-stu-id="2d449-p107">To configure dial-in conferencing, you create dial plans and dial-in conferencing access numbers. You also specify the dial-in regions that associate a dial-in conferencing access number with its dial plans. More specifically:</span></span>
  
- <span data-ttu-id="2d449-134">ダイヤル プランは、通話のルーティングに必要な、電話番号の桁数と数字パターンを指定して電話番号を標準の E.164 形式に変換する、正規化ルールのセットです。</span><span class="sxs-lookup"><span data-stu-id="2d449-134">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number, and translate the phone number into the standard E.164 format required for call routing.</span></span>
    
- <span data-ttu-id="2d449-135">ダイヤルイン会議アクセス番号は、会議に参加するために参加者が発信する番号です。</span><span class="sxs-lookup"><span data-stu-id="2d449-135">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>
    
- <span data-ttu-id="2d449-136">すべてのダイヤルイン会議アクセス番号を、少なくとも 1 つのダイヤル プランに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d449-136">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> 
    
- <span data-ttu-id="2d449-137">すべてのダイヤル プランは、会議の地域に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="2d449-137">Every dial plan is associated with a conferencing region.</span></span>
    
<span data-ttu-id="2d449-p108">ダイヤル プランを作成するときに、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。ダイヤルイン アクセス番号を作成するときには、アクセス番号と適切なダイヤル プランを関連付ける地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d449-p108">When you create a dial plan, you specify the dial-in conferencing region that applies to the dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>
  
<span data-ttu-id="2d449-p109">また、ダイヤル プランのスコープとしてユーザー スコープ、プール スコープ、またはサイト スコープを指定します。すべてのユーザーに、そのユーザーに適用される最も狭いスコープからダイヤル プランが割り当てられます。たとえば、ユーザー レベルのダイヤル プランが適用される場合、ユーザーにはユーザー レベルのダイヤル プランが割り当てられます。ユーザー レベルのダイヤル プランが適用されない場合、そのユーザーにはプール レベルのダイヤル プランが割り当てられます。プール レベルのダイヤル プランが適用されない場合、そのユーザーにはサイト レベルのダイヤル プランが割り当てられます。サイト レベルのダイヤル プランが適用されない場合、そのユーザーにはグローバル ダイヤル プランが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2d449-p109">You also specify the scope of the dial plan: user scope, pool scope, or site scope. Every user is assigned the dial plan from the narrowest scope that applies to the user. For example, a user is assigned a user-level dial plan, if one applies. If a user-level dial plan does not apply, the user is assigned a pool-level dial plan. If a pool-level dial plan does not apply, the user is assigned a site-level dial plan. If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span> 
  
<span data-ttu-id="2d449-p110">ダイヤル プランを構成する前に、地域にどのように名前を指定してその地域をどのように使用するのかを計画することが重要です。 ダイヤルイン会議の地域には、次の考慮事項が適用されます。</span><span class="sxs-lookup"><span data-stu-id="2d449-p110">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>
  
- <span data-ttu-id="2d449-148">地域は通常、1 つのオフィスまたはオフィスのグループに関連付けられた地理的地域です。</span><span class="sxs-lookup"><span data-stu-id="2d449-148">A region is typically a geographical area that is associated with an office or group of offices.</span></span>
    
- <span data-ttu-id="2d449-p111">言語をダイヤル アクセス番号に関連付けます。複数の言語が使用されている地理的地域をサポートしている場合、複数の言語をサポートするよう地域をどのように定義するのかを決定する必要があります。たとえば、地理的条件と言語の組み合わせに基づいて複数の言語を定義したり、地理的条件に基づいて 1 つの地域を定義し、各言語に異なるダイヤルイン アクセス番号を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="2d449-p111">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>
    
- <span data-ttu-id="2d449-152">ユーザーが会議をスケジュールする際、既定では、会議にはそのユーザーのダイヤル プランで指定されている地域が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d449-152">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>
    
- <span data-ttu-id="2d449-153">既定では、その地域のすべてのダイヤルイン アクセス番号が会議出席依頼に含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d449-153">By default, all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>
    
- <span data-ttu-id="2d449-154">明確に認識できるように、地域に名前を指定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="2d449-154">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="2d449-155">ユーザーは、地域の名前を使用して会議の地域を変更し、出席依頼に異なるアクセス番号が含まれるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2d449-155">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="2d449-156">(ユーザーが Outlook を使用して会議をスケジュールする場合、ユーザーは Skype for Business 用のオンライン会議アドインを使用して地域を変更します)。</span><span class="sxs-lookup"><span data-stu-id="2d449-156">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Skype for Business to change the region).</span></span>
    
- <span data-ttu-id="2d449-157">会議にダイヤルインする招待されたユーザーが会議出席依頼で地域のアクセス番号を確認できるよう、地域を設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d449-157">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>
    
- <span data-ttu-id="2d449-158">Skype for Business Server 管理シェルコマンドレットを使用して、[ダイヤルイン会議の設定] ページ (その場合は、会議出席依頼に表示される順序) に、地域内のアクセス番号が表示される順序を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="2d449-158">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Skype for Business Server Management Shell cmdlets.</span></span>
    
- <span data-ttu-id="2d449-159">すべての場所のすべてのユーザーが、任意のダイヤルイン アクセス番号を発信して会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="2d449-159">Any user from any location can call any dial-in access number to join a conference.</span></span>
    
<span data-ttu-id="2d449-160">ダイヤルプランの作成の詳細については、「 [skype For Business Server でダイヤルプランを作成または変更](../../deploy/deploy-enterprise-voice/dial-plans.md)する」と「 [skype for business で正規化ルールを作成または変更](../../deploy/deploy-enterprise-voice/normalization-rules.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d449-160">For more information about creating a dial plan, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) and [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span> 
  
## <a name="plan-for-conference-directories"></a><span data-ttu-id="2d449-161">会議ディレクトリを計画する</span><span class="sxs-lookup"><span data-stu-id="2d449-161">Plan for conference directories</span></span>

<span data-ttu-id="2d449-162">会議ディレクトリは、Skype for Business を使用しているときに参加者が会議に参加するために使用する英数字の会議 ID と、ダイヤルイン会議の参加者が会議に参加するために使用する電話番号のみの会議 id の間のマッピングを維持します。</span><span class="sxs-lookup"><span data-stu-id="2d449-162">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="2d449-163">電話会議 ID の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d449-163">The format of the conference ID is as follows:</span></span>
  

<span data-ttu-id="2d449-164">\<ハウスキーピング番号 (1 桁)\>\<会議ディレクトリ (通常は1-2 桁\>\<) 会議の電話番号 (桁数\>\<の可変数のチェックディジット (1 桁)\></span><span class="sxs-lookup"><span data-stu-id="2d449-164">\<housekeeping digit (1 digit)\>\<conference directory (usually 1-2 digits)\>\<conference number (variable number of digits\>\<check digit (1 digit)\></span></span>


<span data-ttu-id="2d449-p114">複数の会議ディレクトリを作成すると、作成する会議の数がよほど多くならない限り電話会議 ID を短く保つことができます。ユーザーあたりの電話会議の数が一般的な組織の場合、プール内の 999 ユーザーごとに 1 つの会議ディレクトリを作成することをお勧めします。このガイドラインを使用すると、一般に電話会議 ID が短く保たれます。ただし、(すべてのプールの) 会議ディレクトリの数が 9 を超えると、追加の会議をサポートするために電話会議 ID の番号が長くなります。</span><span class="sxs-lookup"><span data-stu-id="2d449-p114">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created. In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline, the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a><span data-ttu-id="2d449-169">ダイヤルイン アクセスを許可する会議ポリシーを計画する</span><span class="sxs-lookup"><span data-stu-id="2d449-169">Plan for a conferencing policy that allows dial-in access</span></span>

<span data-ttu-id="2d449-170">会議ポリシーを構成するときは、ダイヤルインアクセスのために会議を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d449-170">Conferences must be enabled for dial-in access when you configure conferencing policies.</span></span> <span data-ttu-id="2d449-171">既定では、会議でダイヤルイン アクセスが有効になっている場合は、会議の招待通知に次の情報が記載されます。</span><span class="sxs-lookup"><span data-stu-id="2d449-171">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>
  
- <span data-ttu-id="2d449-172">会議を識別する、数字の電話会議 ID</span><span class="sxs-lookup"><span data-stu-id="2d449-172">A numeric conference ID that identifies the conference</span></span>
    
- <span data-ttu-id="2d449-173">1 つ以上の PSTN アクセス番号</span><span class="sxs-lookup"><span data-stu-id="2d449-173">One or more PSTN access numbers</span></span>
    
- <span data-ttu-id="2d449-174">ダイヤルイン会議の設定ページへのリンク。このページには、アクセス番号とそれに関連付けられた言語の完全な一覧、暗証番号 (PIN) の作成、リセット、または解除する場所、およびデュアルトーン多重周波数 (DTMF) 制御などのその他の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d449-174">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls</span></span>
    
<span data-ttu-id="2d449-175">会議ポリシーの詳細については、「skype for business [server でダイヤルイン会議を設定する](../../deploy/deploy-conferencing/dial-in-conferencing.md)」および「 [Skype for business server の会議ポリシーを管理](../../manage/conferencing/conferencing-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d449-175">For more information about conferencing policies, see [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) and [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>  

## <a name="support-for-enterprise-and-anonymous-users"></a><span data-ttu-id="2d449-176">エンタープライズ ユーザーと匿名ユーザーのサポート</span><span class="sxs-lookup"><span data-stu-id="2d449-176">Support for enterprise and anonymous users</span></span>

<span data-ttu-id="2d449-177">ダイヤルイン会議は、エンタープライズ ユーザーと匿名ユーザーの両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2d449-177">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="2d449-178">エンタープライズユーザーは、組織内で Active Directory ドメインサービスの資格情報と Skype for Business Server アカウントを持っています。</span><span class="sxs-lookup"><span data-stu-id="2d449-178">Enterprise users have Active Directory Domain Services credentials and Skype for Business Server accounts within their organization.</span></span> <span data-ttu-id="2d449-179">匿名ユーザーは、組織内のエンタープライズ資格情報を持っていません。</span><span class="sxs-lookup"><span data-stu-id="2d449-179">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="2d449-180">ダイヤルイン会議のコンテキストでは、PSTN を使って会議に接続しているフェデレーションパートナーの組織内のユーザーは、匿名ユーザーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="2d449-180">In the dial-in conferencing context, a user in a federated partner's organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="2d449-181">ダイヤルイン会議では、他の状況とは異なり、フェデレーション ユーザーは認証されません。</span><span class="sxs-lookup"><span data-stu-id="2d449-181">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>
  
<span data-ttu-id="2d449-p117">ダイヤルイン アクセスが有効な会議に参加するエンタープライズ ユーザーまたは会議主催者は、電話会議のアクセス番号の 1 つをダイヤルすると、電話会議 ID を入力するよう求められます。会議主催者が会議にまだ参加していない場合、ユーザーは、統合コミュニケーション (UC) 内線番号 (または完全な電話番号) と PIN を入力するか、会議主催者によって許可されるまで待機できます。会議の開催者は、PIN を入力するだけで、主催者として会議に参加できます。フロントエンド サーバーでは、完全な電話番号または内線番号と PIN の組み合わせを使用して、エンタープライズ ユーザーを Active Directory の資格情報に一意にマップします。これによって、エンタープライズ ユーザーは認証を受けて、電話会議では名前で識別されます。また、エンタープライズ ユーザーは、開催者が事前に定義した電話会議の役割を引き受けることもできます。</span><span class="sxs-lookup"><span data-stu-id="2d449-p117">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID. If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader. The Meeting organizer can join the meeting as a leader by entering just their PIN. The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials. As a result, enterprise users are authenticated and identified by name in the conference. Enterprise users can also assume a conference role predefined by the organizer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d449-188">Office IP 電話または Skype for Business Server アテンダントからダイヤルインしているエンタープライズユーザーは、既に認証されているため、電話番号を入力するように求められることはありません。</span><span class="sxs-lookup"><span data-stu-id="2d449-188">Enterprise users who dial in from an office IP phone or from Skype for Business Server Attendant are not prompted for their phone number because they are already authenticated.</span></span> 
  
<span data-ttu-id="2d449-p118">ダイヤルイン電話会議に参加する必要がある匿名ユーザーは、電話会議のアクセス番号の 1 つをダイヤルすると、電話会議 ID を入力するよう求められます。認証されていない匿名ユーザーは、名前を録音するようにも求められます。会議に出席中の認証されていないユーザーは、この録音された名前によって識別されます。 少なくとも 1 人の主催者または認証済みのユーザーが参加するまで、匿名ユーザーは会議への参加が許可されません。また、匿名ユーザーには事前に定義された役割は割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="2d449-p118">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2d449-p119">電話番号と PIN を入力しないエンタープライズ ユーザーは認証されません。そのようなユーザーは名前を録音するよう求められ、電話会議で匿名ユーザーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="2d449-p119">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span> 
  
<span data-ttu-id="2d449-p120">会議のスケジュール時に、会議の開催者は、会議を非公開またはロックすることで会議へのアクセスを制限できます。この場合、ダイヤルイン ユーザーは認証が要求されます。</span><span class="sxs-lookup"><span data-stu-id="2d449-p120">When scheduling a meeting, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked. In this case, dial-in users are requested to authenticate.</span></span> 
  
- <span data-ttu-id="2d449-197">ダイヤルイン ユーザーが認証に失敗したり認証しないよう選択した場合、ロビーに転送されます。ダイヤルイン ユーザーは、主催者が参加を許可または拒否するか、タイムアウトになって切断されるまで、ロビーで待機します。</span><span class="sxs-lookup"><span data-stu-id="2d449-197">If dial-in users fail or choose not to authenticate, they are transferred to the lobby where they until a leader accepts or rejects them, or they time out and are disconnected.</span></span>
    
- <span data-ttu-id="2d449-198">会議への参加が許可されると、ダイヤルイン ユーザーは会議の音声部分に参加し、電話キーパッドを使用して、デュアルトーン多重周波数 (DTMF) コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2d449-198">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span>
    
- <span data-ttu-id="2d449-199">ダイヤルイン会議の主催者は、DTMF コマンドを実行して参加者のミュート解除機能のオンとオフの切り替え、会議のロックとロック解除、ロビーからのユーザーの許可、および入室と退室のアナウンスのオンとオフの切り替えを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2d449-199">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span>
    
- <span data-ttu-id="2d449-200">また、主催者は、DTMF コマンドを使用してロビーからのすべてのユーザーを許可できるため、後から参加するすべてのユーザーを許可するよう、会議のアクセス許可が変更されます。</span><span class="sxs-lookup"><span data-stu-id="2d449-200">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> 
    
- <span data-ttu-id="2d449-201">すべてのダイヤルイン参加者は、DTMF コマンドを実行して、ヘルプを聞いたり、会議名簿を聞いたり、自分をミュートにしたりできます。</span><span class="sxs-lookup"><span data-stu-id="2d449-201">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>
    
- <span data-ttu-id="2d449-202">ダイヤルイン参加者 (PSTN からダイヤルするかどうかに関係なく) には、会議中に、ミュートまたはミュート解除のいずれになっているのか、会議が記録されているかどうか、ユーザーがロビーで待機しているかどうかなどの、個人向けのアナウンスが流されます。</span><span class="sxs-lookup"><span data-stu-id="2d449-202">Dial-in participants (that is, whether or not they dial from the PSTN) hear personal announcements during the conference, such as whether they have been muted or unmuted, whether the meeting is being recorded, or whether someone is waiting in the lobby.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2d449-203">ダイヤルインではなくリンクをクリックして会議に参加する参加者には、個人向けアナウンスは流されません。</span><span class="sxs-lookup"><span data-stu-id="2d449-203">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span> 
  

