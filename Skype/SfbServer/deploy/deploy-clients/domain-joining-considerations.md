---
title: Skype Room System のドメイン参加に関する考慮事項
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。
ms.openlocfilehash: 9e6260ae852d66fd435ce236e28df0c992369eb6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895188"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="64f40-103">Skype Room System のドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="64f40-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="64f40-104">このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64f40-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="64f40-105">ドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="64f40-105">Domain joining considerations</span></span>

<span data-ttu-id="64f40-106">PC Skype ルーム システムのアプライアンスを Active Directory ドメインに参加するか、ワークグループ内のままにできます。</span><span class="sxs-lookup"><span data-stu-id="64f40-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="64f40-107">決定の前に以下の点を検討してください。</span><span class="sxs-lookup"><span data-stu-id="64f40-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="64f40-108">Skype ルーム システム アプライアンス PC のドメイン参加は、組織の秘密のルート証明書チェーンを自動的にインポートするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="64f40-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="64f40-109">Skype ルーム システム アプライアンス PC のドメイン参加を使用すると、ドメイン ユーザーおよびグループの管理権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="64f40-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="64f40-110">そうすることで、ローカル マシン レベルの管理者アカウントのパスワードを覚えておく必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="64f40-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="64f40-111">Skype ルーム システム アプライアンス コンピューターをドメインに参加するときは、必要な Skype ルーム システムのすべてのコンピューター オブジェクトが存在する OU にグループ ポリシー オブジェクト (GPO) の除外を提供できるように、独立した組織単位 (OU) を作成することです。</span><span class="sxs-lookup"><span data-stu-id="64f40-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="64f40-112">これを行うと、コンピューター オブジェクトを OU に含まれる Skype ルーム システム アプライアンス PC をドメインに参加する前に作成します。</span><span class="sxs-lookup"><span data-stu-id="64f40-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="64f40-113">多くの組織では、次の Gpo は、Skype ルーム システム アプライアンス PC の機能に影響を与えるがあります。</span><span class="sxs-lookup"><span data-stu-id="64f40-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="64f40-114">オーバーライドしたり、Skype ルーム システムの OU で Gpo の継承をブロックすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="64f40-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="64f40-115">ログオン セッションのタイムアウト (自動ロックアウト)</span><span class="sxs-lookup"><span data-stu-id="64f40-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="64f40-116">電源管理関連のポリシー</span><span class="sxs-lookup"><span data-stu-id="64f40-116">Power management related policies</span></span>
    
  - <span data-ttu-id="64f40-117">追加の認証手順が必要</span><span class="sxs-lookup"><span data-stu-id="64f40-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="64f40-118">ローカル ドライブへのアクセスを拒否</span><span class="sxs-lookup"><span data-stu-id="64f40-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="64f40-119">ユーザーに低速のネットワーク接続を推奨する</span><span class="sxs-lookup"><span data-stu-id="64f40-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="64f40-120">ログオン時に特定のプログラムを起動する</span><span class="sxs-lookup"><span data-stu-id="64f40-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="64f40-121">ドメインに参加するすべてのマシンで別のドメイン ユーザー アカウントを作成する。</span><span class="sxs-lookup"><span data-stu-id="64f40-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="64f40-122">Skype ルーム システムに Windows の更新プログラムをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="64f40-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="64f40-123">または、アプライアンス PC をワークグループに残しておくことも可能です。</span><span class="sxs-lookup"><span data-stu-id="64f40-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="64f40-124">として Skype ビジネスのクライアントのデスクトップにこの必要があります Skype ルーム システム アプライアンス PC のルート証明書チェーンを手動でインポートするのには。</span><span class="sxs-lookup"><span data-stu-id="64f40-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="64f40-125">ビジネス展開するため、Skype が (たとえばと Entrust、VeriSign) のパブリック証明書を使用する場合は、ルート証明書チェーンをインポートする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="64f40-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="64f40-126">Skype ルーム システムのコンピューターをドメインに参加する場合は、OU、Gpo からできない可能性があります、意図しないに誤って Skype ルーム システムのマシンへの参加を回避するようにしてください正しい OU に参加します。</span><span class="sxs-lookup"><span data-stu-id="64f40-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="64f40-127">Skype ルーム システムのコンピューターから次のコマンドレットを使用して正しい OU に参加することができ、LRS の機能を妨げる可能性がある Gpo を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="64f40-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="64f40-128">これらのコマンドレットを実行するには、システム管理者か OEM パートナーに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="64f40-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="64f40-129">独立した OU を作成して継承をブロックしても、ハイ レベルな部分で問題を引き起こす可能性のあるポリシーがいくつか存在します。</span><span class="sxs-lookup"><span data-stu-id="64f40-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="64f40-130">No Override を設定したグループ ポリシーは、Block Policy Inheritance を設定した OU より優先されます。</span><span class="sxs-lookup"><span data-stu-id="64f40-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="64f40-131">詳細については、グループ ポリシーのドキュメントに[上書きポリシー継承のブロックと比較して](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f40-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="64f40-132">これらの問題を解決する手段は、1 つではないかもしれません。</span><span class="sxs-lookup"><span data-stu-id="64f40-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="64f40-133">組織の Active Directory の専門家に、適切な GPO 設定の OU、少なくとも上で説明したポリシーが存在しない OU が提供されていることを確認するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="64f40-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="64f40-134">Skype ルーム システム デバイスのサービスの品質 (QoS) を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64f40-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="64f40-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="64f40-135">See also</span></span>
  
[<span data-ttu-id="64f40-136">デバイス構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="64f40-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="64f40-137">サービスの品質の管理</span><span class="sxs-lookup"><span data-stu-id="64f40-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
