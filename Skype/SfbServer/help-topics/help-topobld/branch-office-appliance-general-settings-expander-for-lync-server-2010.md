---
title: Lync Server 2010 用のブランチ オフィス アプライアンス全般設定エキスパンダー
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a41754a-4653-4845-afb6-4a74b2edfeb4
description: Survivable Branch Appliance または Survivable Branch Server のプロパティを編集するには、[全般] で次のように構成します。
ms.openlocfilehash: 5aa8a41cbe6c73cd103810c2661979cbba6bbdd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820309"
---
# <a name="branch-office-appliance-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="bc465-103">Lync Server 2010 用のブランチ オフィス アプライアンス全般設定エキスパンダー</span><span class="sxs-lookup"><span data-stu-id="bc465-103">Branch Office Appliance General Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="bc465-104">Survivable Branch Appliance または Survivable Branch Server のプロパティを編集するには、[**全般**] で次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="bc465-104">To edit properties for Survivable Branch Appliance or Survivable Branch Server , under **General**, you configure:</span></span>
  
- <span data-ttu-id="bc465-105">[ **FQDN**: Survivable branch Appliance または Survivable branch Server の完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc465-105">**FQDN**: You type the fully qualified domain name of the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="bc465-106">**すべての構成済み ip アドレスを使用する**には、Survivable branch Appliance または Survivable branch Server で構成されている ip アドレスをすべての目的で使います。</span><span class="sxs-lookup"><span data-stu-id="bc465-106">**Use all configured IP addresses** uses the IP addresses configured on the Survivable Branch Appliance or Survivable Branch Server for all purposes.</span></span>
    
    <span data-ttu-id="bc465-107">[**選択された IP アドレスのみにサービスの使用を制限する**]: PSTN で使用するサーバーおよび IP アドレスを定義する別のアドレスを構成します。</span><span class="sxs-lookup"><span data-stu-id="bc465-107">**Limit service usage to selected IP addresses** You configure the distinct address that define the server and the IP address to be used for PSTN.</span></span>
    
    <span data-ttu-id="bc465-108">[**プライマリ IP アドレス**]: PSTN 関連の機能を除く、すべての目的のために IP アドレスを定義および構成します。</span><span class="sxs-lookup"><span data-stu-id="bc465-108">**Primary IP address**: The IP address is defined and configured for all purposes, except for PSTN-associated functions.</span></span>
    
    <span data-ttu-id="bc465-109">[**PSTN の IP アドレス**]: 公衆交換電話網 (PSTN) 機能に関連付けられた IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="bc465-109">**PSTN IP address**: The IP address associated with the public switched telephone network (PSTN) functions.</span></span>
    
- <span data-ttu-id="bc465-110">他のサーバーの役割を構成し、Survivable Branch Appliance または Survivable ブランチサーバーと関連付けられるように、**関連付け**を構成します。</span><span class="sxs-lookup"><span data-stu-id="bc465-110">You configure **Associations** to ensure that other server roles are configured and associated with the Survivable Branch Appliance or Survivable Branch Server.</span></span>
    
    <span data-ttu-id="bc465-111">**アーカイブサーバーの関連付け**Survivable Branch Appliance または Survivable Branch Server に関連付けるアーカイブサーバーの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="bc465-111">**Associate Archiving Server** Select from the list the Archiving Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="bc465-112">この Survivable Branch Appliance または Survivable Branch Server に関連付けるアーカイブサーバーを作成していない場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc465-112">Click **New** if you have not created the Archiving Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="bc465-113">**監視サーバーの関連付け**Survivable Branch Appliance または Survivable Branch Server に関連付ける監視サーバーの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="bc465-113">**Associate Monitoring Server** Select from the list the Monitoring Server that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="bc465-114">この Survivable Branch Appliance または Survivable Branch Server に関連付ける監視サーバーを作成していない場合は、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc465-114">Click **New** if you have not created the Monitoring Server that you want to associate with this Survivable Branch Appliance or Survivable Branch Server</span></span>
    
    <span data-ttu-id="bc465-115">**エッジプールを関連付ける (メディアコンポーネント)** Survivable Branch Appliance または Survivable Branch Server に関連付けるエッジサーバーまたはエッジプールの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="bc465-115">**Associate Edge pool (for media components)** Select from the list the Edge Server or Edge pool that you want to associate with the Survivable Branch Appliance or Survivable Branch Server</span></span>
    
  <span data-ttu-id="bc465-116">[**OK**]: ダイアログでの変更を受け入れて確定します。</span><span class="sxs-lookup"><span data-stu-id="bc465-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="bc465-117">[**キャンセル**]: 変更を破棄してダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bc465-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="bc465-118">[**ヘルプ**]: このヘルプ画面を表示します。</span><span class="sxs-lookup"><span data-stu-id="bc465-118">**Help** Displays this help screen.</span></span>
  

