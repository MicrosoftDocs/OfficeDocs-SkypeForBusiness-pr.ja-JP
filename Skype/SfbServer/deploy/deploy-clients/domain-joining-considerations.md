---
title: Skype Room System ドメイン参加に関する考慮事項
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: Skype Room System アプライアンス PC をドメインに参加する方法については、このトピックを参照してください。
ms.openlocfilehash: cf98f98a7294ead0920b3d6b07b00879cbfe15f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093571"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="ddb42-103">Skype Room System ドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="ddb42-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="ddb42-104">Skype Room System アプライアンス PC をドメインに参加する方法については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddb42-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="ddb42-105">ドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="ddb42-105">Domain joining considerations</span></span>

<span data-ttu-id="ddb42-106">Skype Room System アプライアンス PC を Active Directory ドメインに参加するか、ワークグループに残します。</span><span class="sxs-lookup"><span data-stu-id="ddb42-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="ddb42-107">この決定を行う前に、次の点を検討してください。</span><span class="sxs-lookup"><span data-stu-id="ddb42-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="ddb42-108">Skype Room System アプライアンス PC へのドメイン参加は、組織のプライベート ルート証明書チェーンを自動的にインポートするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ddb42-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="ddb42-109">Skype Room System アプライアンス PC にドメインを参加すると、ドメイン ユーザーとグループの管理者権限を付与できます。</span><span class="sxs-lookup"><span data-stu-id="ddb42-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="ddb42-110">これにより、ローカル コンピューター レベルの管理者アカウントのパスワードを覚えておく必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ddb42-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="ddb42-111">Skype Room System アプライアンス PC をドメインに参加する場合は、別の組織単位 (OU) を作成して、すべての Skype Room System マシン オブジェクトが存在する OU にグループ ポリシー オブジェクト (GPO) の除外を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb42-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="ddb42-112">これを行う場合は、Skype Room System アプライアンス PC をドメインに参加する前に、OU にマシン オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ddb42-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="ddb42-113">多くの組織では、Skype Room System アプライアンス PC の機能に影響を与える次の GPO があります。</span><span class="sxs-lookup"><span data-stu-id="ddb42-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="ddb42-114">Skype Room System OU でこれらの GPO の継承を上書きまたはブロックしてください。</span><span class="sxs-lookup"><span data-stu-id="ddb42-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="ddb42-115">ログオン セッションのタイムアウト (自動ロックアウト)</span><span class="sxs-lookup"><span data-stu-id="ddb42-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="ddb42-116">電源管理関連のポリシー</span><span class="sxs-lookup"><span data-stu-id="ddb42-116">Power management related policies</span></span>
    
  - <span data-ttu-id="ddb42-117">追加の認証手順を要求する</span><span class="sxs-lookup"><span data-stu-id="ddb42-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="ddb42-118">ローカル ドライブへのアクセスを拒否する</span><span class="sxs-lookup"><span data-stu-id="ddb42-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="ddb42-119">低速のネットワーク接続をユーザーに求める</span><span class="sxs-lookup"><span data-stu-id="ddb42-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="ddb42-120">ログオン時に特定のプログラムを開始する</span><span class="sxs-lookup"><span data-stu-id="ddb42-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="ddb42-121">すべてのドメインに参加しているコンピューターに別のドメイン ユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ddb42-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="ddb42-122">Windows Update を Skype ルーム システムにプッシュする</span><span class="sxs-lookup"><span data-stu-id="ddb42-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="ddb42-123">または、アプライアンス PC をワークグループに残す場合があります。</span><span class="sxs-lookup"><span data-stu-id="ddb42-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="ddb42-124">デスクトップの Skype for Business クライアントと同様に、Skype Room System アプライアンス PC でルート証明書チェーンを手動でインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb42-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="ddb42-125">Skype for Business 展開でパブリック証明書 (Entrust、VeriSign など) を使用している場合は、ルート証明書チェーンをインポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ddb42-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="ddb42-126">Skype Room System マシンをドメインに参加する予定がある場合は、意図しない OU に誤って Skype Room System マシンに参加しないようにしてください。GPO から解放されない可能性があります。正しい OU に参加していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ddb42-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="ddb42-127">Skype Room System コンピューターから次のコマンドレットを使用して、正しい OU に参加し、LRS 機能をブロックする GPO を受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="ddb42-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="ddb42-128">次のコマンドレットを実行するには、システム管理者または OEM パートナーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="ddb42-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="ddb42-129">別の OU を作成して継承をブロックしても、より高いレベルで問題が発生する可能性があるポリシーもあります。</span><span class="sxs-lookup"><span data-stu-id="ddb42-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="ddb42-130">[上書きなし] 設定のグループ ポリシーは、[ポリシーの継承をブロック] 設定を使用して OU を打ち負かします。</span><span class="sxs-lookup"><span data-stu-id="ddb42-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="ddb42-131">詳細については、「グループ ポリシー」のドキュメントの「 [ポリシー](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) の継承をブロックする」の記事「上書きなし」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddb42-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="ddb42-132">これらの問題を解決するには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="ddb42-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="ddb42-133">Active Directory の専門家に相談して、適切な GPO 設定を持つ OU、または前に説明したポリシーが存在しない OU が提供されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb42-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="ddb42-134">Skype Room System デバイスのサービス品質 (QoS) を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="ddb42-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddb42-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="ddb42-135">See also</span></span>
  
[<span data-ttu-id="ddb42-136">デバイス構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="ddb42-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="ddb42-137">サービス品質の管理</span><span class="sxs-lookup"><span data-stu-id="ddb42-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)