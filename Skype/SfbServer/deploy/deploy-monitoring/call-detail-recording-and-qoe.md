---
title: ビジネス サーバー 2015 の Skype の通話の詳細記録と品質のエクスペリエンスの設定を構成します。
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: ': の概要では、Skype のビジネス サーバー 2015 の CDR および QoE を構成する方法について説明します。'
ms.openlocfilehash: 0d5a6ba25a524578a13f16c92149977b0180fbdb
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569457"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="03ed1-103">ビジネス サーバー 2015 の Skype の通話の詳細記録と品質のエクスペリエンスの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="03ed1-103">Configure call detail recording and Quality of Experience settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="03ed1-104">**の概要:** Skype のビジネス サーバー 2015 の CDR および QoE を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="03ed1-104">**Summary:** Learn how to configure CDR and QoE in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="03ed1-105">CDR と QoE の Skype のビジネス サーバー 2015 の SQL Server レポート サービスのレポートを使用して監視を構成します。</span><span class="sxs-lookup"><span data-stu-id="03ed1-105">Configure CDR and QoE monitoring using SQL Server Reporting Services reports for Skype for Business Server 2015.</span></span>
  
## <a name="configure-cdr-and-qoe"></a><span data-ttu-id="03ed1-106">CDR および QoE の構成</span><span class="sxs-lookup"><span data-stu-id="03ed1-106">Configure CDR and QoE</span></span>

<span data-ttu-id="03ed1-107">監視ストアとフロント エンド プール、監視ストアを設定してから、インストールおよび構成されている SQL Server レポート サービス監視レポートに関連付けた後は、呼び出しの詳細記録 (CDR) とエクスペリエンスの品質 (QoE) を管理することSkype ビジネス サーバー管理シェルを使用して監視します。</span><span class="sxs-lookup"><span data-stu-id="03ed1-107">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Skype for Business Server Management Shell.</span></span> <span data-ttu-id="03ed1-108">Skype ビジネス サーバー管理シェル コマンドレットを使用すると、CDR と QoE の特定のサイト、または、全体の Skype ビジネス サーバーの配置のための監視を無効にするにはだけでこのコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-108">Skype for Business Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Skype for Business Server deployment; that can be done with a command as simple as this:</span></span>
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

<span data-ttu-id="03ed1-109">ビジネス サーバー 2015 の Skype をインストールするときは、CDR と QoE の両方のグローバル構成設定の定義済みコレクションもインストールされます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-109">When you install Skype for Business Server 2015, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="03ed1-110">以下の表に、通話詳細記録で比較的よく使用される一部の設定の既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="03ed1-110">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>
  
|<span data-ttu-id="03ed1-111">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="03ed1-111">**Property**</span></span>|<span data-ttu-id="03ed1-112">**説明**</span><span class="sxs-lookup"><span data-stu-id="03ed1-112">**Description**</span></span>|<span data-ttu-id="03ed1-113">**既定値**</span><span class="sxs-lookup"><span data-stu-id="03ed1-113">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03ed1-114">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="03ed1-114">EnableCDR</span></span>  <br/> |<span data-ttu-id="03ed1-p103">CDR が有効かどうかを示します。True の場合、すべての CDR レコードが収集され、監視データベースに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="03ed1-117">True</span><span class="sxs-lookup"><span data-stu-id="03ed1-117">True</span></span>  <br/> |
|<span data-ttu-id="03ed1-118">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="03ed1-118">EnablePurging</span></span>  <br/> |<span data-ttu-id="03ed1-p104">CDR レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepCallDetailForDays プロパティ (CDR レコードの場合) および KeepErrorReportForDays プロパティ (CDR エラーの場合) で指定されている期間を過ぎると、レコードが削除されます。False の場合、CDR レコードは無期限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="03ed1-122">True</span><span class="sxs-lookup"><span data-stu-id="03ed1-122">True</span></span>  <br/> |
|<span data-ttu-id="03ed1-123">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="03ed1-123">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="03ed1-p105">CDR レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="03ed1-126">KeepCallDetailForDays には、1 ～ 2,562 日 (約 7 年間) の間の整数値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-126">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span>  <br/> |<span data-ttu-id="03ed1-127">60 (日)</span><span class="sxs-lookup"><span data-stu-id="03ed1-127">60 days</span></span>  <br/> |
|<span data-ttu-id="03ed1-128">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="03ed1-128">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="03ed1-129">CDR エラー報告を保持する日数を示します。指定した日数より古いすべてのレポートが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-129">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="03ed1-130">CDR エラー報告は、業務サーバー 2015 の Skype などのクライアント アプリケーションによってアップロードされた診断のレポートです。</span><span class="sxs-lookup"><span data-stu-id="03ed1-130">CDR error reports are diagnostic reports uploaded by client applications such as Skype for Business Server 2015.</span></span>  <br/> <span data-ttu-id="03ed1-131">このプロパティには、1 ～ 2,562 (日) の範囲の任意の整数値に指定できます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-131">You can set this property to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="03ed1-132">60 (日)</span><span class="sxs-lookup"><span data-stu-id="03ed1-132">60 days</span></span>  <br/> |
   
<span data-ttu-id="03ed1-133">同様に、一部の QoE 設定の既定値を以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="03ed1-133">Similarly, default values for selected QoE settings are shown in this table:</span></span>
  
|<span data-ttu-id="03ed1-134">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="03ed1-134">**Property**</span></span>|<span data-ttu-id="03ed1-135">**説明**</span><span class="sxs-lookup"><span data-stu-id="03ed1-135">**Description**</span></span>|<span data-ttu-id="03ed1-136">**既定値**</span><span class="sxs-lookup"><span data-stu-id="03ed1-136">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03ed1-137">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="03ed1-137">EnableQoE</span></span>  <br/> |<span data-ttu-id="03ed1-p107">QoE 監視が有効かどうかを示します。True の場合、すべての QoE レコードが収集され、監視データベースに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="03ed1-140">True</span><span class="sxs-lookup"><span data-stu-id="03ed1-140">True</span></span>  <br/> |
|<span data-ttu-id="03ed1-141">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="03ed1-141">EnablePurging</span></span>  <br/> |<span data-ttu-id="03ed1-p108">QoE レコードをデータベースから定期的に削除するかどうかを示します。True の場合、KeepQoEDataForDays プロパティで指定されている期間を過ぎると、レコードが削除されます。False の場合、QoE レコードは無期限に保持されます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="03ed1-145">True</span><span class="sxs-lookup"><span data-stu-id="03ed1-145">True</span></span>  <br/> |
|<span data-ttu-id="03ed1-146">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="03ed1-146">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="03ed1-p109">QoE レコードをデータベース内に保持する日数を指定します。指定した日数を超えて存在する古いレコードはすべて自動的に削除されます。ただし、この処理は削除が有効になっている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="03ed1-149">KeepCallDetailForDays は、1 ～ 2,562 (日) の範囲の任意の整数値に設定できます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-149">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="03ed1-150">60 (日)</span><span class="sxs-lookup"><span data-stu-id="03ed1-150">60 days</span></span>  <br/> |
   
<span data-ttu-id="03ed1-151">これらのグローバル設定を変更する必要がある場合これを行う一連の CsCdrConfiguration とセット CsQoEConfiguration コマンドレットを使用しています。</span><span class="sxs-lookup"><span data-stu-id="03ed1-151">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="03ed1-152">(内から実行、Skype ビジネス サーバー管理シェルの) 次のコマンドが CDR は、グローバル スコープで監視を無効にするなど、False ($False) に、EnableCDR プロパティを設定することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-152">For example, this command (run from within the Skype for Business Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

<span data-ttu-id="03ed1-153">監視を無効にしても、監視ストアとフロントエンド プールとの関連付けは解除されず、バックエンド監視データベースがアンインストールされたり、その他の影響がこのデータベースに及んだりすることもありません。</span><span class="sxs-lookup"><span data-stu-id="03ed1-153">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="03ed1-154">CDR または QoE の監視を無効にするのには Skype ビジネス サーバー管理シェルを使用すると、実際には、ビジネスのサーバーから収集し、監視データをアーカイブに Skype を一時的に停止です。</span><span class="sxs-lookup"><span data-stu-id="03ed1-154">When you use Skype for Business Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Skype for Business Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="03ed1-155">この場合、次のように EnableCDR プロパティの設定を True ($True) に戻すだけで、CDR データの収集とアーカイブを再開できます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-155">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

<span data-ttu-id="03ed1-156">同様に、次のコマンドは、QoE レコードの削除をグローバル スコープで無効にします。</span><span class="sxs-lookup"><span data-stu-id="03ed1-156">Similarly, this command disables the purging of QoE records at the global scope:</span></span>
  
```
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

<span data-ttu-id="03ed1-p112">CDR と QoE の構成設定は、グローバル設定だけでなく、サイト スコープに割り当てることもできます。この操作を行うと、監視についての管理の柔軟性が向上します。たとえば、管理者は Redmond サイトで CDR 監視を有効にする一方で Dublin サイトでは CDR 監視を無効にできます。新しい CDR 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="03ed1-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>
  
```
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

<span data-ttu-id="03ed1-p113">サイト スコープで構成されたこの設定は、グローバル スコープで構成された設定よりも優先されることに注意してください。たとえば、CDR 監視がグローバル スコープで有効になっていても、サイト スコープ (Redmond サイト) では無効になっているとします。この場合、Redmond サイト内のユーザーについては通話詳細記録の情報がアーカイブされません。ただし、その他のサイト内のユーザー (つまり、Redmond サイトの設定ではなくグローバル設定によって管理されているユーザー) の通話詳細記録の情報はアーカイブされます。</span><span class="sxs-lookup"><span data-stu-id="03ed1-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>
  
<span data-ttu-id="03ed1-164">新しい QoE 構成設定をサイト スコープで作成するには、次のようなコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="03ed1-164">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>
  
```
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

<span data-ttu-id="03ed1-165">詳細については、サーバー管理シェルのビジネスから、Skype 内の次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="03ed1-165">For more information, type the following commands from within the Skype for Business Server Management Shell:</span></span>
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```