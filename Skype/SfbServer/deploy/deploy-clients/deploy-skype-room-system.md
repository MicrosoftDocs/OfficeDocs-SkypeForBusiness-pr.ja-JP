---
title: Skype ルーム システムの展開の概要
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: 方法については、Skype ルーム システムでは、会議を導入してルーム ソリューションの統合されたハードウェアと Skype をビジネス ・ ミーティングに参加するのには最適なソフトウェアで構成されます。
ms.openlocfilehash: ed31a1892ca1661282f87775fae805da5b5f8504
ms.sourcegitcommit: 0f089f0c1bc641793c61928fb1c8fa62b2dfabee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2018
ms.locfileid: "19927803"
---
# <a name="deployment-planning-for-skype-room-system-in-skype-for-business"></a><span data-ttu-id="84991-103">ビジネス用の Skype の Skype ルームのシステムの計画の展開</span><span class="sxs-lookup"><span data-stu-id="84991-103">Deployment planning for Skype Room System in Skype for Business</span></span>
 
<span data-ttu-id="84991-104">方法については、Skype ルーム システムでは、会議を導入してルーム ソリューションの統合されたハードウェアと Skype をビジネス ・ ミーティングに参加するのには最適なソフトウェアで構成されます。</span><span class="sxs-lookup"><span data-stu-id="84991-104">Read about how do deploy Skype Room System, a meeting room solution consisting of integrated hardware and software that is optimized to join Skype for Business meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="84991-105">これの目的でコンテンツ、Crestron RL、スマート ・ ルーム システムのビジネス用の Skype とポリコム CX8000 があると呼ばれる Skype ルーム システムです。</span><span class="sxs-lookup"><span data-stu-id="84991-105">For the purposes of this content, Skype for Business for SMART Room System, Crestron RL, and Polycom CX8000 will be referred to as Skype Room System.</span></span> 

> [!NOTE]
> <span data-ttu-id="84991-106">Skype ルーム システム v2 は、さまざまな依存関係および展開の手順で別の製品です。</span><span class="sxs-lookup"><span data-stu-id="84991-106">Skype Room Systems v2 is a different product with different dependencies and deployment procedures.</span></span> <span data-ttu-id="84991-107">Skype ルーム システム v2 については、 [Skype ルーム システムの計画のバージョン 2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84991-107">For information on Skype Room Systems v2, see [Plan Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md).</span></span>
  
 <span data-ttu-id="84991-108">Skype ルーム システムは、Skype のビジネス会議は、物理的な会議室での最適化された統合コミュニケーション クライアントをビジネス用の Skype です。</span><span class="sxs-lookup"><span data-stu-id="84991-108">Skype Room System is a Skype for Business unified communications client that has been optimized for Skype for Business meetings in physical conference rooms.</span></span>
  
<span data-ttu-id="84991-109">Skype ルーム システムのクライアントは、ビジネスの SDK は、Skype を使用してビジネス クライアント用の Skype から開発されました。</span><span class="sxs-lookup"><span data-stu-id="84991-109">The Skype Room System client was developed from the Skype for Business client by using the Skype for Business SDK.</span></span> <span data-ttu-id="84991-110">ビジネス クライアント用の Skype は、一部の UI が非表示モードでバック グラウンドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="84991-110">The Skype for Business client runs in the background in partial UI suppressed mode.</span></span> <span data-ttu-id="84991-111">ビジネス クライアント用の Skype では、ビデオ ギャラリー、部屋の前面にある画面上のコンテンツのステージを制御します。</span><span class="sxs-lookup"><span data-stu-id="84991-111">The Skype for Business client controls the video gallery and content stage on the screen at the front of the room.</span></span> <span data-ttu-id="84991-112">Skype ルーム システムのクライアントは、会議を制御するため、卓上型のディスプレイにコンソール経験を提供します。</span><span class="sxs-lookup"><span data-stu-id="84991-112">The Skype Room System client provides a console experience on the tabletop display for controlling the meetings.</span></span> <span data-ttu-id="84991-113">Skype ルームのシステムを提供します。</span><span class="sxs-lookup"><span data-stu-id="84991-113">Skype Room System provides:</span></span> 
  
- <span data-ttu-id="84991-114">ワンタッチでの会議への参加</span><span class="sxs-lookup"><span data-stu-id="84991-114">A one-touch meeting join experience</span></span>
    
- <span data-ttu-id="84991-115">マルチビュー ビデオ ギャラリーの自動セットアップ</span><span class="sxs-lookup"><span data-stu-id="84991-115">Automatic setup of multi-view video gallery</span></span> 
    
- <span data-ttu-id="84991-116">会議室の前方画面でのタッチ対応ホワイトボード</span><span class="sxs-lookup"><span data-stu-id="84991-116">Touch-enabled white boarding on the screen at the front of the room</span></span> 
    
- <span data-ttu-id="84991-117">スケジュールされた会議にアクセスできるカレンダー統合</span><span class="sxs-lookup"><span data-stu-id="84991-117">Calendar integration for access to scheduled meetings</span></span>
    
- <span data-ttu-id="84991-118">コンテンツの共有と切り替え</span><span class="sxs-lookup"><span data-stu-id="84991-118">Content sharing and switching</span></span> 
    
<span data-ttu-id="84991-119">このガイドでは、ビジネスのサーバーと Exchange Server の Skype の Skype ルームのシステムをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="84991-119">This document guides you through provisioning Skype Room System in Skype for Business Server and Exchange Server.</span></span> <span data-ttu-id="84991-120">管理者は、会議室でアプライアンスの PC とデバイスの設定の手順が用意されている Skype ルーム システムのインストール ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84991-120">See also the Skype Room System Installation Guide provided by your administrator, which guides you through setting up the appliance PC and devices in the meeting room.</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="84991-121">前提条件</span><span class="sxs-lookup"><span data-stu-id="84991-121">Prerequisites</span></span>

<span data-ttu-id="84991-122">Skype ルーム システムの要件は、以下です。</span><span class="sxs-lookup"><span data-stu-id="84991-122">Following are the requirements for Skype Room System:</span></span> 
  
- <span data-ttu-id="84991-123">Exchange リソース メールボックス アカウント。Exchange Server (できれば 2013) で有効になっている AutoDiscover サービスを使用する会議室で予定表によるスケジューリングをやりやすくするためです。</span><span class="sxs-lookup"><span data-stu-id="84991-123">An Exchange resource mailbox account to facilitate calendar scheduling for the meeting rooms with AutoDiscover service enabled on Exchange Server (2013 preferred).</span></span>
    
- <span data-ttu-id="84991-124">ビジネス サーバー プール (エンタープライズまたは Standard Edition) は、Skype の Skype ルーム システムのビジネスを有効にしたアカウントの Skype です。</span><span class="sxs-lookup"><span data-stu-id="84991-124">A Skype for Business-enabled Skype Room System account on a Skype for Business Server pool (Enterprise or Standard Edition).</span></span>
    
- <span data-ttu-id="84991-125">必要なすべてのソフトウェアがインストールされた Skype ルーム システム クライアント アプライアンス PC です。</span><span class="sxs-lookup"><span data-stu-id="84991-125">A Skype Room System client appliance PC with all required software installed.</span></span> <span data-ttu-id="84991-126">アプライアンス PC では Windows 7 Embedded Standard オペレーティング システムが実行されていることが必要です。</span><span class="sxs-lookup"><span data-stu-id="84991-126">The appliance PC must be running Windows 7 Embedded Standard operating system.</span></span> <span data-ttu-id="84991-127">アプライアンス PC は、機器一式 (ディスプレイ、カメラ、マイク、スピーカー) と併せて OEM パートナーから提供されます。</span><span class="sxs-lookup"><span data-stu-id="84991-127">This hardware is provided by OEM partners along with all devices (displays, camera, microphone, speakers).</span></span>
    
- <span data-ttu-id="84991-128">PC Skype ルーム システムのアプライアンスを Active Directory ドメイン サービス (AD DS) ドメインに参加させる場合は、Skype の部屋のシステムに影響を与えないグループ ポリシーの設定を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84991-128">If you decide to join the Skype Room System appliance PC to an Active Directory Domain Services (AD DS) domain, you must specify group policy settings that do not interfere with Skype Room System.</span></span> <span data-ttu-id="84991-129">また、アプライアンス PC を Workgroup のままにしておくこともできます。</span><span class="sxs-lookup"><span data-stu-id="84991-129">Alternatively, you can leave this appliance PC in the Workgroup.</span></span> 
    
- <span data-ttu-id="84991-p106">この記事で指示されているコマンドレットを実行するための適切なユーザー権限。CsMeetingRoom コマンドレットは CsUser コマンドレットを基にモデル化されています。そのため、CsUser コマンドレットを実行するために必要な役割ベースのアクセス制御 (RBAC) の役割がすべて、CsMeetingRoom コマンドレットを実行するためにも必要です。</span><span class="sxs-lookup"><span data-stu-id="84991-p106">Appropriate user rights to run the cmdlets specified in this document. The CsMeetingRoom cmdlets are modeled after the CsUser cmdlet. Therefore, all role-based access control (RBAC) roles required to run CsUser cmdlets also apply to CsMeetingRoom cmdlets.</span></span> 
    
## <a name="supported-topologies"></a><span data-ttu-id="84991-133">サポートされるトポロジ</span><span class="sxs-lookup"><span data-stu-id="84991-133">Supported topologies</span></span>

<span data-ttu-id="84991-134">Skype ルーム システム クライアント、社内設置型またはクラウドで、ビジネスおよび Exchange のトポロジの Skype のさまざまな環境間での相互運用性を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="84991-134">The following table indicates Skype Room System client interoperability among various deployments of Skype for Business and Exchange topologies, either on premises or in the cloud:</span></span> 
  

|<span data-ttu-id="84991-135">**トポロジ**</span><span class="sxs-lookup"><span data-stu-id="84991-135">**Topology**</span></span>|<span data-ttu-id="84991-136">**AD**</span><span class="sxs-lookup"><span data-stu-id="84991-136">**AD**</span></span>|<span data-ttu-id="84991-137">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="84991-137">**Skype for Business**</span></span>|<span data-ttu-id="84991-138">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="84991-138">**Exchange**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84991-139">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="84991-139">On premises</span></span>  <br/> |<span data-ttu-id="84991-140">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="84991-140">On premises</span></span>  <br/> |<span data-ttu-id="84991-141">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="84991-141">On premises</span></span>  <br/> |<span data-ttu-id="84991-142">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="84991-142">On premises</span></span>  <br/> |
|<span data-ttu-id="84991-143">Office 365 のマルチ テナント型 (O365MT)</span><span class="sxs-lookup"><span data-stu-id="84991-143">Office 365 Multi-tenant (O365MT)</span></span>  <br/> |<span data-ttu-id="84991-144">オンライン</span><span class="sxs-lookup"><span data-stu-id="84991-144">Online</span></span>  <br/> |<span data-ttu-id="84991-145">オンライン</span><span class="sxs-lookup"><span data-stu-id="84991-145">Online</span></span>  <br/> |<span data-ttu-id="84991-146">オンライン</span><span class="sxs-lookup"><span data-stu-id="84991-146">Online</span></span>  <br/> |
|<span data-ttu-id="84991-147">Office 365 専用</span><span class="sxs-lookup"><span data-stu-id="84991-147">Office 365 Dedicated</span></span>  <br/> <span data-ttu-id="84991-148">(サービス プロバイダーに問い合わせてください)</span><span class="sxs-lookup"><span data-stu-id="84991-148">(Contact your service provider)</span></span>  <br/> |<span data-ttu-id="84991-149">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="84991-149">On premises</span></span>  <br/> |<span data-ttu-id="84991-150">オンライン</span><span class="sxs-lookup"><span data-stu-id="84991-150">Online</span></span>  <br/> |<span data-ttu-id="84991-151">オンライン</span><span class="sxs-lookup"><span data-stu-id="84991-151">Online</span></span>  <br/> |
|<span data-ttu-id="84991-152">ハイブリッド (分割ドメイン)</span><span class="sxs-lookup"><span data-stu-id="84991-152">Hybrid (Split domain)</span></span>  <br/> <span data-ttu-id="84991-153">未サポート</span><span class="sxs-lookup"><span data-stu-id="84991-153">Unsupported</span></span>  <br/> |<span data-ttu-id="84991-154">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="84991-154">On premises</span></span>  <br/> <span data-ttu-id="84991-155">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="84991-155">On premises</span></span>  <br/> <span data-ttu-id="84991-156">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="84991-156">On premises</span></span>  <br/> |<span data-ttu-id="84991-157">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="84991-157">On premises</span></span>  <br/> <span data-ttu-id="84991-158">オンライン</span><span class="sxs-lookup"><span data-stu-id="84991-158">Online</span></span>  <br/> <span data-ttu-id="84991-159">オンライン</span><span class="sxs-lookup"><span data-stu-id="84991-159">Online</span></span>  <br/> |<span data-ttu-id="84991-160">オンライン</span><span class="sxs-lookup"><span data-stu-id="84991-160">Online</span></span>  <br/> <span data-ttu-id="84991-161">オンライン</span><span class="sxs-lookup"><span data-stu-id="84991-161">Online</span></span>  <br/> <span data-ttu-id="84991-162">オンプレミス</span><span class="sxs-lookup"><span data-stu-id="84991-162">On premises</span></span>  <br/> |
   
<span data-ttu-id="84991-163">Lync Server 2013 より前のリリースは、部分的にサポートします。</span><span class="sxs-lookup"><span data-stu-id="84991-163">Releases prior to Lync Server 2013 are partially supported.</span></span> <span data-ttu-id="84991-164">これらのシナリオで Skype ルームのシステムに参加できる Skype (ユーザーによってスケジュールされたものが置かれている Lync Server 2010) ビジネス会議の会議は、"public"は、限り、会議の意味は用にカスタマイズされたアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="84991-164">In these scenarios, Skype Room System can participate in Skype for Business conferences (those that are scheduled by users homed on Lync Server 2010) as long as the conferences are "public," meaning the conferences aren't customized for restricted access.</span></span> 
  
<span data-ttu-id="84991-165">Skype ルーム システムは、Lync server のバージョンの Lync Server 2013 より前のホームことはできません。</span><span class="sxs-lookup"><span data-stu-id="84991-165">Skype Room System cannot be homed on a Lync server version earlier than Lync Server 2013.</span></span> <span data-ttu-id="84991-166">Skype ルーム システムは、カレンダーの設定 - を取得するために Exchange に接続できない場合など、Skype ルーム システム アカウント用に構成された Exchange メールボックスがないか、Exchange にアクセスすることはできません--とアドホック会議と会議の開始が、参加するが、スケジュールされた会議は表示されません。</span><span class="sxs-lookup"><span data-stu-id="84991-166">When a Skype Room System cannot connect to Exchange to retrieve calendar settings--for example, when there is no Exchange mailbox configured for the Skype Room System account or Exchange cannot be accessed--Meet Now and ad hoc conferencing will work, but joining a scheduled meeting will not.</span></span> 
  
<span data-ttu-id="84991-167">次の表は、Exchange Server のバージョンと Skype ルーム システム クライアントのサポートを示します。</span><span class="sxs-lookup"><span data-stu-id="84991-167">The following table indicates Skype Room System client supportability with versions of Exchange Server:</span></span> 
  

|<span data-ttu-id="84991-168">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="84991-168">**Exchange**</span></span>|<span data-ttu-id="84991-169">**設置型の**</span><span class="sxs-lookup"><span data-stu-id="84991-169">**On premises**</span></span>|<span data-ttu-id="84991-170">**オンライン**</span><span class="sxs-lookup"><span data-stu-id="84991-170">**Online**</span></span>|<span data-ttu-id="84991-171">**ハイブリッド**</span><span class="sxs-lookup"><span data-stu-id="84991-171">**Hybrid**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="84991-172">Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="84991-172">Exchange 2010</span></span>  <br/> |<span data-ttu-id="84991-173">はい (単一フォレストのみ)</span><span class="sxs-lookup"><span data-stu-id="84991-173">Yes (single forest only)</span></span>  <br/> |<span data-ttu-id="84991-174">該当なし</span><span class="sxs-lookup"><span data-stu-id="84991-174">N/A</span></span>  <br/> |<span data-ttu-id="84991-175">該当なし</span><span class="sxs-lookup"><span data-stu-id="84991-175">N/A</span></span>  <br/> |
|<span data-ttu-id="84991-176">Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="84991-176">Exchange 2013</span></span>  <br/> |<span data-ttu-id="84991-177">はい (複数フォレスト サポートは Exchange 2013 CU6 以降のバージョン)</span><span class="sxs-lookup"><span data-stu-id="84991-177">Yes (multi forest support available for Exchange 2013 CU6 and later versions)</span></span>  <br/> |<span data-ttu-id="84991-178">可</span><span class="sxs-lookup"><span data-stu-id="84991-178">Yes</span></span>  <br/> |<span data-ttu-id="84991-179">あり</span><span class="sxs-lookup"><span data-stu-id="84991-179">Yes</span></span>  <br/> |
|<span data-ttu-id="84991-180">Exchange 2016</span><span class="sxs-lookup"><span data-stu-id="84991-180">Exchange 2016</span></span>  <br/> |<span data-ttu-id="84991-181">[はい] (複数フォレストのサポート可能)</span><span class="sxs-lookup"><span data-stu-id="84991-181">Yes (multi forest support available)</span></span>  <br/> |<span data-ttu-id="84991-182">あり</span><span class="sxs-lookup"><span data-stu-id="84991-182">Yes</span></span>  <br/> |<span data-ttu-id="84991-183">はい</span><span class="sxs-lookup"><span data-stu-id="84991-183">Yes</span></span>  <br/> |
   

