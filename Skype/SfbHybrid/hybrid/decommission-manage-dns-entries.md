---
title: オンプレミス環境の使用停止時に DNS エントリを管理する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: オンプレミス環境を使用停止する際に DNS エントリを管理するSkype for Business手順。
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458996"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a><span data-ttu-id="96c90-103">DNS エントリを更新して、組織がすべてのユーザーのみTeamsする</span><span class="sxs-lookup"><span data-stu-id="96c90-103">Update DNS entries to enable your organization to be all Teams Only</span></span>

<span data-ttu-id="96c90-104">以前にオンプレミスの展開が Skype for Business Server または Lync Server に存在していた組織には、オンプレミスの展開を指す DNS エントリSkype for Businessがあります。</span><span class="sxs-lookup"><span data-stu-id="96c90-104">Organizations that previously had on-premises deployments of Skype for Business Server or Lync Server may still have DNS entries that point to an on-premises Skype for Business deployment.</span></span> <span data-ttu-id="96c90-105">これらのレコードは、組織にオンプレミスのユーザーが含まれる場合Skype for Businessです。</span><span class="sxs-lookup"><span data-stu-id="96c90-105">These records are required if your organization includes on-premises Skype for Business users.</span></span> <span data-ttu-id="96c90-106">ただし、組織にオンプレミスのユーザーまたは Lync Server ユーザー Skype for Businessがなくなったら、これらのレコードは不要になります。</span><span class="sxs-lookup"><span data-stu-id="96c90-106">However, once your organization no longer has any on-premises Skype for Business or Lync Server users, these records are no longer required.</span></span> <span data-ttu-id="96c90-107">実際、オンプレミスから Teams への移行を完了する一環として、これらのレコードを更新して、Microsoft 365または削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c90-107">And in fact, as part of completing the migration from on-premises to Teams, these records must be updated to point to Microsoft 365 or removed.</span></span> <span data-ttu-id="96c90-108">Microsoft は、この手順を実行できません。</span><span class="sxs-lookup"><span data-stu-id="96c90-108">Microsoft cannot take this step for you.</span></span>

<span data-ttu-id="96c90-109">TeamsOnly をテナント全体に付与しようとすると、Teamsは DNS をチェックして、組織にこれらの DNS レコードが存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="96c90-109">When attempting to grant TeamsOnly to the entire tenant, Teams will check DNS to determine if any of these DNS records exist for your organization.</span></span> <span data-ttu-id="96c90-110">レコードが見つかり、Microsoft 365 以外を指している場合は、テナント共存モードを TeamsOnly に変更しようとすると、設計上失敗します。</span><span class="sxs-lookup"><span data-stu-id="96c90-110">If any records are found, and if they point to something other than Microsoft 365, the attempt to change the tenant coexistence mode to TeamsOnly will fail by design.</span></span> <span data-ttu-id="96c90-111">この設計は、オンプレミスユーザーを持つハイブリッド組織が、誤って TeamsOnly モードをテナントに適用するのを防ぐためです。これは、オンプレミスの Skype for Business ユーザー (Teams または Skype for Business を使用するかどうか) のフェデレーションを壊す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="96c90-111">This design is to prevent hybrid organizations with on-premises users from mistakenly applying TeamsOnly mode to the tenant--because doing so would break federation for any on-premises Skype for Business users (whether using Teams or Skype for Business).</span></span>

<span data-ttu-id="96c90-112">さらに、これらのレコードを更新して、テナント全体に TeamsOnly を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c90-112">Furthermore, these records must be updated so that you can grant TeamsOnly to the entire tenant.</span></span>

> [!Note] 
> <span data-ttu-id="96c90-113">まれに、組織の DNS をオンプレミスのポイントから Microsoft 365 に変更すると、他の組織がフェデレーション構成を更新するまで、他の組織とのフェデレーションが停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="96c90-113">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
>
> - <span data-ttu-id="96c90-114">以前のダイレクト フェデレーション モデル (許可パートナー サーバーとも呼ばれる) を使用しているフェデレーション組織は、プロキシ FQDN を削除するために、組織の許可されたドメイン エントリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c90-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="96c90-115">この従来のフェデレーション モデルは DNS SRV レコードに基づいていないので、組織がクラウドに移行すると、このような構成は古くなる。</span><span class="sxs-lookup"><span data-stu-id="96c90-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
> 
> - <span data-ttu-id="96c90-116">sipfed.online.lync のホスティング プロバイダーが有効になっていないフェデレーション組織。 <span>com は構成を更新して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c90-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="96c90-117">この状況は、フェデレーション組織が純粋にオンプレミスであり、ハイブリッドテナントまたはオンライン テナントとフェデレーションしたことがない場合にのみ可能です。</span><span class="sxs-lookup"><span data-stu-id="96c90-117">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="96c90-118">このような場合、ホスティング プロバイダーを有効にするまで、これらの組織とのフェデレーションは機能しません。</span><span class="sxs-lookup"><span data-stu-id="96c90-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
>
> <span data-ttu-id="96c90-119">フェデレーション パートナーが直接フェデレーションを使用している可能性がある、またはオンラインまたはハイブリッド組織とフェデレーションしていないと疑われる場合は、クラウドへの移行を完了する準備をしている間に、この情報に関する通信を送信してください。</span><span class="sxs-lookup"><span data-stu-id="96c90-119">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

## <a name="how-to-identify-stale-dns-records"></a><span data-ttu-id="96c90-120">古い DNS レコードを識別する方法</span><span class="sxs-lookup"><span data-stu-id="96c90-120">How to identify stale DNS records</span></span>

<span data-ttu-id="96c90-121">組織がすべての Teams のみになるのを妨げる DNS レコードを識別するには、Teams 管理センターを使用して共存モードを TeamsOnly に変更できます。</span><span class="sxs-lookup"><span data-stu-id="96c90-121">To identify any DNS records that prevent your organization from becoming all Teams Only, you can use the Teams admin center  to change the coexistence mode to TeamsOnly.</span></span> <span data-ttu-id="96c90-122">[アップグレード]**の [組織全体の**  ->  **設定Teams移動します**。</span><span class="sxs-lookup"><span data-stu-id="96c90-122">Go to **Org-wide setting** -> **Teams Upgrade**.</span></span> <span data-ttu-id="96c90-123">組織が [のみ] になTeams DNS レコードは、エラー メッセージに含まれます。</span><span class="sxs-lookup"><span data-stu-id="96c90-123">Any DNS records that prevent the organization from becoming Teams Only will be included in the error message.</span></span>  <span data-ttu-id="96c90-124">DNS レコードが見つからない場合、組織の共存モードは TeamsOnly に変更されます。</span><span class="sxs-lookup"><span data-stu-id="96c90-124">In the event no DNS records are found, the coexistence mode for your organization will be changed to TeamsOnly.</span></span> 

## <a name="how-to-remove-stale-dns-records"></a><span data-ttu-id="96c90-125">古い DNS レコードを削除する方法</span><span class="sxs-lookup"><span data-stu-id="96c90-125">How to remove stale DNS records</span></span>

<span data-ttu-id="96c90-126">組織にオンプレミスのユーザーまたは Lync Server Skype for Business Serverが存在しない場合は、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="96c90-126">If your organization no longer has any on-premises Skype for Business Server or Lync Server users, you must do the following:</span></span>

- <span data-ttu-id="96c90-127">DNS Skype for Businessを更新して、(オンプレミスMicrosoft 365ではなく) DNS レコードをポイントします。</span><span class="sxs-lookup"><span data-stu-id="96c90-127">Update Skype for Business DNS records to point to Microsoft 365 (instead of the on-premises deployment).</span></span>

- <span data-ttu-id="96c90-128">SIP Skype for Business使用されなくなった場合は、DNS レコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="96c90-128">Remove Skype for Business DNS records if the SIP domain is no longer used.</span></span> 

<span data-ttu-id="96c90-129">次のレコードを見つける各ドメインで、次のように更新します。</span><span class="sxs-lookup"><span data-stu-id="96c90-129">In each domain where you find any of the following records, update them as follows:</span></span>

| <span data-ttu-id="96c90-130">レコードの種類</span><span class="sxs-lookup"><span data-stu-id="96c90-130">Record type</span></span> | <span data-ttu-id="96c90-131">名前</span><span class="sxs-lookup"><span data-stu-id="96c90-131">Name</span></span> | <span data-ttu-id="96c90-132">TTL</span><span class="sxs-lookup"><span data-stu-id="96c90-132">TTL</span></span> | <span data-ttu-id="96c90-133">優先度</span><span class="sxs-lookup"><span data-stu-id="96c90-133">Priority</span></span> | <span data-ttu-id="96c90-134">太さ</span><span class="sxs-lookup"><span data-stu-id="96c90-134">Weight</span></span> | <span data-ttu-id="96c90-135">ポート</span><span class="sxs-lookup"><span data-stu-id="96c90-135">Port</span></span> | <span data-ttu-id="96c90-136">Value</span><span class="sxs-lookup"><span data-stu-id="96c90-136">Value</span></span> |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| <span data-ttu-id="96c90-137">SRV</span><span class="sxs-lookup"><span data-stu-id="96c90-137">SRV</span></span> | <span data-ttu-id="96c90-138">_sipfederationtls.tcp</span><span class="sxs-lookup"><span data-stu-id="96c90-138">_sipfederationtls.tcp</span></span> | <span data-ttu-id="96c90-139">3600</span><span class="sxs-lookup"><span data-stu-id="96c90-139">3600</span></span> |  <span data-ttu-id="96c90-140">100</span><span class="sxs-lookup"><span data-stu-id="96c90-140">100</span></span> | <span data-ttu-id="96c90-141">1</span><span class="sxs-lookup"><span data-stu-id="96c90-141">1</span></span> | <span data-ttu-id="96c90-142">5061</span><span class="sxs-lookup"><span data-stu-id="96c90-142">5061</span></span>  | <span data-ttu-id="96c90-143">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="96c90-143">sipfed.online.lync.com</span></span> |
| <span data-ttu-id="96c90-144">SRV</span><span class="sxs-lookup"><span data-stu-id="96c90-144">SRV</span></span> | <span data-ttu-id="96c90-145">_sip.tls</span><span class="sxs-lookup"><span data-stu-id="96c90-145">_sip.tls</span></span> | <span data-ttu-id="96c90-146">3600</span><span class="sxs-lookup"><span data-stu-id="96c90-146">3600</span></span>  | <span data-ttu-id="96c90-147">100</span><span class="sxs-lookup"><span data-stu-id="96c90-147">100</span></span> |    <span data-ttu-id="96c90-148">1</span><span class="sxs-lookup"><span data-stu-id="96c90-148">1</span></span>   | <span data-ttu-id="96c90-149">443</span><span class="sxs-lookup"><span data-stu-id="96c90-149">443</span></span>   | <span data-ttu-id="96c90-150">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="96c90-150">sipdir.online.lync.com</span></span> |
| <span data-ttu-id="96c90-151">CNAME</span><span class="sxs-lookup"><span data-stu-id="96c90-151">CNAME</span></span> | <span data-ttu-id="96c90-152">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="96c90-152">lyncdiscover</span></span> |    <span data-ttu-id="96c90-153">3600</span><span class="sxs-lookup"><span data-stu-id="96c90-153">3600</span></span> |  <span data-ttu-id="96c90-154">該当なし</span><span class="sxs-lookup"><span data-stu-id="96c90-154">N/A</span></span> |   <span data-ttu-id="96c90-155">該当なし</span><span class="sxs-lookup"><span data-stu-id="96c90-155">N/A</span></span> |   <span data-ttu-id="96c90-156">該当なし</span><span class="sxs-lookup"><span data-stu-id="96c90-156">N/A</span></span> |   <span data-ttu-id="96c90-157">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="96c90-157">webdir.online.lync.com</span></span> |
| <span data-ttu-id="96c90-158">CNAME</span><span class="sxs-lookup"><span data-stu-id="96c90-158">CNAME</span></span> |   <span data-ttu-id="96c90-159">sip</span><span class="sxs-lookup"><span data-stu-id="96c90-159">sip</span></span> | <span data-ttu-id="96c90-160">3600</span><span class="sxs-lookup"><span data-stu-id="96c90-160">3600</span></span> |    <span data-ttu-id="96c90-161">該当なし</span><span class="sxs-lookup"><span data-stu-id="96c90-161">N/A</span></span> |   <span data-ttu-id="96c90-162">該当なし</span><span class="sxs-lookup"><span data-stu-id="96c90-162">N/A</span></span>  | <span data-ttu-id="96c90-163">該当なし</span><span class="sxs-lookup"><span data-stu-id="96c90-163">N/A</span></span> |    <span data-ttu-id="96c90-164">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="96c90-164">sipdir.online.lync.com</span></span> |
|||||||




