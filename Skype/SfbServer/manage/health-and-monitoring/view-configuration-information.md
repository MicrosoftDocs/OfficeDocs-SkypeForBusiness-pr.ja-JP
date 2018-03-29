---
title: Skype for Business Server 2015 での CDR 構成情報の表示
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77bd553f-da89-4c84-a5d0-2f7e91d04383
description: '概要: ビジネス サーバー 2015 の Skype での呼び出しの詳細記録 (CDR) を使用する方法を説明します。'
ms.openlocfilehash: 6eacc6c300cfc1faae843a1dc610b17b45ae9c88
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="view-cdr-configuration-information-in-skype-for-business-server-2015"></a><span data-ttu-id="0b26e-103">Skype for Business Server 2015 での CDR 構成情報の表示</span><span class="sxs-lookup"><span data-stu-id="0b26e-103">View CDR configuration information in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0b26e-104">**の概要:**ビジネス サーバー 2015 の Skype での呼び出しの詳細記録 (CDR) を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b26e-104">**Summary:** Learn how to use Call Detail Recording (CDR) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0b26e-p101">通話詳細記録 (CDR) を使用すると、ピアツーピアのインスタント メッセージング セッション、ボイス オーバー IP (VoIP) 電話の通話、電話会議などの使用状況を追跡できます。この使用状況データの中には、通話の発信者と受信者、通話時刻、通話時間の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0b26e-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="0b26e-107">ビジネス サーバー 2015 年、1 つの Skype をインストールすると CDR 構成設定のグローバル コレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0b26e-107">When you install Skype for Business Server 2015, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="0b26e-108">管理者は、個別のサイトに適用できるカスタム設定コレクションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b26e-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="0b26e-109">Skype ビジネス サーバーのコントロール パネルまたは[Get CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)コマンドレットを使用して、使用中で、組織で CDR 構成設定を表示できます。</span><span class="sxs-lookup"><span data-stu-id="0b26e-109">You can view the CDR configuration settings in use in your organization by using Skype for Business Server Control Panel or the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-view-cdr-configuration-information-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0b26e-110">ビジネス サーバーのコントロール パネルの Skype を使用して、CDR 構成情報を表示するのには</span><span class="sxs-lookup"><span data-stu-id="0b26e-110">To view CDR configuration information by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0b26e-111">Skype ビジネス サーバーのコントロール パネルの [**監視とアーカイブ**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b26e-111">In Skype for Business Server Control Panel click **Monitoring and Archiving**.</span></span>
    
2. <span data-ttu-id="0b26e-p103">すべての CDR 構成設定の一覧が、[**通話詳細記録**] タブに表示されます。設定の各コレクションについて、コレクションの [**名前**]、CDR が有効になっているかどうか ([**CDR**] プロパティ)、削除が有効になっているかどうか ([**CDR の削除**] プロパティ) が表示されます。コレクションの詳細情報を表示するには、コレクションをダブルクリックするか、適切なコレクションを選択して [**編集**] をクリックし、続いて [**詳細の表示**] をクリックします。詳細情報を表示できる CDR 構成設定のコレクションは一度に 1 つだけであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0b26e-p103">A list of all your CDR configuration settings will be displayed in the **Call Detail Recording** tab; for each collection of settings you will see the collection **Name**; whether or not CDR has been enabled (the **CDR** property); and whether or not purging has been enabled (the **CDR purging** property). To see detailed information about a collection, double-click the collection, or select the appropriate collection, click **Edit**, and then click **Show Details**. Note that you can only view detailed information for a single collection of CDR configuration settings at a time.</span></span>
    
## <a name="viewing-cdr-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0b26e-115">Windows PowerShell コマンドレットを使用して、CDR 構成情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="0b26e-115">Viewing CDR configuration information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="0b26e-116">CDR 構成設定を表示するには、Windows PowerShell と Get CsCdrConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b26e-116">You can view CDR configuration settings by using Windows PowerShell and the Get-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="0b26e-117">実行できますこのコマンドレットのいずれか、Skype からビジネス サーバー管理シェルまたは Windows PowerShell のリモート セッションから。</span><span class="sxs-lookup"><span data-stu-id="0b26e-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0b26e-118">ビジネス サーバーの Skype に接続するリモートの Windows PowerShell を使用する詳細については、ブログ記事の[「クイック スタート:: を管理する Microsoft Lync サーバー 2010 を使用してリモート PowerShell」](https://go.microsoft.com/fwlink/p/?linkId=255876)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b26e-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="0b26e-119">プロセスは、Skype のビジネス サーバーで同じです。</span><span class="sxs-lookup"><span data-stu-id="0b26e-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-cdr-configuration-information"></a><span data-ttu-id="0b26e-120">CDR の構成情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="0b26e-120">To view CDR configuration information</span></span>

- <span data-ttu-id="0b26e-121">すべての CDR 構成設定に関する情報を表示するのには、Skype のビジネス サーバー管理シェルの次のコマンドを入力し、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0b26e-121">To view information about all your CDR configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsCdrConfiguration
  ```

    <span data-ttu-id="0b26e-122">次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0b26e-122">That will return information similar to this:</span></span>
    
  ```
  Identity               : Global
EnableCDR              : True
EnablePurging          : True
KeepCallDetailForDays  : 90
KeepErrorReportForDays : 60
PurgeHourOfDay         : 2

  ```

<span data-ttu-id="0b26e-123">詳細については、 [Get CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps)コマンドレットのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b26e-123">For more information, see the help topic for the [Get-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/get-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  

