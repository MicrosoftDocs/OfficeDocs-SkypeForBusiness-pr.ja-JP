---
title: "Microsoft チーム」と「Skype for Business の相互運用性"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "ビジネス チャットとエクスペリエンスの呼び出しの外観をチームと Skype の間の相互運用性を理解します。"
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 8eca9f18d02d76fe1ab1b754ecf8a49b6b20aec3
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="microsoft-teams-and-skype-for-business-interoperability"></a><span data-ttu-id="d1b7d-103">Microsoft チーム」と「Skype for Business の相互運用性</span><span class="sxs-lookup"><span data-stu-id="d1b7d-103">Microsoft Teams and Skype for Business interoperability</span></span>
=======================================================

<span data-ttu-id="d1b7d-104">組織が使用して Skype for Business 今日場合は、チームの使用を開始するには、2 つの相互運用するアプリケーションを構成する方法を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-104">If your organization uses Skype for Business today and you intend to start using Teams, it's important to understand how to configure the two applications to interoperate.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1b7d-p101">プランの呼び出しのサポート チームの初期評価については、このドキュメントが表示されます。チームの相互運用ポリシーの詳細については、今後、変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p101">This document is provided for early evaluation of Calling Plans support for Teams. Teams interop policy details are expected to change in the future.</span></span>

<span data-ttu-id="d1b7d-p102">(短い形式の相互運用性) の相互運用性により、Skype for Business とチームのユーザーをチャットし、そのコミュニケーション、通話、組織全体で滑らかをそのまま保持します。IT プロフェッショナルはチームの導入を管理するために、追加した新しいチーム相互運用ポリシー、Skype for Business リモート Windows PowerShell セッションを使用してを通して管理[`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype)コマンドレットします。チームの組織で必要に操作するのに方法を構成するのにには、このポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p102">Interoperability (interop for short) enables Skype for Business and Teams users to chat and call with one another, ensuring that communications remain fluid across your organization. To help IT pros manage the adoption of Teams, we've added a new Teams interop policy, managed through a Skype for Business remote Windows PowerShell session using [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets. Use this policy to configure Teams the way you need it to work in your organization.</span></span>


> [!TIP]
> <span data-ttu-id="d1b7d-110">相互運用に必要な PowerShell コマンドレットを検索するには、 [Skype for Business PowerShell コマンドレットのドキュメント](https://docs.microsoft.com/powershell/module/skype)で**フィルター** ] ボックスに"CsTeamsInteropPolicy"を入力します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-110">To find the PowerShell cmdlets you need for interop, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

<span data-ttu-id="d1b7d-p103">チームの相互運用ポリシーは、IT プロフェッショナル チャットと通話を受信するユーザーの任意のアプリケーションを指定するのには使用できます。チームと Skype for Business、孤立の通信を維持するように構成できるまたはアプリケーションの境界を超えた通信するためにユーザーを有効にするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p103">Teams interop policy enables an IT pro to designate a user’s preferred application for receiving chats and calls. It can be configured to keep communications in Teams and Skype for Business siloed, or it can be configured to enable users to communicate across application boundaries.</span></span>

<span data-ttu-id="d1b7d-113">チームの相互運用ポリシーは、テナント レベルまたはユーザーごとのレベルで定義されることができ、使ってがチャットと通話を受信するには、どのようなアプリケーションを選択するユーザーを有効にも構成されていることができます。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-113">Teams interop policy can be defined at the tenant or per-user level, and can even be configured to enable users to choose what application they would like to use to receive their chats and calls.</span></span>

<span data-ttu-id="d1b7d-114">この組み込みの柔軟性が、組織の試用版のヘルプ、評価、およびペースでと、組織に最適な方法でチームに移行する想定しています。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-114">This built-in flexibility is intended to help your organization trial, evaluate, and migrate to Teams at the pace and in the manner that is best suited to your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="d1b7d-115">チームと Skype for Business の間の相互運用性が純オンライン (Skype for Business Online やチーム)、ユーザーの間でサポートされているし、Skype for 混在 (ハイブリッド) 展開トポロジでビジネスのオンプレミス展開でユーザーが存在します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-115">Interoperability between Teams and Skype for Business is supported between users who are purely online (Skype for Business Online and Teams), and users homed in a Skype for Business on-premises deployment in a mixed (Hybrid) deployment topology.</span></span>

## <a name="what-interoperability-means"></a><span data-ttu-id="d1b7d-116">どのような相互運用性を意味します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-116">What interoperability means</span></span>
<span data-ttu-id="d1b7d-117">相互運用性は、チャット (IM) のビジネス ユーザーのチームと Skype の機能で互いをチームと Skype for Business 通話します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-117">Interop is the ability for Teams and Skype for Business users to chat (IM) and call each other across Teams and Skype for Business.</span></span>

<span data-ttu-id="d1b7d-118">組織では、Skype for Business からチームへの旅を開始、予想は、組織内で別のクライアントを使用しているユーザーの組み合わせがあるされます。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-118">As organizations begin the journey from Skype for Business to Teams, the expectation is that there will be a mix of users using different clients in the organization.</span></span>

<span data-ttu-id="d1b7d-119">"続く"の生産性を確認するには、チームには、ユーザーと通信するいずれかの別のアプリケーションに関係なく (チームまたは Skype for Business) を使用する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-119">To ensure continued productivity, Teams provides the ability for users to communicate with one another regardless of the application they use (Teams or Skype for Business).</span></span>

<span data-ttu-id="d1b7d-120">サポートされているの相互運用エクスペリエンス、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-120">Supported interop experiences include the following:</span></span>
- <span data-ttu-id="d1b7d-121">Skype for Business ユーザー チームを使用していないチャットできるは、チームのユーザー間で変換</span><span class="sxs-lookup"><span data-stu-id="d1b7d-121">Skype for Business users that do not use Teams can chat with Teams users, vice versa</span></span><p>
<span data-ttu-id="d1b7d-122">![チームからの相互運用チャット エクスペリエンス](media/Interop_chat_experience_from_Teams.png)</span><span class="sxs-lookup"><span data-stu-id="d1b7d-122">![Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png)</span></span><br>
- <span data-ttu-id="d1b7d-p104">Skype for Business ユーザー音声やビデオの上には、チームのユーザーを転換呼び出すことができます。詳細呼び出しのオプション] で、着信の転送と、着信の転送など、作業を続けられます、相互運用呼び出しに対してもします。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p104">Skype for Business users can call Teams users over voice and video, vice versa. Advanced calling options, such as call transfer and call forwarding will continue to work, even for interop calls.</span></span><p>
<span data-ttu-id="d1b7d-125">![チームからの相互運用呼び出しエクスペリエンス](media/Interop_calling_experience_from_Teams.png)</span><span class="sxs-lookup"><span data-stu-id="d1b7d-125">![Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png)</span></span><br>

> [!NOTE]
> <span data-ttu-id="d1b7d-p105">ビジネス ユーザーの観点の Skype からチャットとからウィンドウにドッキング、チーム呼び出しは、基本的な Skype for Business チャットと通話として表示されます。詳細については、[相互運用性の制限事項が発生した](#interop-experiences-limitations)のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p105">From a Skype for Business user point of view, chats and calls from/to Teams will appear as basic Skype for Business chats and calls. Please review the [Interop experiences limitations](#interop-experiences-limitations) section for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1b7d-p106">チームと Skype for Business の統合されたプレゼンス現在、サポートされていないことを意味チームと Skype for Business で独自の独立したプレゼンス状態が表示されます。サポート プレゼンスの統合を調べるにはできるように、 [Skype for Business に Microsoft チーム機能ロードマップ](https://aka.ms/skype2teamsroadmap)を確認します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p106">Unified presence between Teams and Skype for Business is currently not supported, which means Teams and Skype for Business will show their own independent presence states. To find out when support for unified presence is going to be available, review [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap).</span></span>

## <a name="interop-requirements"></a><span data-ttu-id="d1b7d-130">相互運用機能の要件</span><span class="sxs-lookup"><span data-stu-id="d1b7d-130">Interop requirements</span></span>
<span data-ttu-id="d1b7d-131">相互運用の機能を有効にする、ユーザーは次の抽出条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-131">For interop capabilities to be enabled, users must meet the following criteria:</span></span>
- <span data-ttu-id="d1b7d-132">ユーザーする必要がありますが有効になっている (またはライセンスが付与されて) チーム</span><span class="sxs-lookup"><span data-stu-id="d1b7d-132">Users must be enabled (and/or licensed) for Teams</span></span>
- <span data-ttu-id="d1b7d-133">ユーザーする必要がありますが有効になっている (またはライセンスが付与されて) Skype for Business Online の</span><span class="sxs-lookup"><span data-stu-id="d1b7d-133">Users must be enabled (and/or licensed) for Skype for Business Online</span></span>
    - <span data-ttu-id="d1b7d-134">これは、プライマリ チャット呼び出し元のアプリケーションとチームをのみを使用することを計画しているユーザーまたはチームに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-134">This is applicable to users that are planning to use Teams only or Teams as their primary chat and calling application</span></span>
- <span data-ttu-id="d1b7d-135">ビジネス展開の場合は、ハイブリッド Skype で</span><span class="sxs-lookup"><span data-stu-id="d1b7d-135">In a hybrid Skype for Business deployment,</span></span>
    - <span data-ttu-id="d1b7d-136">クラウドのユーザーがチームを使用してビジネス (または現在 Business ハイブリッド展開の Skype でサポートされているすべての Lync Server バージョン) の内部設置型の Skype のユーザーが存在、相互運用性</span><span class="sxs-lookup"><span data-stu-id="d1b7d-136">Users homed at on-premises Skype for Business (or any Lync Server version currently supported for Skype for Business Hybrid deployment), can interop with cloud users using Teams</span></span>
    - <span data-ttu-id="d1b7d-137">クラウドのユーザーのプライマリ チャットとしてチームの使用を計画、アプリケーションの呼び出しをする必要がありますが有効になっている (またはライセンスが付与されて) Skype for Business Online の</span><span class="sxs-lookup"><span data-stu-id="d1b7d-137">Cloud users that are planning to use Teams as their primary chat and calling application must be enabled (and/or licensed) for Skype for Business Online</span></span>

## <a name="supported-topologies-for-interop"></a><span data-ttu-id="d1b7d-138">サポートされているトポロジの相互運用性</span><span class="sxs-lookup"><span data-stu-id="d1b7d-138">Supported topologies for interop</span></span>
<span data-ttu-id="d1b7d-139">チームと Skype for Business の間の相互運用性は主に以下 Skype for Business の展開トポロジのサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-139">Interop between Teams and Skype for Business is primarily supported for the following Skype for Business deployment topologies:</span></span>
- <span data-ttu-id="d1b7d-140">Skype for Business Online のみ</span><span class="sxs-lookup"><span data-stu-id="d1b7d-140">Skype for Business Online only</span></span>
- <span data-ttu-id="d1b7d-141">Skype for Business (混在 Skype の展開 Business Online と Skype for Business オンプレミス用)</span><span class="sxs-lookup"><span data-stu-id="d1b7d-141">Skype for Business Hybrid (mixed deployment of Skype for Business Online and Skype for Business on-premises)</span></span>

### <a name="skype-for-business-online-only-topology"></a><span data-ttu-id="d1b7d-142">Business Online のみトポロジの Skype</span><span class="sxs-lookup"><span data-stu-id="d1b7d-142">Skype for Business Online only topology</span></span>
<span data-ttu-id="d1b7d-143">のみ Skype for Business Online 展開組織は、チャットの相互運用と Skype for Business Online のユーザーとチームのユーザーの呼び出し元のサポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-143">Organizations with Skype for Business Online deployment only can benefit from interop chat and calling support between Skype for Business Online users and Teams users.</span></span>

<span data-ttu-id="d1b7d-144">このトポロジでプライマリ チャットとしてチームと、ユーザーが設定されているし、呼び出し元のアプリケーションも有効化が必要 skype for Business Online の相互運用性関数にします。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-144">In this topology, users configured with Teams as the primary chat and calling application must also be enabled for Skype for Business Online for interop to function.</span></span>

![Skype for Business Online のみ展開トポロジの相互運用性](media/Interop_SkypeforBusinessOnlineOnly_topology.png)

### <a name="skype-for-business-hybrid-deployment-topology"></a><span data-ttu-id="d1b7d-146">Skype for Business のハイブリッド展開のトポロジ</span><span class="sxs-lookup"><span data-stu-id="d1b7d-146">Skype for Business Hybrid deployment topology</span></span>
<span data-ttu-id="d1b7d-147">Skype for Business Online と Skype for Business 組み合わせた展開の構成の展開を持つ組織サーバー (オンプレミス) のハイブリッド展開トポロジでは、役に立つ相互運用チャットと Skype for Business のユーザー (ホームが間呼び出しのサポートいずれかのオンラインや社内)、およびチームのユーザー。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-147">Organizations with a deployment that consists of mixed deployment of Skype for Business Online and Skype for Business server (on-premises) in a Hybrid deployment topology, can benefit from interop chat and calling support between Skype for Business users (homed at either online and on-premises) and Teams users.</span></span>

<span data-ttu-id="d1b7d-148">同様に Business Online のみ展開トポロジの Skype、プライマリ チャットとしてチームと、ユーザーが設定されているアプリケーションを呼び出す必要がありますもは用に有効に存在してで Skype for Business Online 関数には、相互運用性の。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-148">Like Skype for Business Online only deployment topology, users configured with Teams as the primary chat and calling application must also be enabled for and homed at Skype for Business Online for interop to function.</span></span>

![Skype for Business のハイブリッド展開のトポロジの相互運用性](media/Interop_SkypeforBusinessHybrid_topology.png)

> [!IMPORTANT]
> <span data-ttu-id="d1b7d-p107">Skype for Business の相互運用サポート CCE (クラウド コネクタ エディション) 経由で配信ハイブリッド音声機能は含まれませんまたはオンプレミス PSTN 接続 - 既存の展開を使用するか、OPCH ([Prem 構成ハイブリッド) として一般的と呼ばれます。チームのユーザーは PSTN 通話の CCE または OPCH を使用する機能を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p107">Interop support for Skype for Business Hybrid does not include Hybrid Voice capabilities delivered through CCE (Cloud Connector Edition) or on-premises PSTN connectivity using existing deployment--or commonly called as OPCH (On Prem Config Hybrid). Teams users cannot be enabled for PSTN calling capabilities using CCE or OPCH.</span></span>

### <a name="interop-experiences-limitations"></a><span data-ttu-id="d1b7d-152">相互運用エクスペリエンスの制限事項</span><span class="sxs-lookup"><span data-stu-id="d1b7d-152">Interop experiences limitations</span></span>
<span data-ttu-id="d1b7d-153">現在、チームと Skype for Business で、チームと Skype for Business の自分の独立したプレゼンス状態が発生する潜在顧客、統合されたプレゼンスがない場合以外は相互運用チャットと相互運用呼び出しを利用できない機能チームと Skype for Business のエクスペリエンスします。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-153">Currently, in addition to the absence of unified presence between Teams and Skype for Business, which leads to Teams and Skype for Business having their own independent presence states, there are features that are not available for interop chat and interop calling experiences between Teams and Skype for Business.</span></span>

<span data-ttu-id="d1b7d-154">チャットの相互運用には、次の制限事項の現在のリストです。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-154">For chat interop, the following are the current list of limitations:</span></span>
- <span data-ttu-id="d1b7d-155">チームで複数のパーティー (グループ) の会話 (チャット) は、チームを使用する参加者を含めることができますのみ</span><span class="sxs-lookup"><span data-stu-id="d1b7d-155">Multi-party (group) conversation (chat) in Teams can only include participants using Teams</span></span>
- <span data-ttu-id="d1b7d-156">マルチパーティ IM 会話 (チャット) Skype for Business では、Skype for Business 使い参加者を含めることができますのみ</span><span class="sxs-lookup"><span data-stu-id="d1b7d-156">Multi-party IM conversation (chat) in Skype for Business can only include participants using Skype for Business</span></span>
- <span data-ttu-id="d1b7d-157">2 者間のチャットの会話またはチームと Skype for Business では、複数の会話でファイルの添付ファイルのファイル転送間の切り替えはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-157">File transfer for two-party chat conversation or file attachment in multi-party conversation across Teams and Skype for Business, vice versa, are not supported</span></span>
- <span data-ttu-id="d1b7d-158">チームの相互運用チャットは保持されません。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-158">Interop chat is not persisted in Teams</span></span>
- <span data-ttu-id="d1b7d-159">値下げ、リッチ テキスト、完全な絵文字セット、相互運用チャットのチームでなどがサポートされていません</span><span class="sxs-lookup"><span data-stu-id="d1b7d-159">Markdown, rich text, full emoticon set, etc. in Teams are not supported for interop chat</span></span>

<span data-ttu-id="d1b7d-160">呼び出しの相互運用には、次の制限事項の現在のリストです。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-160">For calling interop, the following are the current list of limitations:</span></span>
- <span data-ttu-id="d1b7d-161">スクリーン (デスクトップまたはアプリケーションの共有) をチームと Skype for Business の共有はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="d1b7d-161">Screen sharing (desktop or app sharing) between Teams and Skype for Business is not supported</span></span>
- <span data-ttu-id="d1b7d-162">ピア ツー ピア (P2P) の進行中の音声とビデオ通話をチームと Skype のビジネス ユーザーの検出しやすくマルチパーティの通話の昇格はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="d1b7d-162">Escalation of ongoing peer to peer (P2P) voice and video call to multi-party call involving Teams and Skype for Business users is not supported</span></span>

## <a name="managing-interoperability"></a><span data-ttu-id="d1b7d-163">管理の相互運用性</span><span class="sxs-lookup"><span data-stu-id="d1b7d-163">Managing interoperability</span></span>
<span data-ttu-id="d1b7d-164">チームと Skype for Business の間の相互運用性を管理するには、チームの相互運用ポリシーと呼ばれる新しいポリシーを使用して、位置の制御をチャットの送信、通話をルーティングするには、チームの組織内のすべてのユーザーは、Skype for Business、およびこのポリシーを構成することができます。(グローバル ポリシー) または Business リモート Windows PowerShell セッションを使う場合の Skype を管理しやすく、ユーザーごとに適用される[`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)コマンドレットします。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-164">To manage the interoperability between Teams and Skype for Business, a new policy called Teams interop policy can be utilized to control where to send chats and route calls, Teams or Skype for Business, and this policy can be configured for all users in the organization (global policy) or applied at the per user basis, manageable through Skype for Business remote Windows PowerShell session using [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps) cmdlets.</span></span>

<span data-ttu-id="d1b7d-p108">既定では、このポリシーように構成されてチームと Skype for Business できる間に最低限の相互運用性と並行して使用することを確認します。この方法は、現在のビジネス プロセスと、組織内の通信が中断するチーム導入の結果としてことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p108">By default, this policy is configured to ensure that Teams and Skype for Business can be used side-by-side with minimal interop between them. This approach is intended to ensure that current business processes and communications within your organizations are not disrupted as a result of Teams adoption.</span></span>

### <a name="interop-policy-overview"></a><span data-ttu-id="d1b7d-167">相互運用ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="d1b7d-167">Interop policy overview</span></span>
<span data-ttu-id="d1b7d-168">チームの相互運用ポリシーは、次のパラメーターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-168">Teams interop policy consists of the following parameters:</span></span>

|<span data-ttu-id="d1b7d-169">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1b7d-169">Parameter</span></span>                    |<span data-ttu-id="d1b7d-170">指定可能な値</span><span class="sxs-lookup"><span data-stu-id="d1b7d-170">Possible values</span></span>      |<span data-ttu-id="d1b7d-171">説明</span><span class="sxs-lookup"><span data-stu-id="d1b7d-171">Description</span></span>  |
|-----------------------------|---------------------|---------|
|`ChatDefaultClient`          | <span data-ttu-id="d1b7d-172">既定のデバイス、チーム</span><span class="sxs-lookup"><span data-stu-id="d1b7d-172">Default, SfB, Teams</span></span> | <span data-ttu-id="d1b7d-173">このパラメーターは、チャットの既定のアプリを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-173">This parameter specifies the default Chat app</span></span>        |
|`CallingDefaultClient`       | <span data-ttu-id="d1b7d-174">既定のデバイス、チーム</span><span class="sxs-lookup"><span data-stu-id="d1b7d-174">Default, SfB, Teams</span></span> | <span data-ttu-id="d1b7d-175">このパラメーターは、通話の既定のアプリを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-175">This parameter specifies the default Calling app</span></span>        |
|`AllowEndUserClientOverride` | <span data-ttu-id="d1b7d-176">True、false の場合</span><span class="sxs-lookup"><span data-stu-id="d1b7d-176">True, False</span></span>         | <span data-ttu-id="d1b7d-177">このパラメーターは、ユーザーが既定のチャットとアプリの呼び出しを上書きできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-177">This parameter specifies whether users can override the default Chat and Calling app</span></span>         |

> [!WARNING]
> <span data-ttu-id="d1b7d-p109">現在の独立した値を持つチームの相互運用ポリシーを作成することはできますが`ChatDefaultClient`と`CallingDefaultClient`パラメーターを考えて、今後、変更します。この時点で確認してください両方のパラメーターの値を使用しています。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p109">While it is currently possible to create Teams interop policy with independent values for `ChatDefaultClient` and `CallingDefaultClient` parameters, we expect this to change in the future. At this time, please ensure that you are using the same value for both parameters.</span></span>

#### <a name="chat-default-client"></a><span data-ttu-id="d1b7d-180">チャットの既定のクライアント</span><span class="sxs-lookup"><span data-stu-id="d1b7d-180">Chat default client</span></span>
<span data-ttu-id="d1b7d-181">[`ChatDefaultClient`チームと Skype for Business] の [チャットのルーティング方法を定義して、このパラメーターのグローバル既定値は、**既定**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-181">The `ChatDefaultClient` parameter defines how chats are routed between Teams and Skype for Business, and the default global value of this parameter is set to **Default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1b7d-p110">、現時点では、`ChatDefaultClient`パラメーターはチームが尊重されません。チームが尊重パラメーターと想定される動作を説明するには、このドキュメントが更新されます。チームと Skype for Business のテナント レベルで管理されている間は、既存のチャット相互運用機能は引き続き機能はします。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p110">At the present time, the `ChatDefaultClient` parameter is not respected by Teams. We will update this documentation to describe the expected behavior once the parameter is respected by Teams. Existing chat interop capabilities between Teams and Skype for Business controlled at the tenant level will continue to work as is.</span></span>

#### <a name="calling-default-client"></a><span data-ttu-id="d1b7d-185">通話の既定のクライアント</span><span class="sxs-lookup"><span data-stu-id="d1b7d-185">Calling default client</span></span>
<span data-ttu-id="d1b7d-186">`CallingDefaultClient`チームと Skype for Business で通話をルーティングする方法を定義して、このパラメーターのグローバル既定値は、**既定**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-186">The `CallingDefaultClient` parameter defines how calls are routed between Teams and Skype for Business, and the default global value of this parameter is set to **Default**.</span></span>

<span data-ttu-id="d1b7d-187">このパラメーターの各値に影響するしくみチームと Skype for Business クライアントの動作の詳細な説明を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-187">Below is the detailed explanation of how each setting of this parameter influences Teams and Skype for Business client behavior.</span></span>

|<span data-ttu-id="d1b7d-188">発信者からを呼び出す</span><span class="sxs-lookup"><span data-stu-id="d1b7d-188">Caller calling from</span></span>  |<span data-ttu-id="d1b7d-189">既定の設定:通話の受信</span><span class="sxs-lookup"><span data-stu-id="d1b7d-189">Setting: Default; call received on</span></span>  |<span data-ttu-id="d1b7d-190">チームの設定:通話の受信</span><span class="sxs-lookup"><span data-stu-id="d1b7d-190">Setting: Teams; call received on</span></span>  |<span data-ttu-id="d1b7d-191">デバイスの設定: です。通話の受信</span><span class="sxs-lookup"><span data-stu-id="d1b7d-191">Setting: SfB; call received on</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="d1b7d-192">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="d1b7d-192">**Skype for Business**</span></span>     |<span data-ttu-id="d1b7d-193">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1b7d-193">Skype for Business</span></span>         |<span data-ttu-id="d1b7d-194">チーム</span><span class="sxs-lookup"><span data-stu-id="d1b7d-194">Teams</span></span>        |<span data-ttu-id="d1b7d-195">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1b7d-195">Skype for Business</span></span>         |
|<span data-ttu-id="d1b7d-196">**チーム**</span><span class="sxs-lookup"><span data-stu-id="d1b7d-196">**Teams**</span></span>     |<span data-ttu-id="d1b7d-197">チーム</span><span class="sxs-lookup"><span data-stu-id="d1b7d-197">Teams</span></span>         |<span data-ttu-id="d1b7d-198">チーム</span><span class="sxs-lookup"><span data-stu-id="d1b7d-198">Teams</span></span>         |<span data-ttu-id="d1b7d-199">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1b7d-199">Skype for Business</span></span>         |
|<span data-ttu-id="d1b7d-200">**PSTN**</span><span class="sxs-lookup"><span data-stu-id="d1b7d-200">**PSTN**</span></span>   |<span data-ttu-id="d1b7d-201">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1b7d-201">Skype for Business</span></span>        |<span data-ttu-id="d1b7d-202">チーム</span><span class="sxs-lookup"><span data-stu-id="d1b7d-202">Teams</span></span>        |<span data-ttu-id="d1b7d-203">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1b7d-203">Skype for Business</span></span>         |
|<span data-ttu-id="d1b7d-204">**フェデレーションの Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="d1b7d-204">**Federated Skype for Business**</span></span>     |<span data-ttu-id="d1b7d-205">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1b7d-205">Skype for Business</span></span>         |<span data-ttu-id="d1b7d-206">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1b7d-206">Skype for Business</span></span>         |<span data-ttu-id="d1b7d-207">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d1b7d-207">Skype for Business</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="d1b7d-p111">現時点では、変更する`CallingDefaultClient`チームにも影響 skype 通話ビジネス IP 電話用します。着信通話られ、携帯電話に受信できませんが、リング チーム クライアントのみをされます。既存の認定 SIP 電話のサポートについては、 [Skype for Business に Microsoft チーム機能ロードマップ](https://aka.ms/skype2teamsroadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p111">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones. Incoming calls will not be received on the phones and will only ring Teams clients. Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

#### <a name="allowing-user-choice"></a><span data-ttu-id="d1b7d-211">ユーザーの選択を許可します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-211">Allowing user choice</span></span>
<span data-ttu-id="d1b7d-212">`AllowEndUserClientOverride`パラメーターがブール値 (**TRUE**または**FALSE**) を受け入れるし、チームがチームまたは Skype for Business、-、通話を受信する必要があると、ユーザーが、プライマリを変更できる場所を選択する許可を持つ**TRUE**に設定されている場合いつでもアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-212">The `AllowEndUserClientOverride` parameter accepts Boolean value (**TRUE** or **FALSE**), and when it is set to **TRUE**, Teams will allow users to select where they want to receive their calls--Teams or Skype for Business, and users will be able to change their primary application at any time.</span></span>

![好みの呼び出し元アプリケーション オプション](media/Preferred_calling_application_option.png)

<span data-ttu-id="d1b7d-214">このパラメーターのグローバル既定値が**FALSE**されないようにユーザーは可能管理者からしなくても、プライマリ アプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-214">The global default value for this parameter is **FALSE**, thereby users will not be allowed to choose their primary application without intervention from administrator.</span></span>

## <a name="teams-interop-policy-special-cases"></a><span data-ttu-id="d1b7d-215">チームの相互運用ポリシーの特殊な場合</span><span class="sxs-lookup"><span data-stu-id="d1b7d-215">Teams interop policy special cases</span></span>
<span data-ttu-id="d1b7d-216">チームの相互運用ポリシー、ビジネス オンプレミス--混在 (ハイブリッド) 展開トポロジでの Skype のホームに残っているユーザーに割り当てる (両方 CCE や OPCH)、ハイブリッドの音声を持つユーザーとビジネス ワークフローの特殊な skype ユーザーと見なされ、特殊な場合は、およびが割り当てられているポリシーに特別な注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-216">When assigning Teams interop policy, users that remain homed at Skype for Business on-premises--in a mixed (Hybrid) deployment topology, users with Hybrid Voice (both through CCE or OPCH), and users with specialized Skype for Business workflows are considered special cases, and they require special attention on the policy assigned to them.</span></span>

### <a name="policy-for-skype-for-business-on-premises-users"></a><span data-ttu-id="d1b7d-217">Skype for Business のポリシー オンプレミス ユーザー</span><span class="sxs-lookup"><span data-stu-id="d1b7d-217">Policy for Skype for Business on-premises users</span></span>
<span data-ttu-id="d1b7d-p112">混合 (ハイブリッド) 展開トポロジでは、ユーザーが所属 Skype でのビジネス オンプレミスにチームのいずれかの設定、ポリシーを使用する必要はありません`ChatDefaultClient`と`CallingDefaultClient`パラメーターします。存在する場合は、することはできませんチャットと通話を受信します。オンプレミスのユーザーには、次のポリシーの定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p112">In a mixed (Hybrid) deployment topology, users homed at Skype for Business on-premises should never have their policy set to Teams for either `ChatDefaultClient` and `CallingDefaultClient` parameters. If they do, they will be unable to receive chats and calls. Use the following policy definition for on-prem users:</span></span>

|<span data-ttu-id="d1b7d-221">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1b7d-221">Parameter</span></span>  |<span data-ttu-id="d1b7d-222">値</span><span class="sxs-lookup"><span data-stu-id="d1b7d-222">Value</span></span>  |
|---------|---------|
|`ChatDefaultClient`    |<span data-ttu-id="d1b7d-223">既定のグループまたはデバイス</span><span class="sxs-lookup"><span data-stu-id="d1b7d-223">Default or SfB</span></span>         |
|`CallingDefaultClient`     |<span data-ttu-id="d1b7d-224">既定のグループまたはデバイス</span><span class="sxs-lookup"><span data-stu-id="d1b7d-224">Default or SfB</span></span>         |
|`AllowEndUserClientOverride`     |<span data-ttu-id="d1b7d-225">False</span><span class="sxs-lookup"><span data-stu-id="d1b7d-225">False</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="d1b7d-p113">ユーザー Skype から for Business Online に移動 Skype for Business、社内でときに、その逆の動作を適用する必要のあるユーザーに割り当てられているチームの相互運用ポリシーが配置されたかどうかを確認する必要があります。プライマリ チャット アプリケーションを呼び出すとチームを使用するオンプレミスのユーザーを構成できないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p113">When moving users from Skype for Business Online to Skype for Business on-premises, or vice versa, you need to make sure the Teams interop policy assigned to the user is aligned with the behavior that needs to be enforced. Remember that on-premises users cannot be configured to use Teams as primary chat and calling application.</span></span>

### <a name="policy-for-hybrid-voice-users-cce-or-opch"></a><span data-ttu-id="d1b7d-228">ハイブリッド ボイス ユーザー (CCE または OPCH) のポリシー</span><span class="sxs-lookup"><span data-stu-id="d1b7d-228">Policy for Hybrid Voice users (CCE or OPCH)</span></span>
<span data-ttu-id="d1b7d-p114">Skype for Business Online のユーザーがハイブリッドの音声 (CCE または OPCH) 経由で電話システム用に有効には、チームで PSTN 通話を受信することはできません。ハイブリッド ボイス ユーザーのチームの相互運用ポリシーを割り当てる場合は、次のポリシーの定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p114">Skype for Business Online users enabled for Phone System with Hybrid Voice (through CCE or OPCH) cannot receive PSTN calls in Teams. When assigning Teams interop policy for Hybrid Voice users, use the following policy definition</span></span>

|<span data-ttu-id="d1b7d-231">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1b7d-231">Parameter</span></span>  |<span data-ttu-id="d1b7d-232">値</span><span class="sxs-lookup"><span data-stu-id="d1b7d-232">Value</span></span>  |
|---------|---------|
|`ChatDefaultClient`    |<span data-ttu-id="d1b7d-233">既定のデバイスまたはチーム</span><span class="sxs-lookup"><span data-stu-id="d1b7d-233">Default or SfB or Teams</span></span>         |
|`CallingDefaultClient`     |<span data-ttu-id="d1b7d-234">既定のグループまたはデバイス</span><span class="sxs-lookup"><span data-stu-id="d1b7d-234">Default or SfB</span></span>         |
|`AllowEndUserClientOverride`     |<span data-ttu-id="d1b7d-235">False</span><span class="sxs-lookup"><span data-stu-id="d1b7d-235">False</span></span>         |

### <a name="policy-for-users-with-specialized-skype-for-business-workflows"></a><span data-ttu-id="d1b7d-236">ビジネス ワークフローの特殊な Skype でのユーザーに対してポリシー</span><span class="sxs-lookup"><span data-stu-id="d1b7d-236">Policy for users with specialized Skype for Business workflows</span></span>
<span data-ttu-id="d1b7d-p115">場合によっては、ユーザーのグループを使用している可能性 Skype for Business に依存するサードパーティのアプリケーション (例:: センター、受付応答などの着信します。) します。場合、次のことが必要になるまで、チーム内と同じ機能がある Skype for Business で維持するためにします。これらのユーザーでは、次のポリシーの定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="d1b7d-p115">In some cases, a group of users may be using third party applications that rely on Skype for Business (e.g.: call centers, front desk attendants, etc.). In these cases, you will want to ensure that they remain on Skype for Business until they have equivalent capabilities in Teams. For these users, use the following policy definition:</span></span>

|<span data-ttu-id="d1b7d-240">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d1b7d-240">Parameter</span></span>  |<span data-ttu-id="d1b7d-241">値</span><span class="sxs-lookup"><span data-stu-id="d1b7d-241">Value</span></span>  |
|---------|---------|
|`ChatDefaultClient`    |<span data-ttu-id="d1b7d-242">既定のグループまたはデバイス</span><span class="sxs-lookup"><span data-stu-id="d1b7d-242">Default or SfB</span></span>         |
|`CallingDefaultClient`     |<span data-ttu-id="d1b7d-243">既定のグループまたはデバイス</span><span class="sxs-lookup"><span data-stu-id="d1b7d-243">Default or SfB</span></span>         |
|`AllowEndUserClientOverride`     |<span data-ttu-id="d1b7d-244">False</span><span class="sxs-lookup"><span data-stu-id="d1b7d-244">False</span></span>         |