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
ms.openlocfilehash: e00bfc5606e23460255e3ee4748010843415eb1b
ms.sourcegitcommit: 92fdfad4564eb27190cd88f109bded2b95d473ee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2020
ms.locfileid: "47408233"
---
# <a name="it-admin-guide-to-insights-in-teams-for-education"></a><span data-ttu-id="c8b16-103">Teams for Education インサイトへの IT 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="c8b16-103">IT Admin Guide to Insights in Teams for Education</span></span>

<span data-ttu-id="c8b16-104">教職員やリーダーは、Microsoft Teams for Education のインサイトを使って、デジタル契約、割り当てのワークロード、成績、コミュニケーションなどに関する分析データにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-104">With Insights in Microsoft Teams for Education, educators and leaders can access analytics data about digital engagement, assignment workload, grades, communication and more.</span></span>

<span data-ttu-id="c8b16-105">インサイトは、Office 365 Education SKU 番号 A1、A3、A5 でアクティブになっています。</span><span class="sxs-lookup"><span data-stu-id="c8b16-105">Insights is active in Office 365 Education SKUs A1, A3, and A5.</span></span>

> [!NOTE]
> <span data-ttu-id="c8b16-106">教職員は、[ここで](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181)インサイトの使用方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="c8b16-106">Educators, learn how to use Insights [here](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181).</span></span>

## <a name="permissions"></a><span data-ttu-id="c8b16-107">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="c8b16-107">Permissions</span></span>

### <a name="user-types"></a><span data-ttu-id="c8b16-108">ユーザーの種類</span><span class="sxs-lookup"><span data-stu-id="c8b16-108">User types</span></span>
- <span data-ttu-id="c8b16-109">**学生**は、ライセンスによって識別され、たとえチームの所有者であったとしても、インサイト タブへのアクセスは _できません_。</span><span class="sxs-lookup"><span data-stu-id="c8b16-109">**Students** are identified by their license and _do not have_ access to the Insights tab (even if they are an owner of the team).</span></span> 
- <span data-ttu-id="c8b16-110">**教職者**は教職員用ライセンスで識別されます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-110">**Educators** are identified by faculty licenses.</span></span> <span data-ttu-id="c8b16-111">教職員がインサイト タブで表示されるデータを追加して見ることができるようにするには、教職員用ライセンスを保持し、さらにクラスチームの所有者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b16-111">Educators must have a faculty license and be a class team owner to add and see the data presented in the Insights tab.</span></span> 
- <span data-ttu-id="c8b16-112">**リーダー**も教職員用ライセンスで識別されますが、さらに IT グローバル管理者からインサイト アプリのレポートを表示するための明示的なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="c8b16-112">**Leaders** are also identified by faculty license, but in addition they need explicit permissions from the IT global admin to view the reports in the Insights app.</span></span>
- <span data-ttu-id="c8b16-113">ゲスト アカウントからはインサイトにアクセス_できません_。</span><span class="sxs-lookup"><span data-stu-id="c8b16-113">Guest accounts _do not have_ access to Insights.</span></span>

### <a name="permission-levels"></a><span data-ttu-id="c8b16-114">アクセス許可レベル</span><span class="sxs-lookup"><span data-stu-id="c8b16-114">Permission levels</span></span>
<span data-ttu-id="c8b16-115">教職員やリーダーには、次のように異なるアクセス許可レベルとロジックがあります。</span><span class="sxs-lookup"><span data-stu-id="c8b16-115">Educators and leaders have different permission levels and logic:</span></span>
- <span data-ttu-id="c8b16-116">**教職員**は、Teams アプリ バーの [アプリ] に移動して [インサイト] を検索することで、クラスチーム内のパブリック チャネルにインサイト アプリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-116">**Educators** can add the Insights app to a public channel within a class team by navigating to Apps in the Teams app bar and searching for Insights.</span></span> <span data-ttu-id="c8b16-117">このタブには、 所有者以外のクラスチーム内のすべてのユーザーのアクティビティが反映されます (チームの所有者ではない教職員も含む)。</span><span class="sxs-lookup"><span data-stu-id="c8b16-117">The tab reflects activity from everyone in the class team who isn’t an owner (including educators who aren’t owners of the team).</span></span> 
- <span data-ttu-id="c8b16-118">**リーダー**は、Teams アプリ バーの[アプリ] に移動して [インサイト] を検索することで、インサイト アプリを (Teams の左側メニューに表示されている) 個人用アプリとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-118">**Leaders** can add the Insights app as a personal app (appears on Teams left menu) by navigating to Apps in the Teams app bar and searching for Insights.</span></span> 

## <a name="compliance"></a><span data-ttu-id="c8b16-119">コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="c8b16-119">Compliance</span></span>

<span data-ttu-id="c8b16-120">インサイトは業界をリードするコンプライアンス コミットメントを提供しており、Office 365 コンプライアンス フレームワーク内の Tier-C サービスとして分類されています。</span><span class="sxs-lookup"><span data-stu-id="c8b16-120">Insights has industry-leading compliance commitments, and is classified as a Tier-C service within the Office 365 Compliance Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="c8b16-121">[Microsoft トラストセンターの](https://www.microsoft.com/trust-center) にアクセスして、Microsoft でデータを保護している方法をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="c8b16-121">Visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center) to learn more about how Microsoft protects your data.</span></span>

## <a name="privacy"></a><span data-ttu-id="c8b16-122">プライバシー</span><span class="sxs-lookup"><span data-stu-id="c8b16-122">Privacy</span></span>

<span data-ttu-id="c8b16-123">インサイトで収集、表示される情報は、学生、子供、その他同様のプライバシーに関する規定に対して、GDPR、家庭教育の権利とプライバシーに関する法律 （FERPA） などを含む 90 以上の規制および業界標準を満たしています。</span><span class="sxs-lookup"><span data-stu-id="c8b16-123">The information collected and shown through Insights does meets more than 90 regulatory and industry standards, including GDPR and the Family Education Rights and Privacy Act (FERPA) for the security of students and children and other, similar, privacy-oriented regulations.</span></span> <span data-ttu-id="c8b16-124">学生ごとに収集された情報がクラスのコンテキストのみで使用されることを IT 管理者が知るのは重要であり、それにより教職員とリーダーが学生の振る舞いを決定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c8b16-124">It's important for IT admins to know that the information collected on a per-student basis is intended to be used in a class context only, to allow educators and leaders to determine students' behavior.</span></span> <span data-ttu-id="c8b16-125">この情報は、クラス会議出席やメッセージ投稿、さらに級友への返信や割り当て作業、ファイル編集など、有益な学習アクティビティに対して収集されます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-125">The information is collected for meaningful learning activities, such as class meetings attendance, posting messages, responding to classmates' posts, working on assignments, editing files, and more.</span></span> <span data-ttu-id="c8b16-126">たとえば、個人チャットや Teams へのログインに関する情報などを表示することはありません。</span><span class="sxs-lookup"><span data-stu-id="c8b16-126">We don't show information about private chat or a Teams login, as an example.</span></span>

<span data-ttu-id="c8b16-127">目標は、教職員が従事を理解し、学生の学習をわかりやすくすることです。</span><span class="sxs-lookup"><span data-stu-id="c8b16-127">Our goal is to help educators to understand engagement and shine a spotlight on student learning.</span></span> <span data-ttu-id="c8b16-128">これらのクラス活動は生徒レベルのアクションに絞り込むことができますが、これらのアクションには Microsoft Teams が割り当てる正または負の値はなく、基準に基づく個々の学生の判断識別もありません。</span><span class="sxs-lookup"><span data-stu-id="c8b16-128">While these class activities can be focused down to actions at the student level, there is no positive or negative value assigned to these actions by Microsoft Teams, and there is no judgmental identification of individual students based on criteria.</span></span> <span data-ttu-id="c8b16-129">インサイトの情報は、たとえば、学生が特定の期間中にツールでアクティブになっていない場合や、先週のすべての課題を時間内に完了したことを教職員に知らせるものです。</span><span class="sxs-lookup"><span data-stu-id="c8b16-129">The information in  Insights informs an educator that, for example, a student has not been active in the tool during a certain period in time, or has completed all their assignments last week on-time.</span></span> <span data-ttu-id="c8b16-130">学生、学生の家族、または保護者と連絡を取り合って、検知されたアクティビティの原因を特定したり、アクティビティがなかったことへの原因を特定するのは、教職員の責任にとどまります。</span><span class="sxs-lookup"><span data-stu-id="c8b16-130">It remains the responsibility of the educator to interact with the student and that student's family or guardians to determine the underlying reason for any activity or inactivity detected.</span></span>

## <a name="data-collection"></a><span data-ttu-id="c8b16-131">データ収集</span><span class="sxs-lookup"><span data-stu-id="c8b16-131">Data collection</span></span>

- <span data-ttu-id="c8b16-132">テナントに対して Education Analytics がオンになっている場合に、インサイトへのデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="c8b16-132">We collect data for Insights when Education Analytics is turned on for the tenant.</span></span> <span data-ttu-id="c8b16-133">教育用および学習用に役立つインサイトを表示できるように、Teams のアクティビティからデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="c8b16-133">The data is collected from Teams activity in order to surface actionable insights for teaching and learning.</span></span>
- <span data-ttu-id="c8b16-134">ゲストのデータをインサイトのために収集することは_できません_。</span><span class="sxs-lookup"><span data-stu-id="c8b16-134">Guests data _does not_ collected for Insights.</span></span>
- <span data-ttu-id="c8b16-135">規定では、Education Analytics は **オン**になっています。</span><span class="sxs-lookup"><span data-stu-id="c8b16-135">By default, Education Analytics is turned **On**.</span></span>

<span data-ttu-id="c8b16-136">現在、このデータを、クラスチームの生徒および教職員のアクティビティの次の領域から取得しています。</span><span class="sxs-lookup"><span data-stu-id="c8b16-136">Currently, this data is pulled from the following areas of student and educator activity in class teams:</span></span>

|<span data-ttu-id="c8b16-137">Teams コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c8b16-137">Teams component</span></span>  |<span data-ttu-id="c8b16-138">収集データ</span><span class="sxs-lookup"><span data-stu-id="c8b16-138">Data collected</span></span>  |
|-----------------|------------------------|------------------------|
|<span data-ttu-id="c8b16-139">課題</span><span class="sxs-lookup"><span data-stu-id="c8b16-139">Assignments</span></span> |<span data-ttu-id="c8b16-140">課題を開いて調整してから評価</span><span class="sxs-lookup"><span data-stu-id="c8b16-140">Opening, turning in, and grade on assignments.</span></span> |
|<span data-ttu-id="c8b16-141">チャネル契約</span><span class="sxs-lookup"><span data-stu-id="c8b16-141">Channel engagement</span></span> |<span data-ttu-id="c8b16-142">チャネルに移動して投稿を作成したり、投稿に返信し、高く評価したりできます (チャットコンテンツを含まない)。</span><span class="sxs-lookup"><span data-stu-id="c8b16-142">Visiting a channel, creating a post, replying to and liking a post (not including chat content).</span></span> |
|<span data-ttu-id="c8b16-143">ファイル</span><span class="sxs-lookup"><span data-stu-id="c8b16-143">Files</span></span> |<span data-ttu-id="c8b16-144">ファイルのアップロード、ダウンロード、アクセス、変更、コメント添付、共有 (ファイルコンテンツを含まない)。</span><span class="sxs-lookup"><span data-stu-id="c8b16-144">Uploading, downloading, accessing, modifying, commenting on, and sharing a file (not including file content).</span></span> |
|<span data-ttu-id="c8b16-145">会議</span><span class="sxs-lookup"><span data-stu-id="c8b16-145">Meetings</span></span> |<span data-ttu-id="c8b16-146">出席 (会議コンテンツを含まない)。</span><span class="sxs-lookup"><span data-stu-id="c8b16-146">Attendance (not including meeting content).</span></span> |

## <a name="data-location"></a><span data-ttu-id="c8b16-147">データの場所</span><span class="sxs-lookup"><span data-stu-id="c8b16-147">Data location</span></span>

<span data-ttu-id="c8b16-148">欧州のテナントのインサイト データは、欧州にあるサーバーに格納されています。</span><span class="sxs-lookup"><span data-stu-id="c8b16-148">Insights data for European-based tenants is stored on servers in Europe.</span></span> <span data-ttu-id="c8b16-149">米国のテナントのデータは、米国にあるサーバーに格納されています。</span><span class="sxs-lookup"><span data-stu-id="c8b16-149">Data for US-based tenants is stored on servers in the United States.</span></span> <span data-ttu-id="c8b16-150">インサイトを使用していて、Office 365 テナントが欧州の地域または米国以外の地域に存在する場合には、データはその適切な地域に格納されます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-150">If you use Insights and your Office 365 tenant is in a region outside of Europe or the United States, your data will be stored in the appropriate geographic region.</span></span>

## <a name="performance-and-reliability"></a><span data-ttu-id="c8b16-151">パフォーマンスと信頼性</span><span class="sxs-lookup"><span data-stu-id="c8b16-151">Performance and reliability</span></span>

<span data-ttu-id="c8b16-152">インサイトは、最適なパフォーマンスと信頼性を実現して Teams のアクティビティから収集される大量のデータを処理するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c8b16-152">Insights is designed to handle a high volume of data collected from Teams activity with optimal performance and reliability.</span></span>

<span data-ttu-id="c8b16-153">[インサイト] タブが Teams にインストールされているかどうかに関係なく、データ収集のプロセスは別のサーバーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-153">The data collection process takes place on separate servers regardless of the installation of the Insights tab in Teams.</span></span> <span data-ttu-id="c8b16-154">Teams の機能の残りを使用しているので、[インサイト] タブや個人用アプリは、教職員と学生用のアプリケーションのパフォーマンスやネットワーク帯域幅には影響しません。</span><span class="sxs-lookup"><span data-stu-id="c8b16-154">The Insights tab or personal app does not affect application performance or network bandwidth for educators and students using the rest of Teams functionality.</span></span>

> [!TIP]
> <span data-ttu-id="c8b16-155">教育用 Teams を帯域馬場が低い場合に使用する方法は、[こちら](edu-remote-low-bandwidth.md)をお読みください。 </span><span class="sxs-lookup"><span data-stu-id="c8b16-155">Read [here](edu-remote-low-bandwidth.md) about using Teams for Education when bandwidth is low.</span></span>

## <a name="how-to-delete-your-data"></a><span data-ttu-id="c8b16-156">データを削除する方法</span><span class="sxs-lookup"><span data-stu-id="c8b16-156">How to delete your data</span></span>

<span data-ttu-id="c8b16-157">教育用サービスでは、クラスチームのコンテキストで実行された学生と教職員のアクションを格納します。</span><span class="sxs-lookup"><span data-stu-id="c8b16-157">Education services stores student and educator actions performed in the context of a class team.</span></span> <span data-ttu-id="c8b16-158">このデータは、まとまったデータセットと見なされるため、学生または教職員のユーザーアカウントが組織から削除されても、サービスから自動的に削除されません。</span><span class="sxs-lookup"><span data-stu-id="c8b16-158">This data is considered a co-mingled data set and therefore isn't automatically deleted from the service once student or educator user accounts are deleted from your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="c8b16-159">データを削除すると、時間の経過とともにクラスチームの契約を分析するインサイトの機能に悪影響がでます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-159">Deleting data has a negative impact on Insights' ability to analyze class team engagement over time.</span></span>

- <span data-ttu-id="c8b16-160">[ここで](https://edusupport.microsoft.com/support)サポートチケットを開きます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-160">Open a support ticket [here](https://edusupport.microsoft.com/support).</span></span> <span data-ttu-id="c8b16-161">サポートチケットには、GDPR 削除 DSR 操作の要求を明確に記載し、削除するユーザーオブジェクト ID を入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8b16-161">The support ticket must state clearly the request for a GDPR Delete DSR operation and contain the user object ID to be deleted.</span></span> <span data-ttu-id="c8b16-162">削除するデータセットまたは時間帯を制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="c8b16-162">There is no ability to limit the data set or time window of the deletion.</span></span>
- <span data-ttu-id="c8b16-163">ファイルが済むと、サポートチケットは、コンプライアンスの最小限のポリシーを満たすために、1週間キュー内で待機します。</span><span class="sxs-lookup"><span data-stu-id="c8b16-163">Once filed, the support ticket waits in the queue for one week in order to meet compliance minimal retention policy.</span></span> <span data-ttu-id="c8b16-164">この間、操作をキャンセルすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-164">You have the opportunity to cancel the operation during this time.</span></span>
- <span data-ttu-id="c8b16-165">1週間後に、Education Analytics チームが、ユーザー ID に関連するすべてのデータをサービスから削除する処置を行います。</span><span class="sxs-lookup"><span data-stu-id="c8b16-165">After one week, the Education Analytics team takes action to ensure all data related to the user ID is deleted from the service.</span></span> <span data-ttu-id="c8b16-166">Microsoft サポートが ICM チケットを監視し、28 日以内に削除プロセスが完了したことを通知します。</span><span class="sxs-lookup"><span data-stu-id="c8b16-166">Microsoft support monitors the ICM ticket and will notify you once the deletion process is complete, in no more than 28 days.</span></span>

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a><span data-ttu-id="c8b16-167">School Data Sync (SDS) を使用してインサイトの電源をスウィッチ</span><span class="sxs-lookup"><span data-stu-id="c8b16-167">Turn Insights off and on using School Data Sync (SDS)</span></span>

<span data-ttu-id="c8b16-168">School Data Sync (SDS) は、Student Information System (SIS) データをインポートして、Office 365 と同期するプロセスを自動化するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-168">School Data Sync (SDS) helps to automate the process of importing and synchronizing Student Information System (SIS) data with Office 365.</span></span>

<span data-ttu-id="c8b16-169">インサイトを使用するときに SDS を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c8b16-169">The use of Insights does not require the use of SDS.</span></span> <span data-ttu-id="c8b16-170">ただし、SDS 管理センター (**設定** > \*\* Education Analytics 管理\*\*の順に移動) でトグルをオフにして、いつでも Education Analytics からオプトアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-170">However, you may choose to opt out from Education Analytics at any time by turning off the toggle in the SDS Admin Center under **Settings** > **Manage Education Analytics**.</span></span>

:::image type="content" source="media/class-insights-on-off.png" alt-text="インサイトを有効または無効にできるスイッチ。":::

<span data-ttu-id="c8b16-172">既定では、Education Analytics とインサイトはオンになっています。</span><span class="sxs-lookup"><span data-stu-id="c8b16-172">By default, Education Analytics, and therefore Insights, is turned on.</span></span> <span data-ttu-id="c8b16-173">Analytics からオプトアウトすると、[インサイト] タブ用に収集されたすべてのデータが削除されます。Analytics を再び有効にすると、有効になった時間からデータの収集が再開されます。</span><span class="sxs-lookup"><span data-stu-id="c8b16-173">When you opt out of Analytics, we delete all data collected for the Insights tab. Turn Analytics back on, and we start collecting data from the time it's re-enabled.</span></span>

<span data-ttu-id="c8b16-174">詳細については、「[インサイトへの教職員用ガイド](https://support.microsoft.com/ja-JP/office/educator-s-guide-to-insights-in-microsoft-teams-27b56255-90c0-47aa-bac3-1c9f50157181)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8b16-174">Learn more: [Educator's guide to Insights](https://support.microsoft.com/ja-JP/office/educator-s-guide-to-insights-in-microsoft-teams-27b56255-90c0-47aa-bac3-1c9f50157181)</span></span>
