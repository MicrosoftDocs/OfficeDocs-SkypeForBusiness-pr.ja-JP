---
title: 'Lync Server 2013: 監視レポートの使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c37cd0f96ea0dd8e3fa63a851c3c93caf5988c7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a><span data-ttu-id="13c7b-102">Lync Server 2013 での監視レポートの使用</span><span class="sxs-lookup"><span data-stu-id="13c7b-102">Using Monitoring Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13c7b-103">_**トピックの最終更新日:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="13c7b-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="13c7b-104">Lync Server 2013 には、Microsoft SQL Server Reporting Service によって発行される標準レポートのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="13c7b-104">Lync Server 2013 includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="13c7b-105">これらのレポートは、web ブラウザーを使用してアクセスできます。これらのレポートには、使用状況、通話診断情報、およびメディア品質情報があります。これには、CDR および QoE データベースに格納されているすべての通話詳細記録 (CDR) および QoE (Quality of Experience) レコードに基づいています。</span><span class="sxs-lookup"><span data-stu-id="13c7b-105">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>

<span data-ttu-id="13c7b-106">これらのレポートを使用するためには、SQL Server のインスタンスを実行しているコンピューターに監視レポートをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="13c7b-106">In order to use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13c7b-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="13c7b-107">In This Section</span></span>

  - <span data-ttu-id="13c7b-108">[Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   の監視ダッシュボードを使用すると、管理者はシステムの正常性とシステム使用率の概要をすばやく表示できます。</span><span class="sxs-lookup"><span data-stu-id="13c7b-108">[Using the Monitoring Dashboard in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   Provides administrators with a quick overview of their system health and system usage.</span></span>

  - <span data-ttu-id="13c7b-109">[Lync server 2013](lync-server-2013-system-usage-reports.md)   のシステム使用状況レポート lync server で収集された CDR データに基づいてシステム使用状況情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="13c7b-109">[System usage reports in Lync Server 2013](lync-server-2013-system-usage-reports.md)   Provides system usage information based on CDR data collected by Lync Server.</span></span>

  - <span data-ttu-id="13c7b-110">[Lync Server 2013 の通話診断レポート (ユーザーごと)](lync-server-2013-call-diagnostic-reports-per-user.md)   エラーが発生したピアツーピアセッションと電話会議セッションに関する情報をユーザー別に提供します。</span><span class="sxs-lookup"><span data-stu-id="13c7b-110">[Call Diagnostic Reports (per user) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="13c7b-111">[通話診断レポート Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   で、失敗したピアツーピアセッションと電話会議セッションに関する概要情報と診断データが提供されます。</span><span class="sxs-lookup"><span data-stu-id="13c7b-111">[Call Diagnostic Reports in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

  - <span data-ttu-id="13c7b-112">[Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   のメディア品質診断レポート通話品質に関する情報、および失敗した通話の診断およびトラブルシューティングの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="13c7b-112">[Media Quality Diagnostic Reports in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>

</div>

<div>

## <a name="locating-records"></a><span data-ttu-id="13c7b-113">レコードの検索</span><span class="sxs-lookup"><span data-stu-id="13c7b-113">Locating Records</span></span>

<span data-ttu-id="13c7b-p102">監視レポートで画面上に一度に表示されるレコードの数は限られています。実際に画面に表示されるレコードの数は、レポートによって異なります。画面に現在表示されていないレコードを表示する場合は、データの表示ページを切り替えることができる標準の "進む" および "戻る" のコントロール (各レポートのツールバー上にあります) を使用できます。また、データセットの最初または最後のページにすばやく移動できます。</span><span class="sxs-lookup"><span data-stu-id="13c7b-p102">Monitoring Reports only show a limited number of records on the screen at any one time. The actual number of records displayed on a screen varies depending on the report. To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report’s toolbar) that enable you to page through the data. You can also quickly jump to the first page or the last page of the dataset.</span></span>

<span data-ttu-id="13c7b-118">"進む" と "戻る" のコントロールを使用する以外に、[**現在のページ**] ボックスにページ番号を入力して Enter キーを押すだけで、データセットの任意のページに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="13c7b-118">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>

<span data-ttu-id="13c7b-p103">各レポートには、データの表示ページを切り替える機能だけでなく、制限付きのレコード検索の機能も用意されています。特定の値に基づいてレコードを検索するには、その値を [**検索**] ボックスに入力し、[**検索**] をクリックします。レポートでデータの検索が開始され、[**検索**] ボックスに入力した値の最初のインスタンスが見つかると検索は停止します。検索基準を満たす次のレコードを探すには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13c7b-p103">In addition to providing the ability to page through the data, each report also includes the limited ability to find records. To find records based on a given value, type that value into the **Find** box, and then click **Find**. The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box. To find the next record that meets the search criteria, click **Next**.</span></span>

<span data-ttu-id="13c7b-p104">前述のとおり、監視レポートには非常に基本的な検索機能しかありません。たとえば、どのフィールドで値を検索するのかは指定できません。この検索メカニズムでは、自動的にすべてのレコードのすべてのフィールドを対象にして一致する値の検索が行われます。また、検索にワイルドカードは使用できず、すべての検索は値の部分一致に基づいて行われます。つまり、"111" を検索した場合は、111 という値だけでなく、11100、811、3112、611A5B といった値や、フィールド内のどこかに "111" が含まれるその他すべてのフィールドも返されます。</span><span class="sxs-lookup"><span data-stu-id="13c7b-p104">As noted, the Monitoring Reports provide only the most basic search functions. For example, you cannot specify which field the value should be found in. The search mechanism automatically searches for matching values in every field in every record. You cannot use wildcards in your searches, and all searches look for partial values. That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>

<span data-ttu-id="13c7b-p105">各レポートは、既定のレコード セットを表示するように構成されています。たとえば、既定のユーザー登録レポートでは、この 1 週間のユーザー登録アクティビティが表示されます。場合によっては、レポートによってレコードが 1 つも返されないことがあります。これは、ユーザー登録がこの 1 週間に一度も行われなかったということです。"レポート フィルターに一致する結果はありません" というメッセージが表示された場合は、フィルターの値を変更 (たとえば、検索対象の期間を過去 1 週間から過去 1 か月に変更) して、クエリを再実行します。詳細については、後のセクション「データのフィルター処理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13c7b-p105">Each report is configured to show a default set of records. For example, by default the User Registration Report shows user registration activities for the past week. In some cases, this might result in a report that returns no records. In this case, it means that no user registrations have taken place in the past week. If you see the message “No results match the report filters,” try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query. For details, see the "Filtering Data" section later in this topic.</span></span>

</div>

<div>

## <a name="filtering-data"></a><span data-ttu-id="13c7b-134">データのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="13c7b-134">Filtering Data</span></span>

<span data-ttu-id="13c7b-p106">レコードのサブセットのみの検索が必要になることもあります (たとえば、ピアツーピア セッションと会議セッションの両方ではなく、ピアツーピア セッションのみの検索など)。同様に、結果として返されるレコード数の削減が必要になることもあります。既定では、1 つのレポートで表示できる対象がデータ セット内の最初の 1,000 レコードまでに制限されています。こうした問題に対処するために、ほとんどのレポートにはいくつかのフィルター オプションが用意されています。たとえば、2011 年 1 月 1 日から 2011 年 1 月 15 日までの期間のレコードのみを表示する場合は、[**開始**] ボックスに「2011 年 1 月 1 日」、[**終了**] ボックスに「2011 年 1 月 15 日」と入力できます。続いて、[**レポートの表示**] をクリックすると、返されるデータが 2011 年 1 月 1 日から 2011 年 1 月 15 日までに発生したアクティビティのみに制限されます。</span><span class="sxs-lookup"><span data-stu-id="13c7b-p106">There will likely be times when you want to look at only a subset of records. For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions. Likewise, there will be times when you need to reduce the number of records that are returned. By default, a report can only display the first 1,000 records in a data set. To address these issues, most reports include a number of filtering options. For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box. If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>

<span data-ttu-id="13c7b-p107">使用できるフィルターは、表示しているレポートによって異なります。特定のレポートの詳細については、レポートのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="13c7b-p107">The filters available to you vary depending on the report that you are viewing. For details about a specific report, see the help topic for that report.</span></span>

</div>

<div>

## <a name="exporting-data"></a><span data-ttu-id="13c7b-144">データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="13c7b-144">Exporting Data</span></span>

<span data-ttu-id="13c7b-p108">監視レポートには、レポート内のデータをエクスポートする方法が少なくとも 2 つあります。各レポートの最上部に表示されるツールバーの [**エクスポート**] オプションを使用することです。このオプションを使用するには、[**形式を選択してください**] ドロップダウン リストで適切なエクスポート形式を選択します。使用できる形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="13c7b-p108">The Monitoring Reports provide at least two different ways to export the data included in a report. You can use the **Export** option in the toolbar that appears at the top of each report. To use this option, select the desired export format from the **Select a format** drop-down list. The following formats are available to you:</span></span>

  - <span data-ttu-id="13c7b-149">レポート データが含まれている XML ファイル</span><span class="sxs-lookup"><span data-stu-id="13c7b-149">XML file with report data</span></span>

  - <span data-ttu-id="13c7b-150">CSV (コンマ区切り)</span><span class="sxs-lookup"><span data-stu-id="13c7b-150">CSV (comma delimited)</span></span>

  - <span data-ttu-id="13c7b-151">Acrobat (PDF) ファイル</span><span class="sxs-lookup"><span data-stu-id="13c7b-151">Acrobat (PDF) file</span></span>

  - <span data-ttu-id="13c7b-152">MHTML (Web アーカイブ)</span><span class="sxs-lookup"><span data-stu-id="13c7b-152">MHTML (web archive)</span></span>

  - <span data-ttu-id="13c7b-153">Excel</span><span class="sxs-lookup"><span data-stu-id="13c7b-153">Excel</span></span>

  - <span data-ttu-id="13c7b-154">TIFF ファイル</span><span class="sxs-lookup"><span data-stu-id="13c7b-154">TIFF file</span></span>

  - <span data-ttu-id="13c7b-155">Word</span><span class="sxs-lookup"><span data-stu-id="13c7b-155">Word</span></span>

<span data-ttu-id="13c7b-p109">形式の選択後、[**エクスポート**] をクリックします。[**ファイルのダウンロード**] ダイアログ ボックスが表示されたら、[**保存**] をクリックします。[ **名前を付けて保存**] ダイアログ ボックスで、保存先フォルダーを選択し、ファイル名を入力して、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13c7b-p109">After selecting a format, click **Export**. When the **File Download** dialog box appears, click **Save**. In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>

<span data-ttu-id="13c7b-p110">Microsoft OneNote がインストールされている場合は、レポート データを OneNote にコピーすることもできます。そのためには、ツールバーの [**レポートの表示**] ボタンをクリックします。[**OneNote の場所の選択**] ダイアログ ボックスで、データのコピー先となる OneNote のセクションを選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13c7b-p110">If you have Microsoft OneNote installed, you can also copy the report data to OneNote. To do this, right-click the **View Report** button on the toolbar. In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

