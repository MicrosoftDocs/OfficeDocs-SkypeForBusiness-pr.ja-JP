---
title: Skype for Business Server で通話の記録と音質の設定を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: '概要: Skype for Business Server で CDR と QoE を構成する方法について説明します。'
ms.openlocfilehash: 3e0ff3e8dab09f38d71f9b5211f900e0f0e5fe9f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790055"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="63baa-103">Skype for Business Server で通話の記録と音質の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="63baa-103">Configure call detail recording and Quality of Experience settings in Skype for Business Server</span></span>
 
<span data-ttu-id="63baa-104">**概要:** Skype for Business Server で CDR と QoE を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="63baa-104">**Summary:** Learn how to configure CDR and QoE in Skype for Business Server.</span></span>
  
<span data-ttu-id="63baa-105">Skype for Business Server の SQL Server Reporting Services レポートを使用して、CDR と QoE の監視を構成します。</span><span class="sxs-lookup"><span data-stu-id="63baa-105">Configure CDR and QoE monitoring using SQL Server Reporting Services reports for Skype for Business Server.</span></span>
  
## <a name="configure-cdr-and-qoe"></a><span data-ttu-id="63baa-106">CDR および QoE の構成</span><span class="sxs-lookup"><span data-stu-id="63baa-106">Configure CDR and QoE</span></span>

<span data-ttu-id="63baa-107">フロントエンドプールで監視ストアを関連付け、監視ストアをセットアップして、SQL Server Reporting Services と監視レポートをインストールして構成した後、通話の詳細記録 (CDR) と品質のエクスペリエンス (QoE) を管理できます。Skype for Business Server 管理シェルを使用した監視。</span><span class="sxs-lookup"><span data-stu-id="63baa-107">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Skype for Business Server Management Shell.</span></span> <span data-ttu-id="63baa-108">Skype for Business Server 管理シェルコマンドレットを使用すると、特定のサイトまたは Skype for Business Server の展開全体について、CDR または QoE の監視を有効または無効にすることができます。これは、次のような単純なコマンドで実行できます。</span><span class="sxs-lookup"><span data-stu-id="63baa-108">Skype for Business Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Skype for Business Server deployment; that can be done with a command as simple as this:</span></span>
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

<span data-ttu-id="63baa-109">Skype for Business Server をインストールする場合は、CDR と QoE の両方のグローバル構成設定の定義済みコレクションもインストールします。</span><span class="sxs-lookup"><span data-stu-id="63baa-109">When you install Skype for Business Server, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="63baa-110">以下の表に、通話詳細記録で比較的よく使用される一部の設定の既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="63baa-110">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>
  
|<span data-ttu-id="63baa-111">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="63baa-111">**Property**</span></span>|<span data-ttu-id="63baa-112">**説明**</span><span class="sxs-lookup"><span data-stu-id="63baa-112">**Description**</span></span>|<span data-ttu-id="63baa-113">**既定値**</span><span class="sxs-lookup"><span data-stu-id="63baa-113">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63baa-114">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="63baa-114">EnableCDR</span></span>  <br/> |<span data-ttu-id="63baa-p103">CDR が有効かどうかを示します。True の場合、すべての CDR レコードが収集され、監視データベースに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="63baa-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="63baa-117">True</span><span class="sxs-lookup"><span data-stu-id="63baa-117">True</span></span>  <br/> |
|<span data-ttu-id="63baa-118">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="63baa-118">EnablePurging</span></span>  <br/> |<span data-ttu-id="63baa-p104">CDR レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepCallDetailForDays プロパティ (CDR レコードの場合) および KeepErrorReportForDays プロパティ (CDR エラーの場合) で指定されている期間を過ぎると、レコードが削除されます。False の場合、CDR レコードは無期限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="63baa-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="63baa-122">True</span><span class="sxs-lookup"><span data-stu-id="63baa-122">True</span></span>  <br/> |
|<span data-ttu-id="63baa-123">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="63baa-123">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="63baa-p105">CDR レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="63baa-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="63baa-126">KeepCallDetailForDays には、1 ～ 2,562 日 (約 7 年間) の間の整数値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="63baa-126">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span>  <br/> |<span data-ttu-id="63baa-127">60 日</span><span class="sxs-lookup"><span data-stu-id="63baa-127">60 days</span></span>  <br/> |
|<span data-ttu-id="63baa-128">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="63baa-128">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="63baa-129">CDR エラーレポートが保持される日数を示します。指定した日数よりも古いレポートは、自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="63baa-129">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="63baa-130">CDR エラーレポートは、Skype for Business Server などのクライアントアプリケーションによってアップロードされた診断レポートです。</span><span class="sxs-lookup"><span data-stu-id="63baa-130">CDR error reports are diagnostic reports uploaded by client applications such as Skype for Business Server.</span></span>  <br/> <span data-ttu-id="63baa-131">このプロパティには、1 ～ 2,562 (日) の範囲の任意の整数値に指定できます。</span><span class="sxs-lookup"><span data-stu-id="63baa-131">You can set this property to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="63baa-132">60 (日)</span><span class="sxs-lookup"><span data-stu-id="63baa-132">60 days</span></span>  <br/> |
   
<span data-ttu-id="63baa-133">同様に、一部の QoE 設定の既定値を以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="63baa-133">Similarly, default values for selected QoE settings are shown in this table:</span></span>
  
|<span data-ttu-id="63baa-134">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="63baa-134">**Property**</span></span>|<span data-ttu-id="63baa-135">**説明**</span><span class="sxs-lookup"><span data-stu-id="63baa-135">**Description**</span></span>|<span data-ttu-id="63baa-136">**既定値**</span><span class="sxs-lookup"><span data-stu-id="63baa-136">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63baa-137">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="63baa-137">EnableQoE</span></span>  <br/> |<span data-ttu-id="63baa-p107">QoE 監視が有効かどうかを示します。True の場合、すべての QoE レコードが収集され、監視データベースに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="63baa-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="63baa-140">True</span><span class="sxs-lookup"><span data-stu-id="63baa-140">True</span></span>  <br/> |
|<span data-ttu-id="63baa-141">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="63baa-141">EnablePurging</span></span>  <br/> |<span data-ttu-id="63baa-p108">QoE レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepQoEDataForDays プロパティで指定されている期間を過ぎると、レコードが削除されます。False の場合、QoE レコードは無期限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="63baa-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="63baa-145">True</span><span class="sxs-lookup"><span data-stu-id="63baa-145">True</span></span>  <br/> |
|<span data-ttu-id="63baa-146">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="63baa-146">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="63baa-p109">QoE レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="63baa-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="63baa-149">KeepCallDetailForDays は、1 ～ 2,562 (日) の範囲の任意の整数値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="63baa-149">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="63baa-150">60 日</span><span class="sxs-lookup"><span data-stu-id="63baa-150">60 days</span></span>  <br/> |
   
<span data-ttu-id="63baa-151">これらのグローバル設定を変更する必要がある場合は、CsCdrConfiguration と Set-CsQoEConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="63baa-151">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="63baa-152">たとえば、次のコマンド (Skype for Business Server 管理シェルから実行) では、グローバルスコープで CDR の監視が無効になります。これを行うには、EnableCDR プロパティを False ($False) に設定します。</span><span class="sxs-lookup"><span data-stu-id="63baa-152">For example, this command (run from within the Skype for Business Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

<span data-ttu-id="63baa-153">監視を無効にしても、監視ストアとフロントエンド プールとの関連付けは解除されず、バックエンド監視データベースがアンインストールされたり、その他の影響がこのデータベースに及んだりすることもありません。</span><span class="sxs-lookup"><span data-stu-id="63baa-153">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="63baa-154">Skype for Business Server の管理シェルを使用して CDR または QoE の監視を無効にする場合は、Skype for Business Server で監視データの収集とアーカイブを一時的に停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63baa-154">When you use Skype for Business Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Skype for Business Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="63baa-155">この場合、次のように EnableCDR プロパティの設定を True ($True) に戻すだけで、CDR データの収集とアーカイブを再開できます。</span><span class="sxs-lookup"><span data-stu-id="63baa-155">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

<span data-ttu-id="63baa-156">同様に、次のコマンドは、QoE レコードの削除をグローバル スコープで無効にします。</span><span class="sxs-lookup"><span data-stu-id="63baa-156">Similarly, this command disables the purging of QoE records at the global scope:</span></span>
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

<span data-ttu-id="63baa-p112">CDR と QoE の構成設定は、グローバル設定だけでなく、サイト スコープに割り当てることもできます。この操作を行うと、監視についての管理の柔軟性が向上します。たとえば、管理者は Redmond サイトで CDR 監視を有効にする一方で Dublin サイトでは CDR 監視を無効にできます。新しい CDR 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="63baa-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

<span data-ttu-id="63baa-p113">サイト スコープで構成されたこの設定は、グローバル スコープで構成された設定よりも優先されることに注意してください。たとえば、CDR 監視がグローバル スコープで有効になっていても、サイト スコープ (Redmond サイト) では無効になっているとします。この場合、Redmond サイト内のユーザーについては通話詳細記録の情報がアーカイブされません。ただし、その他のサイト内のユーザー (つまり、Redmond サイトの設定ではなくグローバル設定によって管理されているユーザー) の通話詳細記録の情報はアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="63baa-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>
  
<span data-ttu-id="63baa-164">新しい QoE 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="63baa-164">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

<span data-ttu-id="63baa-165">詳細については、Skype for Business Server 管理シェルで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="63baa-165">For more information, type the following commands from within the Skype for Business Server Management Shell:</span></span>
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
