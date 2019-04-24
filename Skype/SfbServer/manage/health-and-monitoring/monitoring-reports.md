---
title: Skype ビジネス サーバーの監視のレポートの使用
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
description: '概要: Skype でレポートをビジネスのサーバーの監視について説明します。'
ms.openlocfilehash: 11eb398d45102cb73fa02e61f63e0eda56e70200
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199678"
---
# <a name="using-monitoring-reports-in-skype-for-business-server"></a><span data-ttu-id="0424a-103">Skype ビジネス サーバーの監視のレポートの使用</span><span class="sxs-lookup"><span data-stu-id="0424a-103">Using Monitoring Reports in Skype for Business Server</span></span> 
 
<span data-ttu-id="0424a-104">**の概要:** Skype でレポートをビジネスのサーバーの監視について説明します。</span><span class="sxs-lookup"><span data-stu-id="0424a-104">**Summary:** Learn about Monitoring Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="0424a-105">Skype ビジネス サーバー用には、Microsoft SQL Server レポート サービスによって公開されている標準的なレポートのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0424a-105">Skype for Business Server includes a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="0424a-106">アクセスできる web ブラウザーを使用して、これらのレポートは、使用法、通話診断情報、およびメディアの品質については、すべてに基づく通話の詳細記録 (CDR) と高品質のエクスペリエンス (QoE) レコードが、CDR および QoE データベースに格納されているを提供します。</span><span class="sxs-lookup"><span data-stu-id="0424a-106">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span>
  
<span data-ttu-id="0424a-107">これらのレポートを使用するには、SQL Server のインスタンスを実行しているコンピューターの監視レポートをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0424a-107">To use these reports, you must install Monitoring Reports on a computer that is running an instance of the SQL Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0424a-108">このセクション中</span><span class="sxs-lookup"><span data-stu-id="0424a-108">In This Section</span></span>

- <span data-ttu-id="0424a-109">[Skype ビジネス サーバーの監視のダッシュ ボードを使用します。](monitoring-dashboard.md)システムの健全性とシステムの使用状況の概要を管理者に提供します。</span><span class="sxs-lookup"><span data-stu-id="0424a-109">[Using the Monitoring Dashboard in Skype for Business Server](monitoring-dashboard.md) Provides administrators with a quick overview of their system health and system usage.</span></span>
    
- <span data-ttu-id="0424a-110">[ビジネス サーバーの Skype でのシステム使用状況レポート](system-usage-reports.md)ビジネス サーバーは、Skype で収集したデータを CDR に基づくシステムの使用状況に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0424a-110">[System usage reports in Skype for Business Server](system-usage-reports.md) Provides system usage information based on CDR data collected by Skype for Business Server.</span></span>
    
- <span data-ttu-id="0424a-111">[呼び出す診断レポート (ユーザー) ごと](call-diagnostic-reports-per-user.md)失敗したピア ツー ピア セッションおよび会議セッションのユーザーごとの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0424a-111">[Call Diagnostic Reports (per user) in Skype for Business Server](call-diagnostic-reports-per-user.md) Provides per-user information about failed peer-to-peer and conferencing sessions.</span></span>
    
- <span data-ttu-id="0424a-112">[Skype ビジネス サーバーの診断レポートを呼び出す](call-diagnostic-reports.md)要約情報と失敗したピア ツー ピア会議セッションの診断データを提供します。</span><span class="sxs-lookup"><span data-stu-id="0424a-112">[Call Diagnostic Reports in Skype for Business Server](call-diagnostic-reports.md) Provides summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>
    
- <span data-ttu-id="0424a-113">[ビジネス サーバーの Skype でのメディア品質診断レポート](media-quality-diagnostic-reports.md)呼び出しの失敗の診断およびトラブルシューティングの情報だけでなく、通話の品質に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0424a-113">[Media Quality Diagnostic Reports in Skype for Business Server](media-quality-diagnostic-reports.md) Provides information about call quality as well as diagnostic and troubleshooting information for failed calls.</span></span>
    
## <a name="locating-records"></a><span data-ttu-id="0424a-114">レコードの検索</span><span class="sxs-lookup"><span data-stu-id="0424a-114">Locating Records</span></span>

<span data-ttu-id="0424a-115">監視レポートで画面上に一度に表示されるレコードの数は限られています。</span><span class="sxs-lookup"><span data-stu-id="0424a-115">Monitoring Reports only show a limited number of records on the screen at any one time.</span></span> <span data-ttu-id="0424a-116">実際に画面に表示されるレコードの数は、レポートによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0424a-116">The actual number of records displayed on a screen varies depending on the report.</span></span> <span data-ttu-id="0424a-117">画面に現在表示されていないレコードを表示するのには、標準的な前方および後方コントロール (各レポートのツールバーにあります) を使用してデータを複数のページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0424a-117">To view the records that are not currently shown on the screen you can use the standard forward and backward control (found on each report's toolbar) that enable you to page through the data.</span></span> <span data-ttu-id="0424a-118">また、データセットの最初または最後のページにすばやく移動できます。</span><span class="sxs-lookup"><span data-stu-id="0424a-118">You can also quickly jump to the first page or the last page of the dataset.</span></span>
  
<span data-ttu-id="0424a-119">"進む" と "戻る" のコントロールを使用する以外に、[**現在のページ**] ボックスにページ番号を入力して Enter キーを押すだけで、データセットの任意のページに移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="0424a-119">In addition to using the forward and backward controls, you can also jump to any page in the dataset simply by typing the page number in the **Current Page** box, and then press ENTER.</span></span>
  
<span data-ttu-id="0424a-p103">各レポートには、データの表示ページを切り替える機能だけでなく、制限付きのレコード検索の機能も用意されています。特定の値に基づいてレコードを検索するには、その値を [**検索**] ボックスに入力し、[**検索**] をクリックします。レポートでデータの検索が開始され、[**検索**] ボックスに入力した値の最初のインスタンスが見つかると検索は停止します。検索基準を満たす次のレコードを探すには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0424a-p103">In addition to providing the ability to page through the data, each report also includes the limited ability to find records. To find records based on a given value, type that value into the **Find** box, and then click **Find**. The report begins searching through the data and stops on the first instance of the value that you entered in the **Find** box. To find the next record that meets the search criteria, click **Next**.</span></span>
  
<span data-ttu-id="0424a-p104">前述のとおり、監視レポートには非常に基本的な検索機能しかありません。たとえば、どのフィールドで値を検索するのかは指定できません。この検索メカニズムでは、自動的にすべてのレコードのすべてのフィールドを対象にして一致する値の検索が行われます。また、検索にワイルドカードは使用できず、すべての検索は値の部分一致に基づいて行われます。つまり、"111" を検索した場合は、111 という値だけでなく、11100、811、3112、611A5B といった値や、フィールド内のどこかに "111" が含まれるその他すべてのフィールドも返されます。</span><span class="sxs-lookup"><span data-stu-id="0424a-p104">As noted, the Monitoring Reports provide only the most basic search functions. For example, you cannot specify which field the value should be found in. The search mechanism automatically searches for matching values in every field in every record. You cannot use wildcards in your searches, and all searches look for partial values. That means that if you search for 111 the search returns the value 111 along with the values 11100, 811, 3112, 611A5B, and any other fields that include the value 111 anywhere within that field.</span></span>
  
<span data-ttu-id="0424a-129">各レポートは、既定のレコード セットを表示するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="0424a-129">Each report is configured to show a default set of records.</span></span> <span data-ttu-id="0424a-130">たとえば、既定のユーザー登録レポートでは、この 1 週間のユーザー登録アクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0424a-130">For example, by default the User Registration Report shows user registration activities for the past week.</span></span> <span data-ttu-id="0424a-131">場合によっては、レポートによってレコードが 1 つも返されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="0424a-131">In some cases, this might result in a report that returns no records.</span></span> <span data-ttu-id="0424a-132">これは、ユーザー登録がこの 1 週間に一度も行われなかったということです。</span><span class="sxs-lookup"><span data-stu-id="0424a-132">In this case, it means that no user registrations have taken place in the past week.</span></span> <span data-ttu-id="0424a-133">「結果フィルターに一致しないレポート」のメッセージが表示された場合は、フィルターの値を変更してください。 (過去 1 週間ではなく、過去の月には、期間を変更するなど)、クエリを再実行しています。</span><span class="sxs-lookup"><span data-stu-id="0424a-133">If you see the message "No results match the report filters," try changing the filter values (for example, change the time period to the past month rather than the past week) and rerun the query.</span></span> <span data-ttu-id="0424a-134">詳細については、後のセクション「データのフィルター処理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0424a-134">For details, see the "Filtering Data" section later in this topic.</span></span>
  
## <a name="filtering-data"></a><span data-ttu-id="0424a-135">データのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="0424a-135">Filtering Data</span></span>

<span data-ttu-id="0424a-p106">レコードのサブセットのみの検索が必要になることもあります (たとえば、ピアツーピア セッションと会議セッションの両方ではなく、ピアツーピア セッションのみの検索など)。同様に、結果として返されるレコード数の削減が必要になることもあります。既定では、1 つのレポートで表示できる対象がデータ セット内の最初の 1,000 レコードまでに制限されています。こうした問題に対処するために、ほとんどのレポートにはいくつかのフィルター オプションが用意されています。たとえば、2011 年 1 月 1 日から 2011 年 1 月 15 日までの期間のレコードのみを表示する場合は、[**開始**] ボックスに「2011 年 1 月 1 日」、[**終了**] ボックスに「2011 年 1 月 15 日」と入力できます。続いて、[**レポートの表示**] をクリックすると、返されるデータが 2011 年 1 月 1 日から 2011 年 1 月 15 日までに発生したアクティビティのみに制限されます。</span><span class="sxs-lookup"><span data-stu-id="0424a-p106">There will likely be times when you want to look at only a subset of records. For example, only peer-to-peer sessions as opposed to both peer-to-peer sessions and conference sessions. Likewise, there will be times when you need to reduce the number of records that are returned. By default, a report can only display the first 1,000 records in a data set. To address these issues, most reports include a number of filtering options. For example, if you want to view only records for the time period January 1, 2011 through January 15, 2011, you can enter January 1, 2011 in the **From** box and January 15, 2011 in the **To** box. If you then click **View Report**, the returned data will be limited to activities that took place between January 1, 2011 and January 15, 2011.</span></span>
  
<span data-ttu-id="0424a-p107">使用できるフィルターは、表示しているレポートによって異なります。特定のレポートの詳細については、レポートのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0424a-p107">The filters available to you vary depending on the report that you are viewing. For details about a specific report, see the help topic for that report.</span></span>
  
## <a name="exporting-data"></a><span data-ttu-id="0424a-145">データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="0424a-145">Exporting Data</span></span>

<span data-ttu-id="0424a-p108">監視レポートには、レポート内のデータをエクスポートする方法が少なくとも 2 つあります。各レポートの最上部に表示されるツール バーの [**エクスポート**] オプションを使用することです。このオプションを使用するには、[**形式を選択してください**] ドロップダウン リストで適切なエクスポート形式を選択します。使用できる形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0424a-p108">The Monitoring Reports provide at least two different ways to export the data included in a report. You can use the **Export** option in the toolbar that appears at the top of each report. To use this option, select the desired export format from the **Select a format** drop-down list. The following formats are available to you:</span></span>
  
- <span data-ttu-id="0424a-150">レポート データが含まれている XML ファイル</span><span class="sxs-lookup"><span data-stu-id="0424a-150">XML file with report data</span></span>
    
- <span data-ttu-id="0424a-151">CSV (コンマ区切り)</span><span class="sxs-lookup"><span data-stu-id="0424a-151">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="0424a-152">Acrobat (PDF) ファイル</span><span class="sxs-lookup"><span data-stu-id="0424a-152">Acrobat (PDF) file</span></span>
    
- <span data-ttu-id="0424a-153">MHTML (Web アーカイブ)</span><span class="sxs-lookup"><span data-stu-id="0424a-153">MHTML (web archive)</span></span>
    
- <span data-ttu-id="0424a-154">Excel</span><span class="sxs-lookup"><span data-stu-id="0424a-154">Excel</span></span>
    
- <span data-ttu-id="0424a-155">TIFF ファイル</span><span class="sxs-lookup"><span data-stu-id="0424a-155">TIFF file</span></span>
    
- <span data-ttu-id="0424a-156">Word</span><span class="sxs-lookup"><span data-stu-id="0424a-156">Word</span></span>
    
<span data-ttu-id="0424a-p109">形式の選択後、[**エクスポート**] をクリックします。[**ファイルのダウンロード**] ダイアログ ボックスが表示されたら、[**保存**] をクリックします。[**名前を付けて保存**] ダイアログ ボックスで、保存先フォルダーを選択し、ファイル名を入力して、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0424a-p109">After selecting a format, click **Export**. When the **File Download** dialog box appears, click **Save**. In the **Save As** dialog box, select a destination folder, enter a file name, and then click **Save**.</span></span>
  
<span data-ttu-id="0424a-p110">Microsoft OneNote がインストールされている場合は、レポート データを OneNote にコピーすることもできます。そのためには、ツールバーの [**レポートの表示**] ボタンをクリックします。[**OneNote の場所の選択**] ダイアログ ボックスで、データのコピー先となる OneNote のセクションを選択し、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0424a-p110">If you have Microsoft OneNote installed, you can also copy the report data to OneNote. To do this, right-click the **View Report** button on the toolbar. In the **Select Location in OneNote** dialog box select the section in OneNote where you want to copy the data, and then click **OK**.</span></span>
  

