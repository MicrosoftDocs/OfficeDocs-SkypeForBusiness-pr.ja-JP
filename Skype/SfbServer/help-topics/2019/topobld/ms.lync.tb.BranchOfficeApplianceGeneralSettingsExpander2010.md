---
title: Lync Server 2010 用のブランチ オフィス アプライアンス全般設定エキスパンダー
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a41754a-4653-4845-afb6-4a74b2edfeb4
description: ブランチ アプライアンスのリカバリ性に優れた、または [全般] で、存続可能ブランチ サーバーのプロパティを編集するのには次の操作を構成します。
ms.openlocfilehash: 9e698854e78837e213ac080ab02098f72e72fec5
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2018
---
# <a name="branch-office-appliance-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="17ead-103">Lync Server 2010 用のブランチ オフィス アプライアンス全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="17ead-103">Branch Office Appliance General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="17ead-104">ブランチ アプライアンスのリカバリ性に優れた、または [**全般**] の下の存続可能ブランチ サーバーのプロパティを編集するのには次の操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="17ead-104">To edit properties for Survivable Branch Appliance or Survivable Branch Server , under **General**, you configure:</span></span>
  
- <span data-ttu-id="17ead-105">**FQDN**: リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="17ead-105">**FQDN**: You type the fully qualified domain name of the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="17ead-106">**構成されているすべての IP アドレスを使用して**すべての目的のリカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーに構成されている IP アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="17ead-106">**Use all configured IP addresses** uses the IP addresses configured on the Survivable Branch Appliance or Survivable Branch Server for all purposes.</span></span>
    
    <span data-ttu-id="17ead-107">[**選択された IP アドレスのみにサービスの使用を制限する**]: PSTN で使用するサーバーおよび IP アドレスを定義する別のアドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="17ead-107">**Limit service usage to selected IP addresses** You configure the distinct address that define the server and the IP address to be used for PSTN.</span></span>
    
    <span data-ttu-id="17ead-108">[**プライマリ IP アドレス**]: PSTN 関連の機能を除く、すべての目的のために IP アドレスを定義および構成します。</span><span class="sxs-lookup"><span data-stu-id="17ead-108">**Primary IP address**: The IP address is defined and configured for all purposes, except for PSTN-associated functions.</span></span>
    
    <span data-ttu-id="17ead-109">[**PSTN の IP アドレス**]: 公衆交換電話網 (PSTN) 機能に関連付けられた IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="17ead-109">**PSTN IP address**: The IP address associated with the public switched telephone network (PSTN) functions.</span></span>
    
- <span data-ttu-id="17ead-110">他のサーバーの役割が構成されているし、リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付けられていることを確認するのには、**関連付け**を構成するとします。</span><span class="sxs-lookup"><span data-stu-id="17ead-110">You configure **Associations** to ensure that other server roles are configured and associated with the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="17ead-111">**アーカイブ サーバーを関連付ける**リストから、リカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付けるアーカイブ サーバーを選択します。</span><span class="sxs-lookup"><span data-stu-id="17ead-111">**Associate Archiving Server** Select from the list the Archiving Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="17ead-112">このリカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付けるアーカイブ サーバーを作成していない場合、**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17ead-112">Click **New** if you have not created the Archiving Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="17ead-113">**関連のサーバーの監視**リストから、監視対象のサーバーをリカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付けるを選択します。</span><span class="sxs-lookup"><span data-stu-id="17ead-113">**Associate Monitoring Server** Select from the list the Monitoring Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="17ead-114">このリカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付ける監視サーバーを作成していない場合、**新規**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17ead-114">Click **New** if you have not created the Monitoring Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="17ead-115">**(メディア コンポーネント) に関連付けるエッジ プール**エッジ サーバーまたはエッジ プールをリカバリ性に優れたブランチ アプライアンスまたは存続可能ブランチ サーバーに関連付けるには、リストから選択します。</span><span class="sxs-lookup"><span data-stu-id="17ead-115">**Associate Edge pool (for media components)** Select from the list the Edge Server or Edge pool that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
 <span data-ttu-id="17ead-116">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="17ead-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="17ead-117">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="17ead-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="17ead-118">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="17ead-118">**Help** Displays this help screen.</span></span>
  

