---
title: 'Lync Server 2013: Lync Server ハイブリッド環境を準備および展開するための手順'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 207cb9b8435294abeac12f67506eb356a6ca73c6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a><span data-ttu-id="d0dc4-102">Lync Server 2013 ハイブリッド環境を準備および展開するための手順</span><span class="sxs-lookup"><span data-stu-id="d0dc4-102">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0dc4-103">_**トピックの最終更新日:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="d0dc4-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="d0dc4-104">次の表に、Skype for Business Online および Microsoft Office 365 を使用したハイブリッド展開用に環境を準備するために必要な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-104">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d0dc4-105">完了済み</span><span class="sxs-lookup"><span data-stu-id="d0dc4-105">Completed?</span></span></th>
<th><span data-ttu-id="d0dc4-106">手順</span><span class="sxs-lookup"><span data-stu-id="d0dc4-106">Step</span></span></th>
<th><span data-ttu-id="d0dc4-107">説明</span><span class="sxs-lookup"><span data-stu-id="d0dc4-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="d0dc4-108">Office 365 のテナントアカウントを作成して Lync Online を有効にする</span><span class="sxs-lookup"><span data-stu-id="d0dc4-108">Create a tenant account for Office 365 and enable Lync Online</span></span></p></td>
<td><p><span data-ttu-id="d0dc4-109">Office 365 および Lync Online ( <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>) について説明します。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-109">Learn about Office 365 and Lync Online at <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span></span></p>
<p><span data-ttu-id="d0dc4-110">環境で Office 365 の準備が整っていることを確認するには、<a href="https://go.microsoft.com/fwlink/p/?linkid=401408">システム要件</a>を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-110">To make sure that your environment is ready for Office 365, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Requirements</a>.</span></span></p>
<p><span data-ttu-id="d0dc4-111">Office 365 のセットアップの詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">365 office を使い始める</a>」および「 <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">office 365</a>をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-111">For details about setting up Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with Office 365</a> and <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">Set Up Office 365</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="d0dc4-112">ドメインを追加して所有権を確認する</span><span class="sxs-lookup"><span data-stu-id="d0dc4-112">Add your domain and verify ownership</span></span></p></td>
<td><p><span data-ttu-id="d0dc4-113">ドメインは、<em>バニティドメイン</em>と呼ばれることもあります。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-113">Your domain is sometimes also referred to as your <em>vanity domain</em>.</span></span> <span data-ttu-id="d0dc4-114">Office 365 テナントにドメインを追加してから、「Office 365 でドメインを検証するには」の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-114">You must add your domain to your Office 365 tenant, and then follow the steps to validate the domain with Office 365.</span></span> <span data-ttu-id="d0dc4-115">これは、ドメインの所有者であることを確認するためのものです。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-115">This is to confirm that you are the owner of the domain.</span></span></p>
<p><span data-ttu-id="d0dc4-116">Office 365 テナントにドメインを追加するには、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">add your domain To office 365</a>」に記載されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-116">To add your domain to your Office 365 tenant, follow the steps described at <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Add your domain to Office 365</a>.</span></span></p>
<p><span data-ttu-id="d0dc4-117">「Office 365 サービスの DNS レコードの編集」を含む&quot;、トピックの各セクションのすべての手順を完了します。&quot;</span><span class="sxs-lookup"><span data-stu-id="d0dc4-117">Complete all of the steps in each section in the topic, including &quot;Edit DNS records for your Office 365 services.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="d0dc4-118">環境の準備状況を確認する</span><span class="sxs-lookup"><span data-stu-id="d0dc4-118">Verify environment readiness</span></span></p></td>
<td><p><span data-ttu-id="d0dc4-119">Office 365 セットアップアシスタントを使用して、Office 365 を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-119">You can use the Office 365 Setup Assistant to help you deploy Office 365.</span></span> <span data-ttu-id="d0dc4-120">詳細については、「<a href="https://go.microsoft.com/fwlink/p/?linkid=254985">セットアップアシスタントを使用して Office 365 の準備状況を判断する</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-120">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Use Setup Assistant to determine Office 365 readiness</a>.</span></span></p>
<p><span data-ttu-id="d0dc4-121">ツールの使用と Office 365 の展開の詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">office 365 展開ガイド</a>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-121">For details about using the tool and deploying Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 deployment guide</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="d0dc4-122">Active Directory の同期を準備する</span><span class="sxs-lookup"><span data-stu-id="d0dc4-122">Prepare for Active Directory synchronization</span></span></p></td>
<td><p><span data-ttu-id="d0dc4-123">Active Directory 同期では、オンプレミスの Active Directory が Office 365 と継続的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-123">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="d0dc4-124">これにより、各ユーザーアカウントおよびグループの同期バージョンを作成できます。また、ローカルの Microsoft Exchange Server 環境から Microsoft Exchange Online へのグローバルアドレス一覧 (GAL) 同期も有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-124">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="d0dc4-125">ユーザーが Lync Online に移動されていない場合でも、組織内のすべての Lync ユーザーの AD アカウントをオンプレミスとオンラインの Lync 展開との間で同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-125">You need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="d0dc4-126">すべてのユーザーを同期しない場合は、組織内のオンプレミスのユーザーとオンラインユーザーとの間の通信が期待どおりに機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-126">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>


</div>
<p><span data-ttu-id="d0dc4-127">Active Directory 同期のために環境を準備するには、「シングルサインオンの設定」を含む「<a href="https://go.microsoft.com/fwlink/p/?linkid=254988">ディレクトリ同期のロードマップ</a>」で説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-127">To prepare your environment for Active Directory synchronization, follow the steps described in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Directory synchronization Roadmap</a>, including setting up single sign-on.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="d0dc4-128">Active Directory フェデレーションサービス (AD FS) の証明書を作成する</span><span class="sxs-lookup"><span data-stu-id="d0dc4-128">Create certificates for Active Directory Federation Services (AD FS)</span></span></p></td>
<td><p><span data-ttu-id="d0dc4-129">Office 365 との id フェデレーションで使用される証明書を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-129">You will need to create the certificates that are used for identity federation with Office 365.</span></span> <span data-ttu-id="d0dc4-130">詳細については、「<a href="https://go.microsoft.com/fwlink/p/?linkid=285376">チェックリスト: AD fs を使用してシングルサインオンを実装および管理する</a>」の「ad Fs を計画して展開する」の「フェデレーションサーバー証明書」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-130">For more information, see the “Federation server certificates” section of the Plan for and deploy AD FS for use with single sign-on topic at <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="d0dc4-131">AD FS 用の証明書の割り当て</span><span class="sxs-lookup"><span data-stu-id="d0dc4-131">Assign certificates for AD FS</span></span></p></td>
<td><p><span data-ttu-id="d0dc4-132">Office 365 との id フェデレーションで使用される証明書を作成した後、それらをインストールして割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-132">After you create the certificates that are used for identity federation with Office 365, you must install and assign them.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="d0dc4-133">パイロットユーザーを Skype for Business Online に移動する</span><span class="sxs-lookup"><span data-stu-id="d0dc4-133">Move pilot users to Skype for Business Online</span></span></p></td>
<td><p><span data-ttu-id="d0dc4-134">Skype for Business Online の環境を準備および構成する手順を完了したら、パイロットユーザーの Lync Online への移行を開始できます。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-134">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to Lync Online.</span></span></p>
<p><span data-ttu-id="d0dc4-135">「 <a href="lync-server-2013-move-users-to-lync-online.md">Lync Server 2013 でユーザーを Lync Online に移行する」を</a>参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-135">See <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="d0dc4-136">ハイブリッド展開でユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="d0dc4-136">Administering users in a hybrid deployment</span></span></p></td>
<td><p><span data-ttu-id="d0dc4-137">ハイブリッド展開でユーザーを管理する方法の詳細については、「<a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">ハイブリッド Lync Server 2013 展開でユーザー</a>を管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0dc4-137">For details about how to administer users in a hybrid deployment, see <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

