---
title: 'Lync Server 2013: ユーザー登録レポート'
description: 'Lync Server 2013: ユーザー登録レポート。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7adb8ef7e94a24f0fd088f12e009fc9d63f3be9d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569753"
---
# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="5aebb-103">Lync Server 2013 のユーザー登録レポート</span><span class="sxs-lookup"><span data-stu-id="5aebb-103">User Registration Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5aebb-104">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="5aebb-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="5aebb-105">ユーザー登録レポートでは、ユーザーログオンのアクティビティの概要、特に、指定された期間 (時間、日、週、月単位) に Microsoft Lync Server 2013 にログオンしたユーザーの数についての情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-105">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="5aebb-106">このレポートで示されるのは、ログオンしたユーザーの数のみです。</span><span class="sxs-lookup"><span data-stu-id="5aebb-106">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="5aebb-107">どの\*\* ユーザーがログオンしたかは示されません。</span><span class="sxs-lookup"><span data-stu-id="5aebb-107">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="5aebb-108">監視レポートでは、どのユーザーが Lync Server 2013 を使用していて、どのユーザーがどのようなものではないかについての情報は提供されません。</span><span class="sxs-lookup"><span data-stu-id="5aebb-108">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="5aebb-109">ただし、ユーザー アクティビティ レポートを使用してユーザー情報の概算は把握できます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-109">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="5aebb-110">ユーザー登録レポートでは、ユーザー ログオンに関する情報を示す場合に 2 つの重要な分類が行われます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-110">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="5aebb-111">まず、内部ログオンと外部ログオンという 2 つの大きなカテゴリにログオンが分類されます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-111">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="5aebb-112">内部ログオンは、組織のファイアウォール内から (企業ネットワークに接続中に) ログオンしたユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-112">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="5aebb-113">外部ログオンは、エッジサーバーを介してファイアウォールの外側からログオンしたユーザーを表します (たとえば、インターネットカフェからログオンしたユーザーが外部ログオンとしてカウントした場合)。</span><span class="sxs-lookup"><span data-stu-id="5aebb-113">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="5aebb-114">ファイアウォールの外部からログオンしたユーザーの数が必要な場合、ユーザー登録レポートでその情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-114">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="5aebb-115">また、ユーザー登録レポートは、指定した期間内に存在した "アクティブ"\*\* ユーザーの数も示します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-115">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="5aebb-116">アクティブなユーザーとは、インスタントメッセージング (IM) セッションに参加し、Lync 会議に参加したか、電話をかけたか、またはその期間中に Lync Server を使用したユーザーです。</span><span class="sxs-lookup"><span data-stu-id="5aebb-116">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="5aebb-117">ログオンしただけで実際にシステムを使用しなかったユーザーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="5aebb-117">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="5aebb-118">ユーザー登録レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="5aebb-118">Accessing the User Registration Report</span></span>

<span data-ttu-id="5aebb-p104">ユーザー登録レポートには、監視レポートのホーム ページからアクセスできます。ユーザー登録レポートからは他のレポートへリンクしません。</span><span class="sxs-lookup"><span data-stu-id="5aebb-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="5aebb-121">ユーザー登録レポートの効果的な活用方法</span><span class="sxs-lookup"><span data-stu-id="5aebb-121">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="5aebb-122">Lync Server を展開した後、よく寄せられる質問は次のとおりです。ユーザーが実際にこの新しいテクノロジを使用しているかどうかを確認する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="5aebb-122">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="5aebb-123">いくつか制限はありますが、ユーザー登録レポートがこの疑問の解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-123">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="5aebb-124">ユーザーが Lync Server を使用しているかどうかを確認するには、2つの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aebb-124">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="5aebb-125">まず、ユーザー登録レポートで [一意のログオン ユーザー数] 指標の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-125">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="5aebb-126">この値は、Lync Server に個別にログオンした個人の数を示します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-126">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="5aebb-127">比較すると、[ログオンの合計数] 指標には、ユーザーが Lync Server にログオンした回数の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-127">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="5aebb-128">たとえば、Ken Myer が Lync Server に5つの異なる時間を1日にログオンしたとします。</span><span class="sxs-lookup"><span data-stu-id="5aebb-128">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="5aebb-129">この場合、Ken Myer は、[ログオン合計数] 指標でログオン セッション回数 5 回として記録されるのに対し、[一意のログオン ユーザー数] 指標ではログオン ユーザー 1 人として記録されます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-129">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="5aebb-130">また、1 人のユーザーが複数のデバイスまたは複数の場所からログオンすることも珍しくありません。</span><span class="sxs-lookup"><span data-stu-id="5aebb-130">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="5aebb-131">たとえば、ユーザーは自分のデスクトップコンピューターであるラップトップコンピューターを使用してログオンでき、Lync Server に自動的にログオンする IP 電話を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-131">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="5aebb-132">この場合、一意のユーザー数は 1 人、ログオン回数は 3 回になります。</span><span class="sxs-lookup"><span data-stu-id="5aebb-132">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="5aebb-133">ログオン合計数と一意のログオン ユーザー数の相違についてさらにわかりやすく説明にするために、ある期間内のログオンが次の表のようになっていた場合について検討します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-133">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5aebb-134">User</span><span class="sxs-lookup"><span data-stu-id="5aebb-134">User</span></span></th>
<th><span data-ttu-id="5aebb-135">ログオン時刻</span><span class="sxs-lookup"><span data-stu-id="5aebb-135">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5aebb-136">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="5aebb-136">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="5aebb-137">2012/7/7 8:45 AM</span><span class="sxs-lookup"><span data-stu-id="5aebb-137">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5aebb-138">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="5aebb-138">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="5aebb-139">2012/7/7 08:46 AM</span><span class="sxs-lookup"><span data-stu-id="5aebb-139">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5aebb-140">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="5aebb-140">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="5aebb-141">2012/7/7 9:17 AM</span><span class="sxs-lookup"><span data-stu-id="5aebb-141">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5aebb-142">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="5aebb-142">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="5aebb-143">2012/7/7 09:22 AM</span><span class="sxs-lookup"><span data-stu-id="5aebb-143">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5aebb-144">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="5aebb-144">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="5aebb-145">2012/7/7 09:31 AM</span><span class="sxs-lookup"><span data-stu-id="5aebb-145">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5aebb-p107">この場合、ログオン合計数は 5 回ですが、ログオンしたユーザーは Ken Myer (ログオン回数 3 回) と Pilar Ackerman (ログオン回数 2 回) の 2 人だけです。ログオン合計数と一意のログオン ユーザー数はこのように異なります。</span><span class="sxs-lookup"><span data-stu-id="5aebb-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="5aebb-148">一意のログオンの数に加えて、Lync Server に対して有効になっているユーザーの合計数を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aebb-148">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="5aebb-149">この値を取得するには、Lync Server 2013 管理シェルを開き、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-149">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="5aebb-150">上記のコマンドを実行すると、1236の値が返され、一意のログオンユーザー指標が返されます。667の平均値を返します。54これは、ユーザーの半数以上が Lync に対して有効になっている場合は、実際には毎日システムにログオンすることを示します (つまり、667は1236で割ることができます)。</span><span class="sxs-lookup"><span data-stu-id="5aebb-150">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="5aebb-151">ログオンの指標に記録されるのは、指定した期間内に実際にログオンしたユーザーの数である点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="5aebb-151">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="5aebb-152">その前に既にシステムにログオンしていたユーザーは追跡されません。</span><span class="sxs-lookup"><span data-stu-id="5aebb-152">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="5aebb-153">たとえば、[一意のログオン ユーザー数] 指標が 667、ユーザー数が 1,236 の場合、約半分のユーザーがシステムにログオンしたことになります。</span><span class="sxs-lookup"><span data-stu-id="5aebb-153">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="5aebb-154">ただし、ログオン データのチェックを開始する前に既に 300 人のユーザーがシステムにログオンしていたとします。</span><span class="sxs-lookup"><span data-stu-id="5aebb-154">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="5aebb-155">これは、実際には約1000のユーザーが Lync Server にログオンしていることを意味します。これは、ユーザーの80% がログオンしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-155">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="5aebb-156">また、[一意のログオン ユーザー数] の値と [一意のアクティブなユーザー数] 指標も比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5aebb-156">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="5aebb-157">一意のアクティブユーザー指標は、実際に Lync Server を使用した一意のユーザーの数を示します。電話をかけたか、Lync 会議に参加したか、または IM セッションに参加したかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-157">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="5aebb-158">Microsoft Lync 2013 は、ユーザーが Windows を起動するたびに自動的に開始するように構成できるため、この情報は役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-158">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="5aebb-159">そのため、毎日 Windows にログオンすると Lync に自動的にログオンするユーザーが多数存在することがありますが、その期間中は実際に Lync Server を使用することはありません。</span><span class="sxs-lookup"><span data-stu-id="5aebb-159">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="5aebb-160">また、一意のアクティブユーザー指標では、ユーザーが1日の最後に Windows をログオフしない組織で、より意味のあるデータが提供されます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-160">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="5aebb-161">代わりに、コンピューターをロックし、Windows と Lync を実行したままにします。</span><span class="sxs-lookup"><span data-stu-id="5aebb-161">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="5aebb-162">このような状態では、ユーザーは何日もログオンしたままでログオフしないので、1 日あたりのログオン数は非常に低くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5aebb-162">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="5aebb-163">ただし、一意のアクティブユーザーは、ユーザーが Lync または別の Lync Server クライアントをアクティブに使用しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-163">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="5aebb-164">フィルター</span><span class="sxs-lookup"><span data-stu-id="5aebb-164">Filters</span></span>

<span data-ttu-id="5aebb-165">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-165">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="5aebb-166">たとえば、ユーザー登録レポートを使用すると、すべてのレジストラープールとエッジサーバーのデータを表示したり、個々のプールのデータを表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-166">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="5aebb-167">また、データをグループ化する方法を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-167">You can also choose how data should be grouped.</span></span> <span data-ttu-id="5aebb-168">この場合は、登録が、時間、日、週、または月を基準にグループ化されています。</span><span class="sxs-lookup"><span data-stu-id="5aebb-168">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="5aebb-169">次の表に、ユーザー登録レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-169">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="5aebb-170">ユーザー登録レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="5aebb-170">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5aebb-171">名前</span><span class="sxs-lookup"><span data-stu-id="5aebb-171">Name</span></span></th>
<th><span data-ttu-id="5aebb-172">説明</span><span class="sxs-lookup"><span data-stu-id="5aebb-172">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5aebb-173"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="5aebb-173"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="5aebb-p113">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="5aebb-176">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5aebb-176">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5aebb-p114">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5aebb-179">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5aebb-179">7/7/2012</span></span></p>
<p><span data-ttu-id="5aebb-180">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="5aebb-180">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5aebb-181">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5aebb-181">7/3/2012</span></span></p>
<p><span data-ttu-id="5aebb-182">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="5aebb-182">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5aebb-183"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="5aebb-183"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="5aebb-p115">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="5aebb-186">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5aebb-186">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5aebb-p116">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5aebb-189">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5aebb-189">7/7/2012</span></span></p>
<p><span data-ttu-id="5aebb-190">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="5aebb-190">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5aebb-191">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5aebb-191">7/3/2012</span></span></p>
<p><span data-ttu-id="5aebb-192">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="5aebb-192">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5aebb-193"><strong>間隔</strong></span><span class="sxs-lookup"><span data-stu-id="5aebb-193"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="5aebb-p117">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5aebb-196">時間単位 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="5aebb-196">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5aebb-197">日単位 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="5aebb-197">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5aebb-198">週単位 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="5aebb-198">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="5aebb-199">月単位 (最大 12 か月の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="5aebb-199">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="5aebb-p118">開始日と終了日が、選択されている期間内で許容される値の最大数を超えると、(開始日から起算した) 値の最大数のみが表示されます。たとえば、期間として [毎日] を選択し、開始日に 2012 年 7 月 7 日、終了日に 2012 年 2 月 28 日を選択した場合、2012 年 8 月 7 日 12:00 AM から 2012 年 9 月 7 日 12:00 AM までの日数分のデータ (合計 31 日分のデータ) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5aebb-202"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5aebb-202"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5aebb-203">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="5aebb-203">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="5aebb-204">個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-204">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="5aebb-205">このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-205">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="5aebb-206">指標</span><span class="sxs-lookup"><span data-stu-id="5aebb-206">Metrics</span></span>

<span data-ttu-id="5aebb-207">次の表に、ユーザー登録レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="5aebb-207">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="5aebb-208">ユーザー登録レポートの指標</span><span class="sxs-lookup"><span data-stu-id="5aebb-208">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5aebb-209">名前</span><span class="sxs-lookup"><span data-stu-id="5aebb-209">Name</span></span></th>
<th><span data-ttu-id="5aebb-210">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="5aebb-210">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="5aebb-211">説明</span><span class="sxs-lookup"><span data-stu-id="5aebb-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5aebb-212"><strong>毎時</strong></span><span class="sxs-lookup"><span data-stu-id="5aebb-212"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="5aebb-213"><strong>毎日</strong></span><span class="sxs-lookup"><span data-stu-id="5aebb-213"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="5aebb-214"><strong>毎週</strong></span><span class="sxs-lookup"><span data-stu-id="5aebb-214"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="5aebb-215"><strong>毎月</strong></span><span class="sxs-lookup"><span data-stu-id="5aebb-215"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="5aebb-216">いいえ</span><span class="sxs-lookup"><span data-stu-id="5aebb-216">No</span></span></p></td>
<td><p><span data-ttu-id="5aebb-p120">フィルター ツール バーで選択した期間を示します。状況に応じて、特定の期間をクリックして、その期間の詳細情報を表示することもできます。たとえば、期間として [毎日] を使用している場合に、「2012 年 7 月 7 日」をクリックすると、その日に行われたユーザー登録アクティビティが時間ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5aebb-220">[<strong>ログオン合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="5aebb-220"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="5aebb-221">いいえ</span><span class="sxs-lookup"><span data-stu-id="5aebb-221">No</span></span></p></td>
<td><p><span data-ttu-id="5aebb-222">成功したログオン セッションの総数です。</span><span class="sxs-lookup"><span data-stu-id="5aebb-222">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5aebb-223">[<strong>内部ログオン数</strong>]</span><span class="sxs-lookup"><span data-stu-id="5aebb-223"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="5aebb-224">いいえ</span><span class="sxs-lookup"><span data-stu-id="5aebb-224">No</span></span></p></td>
<td><p><span data-ttu-id="5aebb-225">内部ネットワーク内でのログオンの総数です。</span><span class="sxs-lookup"><span data-stu-id="5aebb-225">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5aebb-226">[<strong>外部ログオン数</strong>]</span><span class="sxs-lookup"><span data-stu-id="5aebb-226"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="5aebb-227">いいえ</span><span class="sxs-lookup"><span data-stu-id="5aebb-227">No</span></span></p></td>
<td><p><span data-ttu-id="5aebb-228">エッジ サーバーを使用した、内部ネットワークの外部からのログオンの総数です。</span><span class="sxs-lookup"><span data-stu-id="5aebb-228">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5aebb-229">[<strong>一意のログオン ユーザー数</strong>]</span><span class="sxs-lookup"><span data-stu-id="5aebb-229"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="5aebb-230">いいえ</span><span class="sxs-lookup"><span data-stu-id="5aebb-230">No</span></span></p></td>
<td><p><span data-ttu-id="5aebb-p121">少なくとも 1 つのログオン セッションを使用したユーザーの総数です。複数のログオン セッションを使用したユーザーも、ログオン セッションを 1 つしか使用しなかったユーザーと同じように、1 ユーザーとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5aebb-233">[<strong>一意のアクティブなユーザー数</strong>]</span><span class="sxs-lookup"><span data-stu-id="5aebb-233"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="5aebb-234">いいえ</span><span class="sxs-lookup"><span data-stu-id="5aebb-234">No</span></span></p></td>
<td><p><span data-ttu-id="5aebb-p122">ピアツーピア セッションまたは会議セッションに関係したユーザーの総数です。複数のセッションを使用したユーザーも、セッションを 1 つしか使用しなかったユーザーと同じように、1 ユーザーとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="5aebb-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

