---
title: 'Lync Server 2013: IP 電話インベントリレポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0be055238c2e8db45337b9e66d936bb73c73e61
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525204"
---
# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="00229-102">Lync Server 2013 の IP 電話インベントリレポート</span><span class="sxs-lookup"><span data-stu-id="00229-102">IP Phone Inventory Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00229-103">_**トピックの最終更新日:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="00229-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="00229-p101">IP 電話インベントリ レポートは、組織で現在使われている IP 電話に関する情報をレポートします。IP インベントリ レポートには、指定したレポート期間に実際に使用された IP 電話の詳細な一覧が含まれます。このレポートを使用すると、たとえば、交換する必要がある古い電話機が使用されていないかどうかや、ほとんど使用されていない高価な電話機がないかどうかを調べることができます。この種の情報は、新しい電話機を購入したり既存の電話機を割り当てし直したりする際にとても役に立ちます (たとえば、ほとんど使用しないユーザーに割り当てられている高価な電話機を、電話を多用するユーザーの電話機と交換することができます)。</span><span class="sxs-lookup"><span data-stu-id="00229-p101">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization. The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period. Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used. That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones. (For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="00229-109">このレポートでは、実際のインベントリレポートとして使用されるときにいくつかの制限があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="00229-109">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="00229-110">1つの目的として、IP 電話レポートには、指定された期間中に Lync Server にログオンしたすべての電話の一覧が表示されます。これは、最終ログオン時刻で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="00229-110">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="00229-111">電話が指定された期間中にログオンしなかった場合は、インベントリレポートに一覧表示されません。</span><span class="sxs-lookup"><span data-stu-id="00229-111">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="00229-112">これには、指定された期間中にログオンした後にログオンした電話機が含まれます。</span><span class="sxs-lookup"><span data-stu-id="00229-112">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="00229-113">たとえば、2012年7月のすべての電話番号を参照したいとします。</span><span class="sxs-lookup"><span data-stu-id="00229-113">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="00229-114">また、複数の電話が2012年6月30日に Lync Server にログオンしていて、7月1日の時点でまだログオンしていたとします。</span><span class="sxs-lookup"><span data-stu-id="00229-114">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="00229-115">これらの電話は7月1日のインベントリレポートには表示されません。</span><span class="sxs-lookup"><span data-stu-id="00229-115">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="00229-p103">また、このインベントリ レポートには、既に組織で使用されていない電話機が含まれる可能性もあります。たとえば、2012 年 7 月 1 日にシステムにログオンした Fabrikam の電話機が、その 5 日後にすべて Contoso の新しいモデルに置き換えられた場合、それらの Fabrikam の電話機は、7 月中にシステムにログオンしたため "インベントリ" レポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="00229-p103">It's also important to note that the inventory report could include phones that your organization no longer uses. For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model. The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="00229-p104">さらに、IP 電話インベントリ レポートには、電話機の機種別の集計は含まれません。たとえば、組織で Polycom CX600 を 105 台使用している場合、このレポートには、その電話機が 105 台あるという情報は含まれません。Polycom Cx600 のエントリが 105 件含まれるだけです。その数を調べるには、それらを手動で数えるしかありません。</span><span class="sxs-lookup"><span data-stu-id="00229-p104">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones. For example, suppose you have 105 Polycom CX600 phones. The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600. The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="00229-123">あるいは、データをエクスポートして、Microsoft Excel または Windows PowerShell で数を調べます。</span><span class="sxs-lookup"><span data-stu-id="00229-123">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="00229-124">IP 電話インベントリ レポートへのアクセス</span><span class="sxs-lookup"><span data-stu-id="00229-124">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="00229-p105">IP 電話インベントリ レポートは、[監視レポート] ホーム ページからアクセスします。[ユーザー URI] 指標をクリックすると、そのユーザーのユーザー アクティビティ レポートにアクセスできます。ピアツーピア通話の [最後のアクティビティ] 指標をクリックすると、ピアツーピア セッション詳細レポートが表示されます。会議の同じ指標をクリックすると、会議詳細レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="00229-p105">The IP Phone Inventory Report is accessed from the Monitoring Reports home page. If you click the User URI metric you can access the User Activity Report for that user. Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="00229-128">IP 電話インベントリ レポートの活用</span><span class="sxs-lookup"><span data-stu-id="00229-128">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="00229-129">1つの特定の種類の電話 (「ユーザーが Polycom CX600 電話を使用する頻度」など) の利用状況に関する情報のみが必要な場合は、その特定の種類の電話にフィルターを適用することによって、その情報を IP 電話インベントリレポートから直接取得できます。</span><span class="sxs-lookup"><span data-stu-id="00229-129">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="00229-130">ただし、すべての電話の概要情報 (Polycom CX600 を使用しているユーザー数、IP8540 など) を使用し LG-Nortel ている場合は、そのデータをエクスポートし、別のアプリケーション (Windows PowerShell など) を使用してその種類の分析を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00229-130">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="00229-131">たとえば、データをコンマ区切り値ファイル (C: \\ data \\ IP \_ Phone \_ InventoryReport.csv) にエクスポートするとし \_ ます。</span><span class="sxs-lookup"><span data-stu-id="00229-131">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="00229-132">その場合は、次の2つのコマンドを使用して、すべての電話の概要データを提供できます。</span><span class="sxs-lookup"><span data-stu-id="00229-132">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="00229-133">これにより、次のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="00229-133">That will return data similar to this:</span></span>

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

<span data-ttu-id="00229-134">同様に、次の 2 つのコマンドを使用すると、システムにログオンしたが電話をかけるために使用されていない電話機を調べることができます ("Last activity" メトリックの値が空白になっています。これは、最後のアクティビティがないことを表します)。</span><span class="sxs-lookup"><span data-stu-id="00229-134">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="00229-135">これにより、使用されていない電話機ごとに次のようなデータが返されます。</span><span class="sxs-lookup"><span data-stu-id="00229-135">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="00229-136">IP 電話インベントリレポートを使用するもう1つの興味深い方法は次のとおりです。 IP 電話の MAC アドレスを持っている場合は、[MAC アドレス] テキストボックスにそのアドレスを入力するだけで、その電話を最後に使用したユーザーを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="00229-136">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="00229-137">その後、IP 電話インベントリレポートによって、その電話で最後にログオンしたユーザーの SIP アドレスが報告されます。</span><span class="sxs-lookup"><span data-stu-id="00229-137">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="00229-138">または、ユーザーの SIP アドレス ([ユーザー URI プレフィックス] ボックス) を入力して、そのユーザーが使用していたすべての電話を検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="00229-138">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="00229-139">フィルター</span><span class="sxs-lookup"><span data-stu-id="00229-139">Filters</span></span>

<span data-ttu-id="00229-p108">フィルターは、細かく絞り込んだデータ セットを返したり、返されたデータをさまざま方法で表示したりする方法として利用できます。たとえば、IP 電話インベントリでは、特定の会社で製造された電話だけを表示したり、それらの電話の特定のバージョンだけを表示したりすることができます。また、データをグループ化する方法を選択することもできます。この場合は、登録情報が、時間、日、週、または月を基準にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="00229-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones. You can also choose how data should be grouped. In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="00229-144">次の表に、IP 電話インベントリ レポートで使用できるフィルターを示します。</span><span class="sxs-lookup"><span data-stu-id="00229-144">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="00229-145">IP 電話インベントリ レポートのフィルター</span><span class="sxs-lookup"><span data-stu-id="00229-145">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00229-146">名前</span><span class="sxs-lookup"><span data-stu-id="00229-146">Name</span></span></th>
<th><span data-ttu-id="00229-147">説明</span><span class="sxs-lookup"><span data-stu-id="00229-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00229-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="00229-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-p109">時間範囲の開始日と開始時刻。データを時間単位で表示するには、次のように開始日と開始時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="00229-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="00229-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="00229-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="00229-p110">開始時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に開始します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="00229-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="00229-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="00229-154">7/7/2012</span></span></p>
<p><span data-ttu-id="00229-155">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="00229-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="00229-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="00229-156">7/3/2012</span></span></p>
<p><span data-ttu-id="00229-157">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="00229-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00229-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="00229-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-p111">時間範囲の終了日と終了時刻。データを時間単位で表示するには、次のように終了日と終了時刻の両方を入力します。</span><span class="sxs-lookup"><span data-stu-id="00229-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="00229-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="00229-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="00229-p112">終了時刻を入力しないと、レポートは自動的に指定日の午前 12:00 に終了します。データを日単位で表示するには、次のように日付のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="00229-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="00229-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="00229-164">7/7/2012</span></span></p>
<p><span data-ttu-id="00229-165">週単位または月単位で表示するには、表示する週または月の任意の日付を入力します (その週または月の最初の日である必要はありません)。</span><span class="sxs-lookup"><span data-stu-id="00229-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="00229-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="00229-166">7/3/2012</span></span></p>
<p><span data-ttu-id="00229-167">週は、常に日曜日から土曜日までです。</span><span class="sxs-lookup"><span data-stu-id="00229-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00229-168"><strong>製造</strong></span><span class="sxs-lookup"><span data-stu-id="00229-168"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-p113">IP 電話を製造した会社の名前。このフィルターの値は、データベースに現在登録されている IP 電話に基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="00229-p113">Name of the company that manufactured the IP phone. The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00229-171">[<strong>ハードウェア バージョン</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-171"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-172">IP 電話のバージョン番号。製造元とハードウェアバージョンフィルターを使用すると、特定の種類の電話を一意に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="00229-172">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="00229-173">このフィルターの値は、データベースに現在登録されている IP 電話に基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="00229-173">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00229-174">[<strong>ユーザー エージェント</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-174"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-p115">IP 電話で使われているソフトウェアの識別子。このフィルターの値は、データベースに現在登録されている IP 電話に基づいて自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="00229-p115">Identifier for the software used by the IP phone. The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00229-177">[<strong>MAC アドレス</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-177"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-p116">IP 電話のネットワーク インターフェイスの一意の識別子。メディア アクセス制御 (MAC) アドレスは、通常、電話の製造時に割り当てられ、デバイス ハードウェアに組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="00229-p116">Unique identifier for the network interface on the IP phone. The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="00229-p117">特定の MAC アドレスに関係するレコードを検索するには、そのアドレスを入力します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="00229-p117">To search for records pertaining to a specific MAC address simply enter that address. For example:</span></span></p>
<p><span data-ttu-id="00229-182">00-08-5D-16-16-48</span><span class="sxs-lookup"><span data-stu-id="00229-182">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="00229-p118">アドレスの全体を入力しなければなりません。アドレスの一部 (たとえば、00-08-5D) を入力してもデータは返されません。</span><span class="sxs-lookup"><span data-stu-id="00229-p118">You must enter the complete address. A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00229-185">[<strong>この日数より前の最後のアクティビティ</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-185"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-186">次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="00229-186">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="00229-187">[All]</span><span class="sxs-lookup"><span data-stu-id="00229-187">[All]</span></span></p></li>
<li><p><span data-ttu-id="00229-188">10  </span><span class="sxs-lookup"><span data-stu-id="00229-188">10</span></span></p></li>
<li><p><span data-ttu-id="00229-189">1280</span><span class="sxs-lookup"><span data-stu-id="00229-189">20</span></span></p></li>
<li><p><span data-ttu-id="00229-190">31</span><span class="sxs-lookup"><span data-stu-id="00229-190">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00229-191">[<strong>この日数より前の最後のログオフ時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-191"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-192">次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="00229-192">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="00229-193">[All]</span><span class="sxs-lookup"><span data-stu-id="00229-193">[All]</span></span></p></li>
<li><p><span data-ttu-id="00229-194">10  </span><span class="sxs-lookup"><span data-stu-id="00229-194">10</span></span></p></li>
<li><p><span data-ttu-id="00229-195">1280</span><span class="sxs-lookup"><span data-stu-id="00229-195">20</span></span></p></li>
<li><p><span data-ttu-id="00229-196">31</span><span class="sxs-lookup"><span data-stu-id="00229-196">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00229-197">[<strong>ユーザー URI プレフィックス</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-197"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-198">IP 電話を使用したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="00229-198">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="00229-199">指標</span><span class="sxs-lookup"><span data-stu-id="00229-199">Metrics</span></span>

<span data-ttu-id="00229-200">次の表に、IP 電話インベントリ レポートで提供される情報を示します。</span><span class="sxs-lookup"><span data-stu-id="00229-200">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="00229-201">IP 電話インベントリ レポートの指標</span><span class="sxs-lookup"><span data-stu-id="00229-201">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00229-202">名前</span><span class="sxs-lookup"><span data-stu-id="00229-202">Name</span></span></th>
<th><span data-ttu-id="00229-203">この項目での並べ替え</span><span class="sxs-lookup"><span data-stu-id="00229-203">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="00229-204">説明</span><span class="sxs-lookup"><span data-stu-id="00229-204">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00229-205"><strong>製造</strong></span><span class="sxs-lookup"><span data-stu-id="00229-205"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-206">必要</span><span class="sxs-lookup"><span data-stu-id="00229-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="00229-207">IP 電話を製造した会社の名前。</span><span class="sxs-lookup"><span data-stu-id="00229-207">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00229-208">[<strong>ハードウェア バージョン</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-208"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-209">必要</span><span class="sxs-lookup"><span data-stu-id="00229-209">Yes</span></span></p></td>
<td><p><span data-ttu-id="00229-210">IP 電話のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="00229-210">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00229-211">[<strong>MAC アドレス</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-211"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-212">必要</span><span class="sxs-lookup"><span data-stu-id="00229-212">Yes</span></span></p></td>
<td><p><span data-ttu-id="00229-p119">IP 電話のネットワーク インターフェイスの一意の識別子。MAC アドレスは、通常、電話の製造時に割り当てられ、デバイス ハードウェアに組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="00229-p119">Unique identifier for the network interface on the IP phone. The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00229-215">[<strong>ユーザー URI</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-215"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-216">必要</span><span class="sxs-lookup"><span data-stu-id="00229-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="00229-217">IP 電話を使用したユーザーの SIP アドレス。</span><span class="sxs-lookup"><span data-stu-id="00229-217">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00229-218">[<strong>ユーザー エージェント</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-218"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-219">必要</span><span class="sxs-lookup"><span data-stu-id="00229-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="00229-220">IP 電話で使われているソフトウェアの識別子。</span><span class="sxs-lookup"><span data-stu-id="00229-220">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00229-221">[<strong>最後にログオンした時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-221"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-222">必要</span><span class="sxs-lookup"><span data-stu-id="00229-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="00229-223">IP 電話が Lync Server に最後にログオンした日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="00229-223">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="00229-224">[<strong>最後にログオフした時刻</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-224"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-225">必要</span><span class="sxs-lookup"><span data-stu-id="00229-225">Yes</span></span></p></td>
<td><p><span data-ttu-id="00229-226">IP 電話が Lync Server から前回ログオフした日時。</span><span class="sxs-lookup"><span data-stu-id="00229-226">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00229-227">[<strong>最後のアクティビティ</strong>]</span><span class="sxs-lookup"><span data-stu-id="00229-227"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="00229-228">必要</span><span class="sxs-lookup"><span data-stu-id="00229-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="00229-229">IP 電話が最後に使われた日時。</span><span class="sxs-lookup"><span data-stu-id="00229-229">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

