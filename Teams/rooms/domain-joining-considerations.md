---
title: Skype Room System のドメイン参加に関する考慮事項
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。
ms.openlocfilehash: f2cad169b812d3da3a964c96adabc498df1009b8
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826085"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="1b73a-103">Skype Room System ドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1b73a-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="1b73a-104">このトピックでは、Skype Room System アプライアンス PC をドメインに参加させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b73a-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="1b73a-105">ドメイン参加に関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="1b73a-105">Domain joining considerations</span></span>

<span data-ttu-id="1b73a-106">Skype Room System アプライアンス PC を Active Directory ドメインに参加させるか、あるいはワークグループに入れたままにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="1b73a-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="1b73a-107">この決定を行う前に、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="1b73a-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="1b73a-108">Skype Room System アプライアンス PC をドメインに参加させると、組織のプライベート ルート証明書チェーンの自動インポートが容易になります。</span><span class="sxs-lookup"><span data-stu-id="1b73a-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="1b73a-109">Skype Room System アプライアンス PC をドメインに参加させると、ドメイン ユーザーとグループに管理者権限を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="1b73a-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="1b73a-110">これにより、ローカル コンピューター レベルの管理者アカウントのパスワードを記憶する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="1b73a-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="1b73a-111">Skype Room System アプライアンス PC をドメインに参加させる場合、グループ ポリシー オブジェクト (GPO) の例外を、すべての Skype Room System マシン オブジェクトが配置されている OU に提供できるよう、独立した組織単位 (OU) を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b73a-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="1b73a-112">その場合、Skype Room System アプライアンス PC をドメインに参加させる前に OU にマシン オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b73a-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="1b73a-113">多くの組織では、次の GPO が用意されています。それらは Skype Room System アプライアンス PC 機能に影響します。</span><span class="sxs-lookup"><span data-stu-id="1b73a-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="1b73a-114">Skype Room System OU でこれらの GPO の継承を上書きするか、ブロックしてください。</span><span class="sxs-lookup"><span data-stu-id="1b73a-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="1b73a-115">ログオン セッションのタイムアウト (自動ロックアウト)</span><span class="sxs-lookup"><span data-stu-id="1b73a-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="1b73a-116">電源管理関連のポリシー</span><span class="sxs-lookup"><span data-stu-id="1b73a-116">Power management related policies</span></span>
  - <span data-ttu-id="1b73a-117">追加の認証手順が必要</span><span class="sxs-lookup"><span data-stu-id="1b73a-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="1b73a-118">ローカル ドライブへのアクセスを拒否</span><span class="sxs-lookup"><span data-stu-id="1b73a-118">Denying access to local drives</span></span>
  - <span data-ttu-id="1b73a-119">ユーザーに低速のネットワーク接続を推奨する</span><span class="sxs-lookup"><span data-stu-id="1b73a-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="1b73a-120">ログオン時に特定のプログラムを起動する</span><span class="sxs-lookup"><span data-stu-id="1b73a-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="1b73a-121">ドメインに参加するすべてのマシンで別のドメイン ユーザー アカウントを作成する。</span><span class="sxs-lookup"><span data-stu-id="1b73a-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="1b73a-122">Skype Room System に Windows Update をプッシュする</span><span class="sxs-lookup"><span data-stu-id="1b73a-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="1b73a-123">代替策として、アプライアンス PC をワークグループに残しておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="1b73a-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="1b73a-124">デスクトップ Microsoft Teams や Skype for Business クライアントの場合と同様に、この操作を行うには Skype Room System アプライアンス PC でルート証明書チェーンを手動でインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b73a-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="1b73a-125">ただし、展開でパブリック証明書 (たとえば、Entrust、VeriSign など) を使用している場合は、ルート証明書チェーンをインポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1b73a-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="1b73a-126">Skype Room System マシンをドメインに参加させる計画を立てる場合、GPO の範囲外になる可能性があるため、Skype Room System マシンを意図しない OU に誤って参加させないように、正しい OU に参加するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1b73a-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="1b73a-127">Skype Room System マシンから次のコマンドレットを使用することで、正しい OU に参加させることができ、LRS 機能をブロックする可能性のある GPO を受け取ることはありません。</span><span class="sxs-lookup"><span data-stu-id="1b73a-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="1b73a-128">これらのコマンドレットを実行するには、システム管理者か OEM パートナーに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="1b73a-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="1b73a-129">独立した OU を作成して継承をブロックしても、ハイ レベルな部分で問題を引き起こす可能性のあるポリシーがいくつか存在します。</span><span class="sxs-lookup"><span data-stu-id="1b73a-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="1b73a-130">No Override を設定したグループ ポリシーは、Block Policy Inheritance を設定した OU より優先されます。</span><span class="sxs-lookup"><span data-stu-id="1b73a-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="1b73a-131">詳細については、グループ ポリシーに関するドキュメントの「[No Override と Block Policy Inheritance の比較](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b73a-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="1b73a-132">これらの問題を解決する手段は、1 つではないかもしれません。</span><span class="sxs-lookup"><span data-stu-id="1b73a-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="1b73a-133">組織の Active Directory の専門家に、適切な GPO 設定の OU、少なくとも上で説明したポリシーが存在しない OU が提供されていることを確認するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1b73a-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="1b73a-134">また、Skype Room System デバイスでサービスの品質 (QoS) を有効にしておくことを推奨します。</span><span class="sxs-lookup"><span data-stu-id="1b73a-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b73a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b73a-135">See also</span></span>
  
[<span data-ttu-id="1b73a-136">デバイス構成: 新規作成または現在の形式のままで編集</span><span class="sxs-lookup"><span data-stu-id="1b73a-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="1b73a-137">サービスの品質の管理</span><span class="sxs-lookup"><span data-stu-id="1b73a-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements.#managing-quality-of-service)
