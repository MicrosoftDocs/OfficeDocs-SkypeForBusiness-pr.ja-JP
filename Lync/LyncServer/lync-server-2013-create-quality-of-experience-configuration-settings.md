---
title: 'Lync Server 2013: qoe (Quality of Experience) 構成設定の作成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feb0f47ffd0ff2955a783a5fc2912f9f0aaa64ae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="75be5-102">Lync Server 2013 で qoe (Quality of Experience) 構成設定を作成する</span><span class="sxs-lookup"><span data-stu-id="75be5-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75be5-103">_**トピックの最終更新日:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="75be5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="75be5-p101">QoE (Quality of Experience) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="75be5-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="75be5-106">Microsoft Lync Server 2013 をインストールすると、QoE 構成設定のグローバルコレクションが1つ作成されます。</span><span class="sxs-lookup"><span data-stu-id="75be5-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="75be5-107">管理者は、サイト スコープでカスタム設定を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="75be5-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="75be5-108">これらのサイト スコープの設定は、グローバル設定に優先して使用されます。</span><span class="sxs-lookup"><span data-stu-id="75be5-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="75be5-109">たとえば、Redmond サイト用のサイト スコープの設定を作成した場合は、グローバル設定ではなくこれらの設定を使用して Redmond の QoE が管理されます。</span><span class="sxs-lookup"><span data-stu-id="75be5-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="75be5-110">QoE 構成設定を作成するには、Lync Server コントロールパネルまたは[新しい-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration)コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="75be5-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="75be5-111">Lync Server コントロールパネルを使用して新しい設定を作成する場合は、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="75be5-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75be5-112">UI 設定</span><span class="sxs-lookup"><span data-stu-id="75be5-112">UI Setting</span></span></th>
<th><span data-ttu-id="75be5-113">PowerShell パラメーター</span><span class="sxs-lookup"><span data-stu-id="75be5-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="75be5-114">説明</span><span class="sxs-lookup"><span data-stu-id="75be5-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75be5-115">名前</span><span class="sxs-lookup"><span data-stu-id="75be5-115">Name</span></span></p></td>
<td><p><span data-ttu-id="75be5-116">ID</span><span class="sxs-lookup"><span data-stu-id="75be5-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="75be5-p104">作成される設定の一意の ID。QoE 構成設定は、サイト スコープでのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="75be5-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75be5-119">QoE データの監視を有効にする</span><span class="sxs-lookup"><span data-stu-id="75be5-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="75be5-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="75be5-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="75be5-121">QoE レコードを収集し、監視データベースに保存するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="75be5-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75be5-122">QoE データの消去を有効にする</span><span class="sxs-lookup"><span data-stu-id="75be5-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="75be5-123">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="75be5-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="75be5-124">[<strong>QoE データの最大保持期間 (日)</strong>] プロパティに定義された期間が経過した後、レコードを削除するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="75be5-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75be5-125">QoE データの最大保存期間 (日)</span><span class="sxs-lookup"><span data-stu-id="75be5-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="75be5-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="75be5-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="75be5-p105">データベースから削除するまで QoE データを保存する日数。削除が無効の場合、この値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="75be5-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="75be5-129">新しい-CsQoEConfiguration コマンドレットには、Lync Server コントロールパネルでは使用できない追加オプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="75be5-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="75be5-130">詳細については、<A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">新しい-CsQoEConfiguration</A>のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="75be5-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="75be5-131">Lync Server コントロールパネルを使用して QoE 構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="75be5-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="75be5-132">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。</span><span class="sxs-lookup"><span data-stu-id="75be5-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="75be5-133">詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75be5-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="75be5-134">ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="75be5-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="75be5-135">Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75be5-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="75be5-136">左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75be5-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="75be5-137">[**QoE データ**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75be5-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="75be5-138">[**サイトの選択**] でポリシーを適用するサイトをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75be5-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="75be5-139">[**新しい QoE の設定**] で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="75be5-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="75be5-140">[**QoE データの監視を有効にする**] を選択して、監視を有効にします。</span><span class="sxs-lookup"><span data-stu-id="75be5-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="75be5-141">[**QoE データの削除を有効にする**] を選択して、削除を有効にします。</span><span class="sxs-lookup"><span data-stu-id="75be5-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="75be5-142">[**QoE の最大保持期間 (日)**] で、QoE レコードを保持する最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="75be5-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="75be5-143">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75be5-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="75be5-144">Windows PowerShell コマンドレットを使用して QoE 構成設定を作成する</span><span class="sxs-lookup"><span data-stu-id="75be5-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="75be5-145">QoE 構成設定を作成するには、Windows PowerShell と新しい-CsQoEConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="75be5-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="75be5-146">このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="75be5-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="75be5-147">リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。</span><span class="sxs-lookup"><span data-stu-id="75be5-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="75be5-148">QoE 構成設定の新しいコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="75be5-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="75be5-149">次のコマンドは、Redmond サイトに適用される QoE 構成設定の新しいコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="75be5-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="75be5-150">QoE 監視が無効になっている QoE 構成設定の新しいコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="75be5-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="75be5-p110">必須である Identity パラメーターを除いて、先行するコマンドでパラメーターが指定されないため、構成設定の新しいコレクションでは、すべてのプロパティで既定値が使用されます。別のプロパティ値を使用する設定を作成するには、単に適切なパラメーターとパラメーター値を指定します。たとえば、QoE レコードを既定で無効にする Quality of Experience 構成設定のコレクションを作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="75be5-p110">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="75be5-154">QoE 構成設定の新しいコレクションを作成するときに複数のプロパティ値を指定するには</span><span class="sxs-lookup"><span data-stu-id="75be5-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="75be5-p111">複数のパラメーターを含めることで、複数のプロパティ値を指定できます。たとえば、次のコマンドは、QoE データを 30 日間保持し、古いデータを午前 3 時に削除する新しい設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="75be5-p111">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="75be5-157">詳細については、[新しい-CsQoEConfiguration/](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration)コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="75be5-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

