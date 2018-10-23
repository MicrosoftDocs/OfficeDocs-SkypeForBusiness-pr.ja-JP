---
title: Skype Room System のドメイン参加に関する考慮事項
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。
ms.openlocfilehash: 3a457e73b3509967043b1ef11d1e5017f2190434
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699596"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="fc32d-103">Skype Room System のドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="fc32d-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="fc32d-104">このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fc32d-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="fc32d-105">ドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="fc32d-105">Domain joining considerations</span></span>

<span data-ttu-id="fc32d-106">PC Skype ルーム システムのアプライアンスを Active Directory ドメインに参加するか、ワークグループ内のままにできます。</span><span class="sxs-lookup"><span data-stu-id="fc32d-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="fc32d-107">決定の前に以下の点を検討してください。</span><span class="sxs-lookup"><span data-stu-id="fc32d-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="fc32d-108">Skype ルーム システム アプライアンス PC のドメイン参加は、組織の秘密のルート証明書チェーンを自動的にインポートするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fc32d-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="fc32d-109">Skype ルーム システム アプライアンス PC のドメイン参加を使用すると、ドメイン ユーザーおよびグループの管理権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="fc32d-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="fc32d-110">そうすることで、ローカル マシン レベルの管理者アカウントのパスワードを覚えておく必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="fc32d-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="fc32d-111">Skype ルーム システム アプライアンス コンピューターをドメインに参加するときは、必要な Skype ルーム システムのすべてのコンピューター オブジェクトが存在する OU にグループ ポリシー オブジェクト (GPO) の除外を提供できるように、独立した組織単位 (OU) を作成することです。</span><span class="sxs-lookup"><span data-stu-id="fc32d-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="fc32d-112">これを行うと、コンピューター オブジェクトを OU に含まれる Skype ルーム システム アプライアンス PC をドメインに参加する前に作成します。</span><span class="sxs-lookup"><span data-stu-id="fc32d-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="fc32d-113">多くの組織では、次の Gpo は、Skype ルーム システム アプライアンス PC の機能に影響を与えるがあります。</span><span class="sxs-lookup"><span data-stu-id="fc32d-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="fc32d-114">オーバーライドしたり、Skype ルーム システムの OU で Gpo の継承をブロックすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fc32d-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="fc32d-115">ログオン セッションのタイムアウト (自動ロックアウト)</span><span class="sxs-lookup"><span data-stu-id="fc32d-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="fc32d-116">電源管理関連のポリシー</span><span class="sxs-lookup"><span data-stu-id="fc32d-116">Power management related policies</span></span>
    
  - <span data-ttu-id="fc32d-117">追加の認証手順が必要</span><span class="sxs-lookup"><span data-stu-id="fc32d-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="fc32d-118">ローカル ドライブへのアクセスを拒否</span><span class="sxs-lookup"><span data-stu-id="fc32d-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="fc32d-119">ユーザーに低速のネットワーク接続を推奨する</span><span class="sxs-lookup"><span data-stu-id="fc32d-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="fc32d-120">ログオン時に特定のプログラムを起動する</span><span class="sxs-lookup"><span data-stu-id="fc32d-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="fc32d-121">ドメインに参加するすべてのマシンで別のドメイン ユーザー アカウントを作成する。</span><span class="sxs-lookup"><span data-stu-id="fc32d-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="fc32d-122">Skype ルーム システムに Windows の更新プログラムをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="fc32d-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="fc32d-123">または、アプライアンス PC をワークグループに残しておくことも可能です。</span><span class="sxs-lookup"><span data-stu-id="fc32d-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="fc32d-124">として Skype ビジネスのクライアントのデスクトップにこの必要があります Skype ルーム システム アプライアンス PC のルート証明書チェーンを手動でインポートするのには。</span><span class="sxs-lookup"><span data-stu-id="fc32d-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="fc32d-125">ビジネス展開するため、Skype が (たとえばと Entrust、VeriSign) のパブリック証明書を使用する場合は、ルート証明書チェーンをインポートする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="fc32d-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="fc32d-126">Skype ルーム システムのコンピューターをドメインに参加する場合は、OU、Gpo からできない可能性があります、意図しないに誤って Skype ルーム システムのマシンへの参加を回避するようにしてください正しい OU に参加します。</span><span class="sxs-lookup"><span data-stu-id="fc32d-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="fc32d-127">Skype ルーム システムのコンピューターから次のコマンドレットを使用して正しい OU に参加することができ、LRS の機能を妨げる可能性がある Gpo を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="fc32d-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="fc32d-128">これらのコマンドレットを実行するには、システム管理者か OEM パートナーに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="fc32d-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="fc32d-129">独立した OU を作成して継承をブロックしても、ハイ レベルな部分で問題を引き起こす可能性のあるポリシーがいくつか存在します。</span><span class="sxs-lookup"><span data-stu-id="fc32d-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="fc32d-130">No Override を設定したグループ ポリシーは、Block Policy Inheritance を設定した OU より優先されます。</span><span class="sxs-lookup"><span data-stu-id="fc32d-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="fc32d-131">詳細については、グループ ポリシーのドキュメントに[上書きポリシー継承のブロックと比較して](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc32d-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="fc32d-132">これらの問題を解決する手段は、1 つではないかもしれません。</span><span class="sxs-lookup"><span data-stu-id="fc32d-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="fc32d-133">組織の Active Directory の専門家に、適切な GPO 設定の OU、少なくとも上で説明したポリシーが存在しない OU が提供されていることを確認するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="fc32d-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="fc32d-134">Skype ルーム システム デバイスのサービスの品質 (QoS) を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fc32d-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc32d-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="fc32d-135">See also</span></span>
  
[<span data-ttu-id="fc32d-136">デバイス構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="fc32d-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="fc32d-137">サービスの品質の管理</span><span class="sxs-lookup"><span data-stu-id="fc32d-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
