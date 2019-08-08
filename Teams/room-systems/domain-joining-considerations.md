---
title: Skype Room System のドメイン参加に関する考慮事項
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。
ms.openlocfilehash: 02aa02cd0297a9f35db187c3b1b00d6615fbaa39
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243456"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="3b598-103">Skype Room System のドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="3b598-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="3b598-104">このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b598-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="3b598-105">ドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="3b598-105">Domain joining considerations</span></span>

<span data-ttu-id="3b598-106">Skype Room System アプライアンス PC には、Active Directory ドメインに参加することも、ワークグループ内に残しておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="3b598-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="3b598-107">決定の前に以下の点を検討してください。</span><span class="sxs-lookup"><span data-stu-id="3b598-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="3b598-108">ドメイン-Skype Room System アプライアンス PC に参加すると、組織のプライベートルート証明書チェーンを自動的にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="3b598-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="3b598-109">ドメイン-Skype Room System アプライアンス PC に参加すると、ドメインユーザとグループの管理権限を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="3b598-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="3b598-110">そうすることで、ローカル マシン レベルの管理者アカウントのパスワードを覚えておく必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="3b598-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="3b598-111">Skype Room System アプライアンス PC をドメインに参加させるには、別の組織単位 (OU) を作成する必要があります。これにより、すべての Skype Room System machine オブジェクトが存在する OU にグループポリシーオブジェクト (GPO) の除外が提供されます。</span><span class="sxs-lookup"><span data-stu-id="3b598-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="3b598-112">この操作を行う場合は、Skype Room System アプライアンス PC をドメインに参加させる前に、OU にマシンオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b598-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="3b598-113">多くの組織には、次のような Gpo があります。 Skype Room System appliance PC の機能に影響します。</span><span class="sxs-lookup"><span data-stu-id="3b598-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="3b598-114">Skype Room System OU でこれらの Gpo の継承を上書きまたはブロックします。</span><span class="sxs-lookup"><span data-stu-id="3b598-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="3b598-115">ログオン セッションのタイムアウト (自動ロックアウト)</span><span class="sxs-lookup"><span data-stu-id="3b598-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="3b598-116">電源管理関連のポリシー</span><span class="sxs-lookup"><span data-stu-id="3b598-116">Power management related policies</span></span>
    
  - <span data-ttu-id="3b598-117">追加の認証手順が必要</span><span class="sxs-lookup"><span data-stu-id="3b598-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="3b598-118">ローカル ドライブへのアクセスを拒否</span><span class="sxs-lookup"><span data-stu-id="3b598-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="3b598-119">ユーザーに低速のネットワーク接続を推奨する</span><span class="sxs-lookup"><span data-stu-id="3b598-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="3b598-120">ログオン時に特定のプログラムを起動する</span><span class="sxs-lookup"><span data-stu-id="3b598-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="3b598-121">ドメインに参加するすべてのマシンで別のドメイン ユーザー アカウントを作成する。</span><span class="sxs-lookup"><span data-stu-id="3b598-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="3b598-122">Skype Room System に Windows Update をプッシュする</span><span class="sxs-lookup"><span data-stu-id="3b598-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="3b598-123">または、アプライアンス PC をワークグループに残しておくことも可能です。</span><span class="sxs-lookup"><span data-stu-id="3b598-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="3b598-124">デスクトップの Microsoft Teams または Skype for Business クライアントの場合と同様に、Skype Room System アプライアンス PC でルート証明書チェーンを手動でインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b598-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="3b598-125">展開で公開証明書 (Entrust、VeriSign など) を使用している場合は、ルート証明書チェーンをインポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3b598-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="3b598-126">Skype Room システムマシンをドメインに参加させることを計画している場合、Skype Room System machine を意図しない OU に参加させないようにしてください。これは、Gpo から無料ではない可能性がありますので、正しい OU に参加してください。</span><span class="sxs-lookup"><span data-stu-id="3b598-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="3b598-127">Skype Room System コンピューターの次のコマンドレットを使用して、適切な OU に参加し、LRS 機能をブロックしている可能性のある Gpo を受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="3b598-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="3b598-128">これらのコマンドレットを実行するには、システム管理者か OEM パートナーに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="3b598-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="3b598-129">独立した OU を作成して継承をブロックしても、ハイ レベルな部分で問題を引き起こす可能性のあるポリシーがいくつか存在します。</span><span class="sxs-lookup"><span data-stu-id="3b598-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="3b598-130">No Override を設定したグループ ポリシーは、Block Policy Inheritance を設定した OU より優先されます。</span><span class="sxs-lookup"><span data-stu-id="3b598-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="3b598-131">詳細については、「グループポリシードキュメントの[ポリシーの継承をブロックする」という](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b598-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="3b598-132">これらの問題を解決する手段は、1 つではないかもしれません。</span><span class="sxs-lookup"><span data-stu-id="3b598-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="3b598-133">組織の Active Directory の専門家に、適切な GPO 設定の OU、少なくとも上で説明したポリシーが存在しない OU が提供されていることを確認するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="3b598-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="3b598-134">Skype Room システムデバイスのサービス品質 (QoS) を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3b598-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b598-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b598-135">See also</span></span>
  
[<span data-ttu-id="3b598-136">デバイス構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="3b598-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="3b598-137">サービスの品質の管理</span><span class="sxs-lookup"><span data-stu-id="3b598-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
