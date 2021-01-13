---
title: Skype for Business Server でのビデオ相互運用サーバーの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: '概要: Skype for Business Server をサードパーティの電話会議デバイスと統合する計画を立てながら、このトピックを確認してください。'
ms.openlocfilehash: c14d92042922f30ca5dd43acce12d11ef50a8683
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831947"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="81942-103">Skype for Business Server でのビデオ相互運用サーバーの計画</span><span class="sxs-lookup"><span data-stu-id="81942-103">Plan for Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="81942-104">**概要:** Skype for Business Server をサードパーティの電話会議デバイスと統合する計画を立てながら、このトピックを確認してください。</span><span class="sxs-lookup"><span data-stu-id="81942-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with third-party teleconferencing devices.</span></span>
  
<span data-ttu-id="81942-105">Skype for Business Server では、特定のサード パーティ VTC (ビデオ会議システム) ソリューションと統合できます。</span><span class="sxs-lookup"><span data-stu-id="81942-105">Skype for Business Server now allows you to integrate with certain third-party VTC (Video Teleconferencing System) solutions.</span></span> <span data-ttu-id="81942-106">このビデオ会議の相互運用性を有効にする新しいサーバーの役割は、ビデオ相互運用サーバー (VIS) です。現在、オンプレミスインストールでのみ使用できるスタンドアロン サーバーの役割として実装されています。</span><span class="sxs-lookup"><span data-stu-id="81942-106">The new server role that enables this video conferencing interoperability is the Video Interop Server (VIS), which is currently implemented as a standalone server role available only for on-premises installations.</span></span> <span data-ttu-id="81942-107">VIS は、サードパーティの電話会議システムと Skype for Business Server 展開の仲介者として機能します。</span><span class="sxs-lookup"><span data-stu-id="81942-107">A VIS acts as an intermediary between a third party teleconference system and a Skype for Business Server deployment.</span></span> <span data-ttu-id="81942-108">このリリースでは、VIS は Cisco/Tandberg ビデオ システムとの相互運用性に重点を置いされています。</span><span class="sxs-lookup"><span data-stu-id="81942-108">For this release, VIS is focused on interoperability with Cisco/Tandberg video systems.</span></span> <span data-ttu-id="81942-109">この記事を確認して、Skype for Business Server インストールでこの機能を使用するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="81942-109">Review this article to determine whether to use this feature in your Skype for Business Server installation.</span></span>
  
## <a name="device-interoperability"></a><span data-ttu-id="81942-110">デバイスの相互運用性</span><span class="sxs-lookup"><span data-stu-id="81942-110">Device interoperability</span></span>

<span data-ttu-id="81942-111">相互運用は、Cisco Unified Communications Manager (CallManager または CUCM) バージョン 10.5 および CUCM と VIS の間にセットアップされた TCP SIP トランクに登録された Cisco VTC でテストおよびサポートされます。</span><span class="sxs-lookup"><span data-stu-id="81942-111">Interoperation is tested and supported with Cisco VTCs registering with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 and TCP SIP trunks set up between CUCM and the VIS.</span></span>
  
<span data-ttu-id="81942-112">現在サポートされている VTC は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="81942-112">The currently supported VTCs are:</span></span>
  
- <span data-ttu-id="81942-113">Cisco C40</span><span class="sxs-lookup"><span data-stu-id="81942-113">Cisco C40</span></span>
    
- <span data-ttu-id="81942-114">Cisco C60</span><span class="sxs-lookup"><span data-stu-id="81942-114">Cisco C60</span></span>
    
- <span data-ttu-id="81942-115">Cisco C90</span><span class="sxs-lookup"><span data-stu-id="81942-115">Cisco C90</span></span>
    
- <span data-ttu-id="81942-116">Cisco MX200</span><span class="sxs-lookup"><span data-stu-id="81942-116">Cisco MX200</span></span>
    
- <span data-ttu-id="81942-117">Cisco MX300</span><span class="sxs-lookup"><span data-stu-id="81942-117">Cisco MX300</span></span>
    
- <span data-ttu-id="81942-118">Cisco DX80</span><span class="sxs-lookup"><span data-stu-id="81942-118">Cisco DX80</span></span>
    
- <span data-ttu-id="81942-119">Cisco EX60</span><span class="sxs-lookup"><span data-stu-id="81942-119">Cisco EX60</span></span>
    
- <span data-ttu-id="81942-120">Cisco EX90</span><span class="sxs-lookup"><span data-stu-id="81942-120">Cisco EX90</span></span>
    
- <span data-ttu-id="81942-121">Cisco SX20</span><span class="sxs-lookup"><span data-stu-id="81942-121">Cisco SX20</span></span>
    
> [!NOTE]
>  <span data-ttu-id="81942-122">Skype for Business Server との統合が期待通り動作するには、これらのシステムで Cisco ソフトウェア リリース TC7.0.0 以上が必要です。</span><span class="sxs-lookup"><span data-stu-id="81942-122">Cisco software release TC7.0.0 or above is required on these systems for integration with Skype for Business Server to work as expected.</span></span>
  
## <a name="sip-trunks"></a><span data-ttu-id="81942-123">SIP トランク</span><span class="sxs-lookup"><span data-stu-id="81942-123">SIP trunks</span></span>

<span data-ttu-id="81942-124">ビデオ相互運用サーバーは SIP トランク モードで機能します。このモードでは、VTC は既存の Cisco インフラストラクチャ (Cisco Call Manager (CUCM) など) に引き続き登録されます。</span><span class="sxs-lookup"><span data-stu-id="81942-124">The Video Interop Server functions in SIP trunk mode, where the VTCs continue to register with the existing Cisco infrastructure - for example, Cisco Call Manager (CUCM).</span></span> <span data-ttu-id="81942-125">ビデオ SIP トランクは CUCM と VIS の間で定義され、2 つのシステム間で通話をルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="81942-125">A video SIP trunk is defined between CUCM and the VIS so that calls can be routed between the two systems.</span></span> <span data-ttu-id="81942-126">VTC から VIS への SIP トランクの呼び出しだけがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="81942-126">Only calls over the SIP trunk from the VTC to the VIS are supported.</span></span> <span data-ttu-id="81942-127">したがって、(Call Automated Attendant に関連付けられた電話番号をダイヤルして) SKYPE for Business 会議にダイヤルインできますが、電話会議にドラッグ アンド ドロップすることはできません。</span><span class="sxs-lookup"><span data-stu-id="81942-127">Thus, VTCs can dial into a Skype for Business conference (by dialing the phone number associated with the Call Automated Attendant), but cannot be dragged and dropped into the conference.</span></span>
  
![SfB の VIS の図](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a><span data-ttu-id="81942-129">機能</span><span class="sxs-lookup"><span data-stu-id="81942-129">Features</span></span>

<span data-ttu-id="81942-130">このサーバーの役割は、次の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="81942-130">This server role provides:</span></span>
  
- <span data-ttu-id="81942-131">サードパーティ製のビデオ システムで使用される H.264 形式と Skype for Business Server 展開間の変換。</span><span class="sxs-lookup"><span data-stu-id="81942-131">Conversion between the H.264 formats used by 3rd party video systems and the Skype for Business Server deployment.</span></span>
    
- <span data-ttu-id="81942-132">VTC からの特定の解像度での単一のビデオ ストリームを、Skype for Business Server 展開で使用するために異なる解像度の複数のシマルチキャスト ストリームに変換します。</span><span class="sxs-lookup"><span data-stu-id="81942-132">Conversion of a single video stream at a given resolution from a VTC into multiple simulcast streams of different resolutions for use in the Skype for Business Server deployment.</span></span> <span data-ttu-id="81942-133">これらのストリームは、AVMCU に送信してから、異なる解像度を要求した Skype for Business Server エンドポイントや他のビデオ システムに送信できます。</span><span class="sxs-lookup"><span data-stu-id="81942-133">These streams can be sent to the AVMCU and then to Skype for Business Server endpoints and other video systems that have requested different resolutions.</span></span> <span data-ttu-id="81942-134">この変換は、サード パーティ製のビデオ システムが Skype for Business の A/V 電話会議に参加する場合にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="81942-134">This conversion is also used when the third party video system is involved in a Skype for Business A/V conference call.</span></span> <span data-ttu-id="81942-135">特定の VIS サーバーでコード変換の制限に達すると、次に示すさまざまな解像度の要求は、最も低い解像度のストリームのみを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="81942-135">Once the transcoding limit is reached in a particular VIS server, any following requests for different resolutions will only receive a stream with the lowest resolution.</span></span> 
    
- <span data-ttu-id="81942-136">CUCM ゲートウェイと Skype for Business Server ビデオ相互運用サーバー間のビデオ SIP トランクのサポートVTC は引き続き Cisco ゲートウェイに登録し、ゲートウェイを介して Skype for Business 展開への通話を開始します。</span><span class="sxs-lookup"><span data-stu-id="81942-136">Support for a video SIP trunk between the CUCM gateway and a Skype for Business Server Video Interop Server; VTCs continue to register with the Cisco gateway, and initiate calls to the Skype for Business deployment through the gateway.</span></span> <span data-ttu-id="81942-137">通話は、ゲートウェイからビデオ SIP トランクを経由して Skype for Business ビデオ相互運用サーバーにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="81942-137">Calls are routed from the gateway to the Skype for Business Video Interop Server over the video SIP trunk.</span></span>
    
- <span data-ttu-id="81942-138">サポートされているビデオ システムを備えた会議室のユーザーが、そのシステムからダイヤルして、開いている会議または閉じている会議に参加できます。</span><span class="sxs-lookup"><span data-stu-id="81942-138">Support for a user in a conference room with a supported video system to dial from that system to join an open or closed conference.</span></span> <span data-ttu-id="81942-139">この呼び出しは、ビデオ SIP トランクをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="81942-139">This call will traverse the video SIP trunk.</span></span>
    
- <span data-ttu-id="81942-140">Skype for Business クライアントを呼び出すビデオ システムがサポートされている会議室内のユーザーのサポート。</span><span class="sxs-lookup"><span data-stu-id="81942-140">Support for a user in a conference room with a supported video system to call a Skype for Business client.</span></span> <span data-ttu-id="81942-141">呼び出しは SIP トランクを通過します。</span><span class="sxs-lookup"><span data-stu-id="81942-141">The call will traverse the SIP trunk.</span></span>
    
- <span data-ttu-id="81942-142">音声のミュート/ミュート解除、ビデオの一時停止/再開、ビデオのロック、通話の保留/保留解除などのポイント間通話とマルチポイント通話の両方について、Skype for Business Server 側またはサポートされている VTC システムからの通話中の制御のサポート。</span><span class="sxs-lookup"><span data-stu-id="81942-142">Support for mid-call control from the Skype for Business Server side or from the supported VTC system for both point to point and multipoint calls including mute/un-mute audio, pause/resume video, lock video, and hold/un-hold call.</span></span>
    
## <a name="known-limitations"></a><span data-ttu-id="81942-143">既知の制限</span><span class="sxs-lookup"><span data-stu-id="81942-143">Known limitations</span></span>

<span data-ttu-id="81942-144">このサーバーの役割には、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="81942-144">This server role has the following limitations:</span></span>
  
- <span data-ttu-id="81942-145">Skype for Business 展開からビデオ SIP トランク経由の VTC への新しい通話はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="81942-145">New calls from the Skype for Business deployment to the VTCs over the video SIP trunk are not supported.</span></span> <span data-ttu-id="81942-146">.</span><span class="sxs-lookup"><span data-stu-id="81942-146">.</span></span> <span data-ttu-id="81942-147">つまり、ビデオ SIP トランク経由でサポートされているのは、VTC から Skype for Business 展開への新しい呼び出しのみです。</span><span class="sxs-lookup"><span data-stu-id="81942-147">This means that only new calls from the VTCs into the Skype for Business deployment are supported over the video SIP trunk.</span></span> <span data-ttu-id="81942-148">サポートされているビデオ システムのプレゼンスは、ビデオ SIP トランクを使用して VIS に対して使用できません。</span><span class="sxs-lookup"><span data-stu-id="81942-148">Presence for the supported video system will not be available over the video SIP trunk to the VIS.</span></span> 
    
- <span data-ttu-id="81942-149">ビデオ SIP トランク モードでは、スタンドアロンの VIS プールだけがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="81942-149">Only a standalone VIS pool will be supported for video SIP trunk mode.</span></span>
    
-  <span data-ttu-id="81942-150">ビデオ SIP トランクを使用した VTC と VIS の間の通信では、TLS + SRTP または TCP + RTP がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="81942-150">TLS + SRTP or TCP + RTP will be supported for communications between the VTC and VIS over the video SIP trunk.</span></span>
    
- <span data-ttu-id="81942-151">アプリケーション共有はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="81942-151">Application sharing is not supported.</span></span> <span data-ttu-id="81942-152">会議室の Skype for Business ユーザーは、Skype for Business 会議に参加し (ノート PC など)、VTC に関連付けされていない会議室のいずれかの無料モニターにアプリ共有画面を表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81942-152">A Skype for Business user in the conference room needs to join the Skype for Business conference (via a laptop for example) and display the app sharing screens on one of the free monitors in the conference room not associated with the VTC.</span></span>
    
- <span data-ttu-id="81942-153">VTC が VIS を介してフェデレーション会議に参加する機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="81942-153">The ability for a VTC to join a federated meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="81942-154">VTC が VIS を介してオンライン会議に参加する機能はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="81942-154">The ability for a VTC to join an online meeting via VIS is not supported.</span></span>
    
- <span data-ttu-id="81942-155">VTC から VIS 経由の PSTN への通話はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="81942-155">Calls from a VTC to the PSTN via VIS are not supported.</span></span>
    
- <span data-ttu-id="81942-156">PSTN から VIS 経由の VTC への通話はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="81942-156">Calls from the PSTN to a VTC via VIS are not supported.</span></span>
    
## <a name="resiliency-mechanisms"></a><span data-ttu-id="81942-157">復元メカニズム</span><span class="sxs-lookup"><span data-stu-id="81942-157">Resiliency mechanisms</span></span>
<span data-ttu-id="81942-158"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="81942-158"><a name="resiliency"> </a></span></span>

<span data-ttu-id="81942-159">VIS は、ビデオ SIP トランクを引き継ぐ CUCM からの着信呼び出しをサポートします。</span><span class="sxs-lookup"><span data-stu-id="81942-159">The VIS supports incoming calls from a CUCM that are carried over a video SIP trunk.</span></span> <span data-ttu-id="81942-160">アップストリームまたはダウンストリームのどちらかの接続を失う可能性があります。したがって、堅牢な回復性を得る上で、次の両方の可能性を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="81942-160">It's possible to lose connectivity either upstream or downstream, so for robust resiliency consider both possibilities:</span></span>
  
1. <span data-ttu-id="81942-161">**VIS プールフェールオーバー** ビデオ ゲートウェイがポイントするメイン VIS プールがダウンしている場合、ビデオ ゲートウェイが 2 つ以上の VIS プールにトランクを定義している場合、回復が可能です。</span><span class="sxs-lookup"><span data-stu-id="81942-161">**VIS Pool Failover** If the main VIS pool that the video gateway points to is down, recovery is possible if the video gateway has defined trunks to two (or more) VIS pools.</span></span> <span data-ttu-id="81942-162">ビデオ ゲートウェイがプライマリ VIS プールに通話できないと判断した場合は、単に通話をセカンダリ VIS プールにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="81942-162">If the video gateway determines it cannot make calls to the primary VIS pool, it simply routes the calls to a secondary VIS pool.</span></span>
    
     ![VIS プールのフェールオーバーの図](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    <span data-ttu-id="81942-164">特定の VIS プールは複数のゲートウェイへのトランクを持つ場合がありますが、通常、特定のゲートウェイは複数の VIS プールへのトランクを持てないので、このフェールオーバーをサポートするには、2 つの FDQN を DNS で定義する必要があります。これは、ビデオ ゲートウェイの同じ IP アドレスに解決されます。</span><span class="sxs-lookup"><span data-stu-id="81942-164">A particular VIS pool can have trunks to multiple gateways, but normally a particular gateway can't have trunks to multiple VIS pools, so a trick needs to be done to support this failover: Define 2 FDQNs in DNS which resolve to the same IP address of a video gateway.</span></span> <span data-ttu-id="81942-165">各ビデオ ゲートウェイが異なる VIS プールへのトランクを持ち、回復が可能なトポロジ ドキュメントで、各 FQDN を個別のビデオ ゲートウェイとして表します。</span><span class="sxs-lookup"><span data-stu-id="81942-165">Represent each FQDN as a separate video gateway in the Topology Document where each video gateway has a trunk to a different VIS pool, and recovery is now possible.</span></span> <span data-ttu-id="81942-166">(TLS を使用する場合は、複数の名前がビデオ ゲートウェイ証明書の SAN にある必要があります)。</span><span class="sxs-lookup"><span data-stu-id="81942-166">(If TLS is used, the multiple names will need to be in the SAN of the video gateway certificate.)</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="81942-167">VIS では、トポロジ ドキュメントで構成されたゲートウェイからの着信のみを許可します。</span><span class="sxs-lookup"><span data-stu-id="81942-167">VIS only allows incoming calls from gateways configured in the Topology Document.</span></span> 
  
2. <span data-ttu-id="81942-168">**フロントエンドフェールオーバー** VIS プールが CUCM から通話を受信したが、プライマリの次ホップ レジストラーまたはフロントエンド プールに到達できない場合、通話はバックアップ フロントエンド プールにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="81942-168">**Front End failover** If a VIS pool receives a call from CUCM but cannot reach its primary next-hop Registrar or Front End pool, calls are routed to a backup Front End pool.</span></span>
    
     ![フロントエンド フェールオーバーの図](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    <span data-ttu-id="81942-170">VIS は、プライマリ フロントエンド プールとそのバックアップ フロントエンド プールの状態を追跡します (この設定は、トポロジ ドキュメントのレジストラー サービスのバックアップ設定にあります)。</span><span class="sxs-lookup"><span data-stu-id="81942-170">The VIS will keep track of the status of its primary Front End pool and its backup Front End pool (the setting is found in the backup setting for the Registrar service in the Topology Document).</span></span> <span data-ttu-id="81942-171">オプション ポーリングは、1 分に 1 回、両方のプールに送信され、連続して 5 回エラーが発生した場合、VIS は特定のフロントエンド プールがダウンしたと見なします。</span><span class="sxs-lookup"><span data-stu-id="81942-171">It sends Options polls once a minute to both pools, and if there are five consecutive failures the VIS assumes that a particular Front End pool is down.</span></span> <span data-ttu-id="81942-172">プライマリ フロントエンド プールがダウンとしてマークされ、利用可能な構成済みのバックアップがある場合、VIS はゲートウェイからバックアップ フロントエンド プールに新しい呼び出しを送信します。</span><span class="sxs-lookup"><span data-stu-id="81942-172">If the primary Front End pool is marked as down and there is an available configured backup the VIS sends new calls from the gateway to the backup Front End pool.</span></span> <span data-ttu-id="81942-173">プライマリ フロントエンド プールが戻ると、VIS はプライマリ フロントエンド プールを使用して新しい通話を再開します。</span><span class="sxs-lookup"><span data-stu-id="81942-173">Once the primary Front End pool comes back, the VIS will resume using the primary Front End pool for new calls.</span></span>
    
    <span data-ttu-id="81942-174">VIS は、ビデオ SIP トランクからの呼び出しに 10 秒のタイマーも実装します。</span><span class="sxs-lookup"><span data-stu-id="81942-174">The VIS will also implement a 10 second timer for calls from the video SIP trunk.</span></span> <span data-ttu-id="81942-175">プライマリ次ホップ フロント エンド プールがビデオ SIP トランクからの通話に使用され、プライマリ次ホップ フロント エンド プールが、このタイマー値内で送信された招待に対する一部の SIP メッセージ (100 を含む) で応答しなかった場合は、通話のバックアップの次ホップ プロキシが構成されている場合に試みる必要があります。</span><span class="sxs-lookup"><span data-stu-id="81942-175">If the primary next-hop Front End pool was used for a call from the video SIP trunk, and the primary next-hop Front End pool did not answer with some SIP message (including 100 Trying) to the Invite sent to it within this timer value, the backup next-hop proxy for the call should be tried if configured.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="81942-176">バックアップの次ホップが最初に試みらた場合、プライマリは次に試みらなされます。</span><span class="sxs-lookup"><span data-stu-id="81942-176">If the backup next hop was tried first, the primary will not be tried next.</span></span> 
  
    <span data-ttu-id="81942-177">管理者は、プライマリ フロントエンド プールでメンテナンスを実行する必要がある場合など、Windows PowerShell フェールオーバー コマンドを使用して VIS にバックアップ フロントエンド プールを強制的に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="81942-177">The admin could also use the Windows PowerShell failover command to force VIS to use the backup Front End pool, for example, when maintenance has to be performed on the primary Front End pool.</span></span>
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a><span data-ttu-id="81942-178">同じゲートウェイ ピアへの音声トランクとビデオ トランクの同時使用</span><span class="sxs-lookup"><span data-stu-id="81942-178">Co-existence of Voice and Video Trunks to the Same Gateway Peer</span></span>
<span data-ttu-id="81942-179"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="81942-179"><a name="resiliency"> </a></span></span>

<span data-ttu-id="81942-180">Skype for Business Server では、音声とビデオの SIP トランクで同じゲートウェイ ピアを使用できます。</span><span class="sxs-lookup"><span data-stu-id="81942-180">Skype for Business Server supports having voice and video SIP trunks use the same gateway peer.</span></span> <span data-ttu-id="81942-181">したがって、同じ CUCM 展開で、仲介サーバーへの音声 SIP トランクと VIS へのビデオ SIP トランクを使用できます。</span><span class="sxs-lookup"><span data-stu-id="81942-181">So the same CUCM deployment could have voice SIP trunks to the Mediation Server and video SIP trunks to VIS.</span></span>
  
- <span data-ttu-id="81942-182">PSTN ゲートウェイは、音声 SIP トランクのトポロジ ドキュメントで特定の FQDN で定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81942-182">A PSTN Gateway will need to be defined with a particular FQDN in the Topology Document for the voice SIP trunks.</span></span>
    
- <span data-ttu-id="81942-183">PSTN ゲートウェイへのピアが仲介サーバーになります。</span><span class="sxs-lookup"><span data-stu-id="81942-183">The peer to the PSTN Gateway will be the Mediation Server.</span></span>
    
- <span data-ttu-id="81942-184">必要に応じて、PSTN ゲートウェイから複数の仲介サーバー プールに及ぶ複数の音声トランクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="81942-184">Multiple voice trunks can be defines spanning from a PSTN Gateway to multiple Mediation Server pools if necessary.</span></span>
    
- <span data-ttu-id="81942-185">ビデオ ゲートウェイは、PSTN ゲートウェイと同じ FQDN を持つビデオ SIP トランクのトポロジ ドキュメントで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81942-185">A Video Gateway will need to be defined in the Topology Document for the video SIP trunk with the same FQDN as for the PSTN Gateway.</span></span>
    
- <span data-ttu-id="81942-186">ビデオ ゲートウェイへのピアは VIS です。</span><span class="sxs-lookup"><span data-stu-id="81942-186">The peer to the Video Gateway will be VIS.</span></span>
    
- <span data-ttu-id="81942-187">1 つのビデオ トランクをビデオ ゲートウェイから特定の VIS プールに定義できます。</span><span class="sxs-lookup"><span data-stu-id="81942-187">A single video trunk can be defined from a Video Gateway to a particular VIS pool.</span></span>
    
- <span data-ttu-id="81942-188">CUCM は、音声トランクとビデオ トランクを正しくルーティングするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81942-188">CUCM will need to be configured to correctly route calls over the voice trunk vs. the video trunk.</span></span> <span data-ttu-id="81942-189">たとえば、VTC からダイヤルするときに特殊なダイヤル プレフィックスを使用できます。CUCM は、このダイヤル プレフィックスを VIS への呼び出しに関連付け、適切な変換ルールによってこのプレフィックスが VIS への SIP 招待から削除されます。</span><span class="sxs-lookup"><span data-stu-id="81942-189">For example, a special dial prefix could be used when dialing from the VTC; CUCM could associate this dial prefix with calls to VIS, and appropriate translation rules would strip this prefix from the SIP Invite to VIS.</span></span>
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a><span data-ttu-id="81942-190">Skype for Business リリースでの VIS と Lync の以前のリリースとの関連付け</span><span class="sxs-lookup"><span data-stu-id="81942-190">Co-existence of VIS in the Skype for Business Release with Previous Releases of Lync</span></span>
<span data-ttu-id="81942-191"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="81942-191"><a name="resiliency"> </a></span></span>

<span data-ttu-id="81942-192">VIS は、Skype for Business 展開の一部としてのみ展開できます。</span><span class="sxs-lookup"><span data-stu-id="81942-192">VIS can only be deployed as part of Skype for Business deployment.</span></span> <span data-ttu-id="81942-193">既存の展開の一部である Lync 2013 会議およびクライアントと相互運用できます。このような場合、VIS プールは、VIS プールの次ホップであるレジストラー/FE プールを含む Skype for Business 展開の一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="81942-193">It can interoperate with Lync 2013 conferences and clients that are a part of an existing deployment; in those cases, the VIS pool will need to be part of a Skype for Business deployment that includes a Registrar/FE pool that is the next-hop for the VIS pool.</span></span>
  
<span data-ttu-id="81942-194">VIS では、RTV と H.264 の間のコード変換はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="81942-194">VIS does not support transcoding between RTV and H.264.</span></span> <span data-ttu-id="81942-195">会議に参加する Lync 2013 より前のクライアントと VTC 参加者の間には、ビデオの相互運用性はありません。</span><span class="sxs-lookup"><span data-stu-id="81942-195">There is no video interoperability between pre-Lync 2013 clients and VTC participants in a conference.</span></span>
  
<span data-ttu-id="81942-196">会議に Lync 2013 より前のクライアントがある場合、モバイル クライアントは RTV を使用して送信し、その結果、モバイル クライアントが優先スピーカーになると、ビデオを受信しません。</span><span class="sxs-lookup"><span data-stu-id="81942-196">Having pre-Lync 2013 clients in a conference will cause mobile clients to send using RTV resulting in VTCs receiving no video when the mobile client becomes the dominant speaker.</span></span>
  
<span data-ttu-id="81942-197">Lync 2013 が Skype for Business 展開の一部である VIS と正しく動作するには、Lync 2013 が VIS と動作するように Lync 2013 クライアント、CAA、および AVMCU をアップグレードする適切な CU を適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81942-197">In order for Lync 2013 to work correctly with VIS that is part of a Skype for Business deployment, Lync 2013 needs the appropriate CU to be applied that upgrades the Lync 2013 client, CAA, and AVMCU to work with VIS.</span></span>
  
<span data-ttu-id="81942-198">VIS と Lync 2013 および Skype for Business デスクトップ クライアントとの相互運用性はテスト済みで、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="81942-198">Interoperability of VIS with Lync 2013 and Skype for Business desktop clients has been tested and is supported.</span></span>
  
<span data-ttu-id="81942-199">VIS とデスクトップ以外との相互運用性 (Android、Ipad、Iphone、Windows Phone、LMX など)VIS リリース時に該当するアプリ ストアから利用できる Skype for Business クライアントはテスト済みで、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="81942-199">Interoperability of VIS with non-desktop (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Skype for Business clients available from the applicable Apps Store at the time of VIS release has been tested and is supported.</span></span>
  
## <a name="recovery-from-packet-loss-via-fec"></a><span data-ttu-id="81942-200">FEC によるパケット損失からの回復</span><span class="sxs-lookup"><span data-stu-id="81942-200">Recovery from Packet Loss via FEC</span></span>
<span data-ttu-id="81942-201"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="81942-201"><a name="resiliency"> </a></span></span>

<span data-ttu-id="81942-202">FEC をオンにすると、パケット損失からの回復を支援できます。</span><span class="sxs-lookup"><span data-stu-id="81942-202">FEC can be turned on to aid in recovery from packet loss.</span></span> <span data-ttu-id="81942-203">オンにすると、VIS から VTC 方向に 50% 多くのビデオ帯域幅が使用されます。</span><span class="sxs-lookup"><span data-stu-id="81942-203">If turned on, 50% more video bandwidth will be used in the VIS to VTC direction.</span></span>
  
## <a name="vis-sizing-and-transcoding-costs"></a><span data-ttu-id="81942-204">VIS のサイズ変更とコード変換のコスト</span><span class="sxs-lookup"><span data-stu-id="81942-204">VIS Sizing and Transcoding Costs</span></span>
<span data-ttu-id="81942-205"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="81942-205"><a name="resiliency"> </a></span></span>

<span data-ttu-id="81942-206">Cisco VTC から複数のサイマルチ キャスト ストリームへの単一のビデオ ストリームのコード変換では、CPU 容量が使用されます。</span><span class="sxs-lookup"><span data-stu-id="81942-206">Transcoding the single video streams from the Cisco VTC to multiple simulcast streams uses CPU capacity.</span></span> <span data-ttu-id="81942-207">Lync 2013 の推奨 FE プラットフォームと同等の動作をしている単一の VIS で、約 16 台の VTC でビデオをコード変換できます (各 VTC からの 720p ビデオ ストリームが 720p、360p、180p の 3 つの別々のサイプルキャスト ストリームにコード変換されている場合)。</span><span class="sxs-lookup"><span data-stu-id="81942-207">Approximately 16 VTCs can have their video transcoded (assuming a 720p video stream from each VTC is transcoded into 3 separate simulcast streams at 720p, 360p, and 180p) in a single VIS running on the equivalent of the Lync 2013 recommended FE platform.</span></span> <span data-ttu-id="81942-208">コード変換をオフにすると、VIS CPU が節約されます。</span><span class="sxs-lookup"><span data-stu-id="81942-208">If Transcoding is turned off, this will save on VIS CPU.</span></span> <span data-ttu-id="81942-209">ただし、VTC から VIS によって要求されたビデオ 画像は、Skype for Business 側のすべての受信者を満たすために最も低い共通解像度になります。</span><span class="sxs-lookup"><span data-stu-id="81942-209">However, the video image requested by VIS from the VTC will be the lowest common resolution to satisfy all receivers on the Skype for Business side.</span></span> <span data-ttu-id="81942-210">コード変換をオフにした場合でも、Skype for Business クライアントが、VTC が送信できない低解像度を要求すると、コード変換がアクティブ化される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="81942-210">Note that even with transcoding off, transcoding may be activated when Skype for Business clients request certain low resolutions that VTCs cannot send.</span></span>
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a><span data-ttu-id="81942-211">ビデオ ゲートウェイから VIS への通話の配布</span><span class="sxs-lookup"><span data-stu-id="81942-211">Call Distribution from the Video Gateway to VIS</span></span>
<span data-ttu-id="81942-212"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="81942-212"><a name="resiliency"> </a></span></span>

<span data-ttu-id="81942-213">配信は、CUCM 配布メカニズムのいずれかを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="81942-213">Distribution is accomplished via one of the CUCM distribution mechanisms:</span></span>
  
- <span data-ttu-id="81942-214">DNS を動的に使用します。</span><span class="sxs-lookup"><span data-stu-id="81942-214">Dynamically using DNS.</span></span>
    
- <span data-ttu-id="81942-215">CUCM 側では、VIS プール内の異なるサーバーで各トランクが終了する個々のトランクを定義できます。</span><span class="sxs-lookup"><span data-stu-id="81942-215">On the CUCM side, you can define individual trunks, where each trunk terminates on a different server in the VIS pool.</span></span> <span data-ttu-id="81942-216">CUCM は、異なるトランク間で通話をルーティングします。</span><span class="sxs-lookup"><span data-stu-id="81942-216">CUCM will route calls across the different trunks.</span></span>
    
## <a name="no-hybrid-interoperability"></a><span data-ttu-id="81942-217">ハイブリッド相互運用性なし</span><span class="sxs-lookup"><span data-stu-id="81942-217">No Hybrid Interoperability</span></span>
<span data-ttu-id="81942-218"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="81942-218"><a name="resiliency"> </a></span></span>

<span data-ttu-id="81942-219">オンプレミス VIS を介してオンライン会議に参加する VTC のサポートは、Skype for Business の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="81942-219">Support for VTCs joining online meetings via on-premises VIS is not part of Skype for Business.</span></span>
  
## <a name="no-federation-support"></a><span data-ttu-id="81942-220">フェデレーションのサポートなし</span><span class="sxs-lookup"><span data-stu-id="81942-220">No Federation Support</span></span>
<span data-ttu-id="81942-221"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="81942-221"><a name="resiliency"> </a></span></span>

<span data-ttu-id="81942-222">VIS を介してフェデレーション会議に参加する VTC のサポートは、Skype for Business の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="81942-222">Support for VTCs joining federated meetings via VIS is not part of Skype for Business.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="81942-223">関連項目</span><span class="sxs-lookup"><span data-stu-id="81942-223">See also</span></span>
<span data-ttu-id="81942-224"><a name="resiliency"> </a></span><span class="sxs-lookup"><span data-stu-id="81942-224"><a name="resiliency"> </a></span></span>

[<span data-ttu-id="81942-225">Skype for Business Server でのビデオ相互運用サーバーの展開</span><span class="sxs-lookup"><span data-stu-id="81942-225">Deploy Video Interop Server in Skype for Business Server</span></span>](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
