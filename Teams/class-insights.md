---
title: Teams for Education インサイトへの IT 管理者ガイド
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Teams for Education インサイトへの IT 管理者ガイド。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b63ea1a1a09a55d9a51fb2a110c024960f23f6f4
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803525"
---
# <a name="it-admin-guide-to-insights-in-teams-for-education"></a><span data-ttu-id="be8f6-103">Teams for Education インサイトへの IT 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="be8f6-103">IT Admin Guide to Insights in Teams for Education</span></span>

<span data-ttu-id="be8f6-104">教職員やリーダーは、Microsoft Teams for Education のインサイトを使って、デジタル契約、割り当てのワークロード、成績、コミュニケーションなどに関する分析データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-104">With Insights in Microsoft Teams for Education, educators and leaders can access analytics data about digital engagement, assignment workload, grades, communication and more.</span></span> <span data-ttu-id="be8f6-105">インサイトは、教職員や学生を優先し、プライバシー標準を満たし、かつ所属機関に対する継続的なコンプライアンスを保証する倫理的な原則の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-105">Insights is driven by ethical principles that put educators and students first, meet privacy standards, and ensure continuous compliance for your institution.</span></span>

<span data-ttu-id="be8f6-106">インサイトは、Office 365 Education SKU 番号 A1、A3、A5 でアクティブになっています。</span><span class="sxs-lookup"><span data-stu-id="be8f6-106">Insights is active in Office 365 Education SKUs A1, A3, and A5.</span></span>

> [!NOTE]
> <span data-ttu-id="be8f6-107">教職員の場合、インサイトの使用方法に関する詳細については、「[Microsoft Teams でのインサイトへの教職員用ガイド](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be8f6-107">Educators, learn how to use Insights here: [Educator's guide to Insights in Microsoft Teams](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181).</span></span>

## <a name="use-insights"></a><span data-ttu-id="be8f6-108">インサイトの使用</span><span class="sxs-lookup"><span data-stu-id="be8f6-108">Use Insights</span></span>

### <a name="user-types"></a><span data-ttu-id="be8f6-109">ユーザーの種類</span><span class="sxs-lookup"><span data-stu-id="be8f6-109">User types</span></span>
- <span data-ttu-id="be8f6-110">**学生** は、ライセンスによって識別され、たとえチームの所有者であったとしても、インサイト タブへのアクセスは  _できません_ 。</span><span class="sxs-lookup"><span data-stu-id="be8f6-110">**Students** are identified by their license and _do not have_ access to the Insights tab (even if they are an owner of the team).</span></span> 
- <span data-ttu-id="be8f6-111">**教職者** は教職員用ライセンスで識別されます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-111">**Educators** are identified by faculty licenses.</span></span> <span data-ttu-id="be8f6-112">教職員がインサイト タブで表示されるデータを追加して見ることができるようにするには、教職員用ライセンスを保持し、さらにクラスチームの所有者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="be8f6-112">Educators must have a faculty license and be a class team owner to add and see the data presented in the Insights tab.</span></span> 
- <span data-ttu-id="be8f6-113">**リーダー** も教職員用ライセンスで識別されますが、さらに IT グローバル管理者からインサイト アプリのレポートを表示するための明示的なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="be8f6-113">**Leaders** are also identified by faculty license, but in addition they need explicit permissions from the IT global admin to view the reports in the Insights app.</span></span>
- <span data-ttu-id="be8f6-114">ゲスト アカウントからはインサイトにアクセス _できません_ 。</span><span class="sxs-lookup"><span data-stu-id="be8f6-114">Guest accounts _do not have_ access to Insights.</span></span>

### <a name="entry-points"></a><span data-ttu-id="be8f6-115">エントリ ポイント</span><span class="sxs-lookup"><span data-stu-id="be8f6-115">Entry points</span></span>
<span data-ttu-id="be8f6-116">教職員やリーダーには、インサイトを検出して使用できるさまざまなエントリ ポイントがあります。</span><span class="sxs-lookup"><span data-stu-id="be8f6-116">Educators and leaders have different entry points where they can discover and use Insights.</span></span>

<span data-ttu-id="be8f6-117">**教職員** は、次の 2 つのエントリ ポイントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-117">**Educators** can use these two entry points:</span></span>
- <span data-ttu-id="be8f6-118">[タブ](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181) - 教職員が所有する各クラスのインサイトは、上部のナビゲーション メニューから追加されたタブで使用できます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-118">[Tabs](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181) - insights for each class they own are available in a tab added from the top navigation menu.</span></span> <span data-ttu-id="be8f6-119">インサイトでは、クラスチーム内のすべてのチャネルのアクティビティ データが表示されますが、パブリック チャネルにはタブとしてのみ追加できます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-119">Insights will surface activity data from all channels within a class team, but can only be added as a tab to public channels.</span></span> <span data-ttu-id="be8f6-120">このタブには、所有者以外のクラスチーム内のすべてのユーザーのアクティビティが反映されます (チームの所有者ではない教職員も含む)。</span><span class="sxs-lookup"><span data-stu-id="be8f6-120">The tab reflects activity from everyone in the class team who isn’t an owner (including educators who aren’t owners of the team).</span></span>
- <span data-ttu-id="be8f6-121">[個人用アプリ](https://support.microsoft.com/article/747fd8d9-00b0-43e6-bacc-a1bf030b1867) - すべてのアクティブなクラスの概要は、左側の Teams アプリ バーから入手できます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-121">[Personal app](https://support.microsoft.com/article/747fd8d9-00b0-43e6-bacc-a1bf030b1867) - an overview of all their active classes is available from the left Teams app bar.</span></span>

<span data-ttu-id="be8f6-122">**リーダー** は、[個人用アプリ](https://support.microsoft.com/article/8738d1b1-4e1c-49bd-9e8d-b5292474c347)としてインサイトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-122">**Leaders** can use Insights as a [personal app](https://support.microsoft.com/article/8738d1b1-4e1c-49bd-9e8d-b5292474c347).</span></span>

### <a name="manage-setup-policy"></a><span data-ttu-id="be8f6-123">設定ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="be8f6-123">Manage setup policy</span></span>
<span data-ttu-id="be8f6-124">管理者として、教職員やリーダーが Teams の使用を開始する場合に[アプリ設定ポリシー](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies)を使用して既定でインサイトをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-124">As an admin, you can use [app setup policy](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies) to install Insights by default for your educators and leaders when they start Teams.</span></span>
<span data-ttu-id="be8f6-125">このポリシーを使用すると、Teams をカスタマイズして、インサイトを強調表示したり、アプリ バーにインサイトをピン留めしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-125">With that policy you can customize Teams to highlight Insights, and pin it for them in the apps bar.</span></span>

> [!TIP]
> <span data-ttu-id="be8f6-126">教育機関向け Teams ポリシーおよびポリシー パッケージの詳細については、「[教育機関向け Teams ポリシーおよびポリシー パッケージ](https://docs.microsoft.com/microsoftteams/policy-packages-edu)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be8f6-126">Read [Teams Policies and Policy Packages for Education](https://docs.microsoft.com/microsoftteams/policy-packages-edu) about Teams policies and policy packages for education.</span></span>



## <a name="compliance"></a><span data-ttu-id="be8f6-127">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="be8f6-127">Compliance</span></span>

<span data-ttu-id="be8f6-128">インサイトは業界をリードするコンプライアンス コミットメントを提供しており、Office 365 コンプライアンス フレームワーク内の Tier-C サービスとして分類されています。</span><span class="sxs-lookup"><span data-stu-id="be8f6-128">Insights has industry-leading compliance commitments, and is classified as a Tier-C service within the Office 365 Compliance Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="be8f6-129">[Microsoft トラストセンターの](https://www.microsoft.com/trust-center) にアクセスして、Microsoft でデータを保護している方法をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="be8f6-129">Visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center) to learn more about how Microsoft protects your data.</span></span>

## <a name="privacy"></a><span data-ttu-id="be8f6-130">プライバシー</span><span class="sxs-lookup"><span data-stu-id="be8f6-130">Privacy</span></span>

<span data-ttu-id="be8f6-131">インサイトで収集、表示される情報は、学生、子供、その他同様のプライバシーに関する規定に対して、GDPR、家庭教育の権利とプライバシーに関する法律 （FERPA） などを含む 90 以上の規制および業界標準を満たしています。</span><span class="sxs-lookup"><span data-stu-id="be8f6-131">The information collected and shown through Insights does meets more than 90 regulatory and industry standards, including GDPR and the Family Education Rights and Privacy Act (FERPA) for the security of students and children and other, similar, privacy-oriented regulations.</span></span> <span data-ttu-id="be8f6-132">学生ごとに収集された情報がクラスのコンテキストのみで使用されることを IT 管理者が知るのは重要であり、それにより教職員とリーダーが学生の振る舞いを決定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="be8f6-132">It's important for IT admins to know that the information collected on a per-student basis is intended to be used in a class context only, to allow educators and leaders to determine students' behavior.</span></span> <span data-ttu-id="be8f6-133">この情報は、クラス会議出席やメッセージ投稿、さらに級友への返信や割り当て作業、ファイル編集など、有益な学習アクティビティに対して収集されます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-133">The information is collected for meaningful learning activities, such as class meetings attendance, posting messages, responding to classmates' posts, working on assignments, editing files, and more.</span></span> <span data-ttu-id="be8f6-134">たとえば、個人チャットや Teams へのログインに関する情報などを表示することはありません。</span><span class="sxs-lookup"><span data-stu-id="be8f6-134">We don't show information about private chat or a Teams login, as an example.</span></span>

<span data-ttu-id="be8f6-135">目標は、教職員が従事を理解し、学生の学習をわかりやすくすることです。</span><span class="sxs-lookup"><span data-stu-id="be8f6-135">Our goal is to help educators to understand engagement and shine a spotlight on student learning.</span></span> <span data-ttu-id="be8f6-136">これらのクラス活動は生徒レベルのアクションに絞り込むことができますが、これらのアクションには Microsoft Teams が割り当てる正または負の値はなく、基準に基づく個々の学生の判断識別もありません。</span><span class="sxs-lookup"><span data-stu-id="be8f6-136">While these class activities can be focused down to actions at the student level, there is no positive or negative value assigned to these actions by Microsoft Teams, and there is no judgmental identification of individual students based on criteria.</span></span> <span data-ttu-id="be8f6-137">インサイトの情報は、たとえば、学生が特定の期間中にツールでアクティブになっていない場合や、先週のすべての課題を時間内に完了したことを教職員に知らせるものです。</span><span class="sxs-lookup"><span data-stu-id="be8f6-137">The information in  Insights informs an educator that, for example, a student has not been active in the tool during a certain period in time, or has completed all their assignments last week on-time.</span></span> <span data-ttu-id="be8f6-138">学生、学生の家族、または保護者と連絡を取り合って、検知されたアクティビティの原因を特定したり、アクティビティがなかったことへの原因を特定するのは、教職員の責任にとどまります。</span><span class="sxs-lookup"><span data-stu-id="be8f6-138">It remains the responsibility of the educator to interact with the student and that student's family or guardians to determine the underlying reason for any activity or inactivity detected.</span></span>

## <a name="data-collection"></a><span data-ttu-id="be8f6-139">データ収集</span><span class="sxs-lookup"><span data-stu-id="be8f6-139">Data collection</span></span>

- <span data-ttu-id="be8f6-140">テナントに対して Education Analytics がオンになっている場合に、インサイトへのデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="be8f6-140">We collect data for Insights when Education Analytics is turned on for the tenant.</span></span> <span data-ttu-id="be8f6-141">教育用および学習用に役立つインサイトを表示できるように、Teams のアクティビティからデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="be8f6-141">The data is collected from Teams activity in order to surface actionable insights for teaching and learning.</span></span>
- <span data-ttu-id="be8f6-142">ゲストのデータをインサイトのために収集することは _できません_ 。</span><span class="sxs-lookup"><span data-stu-id="be8f6-142">Guests data _does not_ collected for Insights.</span></span>
- <span data-ttu-id="be8f6-143">規定では、Education Analytics は **オン** になっています。</span><span class="sxs-lookup"><span data-stu-id="be8f6-143">By default, Education Analytics is turned **On** .</span></span>

<span data-ttu-id="be8f6-144">現在、このデータを、クラスチームの生徒および教職員のアクティビティの次の領域から取得しています。</span><span class="sxs-lookup"><span data-stu-id="be8f6-144">Currently, this data is pulled from the following areas of student and educator activity in class teams:</span></span>

|<span data-ttu-id="be8f6-145">Teams コンポーネント</span><span class="sxs-lookup"><span data-stu-id="be8f6-145">Teams component</span></span>  |<span data-ttu-id="be8f6-146">収集データ</span><span class="sxs-lookup"><span data-stu-id="be8f6-146">Data collected</span></span>  |
|-----------------|------------------------|------------------------|
|<span data-ttu-id="be8f6-147">課題</span><span class="sxs-lookup"><span data-stu-id="be8f6-147">Assignments</span></span> |<span data-ttu-id="be8f6-148">課題を開いて調整してから評価</span><span class="sxs-lookup"><span data-stu-id="be8f6-148">Opening, turning in, and grade on assignments.</span></span> |
|<span data-ttu-id="be8f6-149">チャネル契約</span><span class="sxs-lookup"><span data-stu-id="be8f6-149">Channel engagement</span></span> |<span data-ttu-id="be8f6-150">チャネルに移動して投稿を作成したり、投稿に返信し、高く評価したりできます (チャットコンテンツを含まない)。</span><span class="sxs-lookup"><span data-stu-id="be8f6-150">Visiting a channel, creating a post, replying to and liking a post (not including chat content).</span></span> |
|<span data-ttu-id="be8f6-151">ファイル</span><span class="sxs-lookup"><span data-stu-id="be8f6-151">Files</span></span> |<span data-ttu-id="be8f6-152">ファイルのアップロード、ダウンロード、アクセス、変更、コメント添付、共有 (ファイルコンテンツを含まない)。</span><span class="sxs-lookup"><span data-stu-id="be8f6-152">Uploading, downloading, accessing, modifying, commenting on, and sharing a file (not including file content).</span></span> |
|<span data-ttu-id="be8f6-153">会議</span><span class="sxs-lookup"><span data-stu-id="be8f6-153">Meetings</span></span> |<span data-ttu-id="be8f6-154">出席 (会議コンテンツを含まない)。</span><span class="sxs-lookup"><span data-stu-id="be8f6-154">Attendance (not including meeting content).</span></span> |

## <a name="data-location"></a><span data-ttu-id="be8f6-155">データの場所</span><span class="sxs-lookup"><span data-stu-id="be8f6-155">Data location</span></span>

<span data-ttu-id="be8f6-156">欧州のテナントのインサイト データは、欧州にあるサーバーに格納されています。</span><span class="sxs-lookup"><span data-stu-id="be8f6-156">Insights data for European-based tenants is stored on servers in Europe.</span></span> <span data-ttu-id="be8f6-157">米国のテナントのデータは、米国にあるサーバーに格納されています。</span><span class="sxs-lookup"><span data-stu-id="be8f6-157">Data for US-based tenants is stored on servers in the United States.</span></span> <span data-ttu-id="be8f6-158">インサイトを使用していて、Office 365 テナントが欧州の地域または米国以外の地域に存在する場合には、データはその適切な地域に格納されます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-158">If you use Insights and your Office 365 tenant is in a region outside of Europe or the United States, your data will be stored in the appropriate geographic region.</span></span>

## <a name="performance-and-reliability"></a><span data-ttu-id="be8f6-159">パフォーマンスと信頼性</span><span class="sxs-lookup"><span data-stu-id="be8f6-159">Performance and reliability</span></span>

<span data-ttu-id="be8f6-160">インサイトは、最適なパフォーマンスと信頼性を実現して Teams のアクティビティから収集される大量のデータを処理するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="be8f6-160">Insights is designed to handle a high volume of data collected from Teams activity with optimal performance and reliability.</span></span>

<span data-ttu-id="be8f6-161">[インサイト] タブが Teams にインストールされているかどうかに関係なく、データ収集のプロセスは別のサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-161">The data collection process takes place on separate servers regardless of the installation of the Insights tab in Teams.</span></span> <span data-ttu-id="be8f6-162">Teams の機能の残りを使用しているので、[インサイト] タブや個人用アプリは、教職員と学生用のアプリケーションのパフォーマンスやネットワーク帯域幅には影響しません。</span><span class="sxs-lookup"><span data-stu-id="be8f6-162">The Insights tab or personal app does not affect application performance or network bandwidth for educators and students using the rest of Teams functionality.</span></span>

> [!TIP]
> <span data-ttu-id="be8f6-163">低帯域幅で教育機関向け Teams を使用する場合の詳細については、「[低帯域幅の状況で教育機関向け Teams を使用する場合のヘルプ](edu-remote-low-bandwidth.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be8f6-163">Read [Help for low-bandwidth situations for Teams for EDU](edu-remote-low-bandwidth.md) about using Teams for Education when bandwidth is low.</span></span>

## <a name="how-to-delete-your-data"></a><span data-ttu-id="be8f6-164">データを削除する方法</span><span class="sxs-lookup"><span data-stu-id="be8f6-164">How to delete your data</span></span>

<span data-ttu-id="be8f6-165">教育用サービスでは、クラスチームのコンテキストで実行された学生と教職員のアクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="be8f6-165">Education services stores student and educator actions performed in the context of a class team.</span></span> <span data-ttu-id="be8f6-166">このデータは、まとまったデータセットと見なされるため、学生または教職員のユーザーアカウントが組織から削除されても、サービスから自動的に削除されません。</span><span class="sxs-lookup"><span data-stu-id="be8f6-166">This data is considered a co-mingled data set and therefore isn't automatically deleted from the service once student or educator user accounts are deleted from your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="be8f6-167">データを削除すると、時間の経過とともにクラスチームの契約を分析するインサイトの機能に悪影響がでます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-167">Deleting data has a negative impact on Insights' ability to analyze class team engagement over time.</span></span>

- <span data-ttu-id="be8f6-168">[https://edusupport.microsoft.com/support](https://edusupport.microsoft.com/support) でサポートチケットを開きます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-168">Open a support ticket at [https://edusupport.microsoft.com/support](https://edusupport.microsoft.com/support).</span></span> <span data-ttu-id="be8f6-169">サポートチケットには、GDPR 削除 DSR 操作の要求を明確に記載し、削除するユーザーオブジェクト ID を入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="be8f6-169">The support ticket must state clearly the request for a GDPR Delete DSR operation and contain the user object ID to be deleted.</span></span> <span data-ttu-id="be8f6-170">削除するデータセットまたは時間帯を制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="be8f6-170">There is no ability to limit the data set or time window of the deletion.</span></span>
- <span data-ttu-id="be8f6-171">ファイルが済むと、サポートチケットは、コンプライアンスの最小限のポリシーを満たすために、1週間キュー内で待機します。</span><span class="sxs-lookup"><span data-stu-id="be8f6-171">Once filed, the support ticket waits in the queue for one week in order to meet compliance minimal retention policy.</span></span> <span data-ttu-id="be8f6-172">この間、操作をキャンセルすることができます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-172">You have the opportunity to cancel the operation during this time.</span></span>
- <span data-ttu-id="be8f6-173">1週間後に、Education Analytics チームが、ユーザー ID に関連するすべてのデータをサービスから削除する処置を行います。</span><span class="sxs-lookup"><span data-stu-id="be8f6-173">After one week, the Education Analytics team takes action to ensure all data related to the user ID is deleted from the service.</span></span> <span data-ttu-id="be8f6-174">Microsoft サポートが ICM チケットを監視し、28 日以内に削除プロセスが完了したことを通知します。</span><span class="sxs-lookup"><span data-stu-id="be8f6-174">Microsoft support monitors the ICM ticket and will notify you once the deletion process is complete, in no more than 28 days.</span></span>

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a><span data-ttu-id="be8f6-175">School Data Sync (SDS) を使用してインサイトの電源をスウィッチ</span><span class="sxs-lookup"><span data-stu-id="be8f6-175">Turn Insights off and on using School Data Sync (SDS)</span></span>

<span data-ttu-id="be8f6-176">School Data Sync (SDS) は、Student Information System (SIS) データをインポートして、Office 365 と同期するプロセスを自動化するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-176">School Data Sync (SDS) helps to automate the process of importing and synchronizing Student Information System (SIS) data with Office 365.</span></span>

<span data-ttu-id="be8f6-177">インサイトを使用するときに SDS を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="be8f6-177">The use of Insights does not require the use of SDS.</span></span> <span data-ttu-id="be8f6-178">ただし、SDS 管理センター ( **設定** > **Education Analytics 管理** の順に移動) でトグルをオフにして、いつでも Education Analytics からオプトアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-178">However, you may choose to opt out from Education Analytics at any time by turning off the toggle in the SDS Admin Center under **Settings** > **Manage Education Analytics** .</span></span>

:::image type="content" source="media/class-insights-on-off.png" alt-text="インサイトを有効または無効にできるスイッチ。":::

<span data-ttu-id="be8f6-180">既定では、Education Analytics とインサイトはオンになっています。</span><span class="sxs-lookup"><span data-stu-id="be8f6-180">By default, Education Analytics, and therefore Insights, is turned on.</span></span> <span data-ttu-id="be8f6-181">Analytics からオプトアウトすると、[インサイト] タブ用に収集されたすべてのデータが削除されます。Analytics を再び有効にすると、有効になった時間からデータの収集が再開されます。</span><span class="sxs-lookup"><span data-stu-id="be8f6-181">When you opt out of Analytics, we delete all data collected for the Insights tab. Turn Analytics back on, and we start collecting data from the time it's re-enabled.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be8f6-182">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="be8f6-182">Additional resources</span></span>
- [<span data-ttu-id="be8f6-183">インサイトへの教職員用ガイド</span><span class="sxs-lookup"><span data-stu-id="be8f6-183">Educator's guide to Insights</span></span>](https://support.microsoft.com/office/27b56255-90c0-47aa-bac3-1c9f50157181)
