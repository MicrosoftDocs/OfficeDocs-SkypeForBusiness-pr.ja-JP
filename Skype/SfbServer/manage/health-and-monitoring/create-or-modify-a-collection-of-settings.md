---
title: 作成するか、Skype でビジネス サーバー用の CDR 構成設定のコレクションを変更します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: '概要: は、Skype のビジネス サーバー (CDR) を記録呼び出しの詳細について説明します。'
ms.openlocfilehash: f1bbf12f3766156b5f30ef3f2760669791e8c4c0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20970373"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="21c9c-103">作成するか、Skype でビジネス サーバー用の CDR 構成設定のコレクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="21c9c-103">Create or modify a collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="21c9c-104">**の概要:** Skype のビジネス サーバー (CDR) を記録呼び出しの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="21c9c-104">**Summary:** Learn about Call detail recording (CDR) in Skype for Business Server.</span></span>
  
<span data-ttu-id="21c9c-p101">通話詳細記録 (CDR) では、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="21c9c-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="21c9c-107">ビジネス サーバー 1 つの Skype をインストールすると、CDR 構成設定のグローバル コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="21c9c-107">When you install Skype for Business Server a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="21c9c-108">管理者は、サイト スコープでカスタム設定を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="21c9c-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="21c9c-109">これらのサイト スコープの設定が使用されるときは常に、グローバル設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="21c9c-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="21c9c-110">たとえば、Redmond サイトにサイト スコープの設定を作成する場合、Redmond での CDR の管理には (グローバル設定ではなく) それらの設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="21c9c-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>
  
<span data-ttu-id="21c9c-111">ビジネス サーバーのコントロール パネルまたは[新規 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)コマンドレットのいずれかの Skype を使用して、CDR 構成設定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="21c9c-111">You can create CDR configuration settings by using either Skype for Business Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="21c9c-112">Skype ビジネス サーバーのコントロール パネルの[設定 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)コマンドレットを使用するには既存の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="21c9c-112">You can use Skype for Business Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet to modify existing settings.</span></span> <span data-ttu-id="21c9c-113">作成または設定を変更するビジネス サーバーのコントロール パネルの Skype を使用する場合に使用可能な次のオプションになります。</span><span class="sxs-lookup"><span data-stu-id="21c9c-113">If you are using Skype for Business Server Control Panel to create or modify settings, the following options will be available to you:</span></span>
  
|<span data-ttu-id="21c9c-114">**UI 設定**</span><span class="sxs-lookup"><span data-stu-id="21c9c-114">**UI setting**</span></span>|<span data-ttu-id="21c9c-115">**PowerShell パラメーター**</span><span class="sxs-lookup"><span data-stu-id="21c9c-115">**PowerShell parameter**</span></span>|<span data-ttu-id="21c9c-116">**説明**</span><span class="sxs-lookup"><span data-stu-id="21c9c-116">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="21c9c-117">名前</span><span class="sxs-lookup"><span data-stu-id="21c9c-117">Name</span></span>  <br/> |<span data-ttu-id="21c9c-118">ID</span><span class="sxs-lookup"><span data-stu-id="21c9c-118">Identity</span></span>  <br/> |<span data-ttu-id="21c9c-p104">作成する CDR 構成設定に対する一意の識別子。これらの設定はサイト スコープでのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="21c9c-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="21c9c-121">CDR の監視を有効にする</span><span class="sxs-lookup"><span data-stu-id="21c9c-121">Enable monitoring of CDRs</span></span>  <br/> |<span data-ttu-id="21c9c-122">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="21c9c-122">EnableCDR</span></span>  <br/> |<span data-ttu-id="21c9c-123">CDR が有効かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="21c9c-123">Indicates whether or not CDR is enabled.</span></span>  <br/> |
|<span data-ttu-id="21c9c-124">CDR の削除を有効にする</span><span class="sxs-lookup"><span data-stu-id="21c9c-124">Enable purging of CDRs</span></span>  <br/> |<span data-ttu-id="21c9c-125">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="21c9c-125">EnablePurging</span></span>  <br/> |<span data-ttu-id="21c9c-126">CDR の記録を CDR データベースから定期的に削除するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="21c9c-126">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span>  <br/> |
|<span data-ttu-id="21c9c-127">CDR を保持する最大期間 (日数)</span><span class="sxs-lookup"><span data-stu-id="21c9c-127">Keep CDRs for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="21c9c-128">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="21c9c-128">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="21c9c-p105">CDR データベースに CDR レコードを保持する日数を示します。指定された日数より前のレコードは、自動的に削除されます (削除が実行されるのは、削除が有効になっている場合のみです)。</span><span class="sxs-lookup"><span data-stu-id="21c9c-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span>  <br/> |
|<span data-ttu-id="21c9c-132">エラー報告データを保持する最大期間 (日数)</span><span class="sxs-lookup"><span data-stu-id="21c9c-132">Keep error report data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="21c9c-133">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="21c9c-133">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="21c9c-p106">CDR エラー報告を保持する日数を指定します。指定した日数を超えて保持されている報告は、自動的に削除されます。CDR エラー報告は、クライアント アプリケーションによってアップロードされる診断レポートです。</span><span class="sxs-lookup"><span data-stu-id="21c9c-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="21c9c-137">新規 CsCdrConfiguration とセット CsCdrConfiguration コマンドレットには、ビジネス サーバーのコントロール パネルの Skype では利用できない追加のオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="21c9c-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="21c9c-138">[新規 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)と、[セット CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)ヘルプ トピックの詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21c9c-138">See the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) and the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) help topics for more information.</span></span>
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="21c9c-139">ビジネス サーバーのコントロール パネルの Skype を使用して、CDR 構成設定を作成するには</span><span class="sxs-lookup"><span data-stu-id="21c9c-139">To create CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="21c9c-140">Skype ビジネス サーバーのコントロール パネルの [**監視とアーカイブ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c9c-140">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="21c9c-141">**呼び出しの詳細記録**] タブで、[**新規**を] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c9c-141">On the **Call Detail Recording** tab, click **New**.</span></span>
    
3. <span data-ttu-id="21c9c-p108">[**サイトの選択**] ダイアログ ボックスで、新しい構成設定を作成するサイトを選択します。ダイアログ ボックスに何も表示されない場合は、すべてのサイトが CDR 構成設定のコレクションに割り当て済みであることを意味します。各サイトに対してこのようなコレクション 1 つに制限されています。その場合、設定を削除してから再作成するか、単純に既存の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="21c9c-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>
    
4. <span data-ttu-id="21c9c-146">[**新しい通話詳細記録 (CDR) 設定を作成する**] ダイアログで、任意に選択を行ってから [**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c9c-146">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="21c9c-147">ビジネス サーバーのコントロール パネルの Skype を使用して既存の CDR 構成設定を変更するのには</span><span class="sxs-lookup"><span data-stu-id="21c9c-147">To modify existing CDR configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="21c9c-148">Skype ビジネス サーバーのコントロール パネルの [**監視とアーカイブ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c9c-148">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="21c9c-149">変更する設定のコレクションをダブルクリックするか、コレクションを選択して [**編集**] をクリックし、さらに [**詳細の表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c9c-149">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="21c9c-150">一度に変更できるのは 1 つのコレクションだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="21c9c-150">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="21c9c-151">同じ変更を複数のコレクションに加えると、代わりにビジネス サーバー管理シェルには、Skype を使用します。</span><span class="sxs-lookup"><span data-stu-id="21c9c-151">To make the same changes to multiple collections, use the Skype for Business Server Management Shell instead.</span></span>
    
3. <span data-ttu-id="21c9c-152">[**通話詳細記録 (CDR) 設定の編集**] ダイアログで、任意の選択を行ってから [**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21c9c-152">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="21c9c-153">Windows PowerShell コマンドレットを使用して、CDR 構成設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="21c9c-153">Creating CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="21c9c-154">CDR 構成の設定は、Windows PowerShell と**新規 CsCdrConfiguration**コマンドレットを使用して作成することもを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="21c9c-154">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="21c9c-155">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="21c9c-155">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="21c9c-156">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21c9c-156">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="21c9c-157">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="21c9c-157">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="21c9c-158">新しい CDR 構成設定のコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="21c9c-158">To create a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="21c9c-159">このコマンドを実行すると、Redmond サイトに適用される新しい CDR 構成設定のコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="21c9c-159">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="21c9c-160">通話詳細記録を無効にする CDR 構成設定のコレクションを作成するには</span><span class="sxs-lookup"><span data-stu-id="21c9c-160">To create a collection of CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="21c9c-p111">前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。たとえば、既定では通話詳細記録の無効化を許可する通話詳細の構成設定のコレクションを作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="21c9c-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="21c9c-164">新しい CDR 構成設定のコレクションの作成時に複数のプロパティ値を指定するには</span><span class="sxs-lookup"><span data-stu-id="21c9c-164">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

 <span data-ttu-id="21c9c-p112">複数のパラメーターを含めることで、複数のプロパティ値を変更できます。たとえば、このコマンドを実行すると、通話詳細記録を 30 日間保持し、エラー レポートを 90 日間保持するための新しい設定が構成されます。</span><span class="sxs-lookup"><span data-stu-id="21c9c-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

<span data-ttu-id="21c9c-167">詳細については、[新規 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="21c9c-167">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

