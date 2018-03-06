---
title: "Microsoft Teams の概要"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: "Microsoft Teams とそのインフラストラクチャについて、および Office 365 と組み合わせた Teams の使用について説明します。"
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: caf445609922dc62d28a4b78cf568d3f8f278c10
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="1d2de-103">Microsoft Teams の概要</span><span class="sxs-lookup"><span data-stu-id="1d2de-103">Overview of Microsoft Teams</span></span>
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


<span data-ttu-id="1d2de-p101">Microsoft Teams は Office 365 のすべてをまとめ、チームワークを遂行する上でチャットベースのハブをもたらし、よりオープンで、スムーズで、デジタルな環境を創り出す機会をお客様に提供します。Microsoft Teams は、Office 365 グループによって作られた既存の Microsoft テクノロジーを基に作られています。</span><span class="sxs-lookup"><span data-stu-id="1d2de-p101">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment. Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="1d2de-106">革新的な発想により、Teams は、Azure Active Directory (Azure AD) に保存された ID を利用し、Office 365 のその他のサービスと統合して、作成されるチームごとに SharePoint オンライン サイトと Exchange Online グループ メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d2de-106">Out of the box, Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="1d2de-107">Teams では常設チャットの機能や通話と会議が利用でき、その強力な拡張性に加えて Office 365 の他のコンポーネントに容易にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-107">Teams provides a persistent chat capability, calling and meetings, easy access to other components of Office 365 as well as a robust extensibility story.</span></span>  <span data-ttu-id="1d2de-108">これにより、大企業から小規模な組織にいたるまで、その中にいるすべてのユーザーにとって最適なチームワークのハブを構成します。</span><span class="sxs-lookup"><span data-stu-id="1d2de-108">This provides a hub for teamwork that is appropriate for enterprise companies, small organizations and everyone in between.</span></span>  

<span data-ttu-id="1d2de-109">Teams の機能を拡張するために、コネクタ、タブ、およびボットを[アプリ](https://go.microsoft.com/fwlink/?linkid=854629)として利用できます。これらによって、外部の情報、コンテンツ、およびインテリジェントなボットとの対話が Teams にもたらされます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-109">To extend Teams capabilities, use Connectors, Tabs, and Bots - available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629), to bring external information, content, and intelligent bot interactions to Teams.</span></span>  

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="1d2de-110">Microsoft Teams のインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="1d2de-110">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="1d2de-111">Teams は、Office 365 グループによって作られた既存の Microsoft テクノロジーを基にしています。</span><span class="sxs-lookup"><span data-stu-id="1d2de-111">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="1d2de-112">Microsoft のクラウドによって、組織はそのコラボレーションの一部として Microsoft Teams を利用する際に優れたパフォーマンスと信頼性を期待することができます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-112">Powered by the Microsoft cloud, organizations can expect excellent performance and reliability when leveraging Teams as part of their collaboration story.</span></span>

<span data-ttu-id="1d2de-113">革新的な発想により、Teams で作成されたチームは、Office 365 グループ、(ドキュメント ライブラリを備えた) SharePoint Online サイト、Teams によって会議の招待などの情報を保存するために使用される Exchange Online グループ メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="1d2de-113">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="1d2de-114">チームは既存の Office 365 グループを使用して作成でき、既存のグループ メンバーシップと、SharePoint Online および Exchange Online に保存されたコンテンツを Teams に移行することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="1d2de-114">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="1d2de-115">リアルタイムでくだけた会話が行われる常設チャット ボードとしての Teams の機能を補完するために、Teams も、Skype および Skype for Business でも使用されている次世代のクラウドベース インフラストラクチャに基づく会議のエクスペリエンスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="1d2de-115">To complement the Teams capability as a persistent chat board where informal, real-time conversations take place, Teams also provides a meeting experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="1d2de-116">これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-116">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="1d2de-117">Office 365 グループは Azure Active Directory (Azure AD) に保存された ID を利用するため、多要素認証 (MFA) のサポートなどの Azure AD におけるすべての認証および承認機能は、Teams ですぐに使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-117">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), are readily available for use by Teams.</span></span>

<span data-ttu-id="1d2de-118">Teams は、Skype および Skype for Business でも使用されている次世代のクラウドベース インフラストラクチャに基づく通話および会議のエクスペリエンスも提供しています。</span><span class="sxs-lookup"><span data-stu-id="1d2de-118">Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="1d2de-119">これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-119">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="1d2de-120">Microsoft Teams と Office 365</span><span class="sxs-lookup"><span data-stu-id="1d2de-120">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="1d2de-121">それぞれのグループにおいて、機能的な役割やワークスタイルに基づくさまざまなニーズが生じています。</span><span class="sxs-lookup"><span data-stu-id="1d2de-121">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="1d2de-122">Office 365 は、あらゆるグループの固有のワークスタイルに対応するよう設計されており、次のような専用の統合アプリケーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="1d2de-122">Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, including:</span></span>

-   <span data-ttu-id="1d2de-123">エンタープライズグレードの電子メールに対応した Outlook。現在はグループ機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="1d2de-123">Outlook for enterprise-grade email, now with groups functionality</span></span>

-   <span data-ttu-id="1d2de-124">サイトおよびポータル用 SharePoint、インテリジェント コンテンツ サービス、ビジネス プロセスの自動化とエンタープライズ検索。</span><span class="sxs-lookup"><span data-stu-id="1d2de-124">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search</span></span>

-   <span data-ttu-id="1d2de-125">会社規模の接続を推進する Yammer</span><span class="sxs-lookup"><span data-stu-id="1d2de-125">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="1d2de-126">エンタープライズ VoIP およびビデオの法人顧客向けバックボーンとしての Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="1d2de-126">Skype for Business as the backbone for enterprise voice and video</span></span>

-   <span data-ttu-id="1d2de-127">現在は、Office 365 の新しいチャットベースのワークスペースである Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="1d2de-127">And now, Microsoft Teams, the new chat-based workspace in Office 365</span></span>

<span data-ttu-id="1d2de-p108">Office 365 の各アプリケーションの一般的な使用例を示します。詳細な使用方法については、[FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="1d2de-p108">Here are common use cases for each application in Office 365. For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![Microsoft Teams アイコン。](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="1d2de-131">同じグループのメンバーとのリアルタイムでのコラボレーションを望んでいるユーザーおよびチームにより利用されます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-131">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="1d2de-132">プロジェクトに関する迅速な反復を行いながら、ファイルを共有し、共有された成果物に関してコラボレーションを行うことを望んでいるチームをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1d2de-132">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="1d2de-133">ユーザーがワークスペースに幅広いツール (Planner、Power BI、GitHub など) を接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1d2de-133">Allows Users looking to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![Microsoft Outlook アイコン。](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="1d2de-135">使い慣れた電子メール環境や、より丁寧で真面目な方法で、共同作業を行うことを希望するユーザーにより利用されます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-135">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="1d2de-136">電子メールの使用が必要な固有のビジネス プロセスを提供して、組織の内外の文書や情報を伝達します。</span><span class="sxs-lookup"><span data-stu-id="1d2de-136">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="1d2de-137">周辺のワークグループまたは組織の外側にいるユーザーと通信したり接続します。</span><span class="sxs-lookup"><span data-stu-id="1d2de-137">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![Yammer アイコン。](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="1d2de-139">組織全体のユーザーと接続して、プラクティスのコミュニティを中心にまとまり、ベスト プラクティスを共有することをサポートするために利用されます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-139">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="1d2de-140">オープンで透明性の高いフィードベースのプラットフォームを通じて、部門連係ワークフローを改善します</span><span class="sxs-lookup"><span data-stu-id="1d2de-140">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="1d2de-141">リーダーとより広範な従業員ベースの間の双方向の会話により、幹部従業員のエンゲージメントを促進します</span><span class="sxs-lookup"><span data-stu-id="1d2de-141">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="1d2de-142">第一線の労働力を鼓舞して、知識と専門性を共有、享受します</span><span class="sxs-lookup"><span data-stu-id="1d2de-142">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![Skype for Business アイコン。](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="1d2de-144">お客様/パートナーとの内部および外部向けのリアルタイムの通信、コラボレーションに利用されます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-144">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="1d2de-145">オーディオ、ビデオ、および大小のチーム (最大 10,000 人の参加者を収容する市役所など) を含むコンテンツを伴う会議を提供します。</span><span class="sxs-lookup"><span data-stu-id="1d2de-145">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="1d2de-146">法人向けのテレフォニー機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1d2de-146">Offers enterprise telephony functionality.</span></span>


![Microsoft SharePoint アイコン。](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="1d2de-148">サイトおよびポータル (会社ニュースとお知らせ、検索、およびドキュメントのコラボレーションなど) で利用されます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-148">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="1d2de-149">Microsoft Flow と PowerApps を統合することで、ドキュメント ライブラリと情報のリストに対してビジネス プロセスの自動化を実装します。</span><span class="sxs-lookup"><span data-stu-id="1d2de-149">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="1d2de-150">ファイルの保存、チームのニュース、ページ、リストなどに関して、すべての Microsoft Team に対して自動的にプロビジョニングされる強力な SharePoint チームサイト。</span><span class="sxs-lookup"><span data-stu-id="1d2de-150">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="1d2de-151">[Teams との SharePoint Online と OneDrive for Business の連携](SharePoint-OneDrive-interact.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1d2de-151">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>

## <a name="teams-known-issuesknown-issuesmd"></a>[<span data-ttu-id="1d2de-152">Teams の既知の問題</span><span class="sxs-lookup"><span data-stu-id="1d2de-152">Teams known issues</span></span>](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[<span data-ttu-id="1d2de-153">Teams クライアントのリリース ノート</span><span class="sxs-lookup"><span data-stu-id="1d2de-153">Teams client release notes</span></span>](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)

## <a name="what-happened-to-the-teams-admin-faq"></a><span data-ttu-id="1d2de-154">Teams 管理者のよくあるご質問 (FAQ) はどうなりましたか?</span><span class="sxs-lookup"><span data-stu-id="1d2de-154">What happened to the Teams admin FAQ?</span></span>

<span data-ttu-id="1d2de-155">Teams 管理者のよくあるご質問 (FAQ) は、最初に Teams をリリースした時点では便利でしたが、次第に「散らかった引き出し」のような状態になり、特定の情報を見つけ出すのが難しくなってしまいました。</span><span class="sxs-lookup"><span data-stu-id="1d2de-155">While the Teams Admin FAQ was handy when we first released Teams, it quickly became a "junk drawer" that made it hard to find anything specific.</span></span> <span data-ttu-id="1d2de-156">このため、よくあるご質問 (FAQ) は廃止して、お客様が現在参照されているこの Teams のドキュメンテーションに FAQ に関する有益な情報を統合しました。</span><span class="sxs-lookup"><span data-stu-id="1d2de-156">So we busted apart the FAQ and incorporated its valuable information into the Teams documentation that you're looking at right now.</span></span> <span data-ttu-id="1d2de-157">よくあるご質問 (FAQ) に記載されていた情報はコンテキストに応じてこのドキュメンテーションですべて見つかります。</span><span class="sxs-lookup"><span data-stu-id="1d2de-157">You'll find all the information that was in the FAQ in this documentation, in context.</span></span>

<span data-ttu-id="1d2de-158">ここで見つけることができない情報を探す場合は、以下にある [**コメント**] セクションにその内容を入力してお知らせください。</span><span class="sxs-lookup"><span data-stu-id="1d2de-158">If you're looking for something that you can't find here, please tell us about it in the **Comments** section below.</span></span> <span data-ttu-id="1d2de-159">いただいたコメントに対しては、24 時間以内に対応するよう努めます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-159">We try to respond to your comments within 24 hours.</span></span>

<span data-ttu-id="1d2de-160">なお、[Skype for Business から Teams への移行](FAQ-journey.md)に関するよくあるご質問 (FAQ) **は**現在もご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="1d2de-160">By the way, we **do** still have an FAQ for the [Journey from Skype for Business to Microsoft Teams](FAQ-journey.md).</span></span> 
