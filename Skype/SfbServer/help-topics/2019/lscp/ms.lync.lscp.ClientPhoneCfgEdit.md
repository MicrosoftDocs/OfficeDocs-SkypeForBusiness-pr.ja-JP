---
title: デバイス構成の作成 (新規) または [既存の編集]
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: '[新しいデバイスの構成] または [デバイス構成の編集] ページでは、Skype for Business Phone Edition の管理に使用する設定のコレクションを作成または変更できます。 これらの設定を使用すると、必須のセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定、非アクティブな電話を指定の時間の経過後に自動的にロックするかどうかなどを構成できます。'
ms.openlocfilehash: 0b330212c8dc050bb618f28ea6444b1c8e58f040
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830197"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="eb297-104">デバイス構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="eb297-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="eb297-105">[新 **しいデバイスの構成**] または [デバイス構成の編集] ページでは、Skype for Business Phone Edition の管理に使用する設定のコレクションを作成または変更できます。 </span><span class="sxs-lookup"><span data-stu-id="eb297-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="eb297-106">これらの設定を使用すると、必須のセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定、非アクティブな電話を指定の時間の経過後に自動的にロックするかどうかなどを構成できます。</span><span class="sxs-lookup"><span data-stu-id="eb297-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="eb297-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="eb297-107">Tasks you can perform</span></span>

<span data-ttu-id="eb297-108">[**新しいデバイス構成**] または [**デバイス構成の編集**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="eb297-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="eb297-109">新しいデバイス構成を追加する</span><span class="sxs-lookup"><span data-stu-id="eb297-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="eb297-110">既存のデバイス構成のプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="eb297-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="eb297-111">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="eb297-111">UI Reference</span></span>

<span data-ttu-id="eb297-112">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="eb297-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="eb297-113">**スコープ** デバイス構成のスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="eb297-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="eb297-114">**名前** デバイス構成の名前を追加または変更できます。</span><span class="sxs-lookup"><span data-stu-id="eb297-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="eb297-115">**SIP セキュリティ** Skype for Business Phone Edition デバイスのトランスポートおよび認証の要件を構成できます。</span><span class="sxs-lookup"><span data-stu-id="eb297-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="eb297-116">次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="eb297-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="eb297-117">**低** 任意の種類の承認またはトランスポートを許可します。</span><span class="sxs-lookup"><span data-stu-id="eb297-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="eb297-118">**中** ユーザー認証には NTLM または Kerberos が必要です。</span><span class="sxs-lookup"><span data-stu-id="eb297-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="eb297-119">**高** ユーザー認証には NTLM または Kerberos が必要であり、SIP 接続には TLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="eb297-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="eb297-120">**ログ 出力レベル** UC デバイスでログ記録を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="eb297-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="eb297-121">有効な値は次のとおりです。低;中および高。</span><span class="sxs-lookup"><span data-stu-id="eb297-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="eb297-122">既定値は Off です。</span><span class="sxs-lookup"><span data-stu-id="eb297-122">The default value is Off.</span></span>
    
- <span data-ttu-id="eb297-123">**音声サービスの品質 (QoS)** Skype for Business Phone Edition デバイスから提供される音声トラフィックに割り当てられる DSCP 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb297-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="eb297-124">既定値は 40 です。</span><span class="sxs-lookup"><span data-stu-id="eb297-124">The default is 40.</span></span> <span data-ttu-id="eb297-125">音声トラフィックは、ほとんど常に DSCP コード 46 でマーキングされます。</span><span class="sxs-lookup"><span data-stu-id="eb297-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="eb297-126">ネットワーク全体の一貫性を維持するために、この値を 46 に変更できます。</span><span class="sxs-lookup"><span data-stu-id="eb297-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="eb297-127">**電話ロック** UC 電話は、指定した非アクティブ期間が終了した後に自動的にロックするかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb297-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="eb297-128">構成できる設定を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eb297-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="eb297-129">**デバイスロックの適用** このチェック ボックスをオンにすると、デバイスのロックを適用できます。</span><span class="sxs-lookup"><span data-stu-id="eb297-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="eb297-130">**PIN の最小長** 電話のロック解除に使用する暗証番号 (PIN) の最小の長さを指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb297-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="eb297-131">PIN の長さの範囲は 4 ~ 15 桁です。</span><span class="sxs-lookup"><span data-stu-id="eb297-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="eb297-132">既定の長さは 6 桁です。</span><span class="sxs-lookup"><span data-stu-id="eb297-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="eb297-133">**電話ロックのタイム アウト** 電話がそれ自体をロックする最小時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb297-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="eb297-134">既定値は 10 分です。</span><span class="sxs-lookup"><span data-stu-id="eb297-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="eb297-135">値は、HH:MM:SS の形式で入力してください。</span><span class="sxs-lookup"><span data-stu-id="eb297-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="eb297-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb297-136">See also</span></span>

[<span data-ttu-id="eb297-137">デバイス構成</span><span class="sxs-lookup"><span data-stu-id="eb297-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="eb297-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb297-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
