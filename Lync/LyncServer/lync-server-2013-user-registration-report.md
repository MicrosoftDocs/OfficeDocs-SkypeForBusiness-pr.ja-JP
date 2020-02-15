---
title: 'Lync Server 2013: ユーザー登録レポート'
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
ms.openlocfilehash: 716d8324fba8346fa1326da2ed253dfa07bc3915
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="e7b34-102">Lync Server 2013 のユーザー登録レポート</span><span class="sxs-lookup"><span data-stu-id="e7b34-102">User Registration Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7b34-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="e7b34-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="e7b34-104">ユーザー登録レポートでは、ユーザーログオンのアクティビティの概要、特に、指定された期間 (時間、日、週、月単位) に Microsoft Lync Server 2013 にログオンしたユーザーの数についての情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-104">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="e7b34-105">このレポートで示されるのは、ログオンしたユーザーの数のみです。</span><span class="sxs-lookup"><span data-stu-id="e7b34-105">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="e7b34-106">どの\*\* ユーザーがログオンしたかは示されません。</span><span class="sxs-lookup"><span data-stu-id="e7b34-106">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="e7b34-107">監視レポートでは、どのユーザーが Lync Server 2013 を使用していて、どのユーザーがどのようなものではないかについての情報は提供されません。</span><span class="sxs-lookup"><span data-stu-id="e7b34-107">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="e7b34-108">ただし、ユーザー アクティビティ レポートを使用してユーザー情報の概算は把握できます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-108">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="e7b34-109">ユーザー登録レポートでは、ユーザー ログオンに関する情報を示す場合に 2 つの重要な分類が行われます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-109">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="e7b34-110">まず、内部ログオンと外部ログオンという 2 つの大きなカテゴリにログオンが分類されます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-110">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="e7b34-111">内部ログオンは、組織のファイアウォール内から (企業ネットワークに接続中に) ログオンしたユーザーを表します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-111">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="e7b34-112">外部ログオンは、エッジサーバーを介してファイアウォールの外側からログオンしたユーザーを表します (たとえば、インターネットカフェからログオンしたユーザーが外部ログオンとしてカウントした場合)。</span><span class="sxs-lookup"><span data-stu-id="e7b34-112">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="e7b34-113">ファイアウォールの外部からログオンしたユーザーの数が必要な場合、ユーザー登録レポートでその情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-113">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="e7b34-114">また、ユーザー登録レポートは、指定した期間内に存在した "アクティブ"\*\* ユーザーの数も示します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-114">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="e7b34-115">アクティブなユーザーとは、インスタントメッセージング (IM) セッションに参加し、Lync 会議に参加したか、電話をかけたか、またはその期間中に Lync Server を使用したユーザーです。</span><span class="sxs-lookup"><span data-stu-id="e7b34-115">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="e7b34-116">ログオンしただけで実際にシステムを使用しなかったユーザーとは異なります。</span><span class="sxs-lookup"><span data-stu-id="e7b34-116">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="e7b34-117">ユーザー登録レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="e7b34-117">Accessing the User Registration Report</span></span>

<span data-ttu-id="e7b34-p104">ユーザー登録レポートには、監視レポートのホーム ページからアクセスできます。ユーザー登録レポートからは他のレポートへリンクしません。</span><span class="sxs-lookup"><span data-stu-id="e7b34-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="e7b34-120">ユーザー登録レポートの効果的な活用方法</span><span class="sxs-lookup"><span data-stu-id="e7b34-120">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="e7b34-121">Lync Server を展開した後、よく寄せられる質問は次のとおりです。ユーザーが実際にこの新しいテクノロジを使用しているかどうかを確認する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="e7b34-121">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="e7b34-122">いくつか制限はありますが、ユーザー登録レポートがこの疑問の解決に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-122">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="e7b34-123">ユーザーが Lync Server を使用しているかどうかを確認するには、2つの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7b34-123">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="e7b34-124">まず、ユーザー登録レポートで [一意のログオン ユーザー数] 指標の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-124">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="e7b34-125">この値は、Lync Server に個別にログオンした個人の数を示します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-125">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="e7b34-126">比較すると、[ログオンの合計数] 指標には、ユーザーが Lync Server にログオンした回数の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-126">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="e7b34-127">たとえば、Ken Myer が Lync Server に5つの異なる時間を1日にログオンしたとします。</span><span class="sxs-lookup"><span data-stu-id="e7b34-127">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="e7b34-128">この場合、Ken Myer は、[ログオン合計数] 指標でログオン セッション回数 5 回として記録されるのに対し、[一意のログオン ユーザー数] 指標ではログオン ユーザー 1 人として記録されます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-128">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="e7b34-129">また、1 人のユーザーが複数のデバイスまたは複数の場所からログオンすることも珍しくありません。</span><span class="sxs-lookup"><span data-stu-id="e7b34-129">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="e7b34-130">たとえば、ユーザーは自分のデスクトップコンピューターであるラップトップコンピューターを使用してログオンでき、Lync Server に自動的にログオンする IP 電話を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-130">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="e7b34-131">この場合、一意のユーザー数は 1 人、ログオン回数は 3 回になります。</span><span class="sxs-lookup"><span data-stu-id="e7b34-131">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="e7b34-132">ログオン合計数と一意のログオン ユーザー数の相違についてさらにわかりやすく説明にするために、ある期間内のログオンが次の表のようになっていた場合について検討します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-132">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7b34-133">ユーザー</span><span class="sxs-lookup"><span data-stu-id="e7b34-133">User</span></span></th>
<th><span data-ttu-id="e7b34-134">ログオン時刻</span><span class="sxs-lookup"><span data-stu-id="e7b34-134">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7b34-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="e7b34-135">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="e7b34-136">2012/7/7 8:45 AM</span><span class="sxs-lookup"><span data-stu-id="e7b34-136">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b34-137">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="e7b34-137">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="e7b34-138">2012/7/7 08:46 AM</span><span class="sxs-lookup"><span data-stu-id="e7b34-138">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b34-139">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="e7b34-139">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="e7b34-140">2012/7/7 9:17 AM</span><span class="sxs-lookup"><span data-stu-id="e7b34-140">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b34-141">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="e7b34-141">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="e7b34-142">2012/7/7 09:22 AM</span><span class="sxs-lookup"><span data-stu-id="e7b34-142">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b34-143">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="e7b34-143">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="e7b34-144">2012/7/7 09:31 AM</span><span class="sxs-lookup"><span data-stu-id="e7b34-144">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e7b34-p107">この場合、ログオン合計数は 5 回ですが、ログオンしたユーザーは Ken Myer (ログオン回数 3 回) と Pilar Ackerman (ログオン回数 2 回) の 2 人だけです。ログオン合計数と一意のログオン ユーザー数はこのように異なります。</span><span class="sxs-lookup"><span data-stu-id="e7b34-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="e7b34-147">一意のログオンの数に加えて、Lync Server に対して有効になっているユーザーの合計数を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7b34-147">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="e7b34-148">この値を取得するには、Lync Server 2013 管理シェルを開き、次の Windows PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-148">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="e7b34-149">上記のコマンドを実行すると、1236の値が返され、一意のログオンユーザー指標が返されます。667は、実際には、少なくとも半数のユーザーが Lync を有効にして毎日システムにログオンすることを示します (つまり、667を1236で割る)。(およそ54%)。</span><span class="sxs-lookup"><span data-stu-id="e7b34-149">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e7b34-150">ログオンの指標に記録されるのは、指定した期間内に実際にログオンしたユーザーの数である点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="e7b34-150">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="e7b34-151">その前に既にシステムにログオンしていたユーザーは追跡されません。</span><span class="sxs-lookup"><span data-stu-id="e7b34-151">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="e7b34-152">たとえば、[一意のログオン ユーザー数] 指標が 667、ユーザー数が 1,236 の場合、約半分のユーザーがシステムにログオンしたことになります。</span><span class="sxs-lookup"><span data-stu-id="e7b34-152">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="e7b34-153">ただし、ログオン データのチェックを開始する前に既に 300 人のユーザーがシステムにログオンしていたとします。</span><span class="sxs-lookup"><span data-stu-id="e7b34-153">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="e7b34-154">これは、実際には約1000のユーザーが Lync Server にログオンしていることを意味します。これは、ユーザーの80% がログオンしていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-154">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="e7b34-155">また、[一意のログオン ユーザー数] の値と [一意のアクティブなユーザー数] 指標も比較する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7b34-155">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="e7b34-156">一意のアクティブユーザー指標は、実際に Lync Server を使用した一意のユーザーの数を示します。電話をかけたか、Lync 会議に参加したか、または IM セッションに参加したかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-156">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="e7b34-157">Microsoft Lync 2013 は、ユーザーが Windows を起動するたびに自動的に開始するように構成できるため、この情報は役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-157">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="e7b34-158">そのため、毎日 Windows にログオンすると Lync に自動的にログオンするユーザーが多数存在することがありますが、その期間中は実際に Lync Server を使用することはありません。</span><span class="sxs-lookup"><span data-stu-id="e7b34-158">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="e7b34-159">また、一意のアクティブユーザー指標では、ユーザーが1日の最後に Windows をログオフしない組織で、より意味のあるデータが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-159">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="e7b34-160">代わりに、コンピューターをロックし、Windows と Lync を実行したままにします。</span><span class="sxs-lookup"><span data-stu-id="e7b34-160">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="e7b34-161">このような状態では、ユーザーは何日もログオンしたままでログオフしないので、1 日あたりのログオン数は非常に低くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7b34-161">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="e7b34-162">ただし、一意のアクティブユーザーは、ユーザーが Lync または別の Lync Server クライアントをアクティブに使用しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-162">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e7b34-163">フィルター</span><span class="sxs-lookup"><span data-stu-id="e7b34-163">Filters</span></span>

<span data-ttu-id="e7b34-164">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-164">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e7b34-165">たとえば、ユーザー登録レポートを使用すると、すべてのレジストラープールとエッジサーバーのデータを表示したり、個々のプールのデータを表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-165">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="e7b34-166">また、データをグループ化する方法を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-166">You can also choose how data should be grouped.</span></span> <span data-ttu-id="e7b34-167">この場合は、登録が、時間、日、週、または月を基準にグループ化されています。</span><span class="sxs-lookup"><span data-stu-id="e7b34-167">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e7b34-168">次の表に、ユーザー登録レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-168">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="e7b34-169">ユーザー登録レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="e7b34-169">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7b34-170">名前</span><span class="sxs-lookup"><span data-stu-id="e7b34-170">Name</span></span></th>
<th><span data-ttu-id="e7b34-171">説明</span><span class="sxs-lookup"><span data-stu-id="e7b34-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7b34-172"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e7b34-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b34-p113">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e7b34-175">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e7b34-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e7b34-p114">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e7b34-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e7b34-178">7/7/2012</span></span></p>
<p><span data-ttu-id="e7b34-179">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="e7b34-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e7b34-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e7b34-180">7/3/2012</span></span></p>
<p><span data-ttu-id="e7b34-181">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="e7b34-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b34-182"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e7b34-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b34-p115">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e7b34-185">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e7b34-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e7b34-p116">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e7b34-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e7b34-188">7/7/2012</span></span></p>
<p><span data-ttu-id="e7b34-189">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="e7b34-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e7b34-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e7b34-190">7/3/2012</span></span></p>
<p><span data-ttu-id="e7b34-191">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="e7b34-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b34-192"><strong>間隔</strong></span><span class="sxs-lookup"><span data-stu-id="e7b34-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b34-p117">時間間隔です。次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e7b34-195">時間単位 (最大 25 時間の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="e7b34-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e7b34-196">日単位 (最大 31 日の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="e7b34-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e7b34-197">週単位 (最大 12 週の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="e7b34-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e7b34-198">月単位 (最大 12 か月の表示が可能)</span><span class="sxs-lookup"><span data-stu-id="e7b34-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e7b34-p118">開始日と終了日が、選択されている期間内で許容される値の最大数を超えると、(開始日から起算した) 値の最大数のみが表示されます。たとえば、期間として [毎日] を選択し、開始日に 2012 年 7 月 7 日、終了日に 2012 年 2 月 28 日を選択した場合、2012 年 8 月 7 日 12:00 AM から 2012 年 9 月 7 日 12:00 AM までの日数分のデータ (合計 31 日分のデータ) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b34-201"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e7b34-201"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b34-202">レジストラー プールまたはエッジ サーバーの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="e7b34-202">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="e7b34-203">個別のプールを選択するか、[<strong>すべて</strong>] をクリックしてすべてのプールのデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-203">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="e7b34-204">このドロップダウン リストは、データベース内のレコードに基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-204">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e7b34-205">指標</span><span class="sxs-lookup"><span data-stu-id="e7b34-205">Metrics</span></span>

<span data-ttu-id="e7b34-206">次の表に、ユーザー登録レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="e7b34-206">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="e7b34-207">ユーザー登録レポートの指標</span><span class="sxs-lookup"><span data-stu-id="e7b34-207">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e7b34-208">名前</span><span class="sxs-lookup"><span data-stu-id="e7b34-208">Name</span></span></th>
<th><span data-ttu-id="e7b34-209">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="e7b34-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e7b34-210">説明</span><span class="sxs-lookup"><span data-stu-id="e7b34-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e7b34-211"><strong>毎時</strong></span><span class="sxs-lookup"><span data-stu-id="e7b34-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="e7b34-212"><strong>毎日</strong></span><span class="sxs-lookup"><span data-stu-id="e7b34-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="e7b34-213"><strong>毎週</strong></span><span class="sxs-lookup"><span data-stu-id="e7b34-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="e7b34-214"><strong>毎月</strong></span><span class="sxs-lookup"><span data-stu-id="e7b34-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b34-215">いいえ</span><span class="sxs-lookup"><span data-stu-id="e7b34-215">No</span></span></p></td>
<td><p><span data-ttu-id="e7b34-p120">フィルター ツール バーで選択した期間を示します。状況に応じて、特定の期間をクリックして、その期間の詳細情報を表示することもできます。たとえば、期間として [毎日] を使用している場合に、「2012 年 7 月 7 日」をクリックすると、その日に行われたユーザー登録アクティビティが時間ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b34-219">[<strong>ログオン合計数</strong>]</span><span class="sxs-lookup"><span data-stu-id="e7b34-219"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b34-220">いいえ</span><span class="sxs-lookup"><span data-stu-id="e7b34-220">No</span></span></p></td>
<td><p><span data-ttu-id="e7b34-221">成功したログオン セッションの総数です。</span><span class="sxs-lookup"><span data-stu-id="e7b34-221">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b34-222">[<strong>内部ログオン数</strong>]</span><span class="sxs-lookup"><span data-stu-id="e7b34-222"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b34-223">いいえ</span><span class="sxs-lookup"><span data-stu-id="e7b34-223">No</span></span></p></td>
<td><p><span data-ttu-id="e7b34-224">内部ネットワーク内でのログオンの総数です。</span><span class="sxs-lookup"><span data-stu-id="e7b34-224">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b34-225">[<strong>外部ログオン数</strong>]</span><span class="sxs-lookup"><span data-stu-id="e7b34-225"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b34-226">いいえ</span><span class="sxs-lookup"><span data-stu-id="e7b34-226">No</span></span></p></td>
<td><p><span data-ttu-id="e7b34-227">エッジ サーバーを使用した、内部ネットワークの外部からのログオンの総数です。</span><span class="sxs-lookup"><span data-stu-id="e7b34-227">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e7b34-228">[<strong>一意のログオン ユーザー数</strong>]</span><span class="sxs-lookup"><span data-stu-id="e7b34-228"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b34-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="e7b34-229">No</span></span></p></td>
<td><p><span data-ttu-id="e7b34-p121">少なくとも 1 つのログオン セッションを使用したユーザーの総数です。複数のログオン セッションを使用したユーザーも、ログオン セッションを 1 つしか使用しなかったユーザーと同じように、1 ユーザーとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e7b34-232">[<strong>一意のアクティブなユーザー数</strong>]</span><span class="sxs-lookup"><span data-stu-id="e7b34-232"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="e7b34-233">いいえ</span><span class="sxs-lookup"><span data-stu-id="e7b34-233">No</span></span></p></td>
<td><p><span data-ttu-id="e7b34-p122">ピアツーピア セッションまたは会議セッションに関係したユーザーの総数です。複数のセッションを使用したユーザーも、セッションを 1 つしか使用しなかったユーザーと同じように、1 ユーザーとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="e7b34-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

