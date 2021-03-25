---
title: デバイス構成 新規の作成または既存の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: '[新しいデバイス構成] または [デバイス構成の編集] ページで、Skype for Business Phone Edition の管理に使用される設定のコレクションを作成または変更できます。 これらの設定を使用すると、必須のセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定、非アクティブな電話を指定の時間の経過後に自動的にロックするかどうかなどを構成できます。'
ms.openlocfilehash: b0973c73580aee3cfc81dfb79ac65613ddfcf204
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119926"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="51c87-104">デバイス構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="51c87-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="51c87-105">[新 **しいデバイス構成]** または **[デバイス** 構成の編集] ページで、Skype for Business Phone Edition の管理に使用される設定のコレクションを作成または変更できます。</span><span class="sxs-lookup"><span data-stu-id="51c87-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="51c87-106">これらの設定を使用すると、必須のセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定、非アクティブな電話を指定の時間の経過後に自動的にロックするかどうかなどを構成できます。</span><span class="sxs-lookup"><span data-stu-id="51c87-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="51c87-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="51c87-107">Tasks you can perform</span></span>

<span data-ttu-id="51c87-108">[**新しいデバイス構成**] または [**デバイス構成の編集**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="51c87-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="51c87-109">新しいデバイス構成を追加する</span><span class="sxs-lookup"><span data-stu-id="51c87-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="51c87-110">既存のデバイス構成のプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="51c87-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="51c87-111">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="51c87-111">UI Reference</span></span>

<span data-ttu-id="51c87-112">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="51c87-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="51c87-113">**スコープ** デバイス構成のスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="51c87-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="51c87-114">**名前** デバイス構成の名前を追加または変更できます。</span><span class="sxs-lookup"><span data-stu-id="51c87-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="51c87-115">**SIP セキュリティ** Skype for Business Phone Edition デバイスのトランスポート要件と認証要件を構成できます。</span><span class="sxs-lookup"><span data-stu-id="51c87-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="51c87-116">次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="51c87-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="51c87-117">**低** 任意の種類の承認またはトランスポートを許可します。</span><span class="sxs-lookup"><span data-stu-id="51c87-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="51c87-118">**中程度** ユーザー認証には NTLM または Kerberos が必要です。</span><span class="sxs-lookup"><span data-stu-id="51c87-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="51c87-119">**High** ユーザー認証には NTLM または Kerberos が必要で、SIP 接続には TLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="51c87-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="51c87-120">**ログ レベル** UC デバイスでログ記録を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="51c87-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="51c87-121">有効な値は次のとおりです。低。Medium。と High。</span><span class="sxs-lookup"><span data-stu-id="51c87-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="51c87-122">既定値は Off です。</span><span class="sxs-lookup"><span data-stu-id="51c87-122">The default value is Off.</span></span>
    
- <span data-ttu-id="51c87-123">**音声サービス品質 (QoS)** Skype for Business Phone Edition デバイスから送信される音声トラフィックに割り当てられた DSCP 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="51c87-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="51c87-124">既定値は 40 です。</span><span class="sxs-lookup"><span data-stu-id="51c87-124">The default is 40.</span></span> <span data-ttu-id="51c87-125">音声トラフィックは、ほとんど常に DSCP コード 46 でマーキングされます。</span><span class="sxs-lookup"><span data-stu-id="51c87-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="51c87-126">ネットワーク全体で一貫性を保つには、この値を 46 に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51c87-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="51c87-127">**電話ロック** 指定された非アクティブ期間の後に UC 電話が自動的にロックするかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="51c87-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="51c87-128">構成できる設定は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="51c87-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="51c87-129">**デバイスのロックを強制する** このチェック ボックスをオンにすると、デバイスのロックを適用できます。</span><span class="sxs-lookup"><span data-stu-id="51c87-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="51c87-130">**PIN の最小長** 電話のロック解除に使用する個人識別番号 (PIN) の最小長を指定できます。</span><span class="sxs-lookup"><span data-stu-id="51c87-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="51c87-131">PIN の長さの範囲は 4 ~ 15 桁です。</span><span class="sxs-lookup"><span data-stu-id="51c87-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="51c87-132">既定の長さは 6 桁です。</span><span class="sxs-lookup"><span data-stu-id="51c87-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="51c87-133">**電話ロックのタイム アウト** 電話がそれ自体をロックする前の最小時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="51c87-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="51c87-134">既定値は 10 分です。</span><span class="sxs-lookup"><span data-stu-id="51c87-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="51c87-135">値は、HH:MM:SS の形式で入力してください。</span><span class="sxs-lookup"><span data-stu-id="51c87-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="51c87-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="51c87-136">See also</span></span>

[<span data-ttu-id="51c87-137">デバイス構成</span><span class="sxs-lookup"><span data-stu-id="51c87-137">Device Configuration</span></span>](device-configuration.md)

[<span data-ttu-id="51c87-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="51c87-138">Set-CsUCPhoneConfiguration</span></span>](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)