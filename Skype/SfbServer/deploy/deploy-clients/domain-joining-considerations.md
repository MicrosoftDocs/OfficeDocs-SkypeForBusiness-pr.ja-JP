---
title: Skype Room System のドメイン参加に関する考慮事項
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
description: このトピックでは、Skype Room System アプライアンス PC をドメインに参加する方法について説明します。
ms.openlocfilehash: 6d6decf689b1a38615851911b42676050a823e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805917"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="f5505-103">Skype Room System のドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="f5505-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="f5505-104">このトピックでは、Skype Room System アプライアンス PC をドメインに参加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5505-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="f5505-105">ドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="f5505-105">Domain joining considerations</span></span>

<span data-ttu-id="f5505-106">Skype Room System アプライアンス PC を Active Directory ドメインに参加するか、ワークグループに残します。</span><span class="sxs-lookup"><span data-stu-id="f5505-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="f5505-107">この決定を行う前に、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="f5505-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="f5505-108">Skype Room System アプライアンス PC のドメイン参加は、組織のプライベート ルート証明書チェーンを自動的にインポートするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f5505-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="f5505-109">Skype Room System アプライアンス PC をドメインに参加すると、ドメイン ユーザーとグループに管理者権限を付与できます。</span><span class="sxs-lookup"><span data-stu-id="f5505-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="f5505-110">そうすることで、ローカル コンピューター レベルの管理者アカウント パスワードを覚えておく必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f5505-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="f5505-111">Skype Room System アプライアンス PC をドメインに参加する場合、すべての Skype Room System コンピューター オブジェクトが存在する OU にグループ ポリシー オブジェクト (GPO) の除外を提供できるよう、個別の組織単位 (OU) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5505-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="f5505-112">これを行う場合は、Skype Room System アプライアンス PC をドメインに参加する前に OU にマシン オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5505-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="f5505-113">多くの組織には、Skype Room System アプライアンス PC の機能に影響する次の GPO があります。</span><span class="sxs-lookup"><span data-stu-id="f5505-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="f5505-114">Skype Room System OU でこれらの GPO の継承を上書きまたはブロックします。</span><span class="sxs-lookup"><span data-stu-id="f5505-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="f5505-115">ログオン セッションのタイムアウト (自動ロックアウト)</span><span class="sxs-lookup"><span data-stu-id="f5505-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="f5505-116">電源管理に関連するポリシー</span><span class="sxs-lookup"><span data-stu-id="f5505-116">Power management related policies</span></span>
    
  - <span data-ttu-id="f5505-117">追加の認証手順を要求する</span><span class="sxs-lookup"><span data-stu-id="f5505-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="f5505-118">ローカル ドライブへのアクセスを拒否する</span><span class="sxs-lookup"><span data-stu-id="f5505-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="f5505-119">低速なネットワーク接続をユーザーに求める</span><span class="sxs-lookup"><span data-stu-id="f5505-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="f5505-120">ログオン時に特定のプログラムを開始する</span><span class="sxs-lookup"><span data-stu-id="f5505-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="f5505-121">ドメインに参加しているすべてのコンピューターに別のドメイン ユーザー アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="f5505-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="f5505-122">Skype Room System への Windows Update のプッシュ</span><span class="sxs-lookup"><span data-stu-id="f5505-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="f5505-123">または、アプライアンス PC をワークグループに残しておく場合があります。</span><span class="sxs-lookup"><span data-stu-id="f5505-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="f5505-124">デスクトップの Skype for Business クライアントと同様に、Skype Room System アプライアンス PC にルート証明書チェーンを手動でインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5505-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="f5505-125">Skype for Business 展開でパブリック証明書 (たとえば、Entrust、VeriSign など) を使用している場合は、ルート証明書チェーンをインポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f5505-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="f5505-126">Skype Room System コンピューターをドメインに参加する予定の場合は、SKYPE Room System コンピューターが意図しない OU に誤って参加しないようにしてください。GPO から解放されない可能性があります。正しい OU に参加していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f5505-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="f5505-127">Skype Room System コンピューターから次のコマンドレットを使用して正しい OU に参加できます。また、LRS 機能をブロックする可能性がある GPO を受信することはできません。</span><span class="sxs-lookup"><span data-stu-id="f5505-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="f5505-128">次のコマンドレットを実行するには、システム管理者または OEM パートナーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f5505-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="f5505-129">別の OU を作成して継承をブロックする場合でも、より高いレベルで問題を引き起こす可能性があるいくつかのポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="f5505-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="f5505-130">[上書きなし] 設定を持つグループ ポリシーは、ポリシーの継承をブロックする設定を持つ OU より優先されます。</span><span class="sxs-lookup"><span data-stu-id="f5505-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="f5505-131">詳細については、「グループ ポリシー」のドキュメントの記事 [「No Override as Compared to Block Policy Inheritance」](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5505-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="f5505-132">これらの問題を解決するには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="f5505-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="f5505-133">Active Directory の専門家に相談して、適切な GPO 設定を持つ OU、または前に説明したポリシーが存在しない OU を必ず提供するようにお願いします。</span><span class="sxs-lookup"><span data-stu-id="f5505-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="f5505-134">Skype Room System デバイスのサービス品質 (QoS) を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="f5505-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5505-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5505-135">See also</span></span>
  
[<span data-ttu-id="f5505-136">デバイス構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="f5505-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="f5505-137">サービスの品質の管理</span><span class="sxs-lookup"><span data-stu-id="f5505-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
