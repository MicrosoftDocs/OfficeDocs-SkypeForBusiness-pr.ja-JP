---
title: デバイス構成の新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
description: '[新しいデバイスの構成] または [デバイス構成の編集] ページでは、Skype for Business Phone Edition を管理するために使用される設定のコレクションを作成または変更できます。 これらの設定により、必要なセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定などを構成したり、指定した非アクティブ期間の経過後、電話を自動的にロックするかどうかを指定したりすることができます。'
ms.openlocfilehash: 2af651846a70605b36a8481ee53a54c47901e258
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285968"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="bec5c-104">デバイス構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="bec5c-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="bec5c-105">[**新しいデバイスの構成**] または [**デバイス構成の編集**] ページでは、Skype for business Phone Edition を管理するために使用される設定のコレクションを作成または変更できます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="bec5c-106">これらの設定により、必要なセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定などを構成したり、指定した非アクティブ期間の経過後、電話を自動的にロックするかどうかを指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="bec5c-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="bec5c-107">Tasks you can perform</span></span>

<span data-ttu-id="bec5c-108">[**新しいデバイス構成**] または [**デバイス構成の編集**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="bec5c-109">新しいデバイス構成を追加する</span><span class="sxs-lookup"><span data-stu-id="bec5c-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="bec5c-110">既存のデバイス構成のプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="bec5c-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="bec5c-111">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="bec5c-111">UI Reference</span></span>

<span data-ttu-id="bec5c-112">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="bec5c-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="bec5c-113">**スコープ**デバイス構成のスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="bec5c-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="bec5c-114">**名前**デバイス構成の名前を追加または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="bec5c-115">**SIP セキュリティ**Skype for Business Phone Edition デバイスのトランスポートと認証の要件を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="bec5c-116">次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="bec5c-117">**低**任意の種類の承認またはトランスポートを許可します。</span><span class="sxs-lookup"><span data-stu-id="bec5c-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="bec5c-118">**Medium**ユーザー認証には、NTLM または Kerberos が必要です。</span><span class="sxs-lookup"><span data-stu-id="bec5c-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="bec5c-119">**高**ユーザー認証には NTLM または Kerberos が必要です。また、SIP 接続には TLS が必要です。</span><span class="sxs-lookup"><span data-stu-id="bec5c-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="bec5c-120">**ログレベル**UC デバイスでログを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="bec5c-121">有効な値は次のとおりです。価媒体および高。</span><span class="sxs-lookup"><span data-stu-id="bec5c-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="bec5c-122">既定値はオフです。</span><span class="sxs-lookup"><span data-stu-id="bec5c-122">The default value is Off.</span></span>
    
- <span data-ttu-id="bec5c-123">**音声品質サービス (QoS)** Skype for Business Phone Edition デバイスから、ボイストラフィック emanating に割り当てられている DSCP 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="bec5c-124">既定値は40です。</span><span class="sxs-lookup"><span data-stu-id="bec5c-124">The default is 40.</span></span> <span data-ttu-id="bec5c-125">ただし、40は、通常はオーディオトラフィックに使用される値ではありません。代わりに、ほとんどの場合、音声トラフィックは DSCP コード46でマークされます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="bec5c-126">ネットワーク全体の一貫性を維持するために、この値を46に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="bec5c-127">**電話のロック**指定した時間の経過後に、UC 携帯電話が自動的にロックされるかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="bec5c-128">次の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="bec5c-129">**デバイスのロックを適用**するこのチェックボックスをオンにすると、デバイスのロックを適用できます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="bec5c-130">**PIN の最小文字数**電話のロックを解除するために使用される暗証番号 (PIN) の最小文字数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="bec5c-131">PIN の長さの範囲は 4 ~ 15 桁です。</span><span class="sxs-lookup"><span data-stu-id="bec5c-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="bec5c-132">既定の長さは6桁です。</span><span class="sxs-lookup"><span data-stu-id="bec5c-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="bec5c-133">**電話のロックタイムアウト**電話がロックされるまでの最小時間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bec5c-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="bec5c-134">既定値は 10 分です。</span><span class="sxs-lookup"><span data-stu-id="bec5c-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="bec5c-135">値は、HH:MM:SS の形式で入力してください。</span><span class="sxs-lookup"><span data-stu-id="bec5c-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bec5c-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="bec5c-136">See also</span></span>

[<span data-ttu-id="bec5c-137">デバイス構成</span><span class="sxs-lookup"><span data-stu-id="bec5c-137">Device Configuration</span></span>](device-configuration.md)

[<span data-ttu-id="bec5c-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="bec5c-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
