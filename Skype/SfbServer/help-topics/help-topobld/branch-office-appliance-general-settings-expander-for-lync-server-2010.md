---
title: Lync Server 2010 用のブランチ オフィス アプライアンス全般設定の展開
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 存続可能 Branch Appliance または存続可能 Branch Server のプロパティを編集するには、一般に、次の構成を行います。
ms.openlocfilehash: 5bdcc283ce9f503af307e37a7c2f76c922d5facb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216158"
---
# <a name="branch-office-appliance-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="4617c-103">Lync Server 2010 用のブランチ オフィス アプライアンス全般設定の展開</span><span class="sxs-lookup"><span data-stu-id="4617c-103">Branch Office Appliance General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="4617c-104">存続可能 Branch Appliance または存続可能 Branch Server のプロパティを編集するには、 **一般**に、次の構成を行います。</span><span class="sxs-lookup"><span data-stu-id="4617c-104">To edit properties for Survivable Branch Appliance or Survivable Branch Server , under **General**, you configure:</span></span>
  
- <span data-ttu-id="4617c-105">**FQDN**: 存続可能 branch Appliance または存続可能ブランチサーバーの完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4617c-105">**FQDN**: You type the fully qualified domain name of the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="4617c-106">すべての目的のために、**構成された ip アドレスを使用**して、存続可能 branch Appliance または存続可能 branch Server で構成されている ip アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4617c-106">**Use all configured IP addresses** uses the IP addresses configured on the Survivable Branch Appliance or Survivable Branch Server for all purposes.</span></span>
    
    <span data-ttu-id="4617c-107">[**選択された IP アドレスのみにサービスの使用を制限する**] PSTN で使用するサーバーおよび IP アドレスを定義する別のアドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="4617c-107">**Limit service usage to selected IP addresses** You configure the distinct address that define the server and the IP address to be used for PSTN.</span></span>
    
    <span data-ttu-id="4617c-108">[**プライマリ IP アドレス**]: PSTN 関連の機能を除く、すべての目的のために IP アドレスを定義および構成します。</span><span class="sxs-lookup"><span data-stu-id="4617c-108">**Primary IP address**: The IP address is defined and configured for all purposes, except for PSTN-associated functions.</span></span>
    
    <span data-ttu-id="4617c-109">[**PSTN の IP アドレス**]: 公衆交換電話網 (PSTN) 機能に関連付けられた IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="4617c-109">**PSTN IP address**: The IP address associated with the public switched telephone network (PSTN) functions.</span></span>
    
- <span data-ttu-id="4617c-110">**関連付け**を構成して、他のサーバーの役割が構成され、存続可能 branch Appliance または存続可能ブランチサーバーに関連付けられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4617c-110">You configure **Associations** to ensure that other server roles are configured and associated with the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="4617c-111">**アーカイブサーバーの関連付け** 存続可能 Branch Appliance または存続可能ブランチサーバーに関連付けるアーカイブサーバーをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="4617c-111">**Associate Archiving Server** Select from the list the Archiving Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="4617c-112">この存続可能 Branch Appliance または存続可能ブランチサーバーに関連付けるアーカイブサーバーをまだ作成していない場合は、[ **新規** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4617c-112">Click **New** if you have not created the Archiving Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="4617c-113">**監視サーバーの関連付け** 存続可能 Branch Appliance または存続可能ブランチサーバーに関連付ける監視サーバーをリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="4617c-113">**Associate Monitoring Server** Select from the list the Monitoring Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="4617c-114">この存続可能 Branch Appliance または存続可能ブランチサーバーに関連付ける監視サーバーをまだ作成していない場合は、[ **新規** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4617c-114">Click **New** if you have not created the Monitoring Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="4617c-115">**エッジプールの関連付け (メディアコンポーネント用)** 存続可能 Branch Appliance または存続可能ブランチサーバーに関連付けるエッジサーバーまたはエッジプールを一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="4617c-115">**Associate Edge pool (for media components)** Select from the list the Edge Server or Edge pool that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
  <span data-ttu-id="4617c-116">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="4617c-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="4617c-117">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4617c-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="4617c-118">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="4617c-118">**Help** Displays this help screen.</span></span>
  

