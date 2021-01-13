---
title: Lync Server 2010 用のブランチ オフィス アプライアンス全般設定の展開
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a41754a-4653-4845-afb6-4a74b2edfeb4
description: '[全般] で、存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーのプロパティを編集するには、次を構成します。'
ms.openlocfilehash: 72bbd89ffd20108cc6b4bcf0786fec7130eea382
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833217"
---
# <a name="branch-office-appliance-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="9a6f3-103">Lync Server 2010 用のブランチ オフィス アプライアンス全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="9a6f3-103">Branch Office Appliance General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="9a6f3-104">[全般] で、存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバー **のプロパティを** 編集するには、次を構成します。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-104">To edit properties for Survivable Branch Appliance or Survivable Branch Server , under **General**, you configure:</span></span>
  
- <span data-ttu-id="9a6f3-105">**FQDN**: 存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-105">**FQDN**: You type the fully qualified domain name of the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="9a6f3-106">**すべての構成済み IP アドレスは、** すべての目的で存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーで構成された IP アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-106">**Use all configured IP addresses** uses the IP addresses configured on the Survivable Branch Appliance or Survivable Branch Server for all purposes.</span></span>
    
    <span data-ttu-id="9a6f3-107">[**選択された IP アドレスのみにサービスの使用を制限する**] PSTN で使用するサーバーおよび IP アドレスを定義する別のアドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-107">**Limit service usage to selected IP addresses** You configure the distinct address that define the server and the IP address to be used for PSTN.</span></span>
    
    <span data-ttu-id="9a6f3-108">[**プライマリ IP アドレス**]: PSTN 関連の機能を除く、すべての目的のために IP アドレスを定義および構成します。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-108">**Primary IP address**: The IP address is defined and configured for all purposes, except for PSTN-associated functions.</span></span>
    
    <span data-ttu-id="9a6f3-109">[**PSTN の IP アドレス**]: 公衆交換電話網 (PSTN) 機能に関連付けられた IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-109">**PSTN IP address**: The IP address associated with the public switched telephone network (PSTN) functions.</span></span>
    
- <span data-ttu-id="9a6f3-110">関連付 **けを構成して** 、他のサーバーの役割が構成され、存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-110">You configure **Associations** to ensure that other server roles are configured and associated with the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="9a6f3-111">**アーカイブ サーバーの関連付け** リストから、存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付けるアーカイブ サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-111">**Associate Archiving Server** Select from the list the Archiving Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="9a6f3-112">この **存続** 可能ブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付けるアーカイブ サーバーをまだ作成していない場合は、[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-112">Click **New** if you have not created the Archiving Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="9a6f3-113">**監視サーバーの関連付け** 一覧から、存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付ける監視サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-113">**Associate Monitoring Server** Select from the list the Monitoring Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="9a6f3-114">この **存続** 可能ブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付ける監視サーバーを作成していない場合は、[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-114">Click **New** if you have not created the Monitoring Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="9a6f3-115">**エッジ プールの関連付け (メディア コンポーネント用)** 一覧から、存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付けるエッジ サーバーまたはエッジ プールを選択します。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-115">**Associate Edge pool (for media components)** Select from the list the Edge Server or Edge pool that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
  <span data-ttu-id="9a6f3-116">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="9a6f3-117">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="9a6f3-118">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="9a6f3-118">**Help** Displays this help screen.</span></span>
  

