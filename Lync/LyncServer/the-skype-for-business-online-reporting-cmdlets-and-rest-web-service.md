---
title: Skype for Business Online のレポートコマンドレットと REST web サービス
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f40d394ba69cf017c11d4eb6cd57246a9d425c0f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755701"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="049c8-102">Skype for Business Online のレポートコマンドレットと REST web サービス</span><span class="sxs-lookup"><span data-stu-id="049c8-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="049c8-103">_**トピックの最終更新日:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="049c8-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="049c8-104">レポート機能と共に、Skype for Business Online は5つの Windows PowerShell コマンドレットへのアクセスを提供します。これらのレポートは、これらのレポートを生成するのに役立ちます。また、管理者がカスタマイズされたレポートデータを返すために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="049c8-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="049c8-105">また、Skype for Business Online には、開発者がカスタマイズされたレポート情報を取得するために使用できる REST ("対象の状態転送") も含まれています。</span><span class="sxs-lookup"><span data-stu-id="049c8-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="049c8-106">管理者が使用可能なレポートのコマンドレットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="049c8-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="049c8-107">Get-CsActiveUserReport。アクティブユーザーの数 (つまり、少なくとも1つの会議またはピアツーピアの通信セッションに参加しているユーザー) の数に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="049c8-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="049c8-108">Get-csavconferencetimereport には、音声ビデオ会議で費やした時間 (分単位) に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="049c8-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="049c8-109">Get-csconferencereport。ユーザーが参加した電話会議の数と種類に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="049c8-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="049c8-110">Get-csp2pavtimereport には、音声やビデオを含むピアツーピアセッションで費やした時間 (分単位) に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="049c8-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="049c8-111">Get-csp2psessionreport。ユーザーが参加したピアツーピアセッションの数と種類に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="049c8-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="049c8-112">ほとんどの管理者は、Microsoft 365 管理センターで利用可能なレポートを使用します。これらのレポートは自動生成されるだけでなく、レポート作成コマンドレットによって返される生の数値よりも簡単に解釈できるデータをグラフィカルに表示します。</span><span class="sxs-lookup"><span data-stu-id="049c8-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="049c8-113">ただし、Windows PowerShell を使い慣れている管理者は、レポート作成コマンドレットを使用して、Lync Online レポートからすぐに利用できないデータを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="049c8-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="049c8-114">たとえば、レポートコマンドレットは、セッション時間 (各セッションが持続する時間) に関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="049c8-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="049c8-115">各セッション期間は、Lync Online レポートを使用して使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="049c8-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="049c8-116">同様に、毎日表示される Lync Online レポートには、過去14日間の情報のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="049c8-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="049c8-117">日単位の合計 (たとえば、4か月前の日付) を確認したい場合は、レポート作成コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="049c8-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="049c8-118">また、管理者は[excel を使用して office 365 レポートデータを取得](https://msdn.microsoft.com/library/dn781442.aspx)することもできます。この記事では、Microsoft Excel の OData データ照会機能を使用してカスタムの office 365 レポートを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="049c8-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](https://msdn.microsoft.com/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="049c8-119">カスタムレポートを使用すると、Office 365 reporting service から返されるデータ (およびデータ量) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="049c8-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="049c8-120">また、カスタムレポートを使用すると、データの並べ替えやグループ化の方法を指定したり、管理センターに表示されていない情報へのアクセスを提供したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="049c8-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="049c8-121">開発のバックグラウンドを備えた管理者は、REST web サービスを使用して、Skype for Business Online 管理センターに表示されていない情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="049c8-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="049c8-122">REST サービスは SOAP サービスに似ていますが、各テクノロジでクライアントとサーバーの間で XML データを転送する方法が提供されています。</span><span class="sxs-lookup"><span data-stu-id="049c8-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="049c8-123">ただし、REST サービスには、SOAP サービスよりも少なくとも2つの利点があります。</span><span class="sxs-lookup"><span data-stu-id="049c8-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="049c8-124">1つの場合、REST は ATOM シンジケーション形式という標準形式を使用して XML データ転送を実行します。</span><span class="sxs-lookup"><span data-stu-id="049c8-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="049c8-125">対照的に、データを転送するときに、非標準形式を使用する SOAP。</span><span class="sxs-lookup"><span data-stu-id="049c8-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="049c8-126">また、REST は、GET と POST 以外の HTTP 動詞をブロックするネットワーク間でデータを転送することができます。</span><span class="sxs-lookup"><span data-stu-id="049c8-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="049c8-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="049c8-127">See Also</span></span>


<span data-ttu-id="049c8-128">[Lync Online レポート](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="049c8-128">[Lync Online reporting](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="049c8-129">Office 365 Reporting Web サービス</span><span class="sxs-lookup"><span data-stu-id="049c8-129">The Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[<span data-ttu-id="049c8-130">Office 365 レポート Web サービスについての学習</span><span class="sxs-lookup"><span data-stu-id="049c8-130">Learning About the Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984321.aspx)  
<span data-ttu-id="049c8-131">[Exchange Online レポートのコマンドレット](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="049c8-131">[The Exchange Online Reporting Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="049c8-132">Excel を使用して Office 365 レポート データを取得する</span><span class="sxs-lookup"><span data-stu-id="049c8-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

