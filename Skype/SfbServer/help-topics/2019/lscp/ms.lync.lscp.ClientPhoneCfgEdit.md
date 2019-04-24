---
title: デバイスの構成を新規作成または既存の編集
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: 新しいデバイス構成やデバイス構成の編集] ページで、作成したり、ビジネス電話のエディションの Skype を管理するために使用される設定のコレクションを変更できます。 これらの設定により、必要なセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定などを構成したり、指定した非アクティブ期間の経過後、電話を自動的にロックするかどうかを指定したりすることができます。
ms.openlocfilehash: 3dd7c9f782160b0f8a58d15e749276b4b2ee6adf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215816"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="9dc34-104">デバイス構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="9dc34-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="9dc34-105">**新しいデバイス構成**や**デバイス構成の編集**] ページで、作成したり、ビジネス電話のエディションの Skype を管理するために使用される設定のコレクションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="9dc34-106">これらの設定により、必要なセキュリティ モード、デバイス ログ レベル、音声のサービス品質 (QoS) の設定などを構成したり、指定した非アクティブ期間の経過後、電話を自動的にロックするかどうかを指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="9dc34-107">実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="9dc34-107">Tasks you can perform</span></span>

<span data-ttu-id="9dc34-108">[**新しいデバイス構成**] または [**デバイス構成の編集**] ページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="9dc34-109">新しいデバイス構成を追加する</span><span class="sxs-lookup"><span data-stu-id="9dc34-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="9dc34-110">既存のデバイス構成のプロパティを変更する</span><span class="sxs-lookup"><span data-stu-id="9dc34-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="9dc34-111">UI リファレンス</span><span class="sxs-lookup"><span data-stu-id="9dc34-111">UI Reference</span></span>

<span data-ttu-id="9dc34-112">次の一覧に、このページのメニュー、コマンド、フィールド、およびプロパティを示します。</span><span class="sxs-lookup"><span data-stu-id="9dc34-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="9dc34-113">**スコープ**デバイス構成のスコープ (グローバルまたはサイト) を識別します。</span><span class="sxs-lookup"><span data-stu-id="9dc34-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="9dc34-114">**名**追加したり、デバイスの構成の名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="9dc34-115">**SIP セキュリティ**ビジネス電話のエディションのデバイスの Skype のトランスポートと認証の要件を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="9dc34-116">次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="9dc34-117">**低**任意の種類の認証またはトランスポートを許可します。</span><span class="sxs-lookup"><span data-stu-id="9dc34-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="9dc34-118">**[中]** Ntlm 認証または Kerberos は、ユーザーの認証に必要です。</span><span class="sxs-lookup"><span data-stu-id="9dc34-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="9dc34-119">**高**Ntlm 認証または Kerberos は、ユーザーの認証に必要と TLS は、SIP の接続に必要です。</span><span class="sxs-lookup"><span data-stu-id="9dc34-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="9dc34-120">**ログ出力のレベル**UC デバイスのログを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="9dc34-121">有効な値: オフになります。低です。[中] です。高い。</span><span class="sxs-lookup"><span data-stu-id="9dc34-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="9dc34-122">既定値ではオフです。</span><span class="sxs-lookup"><span data-stu-id="9dc34-122">The default value is Off.</span></span>
    
- <span data-ttu-id="9dc34-123">**音声サービスの品質 (QoS)** ビジネス電話のエディションのデバイスに、Skype からの音声トラフィックに割り当てられている DSCP 値を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="9dc34-124">デフォルトでは 40 です。</span><span class="sxs-lookup"><span data-stu-id="9dc34-124">The default is 40.</span></span> <span data-ttu-id="9dc34-125">ただし、40 は、通常、オーディオ トラフィックに使用代わりに、オーディオ トラフィックはほとんど常に、DSCP コード 46 を使用してマークされます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="9dc34-126">ネットワーク全体で一貫性を維持するために 46 にこの値を変更する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9dc34-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="9dc34-127">**デバイスのロック**UC 電話がコンピューターを放置したまま指定した時間が経過すると自動的にロックするかどうかはそれ自体を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="9dc34-128">構成できる設定は、次のように。</span><span class="sxs-lookup"><span data-stu-id="9dc34-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="9dc34-129">**デバイス ロックを適用します。** デバイスは、このチェック ボックスを選択することにより、ロックを強制できます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="9dc34-130">**PIN の最小の長さ**携帯電話のロックを解除するために使用される個人識別番号 (PIN) の最小の長さを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="9dc34-131">暗証番号 (pin) の長さの範囲は、4 ~ 15 の数字です。</span><span class="sxs-lookup"><span data-stu-id="9dc34-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="9dc34-132">デフォルトの長さは、6 つの数字です。</span><span class="sxs-lookup"><span data-stu-id="9dc34-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="9dc34-133">**電話のロックのタイムアウト**電話ロックするまでの時間の長さの最小値自体指定できます。</span><span class="sxs-lookup"><span data-stu-id="9dc34-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="9dc34-134">既定値は 10 分です。</span><span class="sxs-lookup"><span data-stu-id="9dc34-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="9dc34-135">値は、HH:MM:SS の形式で入力してください。</span><span class="sxs-lookup"><span data-stu-id="9dc34-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9dc34-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="9dc34-136">See also</span></span>

[<span data-ttu-id="9dc34-137">デバイス構成</span><span class="sxs-lookup"><span data-stu-id="9dc34-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="9dc34-138">セット CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="9dc34-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
