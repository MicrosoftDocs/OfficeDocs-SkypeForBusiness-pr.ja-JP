---
title: 'Lync Server 2013: CDR 構成設定のコレクションを作成または変更する'
description: 'Lync Server 2013: CDR 構成設定のコレクションを作成または変更します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba911607db55a7b7206645495e70a27ed453784
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578333"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e8890-103">Lync Server 2013 での CDR 構成設定のコレクションの作成または変更</span><span class="sxs-lookup"><span data-stu-id="e8890-103">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8890-104">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e8890-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e8890-p101">通話詳細記録 (CDR) では、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e8890-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="e8890-107">Microsoft Lync Server 2013 をインストールすると、1つのグローバルな CDR 構成設定のグローバルコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e8890-107">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="e8890-108">管理者は、サイト スコープでカスタム設定を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8890-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="e8890-109">これらのサイト スコープの設定が使用されるときは常に、グローバル設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="e8890-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="e8890-110">たとえば、レドモンド サイトにサイト スコープの設定を作成する場合、レドモンドでの CDR の管理には (グローバル設定ではなく) それらの設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8890-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="e8890-111">CDR 構成設定は、Lync Server コントロールパネルまたは [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) コマンドレットのいずれかを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="e8890-111">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="e8890-112">Lync Server コントロールパネルまたは [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) コマンドレットを使用して、既存の設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e8890-112">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="e8890-113">Lync Server コントロールパネルを使用して設定を作成または変更する場合は、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8890-113">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8890-114">UI 設定</span><span class="sxs-lookup"><span data-stu-id="e8890-114">UI Setting</span></span></th>
<th><span data-ttu-id="e8890-115">PowerShell パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8890-115">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="e8890-116">説明</span><span class="sxs-lookup"><span data-stu-id="e8890-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8890-117">名前</span><span class="sxs-lookup"><span data-stu-id="e8890-117">Name</span></span></p></td>
<td><p><span data-ttu-id="e8890-118">ID</span><span class="sxs-lookup"><span data-stu-id="e8890-118">Identity</span></span></p></td>
<td><p><span data-ttu-id="e8890-p104">作成する CDR 構成設定に対する一意の識別子。これらの設定はサイト スコープでのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="e8890-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8890-121">CDR の監視を有効にする</span><span class="sxs-lookup"><span data-stu-id="e8890-121">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="e8890-122">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="e8890-122">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="e8890-123">CDR を有効にするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e8890-123">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8890-124">CDR の削除を有効にする</span><span class="sxs-lookup"><span data-stu-id="e8890-124">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="e8890-125">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="e8890-125">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="e8890-126">CDR の記録を CDR データベースから定期的に削除するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e8890-126">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8890-127">Keep CDRs for maximum duration (days) (CDR の最大保持期間 (日))</span><span class="sxs-lookup"><span data-stu-id="e8890-127">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="e8890-128">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="e8890-128">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="e8890-p105">CDR データベースに CDR レコードを保持する日数を示します。指定された日数より古いレコードは、自動的に削除されます (削除が実行されるのは、削除が有効になっている場合のみです)。</span><span class="sxs-lookup"><span data-stu-id="e8890-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8890-132">エラー報告データを保持する最大期間 (日数)</span><span class="sxs-lookup"><span data-stu-id="e8890-132">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="e8890-133">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="e8890-133">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="e8890-p106">CDR エラー報告を保持する日数を指定します。指定した日数を超えて保持されている報告は、自動的に削除されます。CDR エラー報告は、クライアント アプリケーションによってアップロードされる診断レポートです。</span><span class="sxs-lookup"><span data-stu-id="e8890-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e8890-137">New-CsCdrConfiguration および Set-CsCdrConfiguration コマンドレットには、Lync Server コントロールパネルでは使用できない追加オプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8890-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="e8890-138">詳細については、 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">set-cscdrconfiguration</A> および <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">set-cscdrconfiguration</A> ヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8890-138">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="e8890-139">Lync Server コントロールパネルを使用して CDR 構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="e8890-139">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e8890-140">Lync Server コントロールパネルで **、[監視とアーカイブ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8890-140">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="e8890-141">[ **通話詳細記録** ] タブで、[ **新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8890-141">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="e8890-p108">[**サイトの選択**] ダイアログ ボックスで、新しい構成設定を作成するサイトを選択します。ダイアログ ボックスに何も表示されない場合は、すべてのサイトが CDR 構成設定のコレクションに割り当て済みであることを意味します。各サイトに対してこのようなコレクション 1 つに制限されています。その場合、設定を削除してから再作成するか、単純に既存の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e8890-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="e8890-146">[**新しい通話詳細記録 (CDR) 設定を作成する**] ダイアログで、任意に選択を行ってから [**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8890-146">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="e8890-147">Lync Server コントロールパネルを使用して既存の CDR 構成設定を変更するには</span><span class="sxs-lookup"><span data-stu-id="e8890-147">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e8890-148">Lync Server コントロールパネルで **、[監視とアーカイブ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8890-148">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="e8890-149">変更する設定のコレクションをダブルクリックするか、コレクションを選択して [**編集**] をクリックし、さらに [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8890-149">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="e8890-150">一度に変更できるのは 1 つのコレクションだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e8890-150">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="e8890-151">複数のコレクションに同じ変更を加えるには、代わりに Lync Server 管理シェルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8890-151">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="e8890-152">[**編集 通話詳細記録 (CDR) 設定**] ダイアログで、任意の選択を行ってから [**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8890-152">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e8890-153">Windows PowerShell コマンドレットを使用して CDR 構成設定を作成する</span><span class="sxs-lookup"><span data-stu-id="e8890-153">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e8890-154">CDR 構成設定は、Windows PowerShell および **set-cscdrconfiguration** コマンドレットを使用して作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8890-154">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="e8890-155">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="e8890-155">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e8890-156">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8890-156">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="e8890-157">新しい CDR 構成設定のコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="e8890-157">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="e8890-158">このコマンドを実行すると、レドモンド サイトに適用される新しい CDR 構成設定のコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e8890-158">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="e8890-159">通話詳細記録を無効にする CDR 構成設定のコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="e8890-159">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="e8890-p111">前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。たとえば、既定では通話詳細記録の無効化を許可する通話詳細の構成設定のコレクションを作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8890-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="e8890-163">新しい CDR 構成設定のコレクションの作成時に複数のプロパティ値を指定するには</span><span class="sxs-lookup"><span data-stu-id="e8890-163">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="e8890-p112">複数のパラメーターを含めることで、複数のプロパティ値を変更できます。たとえば、このコマンドを実行すると、通話詳細記録を 30 日間保持し、エラー レポートを 90 日間保持するための新しい設定が構成されます。</span><span class="sxs-lookup"><span data-stu-id="e8890-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="e8890-166">詳細については、 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8890-166">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

