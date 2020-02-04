---
title: 'Lync Server 2013: 代理トランザクションでのリッチログの使用'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48efc99a49fd41678d07eef8685bc7f045397aa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="8ec32-102">Lync Server 2013 での代理トランザクションに対するリッチログの使用</span><span class="sxs-lookup"><span data-stu-id="8ec32-102">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ec32-103">_**最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8ec32-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8ec32-104">代理トランザクション (Microsoft Lync Server 2010 で導入されました) では、管理者は、システムへのログオン、インスタントメッセージの交換、または特定の電話への通話の発信などの一般的なタスクを正常に完了できることを管理者が確認する方法を提供します。[公衆交換電話網 (PSTN)] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-104">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="8ec32-105">これらのテスト (Lync Server Windows PowerShell コマンドレットのセットとしてパッケージ化されているもの) は、管理者によって手動で実行することも、System Center Operations Manager などのアプリケーションで自動的に実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-105">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="8ec32-106">Lync Server 2010 では、管理者がシステムの問題を特定するのに役立つように、代理トランザクションが非常に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-106">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="8ec32-107">たとえば、 **CsRegistration**コマンドレットを使用すると、一部のユーザーが Lync Server への登録に障碍があることを管理者に通知することができます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-107">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="8ec32-108">ただし、代理トランザクションは、管理者が Lync Server に登録できない理由を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-108">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="8ec32-109">これは、管理者が Lync Server の問題のトラブルシューティングを行うときに役立つ詳細なログ情報が、代理トランザクションによって提供されなかったことが原因です。</span><span class="sxs-lookup"><span data-stu-id="8ec32-109">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="8ec32-110">最善策として、合成トランザクションからの冗長な出力について説明しました。管理者は、問題が発生した可能性のある箇所についての知識を得ることができる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ec32-110">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="8ec32-111">Microsoft Lync Server 2013 では、リッチなログを提供するために、代理トランザクションが再設計されています。</span><span class="sxs-lookup"><span data-stu-id="8ec32-111">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="8ec32-112">"リッチログ" とは、代理トランザクション請け負うの各アクティビティについて、次のような情報が記録されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8ec32-112">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="8ec32-113">アクティビティが開始された時刻</span><span class="sxs-lookup"><span data-stu-id="8ec32-113">The time that the activity started</span></span>

  - <span data-ttu-id="8ec32-114">アクティビティが完了した時刻</span><span class="sxs-lookup"><span data-stu-id="8ec32-114">The time that the activity finished</span></span>

  - <span data-ttu-id="8ec32-115">実行されたアクション (たとえば、会議の作成、参加、退席、Lync サーバーへのサインイン、インスタントメッセージの送信など)</span><span class="sxs-lookup"><span data-stu-id="8ec32-115">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="8ec32-116">アクティビティが行われたときに生成された、情報提供メッセージ、詳細メッセージ、警告メッセージ、またはエラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="8ec32-116">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="8ec32-117">SIP 登録メッセージ</span><span class="sxs-lookup"><span data-stu-id="8ec32-117">SIP registration messages</span></span>

  - <span data-ttu-id="8ec32-118">アクティビティの実行時に生成される例外レコードまたは診断コード</span><span class="sxs-lookup"><span data-stu-id="8ec32-118">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="8ec32-119">アクティビティを実行した場合の最終的な結果</span><span class="sxs-lookup"><span data-stu-id="8ec32-119">The net result of running the activity</span></span>

<span data-ttu-id="8ec32-120">この情報は、代理トランザクションが実行されるたびに自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-120">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="8ec32-121">ただし、情報が自動的に表示されたり、ログファイルに保存されたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="8ec32-121">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="8ec32-122">代わりに、代理トランザクションを手動で実行している管理者は、OutLoggerVariable パラメーターを使って、情報が格納される Windows PowerShell 変数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-122">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="8ec32-123">このような場合、管理者は、XML 形式または HTML 形式のリッチログの保存や表示を行うことができるようにする一連のメソッドを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-123">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="8ec32-124">たとえば、Lync Server 2010 管理者は、次のようなコマンドを使用して、 **CsRegistration**コマンドレットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-124">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="8ec32-125">管理者には、OutLoggerVariable パラメーターと、その後に選択する変数名を含めるオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8ec32-125">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="8ec32-126">変数名の先頭に $ 文字を付けないでください。</span><span class="sxs-lookup"><span data-stu-id="8ec32-126">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="8ec32-127">RegistrationTest などの変数名を使用しますが、$RegistrationTest は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="8ec32-127">Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="8ec32-128">上のコマンドを実行すると、次のような内容が出力されます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-128">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="8ec32-129">ただし、このエラーには、上に示したエラーメッセージだけでなく、さらに詳細な情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="8ec32-129">However, much more detailed information is available for this failure than just the error message shown above.</span></span> <span data-ttu-id="8ec32-130">HTML 形式でその情報にアクセスするには、次のようなコマンドを使用して、変数 RegistrationTest に保存されている情報を HTML ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="8ec32-130">To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="8ec32-131">別の方法として、ToXML() メソッドを使用して、XML ファイルにデータを保存できます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-131">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="8ec32-132">これらのファイルは、Internet Explorer、Visual Studio、または HTML/XML ファイルを開くことができるその他のアプリケーションを使って表示できます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-132">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="8ec32-133">System Center Operations Manager の内部で実行される代理トランザクションでは、エラーのログファイルが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="8ec32-133">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="8ec32-134">ただし、Windows PowerShell が代理トランザクションを読み込んで実行できない場合は、これらのログは生成されません。</span><span class="sxs-lookup"><span data-stu-id="8ec32-134">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="8ec32-135">既定では、Lync Server 2013 は共有されていないフォルダーにログファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="8ec32-135">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="8ec32-136">これらのログにアクセスできるようにするには、このフォルダーを共有\\ \\する必要があります (例: litwareinc com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="8ec32-136">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

