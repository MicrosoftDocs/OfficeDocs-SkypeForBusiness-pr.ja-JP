---
title: 'Lync Server 2013: 代理トランザクションに対してリッチログを使用する'
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
ms.openlocfilehash: b1fd1cfd26e1b5d56a6043e13d348e73e3c2b108
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="76891-102">Lync Server 2013 で代理トランザクションに対してリッチログを使用する</span><span class="sxs-lookup"><span data-stu-id="76891-102">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76891-103">_**トピックの最終更新日:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="76891-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="76891-104">代理トランザクション (Microsoft Lync Server 2010 で導入されたもの) は、管理者が、システムへのログオン、インスタントメッセージの交換、または特定の電話への通話の作成などの一般的なタスクを、ユーザーが正常に完了できたことを確認する方法を提供します。公衆交換電話網 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="76891-104">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="76891-105">これらのテスト (Lync Server Windows PowerShell コマンドレットのセットとしてパッケージ化されたもの) は、管理者によって手動で実行することも、System Center Operations Manager などのアプリケーションによって自動的に実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="76891-105">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="76891-106">Lync Server 2010 では、代理トランザクションは、システムの問題を特定するために管理者を支援するために非常に役立つことが実証されています。</span><span class="sxs-lookup"><span data-stu-id="76891-106">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="76891-107">たとえば、 **Test-CsRegistration**コマンドレットを使用すると、一部のユーザーが Lync Server に登録するのに困難があるという事実を管理者に通知できます。</span><span class="sxs-lookup"><span data-stu-id="76891-107">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="76891-108">ただし、代理トランザクションは、管理者が Lync Server への登録を困難にした理由を判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="76891-108">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="76891-109">これは、代理トランザクションが Lync Server の問題のトラブルシューティングに役立つ可能性がある詳細なログ情報を提供していないためです。</span><span class="sxs-lookup"><span data-stu-id="76891-109">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="76891-110">せいぜい、代理トランザクションからの詳細出力では、問題がどこで発生したかを管理者が推測できる、ステップごとの情報を示すだけでした。</span><span class="sxs-lookup"><span data-stu-id="76891-110">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="76891-111">Microsoft Lync Server 2013 では、代理トランザクションは、リッチログを提供するように再設計されています。</span><span class="sxs-lookup"><span data-stu-id="76891-111">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="76891-112">"高機能なログ記録" とは、代理トランザクションが行う各アクティビティについて、以下のような情報が記録されるということです。</span><span class="sxs-lookup"><span data-stu-id="76891-112">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="76891-113">アクティビティが開始した時間</span><span class="sxs-lookup"><span data-stu-id="76891-113">The time that the activity started</span></span>

  - <span data-ttu-id="76891-114">アクティビティが終了した時間</span><span class="sxs-lookup"><span data-stu-id="76891-114">The time that the activity finished</span></span>

  - <span data-ttu-id="76891-115">実行されたアクション (たとえば、会議の作成、参加、または退室、Lync Server へのサインオン、インスタントメッセージの送信など)</span><span class="sxs-lookup"><span data-stu-id="76891-115">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="76891-116">アクティビティが行われたとき生成された、情報提供メッセージ、詳細メッセージ、警告メッセージ、またはエラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="76891-116">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="76891-117">SIP 登録メッセージ</span><span class="sxs-lookup"><span data-stu-id="76891-117">SIP registration messages</span></span>

  - <span data-ttu-id="76891-118">アクティビティが行われたとき生成された例外レコードまたは診断コード</span><span class="sxs-lookup"><span data-stu-id="76891-118">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="76891-119">アクティビティを実行した全体的な結果</span><span class="sxs-lookup"><span data-stu-id="76891-119">The net result of running the activity</span></span>

<span data-ttu-id="76891-120">代理トランザクションが実行されるたびに、この情報は自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="76891-120">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="76891-121">しかし、この情報は、自動的に表示されることや、ログ ファイルに保存されることはありません。</span><span class="sxs-lookup"><span data-stu-id="76891-121">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="76891-122">代わりに、代理トランザクションを手動で実行している管理者は、OutLoggerVariable パラメーターを使用して、情報を格納する Windows PowerShell 変数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="76891-122">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="76891-123">次に、管理者は、ペアのメソッドを使用して、リッチ ログを XML または HTML 形式で、保存または表示できます。</span><span class="sxs-lookup"><span data-stu-id="76891-123">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="76891-124">たとえば、Lync Server 2010 の管理者は、次のようなコマンドを使用して、 **CsRegistration**コマンドレットを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="76891-124">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="76891-125">管理者は、OutLoggerVariable パラメーターと、それに続く任意の変数名を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="76891-125">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="76891-p105">変数名の前に $ 記号を付けないでください。$RegistrationTest ではなく、RegistrationTest のような変数名を使用します。</span><span class="sxs-lookup"><span data-stu-id="76891-p105">Do not preface the variable name with the $ character. Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="76891-128">前記のコマンドは、以下のような内容を出力します。</span><span class="sxs-lookup"><span data-stu-id="76891-128">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="76891-p106">実際には、この障害については、上記のエラー メッセージだけでなく、より詳細な情報を参照できます。この情報に HTML 形式でアクセスするには、以下のようなコマンドを使用して、変数 RegistrationTest に保存された情報を HTML ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="76891-p106">However, much more detailed information is available for this failure than just the error message shown above. To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="76891-131">別の方法として、ToXML() メソッドを使用して、XML ファイルにデータを保存できます。</span><span class="sxs-lookup"><span data-stu-id="76891-131">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="76891-132">これらのファイルは、Internet Explorer、Visual Studio、または HTML/XML ファイルを開くことができるその他のアプリケーションを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="76891-132">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="76891-133">System Center Operations Manager の内部から実行される代理トランザクションは、エラーが発生したときにこれらのログファイルを自動的に生成します。</span><span class="sxs-lookup"><span data-stu-id="76891-133">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="76891-134">ただし、これらのログは、Windows PowerShell が代理トランザクションを読み込んで実行できるようになる前に、実行が失敗した場合は生成されません。</span><span class="sxs-lookup"><span data-stu-id="76891-134">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="76891-135">既定では、Lync Server 2013 は、共有されていないフォルダーにログファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="76891-135">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="76891-136">このようなログにアクセスできるようにするには、このフォルダーを\\ \\共有する必要があります (例: litwareinc。 com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="76891-136">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

