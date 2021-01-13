---
title: Skype for Business Server での Quality of Experience 構成設定の作成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: '概要: Skype for Business Server の QoE (Quality of Experience) 設定について学習します。'
ms.openlocfilehash: d1d0b299b5cf0bbaf3627b7c90f90e7e1d958d10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816997"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="677af-103">Skype for Business Server での Quality of Experience 構成設定の作成</span><span class="sxs-lookup"><span data-stu-id="677af-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="677af-104">**概要:** Skype for Business Server の QoE (Quality of Experience) 設定について学習します。</span><span class="sxs-lookup"><span data-stu-id="677af-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="677af-p101">QoE (Quality of Experience) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="677af-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="677af-107">Skype for Business Server をインストールすると、QoE 構成設定の単一のグローバル コレクションが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="677af-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="677af-108">管理者は、サイト スコープでカスタム設定を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="677af-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="677af-109">これらのサイト スコープの設定は、グローバル設定に優先して使用されます。</span><span class="sxs-lookup"><span data-stu-id="677af-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="677af-110">たとえば、Redmond サイト用のサイト スコープの設定を作成した場合は、グローバル設定ではなくこれらの設定を使用して Redmond の QoE が管理されます。</span><span class="sxs-lookup"><span data-stu-id="677af-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="677af-111">QoE 構成設定は、Skype for Business Server コントロール パネルまたは [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) コマンドレットを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="677af-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="677af-112">Skype for Business Server コントロール パネルを使用して新しい設定を作成する場合は、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="677af-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="677af-113">**UI 設定**</span><span class="sxs-lookup"><span data-stu-id="677af-113">**UI setting**</span></span>|<span data-ttu-id="677af-114">**PowerShell パラメーター**</span><span class="sxs-lookup"><span data-stu-id="677af-114">**PowerShell parameter**</span></span>|<span data-ttu-id="677af-115">**説明**</span><span class="sxs-lookup"><span data-stu-id="677af-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="677af-116">名前</span><span class="sxs-lookup"><span data-stu-id="677af-116">Name</span></span>  <br/> |<span data-ttu-id="677af-117">ID</span><span class="sxs-lookup"><span data-stu-id="677af-117">Identity</span></span>  <br/> |<span data-ttu-id="677af-p104">作成される設定の一意の ID。QoE 構成設定は、サイト スコープでのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="677af-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="677af-120">QoE データの監視を有効にする</span><span class="sxs-lookup"><span data-stu-id="677af-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="677af-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="677af-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="677af-122">QoE レコードを収集し、監視データベースに保存するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="677af-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="677af-123">QoE データの消去を有効にする</span><span class="sxs-lookup"><span data-stu-id="677af-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="677af-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="677af-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="677af-125">[**QoE データの最大保持期間 (日)**] プロパティに定義された期間が経過した後、レコードを削除するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="677af-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="677af-126">QoE データの最大保存期間 (日)</span><span class="sxs-lookup"><span data-stu-id="677af-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="677af-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="677af-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="677af-p105">データベースから削除するまで QoE データを保存する日数。削除が無効の場合、この値は無視されます。</span><span class="sxs-lookup"><span data-stu-id="677af-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="677af-130">次New-CsQoEConfigurationコマンドレットには、Skype for Business Server コントロール パネルでは使用できない追加オプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="677af-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="677af-131">詳細については [、New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) のヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="677af-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="677af-132">Skype for Business Server コントロール パネルを使用して QoE 構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="677af-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="677af-p107">RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「**セットアップのアクセス許可の委任**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="677af-p107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="677af-135">ブラウザー ウィンドウを開き、管理 URL を入力して Skype for Business Server コントロール パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="677af-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="677af-136">左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="677af-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="677af-137">[**QoE データ**] ページで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="677af-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="677af-138">[**サイトの選択**] でポリシーを適用するサイトをクリックし、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="677af-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="677af-139">[**新しい QoE の設定**] で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="677af-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="677af-140">[**QoE データの監視を有効にする**] を選択して、監視を有効にします。</span><span class="sxs-lookup"><span data-stu-id="677af-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="677af-141">[**QoE データの削除を有効にする**] を選択して、削除を有効にします。</span><span class="sxs-lookup"><span data-stu-id="677af-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="677af-142">[**QoE の最大保持期間 (日)**] で、QoE レコードを保持する最大日数を選択します。</span><span class="sxs-lookup"><span data-stu-id="677af-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="677af-143">[**確定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="677af-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="677af-144">カスタム コマンドレットを使用した QoE 構成Windows PowerShell作成</span><span class="sxs-lookup"><span data-stu-id="677af-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="677af-145">QoE 構成設定は、次のコマンドレットをWindows PowerShellしてNew-CsQoEConfigurationできます。</span><span class="sxs-lookup"><span data-stu-id="677af-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="677af-146">このコマンドレットは、Skype for Business Server 管理シェルまたは Skype for Business Server のリモート セッションから実行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="677af-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="677af-147">リモート Windows PowerShell を使用して Skype for Business Server に接続する方法の詳細については、ブログ記事「クイック スタート: リモート PowerShell を使用した [Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)の管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="677af-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="677af-148">プロセスは Skype for Business Server でも同じです。</span><span class="sxs-lookup"><span data-stu-id="677af-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="677af-149">QoE 構成設定の新しいコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="677af-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="677af-150">次のコマンドは、Redmond サイトに適用される QoE 構成設定の新しいコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="677af-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="677af-151">QoE 監視が無効になっている QoE 構成設定の新しいコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="677af-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="677af-p109">必須である Identity パラメーターを除いて、先行するコマンドでパラメーターが指定されないため、構成設定の新しいコレクションでは、すべてのプロパティで既定値が使用されます。別のプロパティ値を使用する設定を作成するには、単に適切なパラメーターとパラメーター値を指定します。たとえば、QoE レコードを既定で無効にする Quality of Experience 構成設定のコレクションを作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="677af-p109">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="677af-155">QoE 構成設定の新しいコレクションを作成するときに複数のプロパティ値を指定するには</span><span class="sxs-lookup"><span data-stu-id="677af-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="677af-p110">複数のパラメーターを含めることで、複数のプロパティ値を指定できます。たとえば、次のコマンドは、QoE データを 30 日間保持し、古いデータを午前 3 時に削除する新しい設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="677af-p110">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="677af-158">詳細については [、New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="677af-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

