---
title: Microsoft Teams の概要
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Microsoft Teams とそのインフラストラクチャについて、および Office 365 と組み合わせた Teams の使用について説明します。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb291c8bd338fa88d5d9b5788413c5e687fc0864
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883780"
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="6c3dd-103">Microsoft Teams の概要</span><span class="sxs-lookup"><span data-stu-id="6c3dd-103">Overview of Microsoft Teams</span></span>
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


<span data-ttu-id="6c3dd-p101">Microsoft Teams は Office 365 のすべてをまとめ、チームワークを遂行する上でチャットベースのハブをもたらし、よりオープンで、スムーズで、デジタルな環境を創り出す機会をお客様に提供します。Microsoft Teams は、Office 365 グループによって作られた既存の Microsoft テクノロジーを基に作られています。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-p101">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment. Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="6c3dd-106">革新的な発想により、Teams は、Azure Active Directory (Azure AD) に保存された ID を利用し、Office 365 のその他のサービスと統合して、作成されるチームごとに SharePoint オンライン サイトと Exchange Online グループ メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-106">Out of the box, Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="6c3dd-107">ビジネスやコンシューマー電子メール アカウントを Outlook、Gmail、またはその他のユーザーなど、すべてのユーザーは、チームにゲストとして参加できます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-107">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span> <span data-ttu-id="6c3dd-108">来園者は Azure AD 内で安全に管理できるし、同じコンプライアンスと監査の保護として、Office 365 の残りの部分は、来園者はチームで対応します。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-108">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span> <span data-ttu-id="6c3dd-109">管理者が一元的に、Office 365 環境内での来園者の参加を管理し簡単に表示、追加、またはホスト テナントへのゲスト アクセスを無効します。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-109">Admins can centrally manage how guests participate within their Office 365 environment and easily view, add, or revoke a guest’s access to the host tenant.</span></span>

<span data-ttu-id="6c3dd-110">Teams では常設チャットの機能や通話と会議が利用でき、その強力な拡張性に加えて Office 365 の他のコンポーネントに容易にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-110">Teams provides a persistent chat capability, calling and meetings, easy access to other components of Office 365 as well as a robust extensibility story.</span></span>  <span data-ttu-id="6c3dd-111">これにより、大企業から小規模な組織にいたるまで、その中にいるすべてのユーザーにとって最適なチームワークのハブを構成します。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-111">This provides a hub for teamwork that is appropriate for enterprise companies, small organizations and everyone in between.</span></span>  

<span data-ttu-id="6c3dd-112">Teams の機能を拡張するために、コネクタ、タブ、およびボットを[アプリ](https://go.microsoft.com/fwlink/?linkid=854629)として利用できます。これらによって、外部の情報、コンテンツ、およびインテリジェントなボットとの対話が Teams にもたらされます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-112">To extend Teams capabilities, use Connectors, Tabs, and Bots - available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629), to bring external information, content, and intelligent bot interactions to Teams.</span></span>  

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="6c3dd-113">Microsoft Teams のインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="6c3dd-113">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="6c3dd-114">Teams は、Office 365 グループによって作られた既存の Microsoft テクノロジーを基にしています。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-114">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="6c3dd-115">Microsoft のクラウドによって、組織はそのコラボレーションの一部として Microsoft Teams を利用する際に優れたパフォーマンスと信頼性を期待することができます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-115">Powered by the Microsoft cloud, organizations can expect excellent performance and reliability when leveraging Teams as part of their collaboration story.</span></span>

<span data-ttu-id="6c3dd-116">革新的な発想により、Teams で作成されたチームは、Office 365 グループ、(ドキュメント ライブラリを備えた) SharePoint Online サイト、Teams によって会議の招待などの情報を保存するために使用される Exchange Online グループ メールボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-116">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="6c3dd-117">チームは既存の Office 365 グループを使用して作成でき、既存のグループ メンバーシップと、SharePoint Online および Exchange Online に保存されたコンテンツを Teams に移行することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-117">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="6c3dd-118">非公式なリアルタイムの会話を行う場所、永続的なチャットの掲示板のチームも、チームの機能を補完するために、通話や会議、次世代クラウド ・ ベースのインフラストラクチャも Skype の Skype を使用する上に構築された経験を提供します。ビジネスです。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-118">To complement the Teams capability as a persistent chat board where informal, real-time conversations take place, Teams also provides a calling and meeting experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="6c3dd-119">これらの技術投資には、Azure ベースのクラウド サービスを利用したメディア処理とシグナリング、H.264 ビデオ コーデック、SILK および Opus オーディオ コーデック、ネットワークの回復力、テレメトリ、および品質診断が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-119">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="6c3dd-120">Office 365 グループは Azure Active Directory (Azure AD) に保存された ID を利用するため、多要素認証 (MFA) のサポートなどの Azure AD におけるすべての認証および承認機能は、Teams ですぐに使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-120">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), are readily available for use by Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="6c3dd-121">顧客からのフィードバックに基づいて、マイクロソフトのチームでチームの作成の結果として生成された新しい Office 365 のグループされなく Outlook でデフォルトで表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-121">Based on customer feedback, new Office 365 Groups generated as a result of creating a team in Microsoft Teams will no longer show in Outlook by default.</span></span> <span data-ttu-id="6c3dd-122">Outlook でこれらのグループを示すは、既存の動作を継続するお客様の場合は、Outlook の環境のグループを有効にすることができる Exchange のオンラインの PowerShell コマンドレットが提供されます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-122">For customers that want to continue with the existing behavior of showing these groups in Outlook, an Exchange Online PowerShell cmdlet will be provided which can enable the group for the Outlook experience.</span></span> <span data-ttu-id="6c3dd-123">Outlook で作成し、後で有効になっているチームのグループは、Outlook とチームの両方に表示する続けます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-123">Groups created through Outlook and then later enabled for Teams will continue to show in both Outlook and Teams.</span></span> <span data-ttu-id="6c3dd-124">この更新プログラムを段階的には数か月の後で Outlook とチーム全体がロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-124">This update will gradually roll out across Outlook and Teams in the coming months.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="6c3dd-125">Microsoft Teams と Office 365</span><span class="sxs-lookup"><span data-stu-id="6c3dd-125">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="6c3dd-126">それぞれのグループにおいて、機能的な役割やワークスタイルに基づくさまざまなニーズが生じています。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-126">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="6c3dd-127">Office 365 は、あらゆるグループの固有のワークスタイルに対応するよう設計されており、次のような専用の統合アプリケーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-127">Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, including:</span></span>

-   <span data-ttu-id="6c3dd-128">エンタープライズグレードの電子メールに対応した Outlook。現在はグループ機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-128">Outlook for enterprise-grade email, now with groups functionality</span></span>

-   <span data-ttu-id="6c3dd-129">サイトおよびポータル用 SharePoint、インテリジェント コンテンツ サービス、ビジネス プロセスの自動化とエンタープライズ検索。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-129">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search</span></span>

-   <span data-ttu-id="6c3dd-130">会社規模の接続を推進する Yammer</span><span class="sxs-lookup"><span data-stu-id="6c3dd-130">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="6c3dd-131">エンタープライズ VoIP およびビデオの法人顧客向けバックボーンとしての Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-131">Skype for Business as the backbone for enterprise voice and video</span></span>

-   <span data-ttu-id="6c3dd-132">現在は、Office 365 の新しいチャットベースのワークスペースである Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-132">And now, Microsoft Teams, the new chat-based workspace in Office 365</span></span>

<span data-ttu-id="6c3dd-p109">Office 365 の各アプリケーションの一般的な使用例を示します。詳細な使用方法については、[FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630) にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-p109">Here are common use cases for each application in Office 365. For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![Microsoft Teams アイコン。](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="6c3dd-136">同じグループのメンバーとのリアルタイムでのコラボレーションを望んでいるユーザーおよびチームにより利用されます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-136">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="6c3dd-137">プロジェクトに関する迅速な反復を行いながら、ファイルを共有し、共有された成果物に関してコラボレーションを行うことを望んでいるチームをサポートします。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-137">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="6c3dd-138">プランナー、電源の BI、GitHub など) などのワークスペースにさまざまなツールを接続することができます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-138">Allows users to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![Microsoft Outlook アイコン。](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="6c3dd-140">使い慣れた電子メール環境や、より丁寧で真面目な方法で、共同作業を行うことを希望するユーザーにより利用されます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-140">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="6c3dd-141">電子メールの使用が必要な固有のビジネス プロセスを提供して、組織の内外の文書や情報を伝達します。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-141">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="6c3dd-142">周辺のワークグループまたは組織の外側にいるユーザーと通信したり接続します。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-142">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![Yammer アイコン。](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="6c3dd-144">組織全体のユーザーと接続して、プラクティスのコミュニティを中心にまとまり、ベスト プラクティスを共有することをサポートするために利用されます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-144">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="6c3dd-145">オープンで透明性の高いフィードベースのプラットフォームを通じて、部門連係ワークフローを改善します</span><span class="sxs-lookup"><span data-stu-id="6c3dd-145">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="6c3dd-146">リーダーとより広範な従業員ベースの間の双方向の会話により、幹部従業員のエンゲージメントを促進します</span><span class="sxs-lookup"><span data-stu-id="6c3dd-146">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="6c3dd-147">第一線の労働力を鼓舞して、知識と専門性を共有、享受します</span><span class="sxs-lookup"><span data-stu-id="6c3dd-147">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![Skype for Business アイコン。](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="6c3dd-149">お客様/パートナーとの内部および外部向けのリアルタイムの通信、コラボレーションに利用されます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-149">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="6c3dd-150">オーディオ、ビデオ、および大小のチーム (最大 10,000 人の参加者を収容する市役所など) を含むコンテンツを伴う会議を提供します。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-150">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="6c3dd-151">法人向けのテレフォニー機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-151">Offers enterprise telephony functionality.</span></span>


![Microsoft SharePoint アイコン。](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="6c3dd-153">サイトおよびポータル (会社ニュースとお知らせ、検索、およびドキュメントのコラボレーションなど) で利用されます。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-153">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="6c3dd-154">Microsoft Flow と PowerApps を統合することで、ドキュメント ライブラリと情報のリストに対してビジネス プロセスの自動化を実装します。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-154">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="6c3dd-155">ファイルの保存、チームのニュース、ページ、リストなどに関して、すべての Microsoft Team に対して自動的にプロビジョニングされる強力な SharePoint チームサイト。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-155">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="6c3dd-156">[Teams との SharePoint Online と OneDrive for Business の連携](SharePoint-OneDrive-interact.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6c3dd-156">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>

## <a name="teams-known-issuesknown-issuesmd"></a>[<span data-ttu-id="6c3dd-157">Teams の既知の問題</span><span class="sxs-lookup"><span data-stu-id="6c3dd-157">Teams known issues</span></span>](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[<span data-ttu-id="6c3dd-158">Teams クライアントのリリース ノート</span><span class="sxs-lookup"><span data-stu-id="6c3dd-158">Teams client release notes</span></span>](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)


