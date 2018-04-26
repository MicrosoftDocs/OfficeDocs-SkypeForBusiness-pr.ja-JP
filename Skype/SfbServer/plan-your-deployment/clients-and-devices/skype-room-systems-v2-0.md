---
title: Skype Room Systems バージョン 2 の計画
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: この資料では、Skype ルーム システム v2 では、Skype ルーム システムの次世代を展開するため、関連する計画に関する考慮事項について説明します。
ms.openlocfilehash: 372c920eaeaaee050e420cd25195565555426561
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2018
---
# <a name="plan-for-skype-room-systems-v2"></a><span data-ttu-id="e752f-103">Skype Room Systems バージョン 2 の計画</span><span class="sxs-lookup"><span data-stu-id="e752f-103">Plan for Skype Room Systems v2</span></span>
 
<span data-ttu-id="e752f-104">この資料では、Skype ルーム システム v2 では、Skype ルーム システムの次世代を展開するため、関連する計画に関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="e752f-104">This article explains the relevant planning considerations for deploying Skype Room Systems v2, the next generation of Skype Room Systems.</span></span> 
  
 <span data-ttu-id="e752f-105">Skype ルーム システム v2 は、ビジネス経験の豊富な共同の Skype 会議室に変換するように設計された、マイクロソフトの最新の会議ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="e752f-105">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="e752f-106">ユーザーは慣れ親しんだ Skype for Business インターフェイスを活用し、IT 管理者は Windows 10 Skype Meeting アプリを簡単に展開および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="e752f-106">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="e752f-107">Skype ルーム システム v2 は、Skype をビジネスの会議室に移動するのにはインストールの容易さの LCD パネルと同様に既存の機器を活用するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="e752f-107">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
<span data-ttu-id="e752f-108">Skype ルーム システム v2 では、Skype の会議のユーザー インターフェイスとして機能する専用の UWP アプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e752f-108">Skype Room Systems v2 uses a purpose-built UWP app which acts as the Skype Meeting user interface.</span></span> <span data-ttu-id="e752f-109">Surface Pro 4 または Surface Pro のコンソール モードで実行される (UWP のアプリケーションを展開した後は、デバイス上で実行される唯一のアプリケーション)、ビジネスの実装については、Skype の独自デバイスのアカウントを必要とします。</span><span class="sxs-lookup"><span data-stu-id="e752f-109">It runs on a Surface Pro 4 or Surface Pro in a console mode (once deployed the UWP app is the only app that will run on the device) and it requires its own device account on your Skype for Business implementation.</span></span> <span data-ttu-id="e752f-110">LCD パネルや比較的安価な周辺機器のカメラのような既存の機器を活用し、および品質の会議室を提供するのにはマイクが発生します。</span><span class="sxs-lookup"><span data-stu-id="e752f-110">It leverages existing equipment like LCD panels and relatively inexpensive peripheral cameras and microphones to provide a quality meeting room experience.</span></span> <span data-ttu-id="e752f-111">Windows ストアと Windows の更新プログラムの両方を使用してソフトウェアを更新します。</span><span class="sxs-lookup"><span data-stu-id="e752f-111">Software is updated via both Windows store and Windows Update.</span></span>
  
<span data-ttu-id="e752f-112">環境の準備を始める前に、必要なハードウェアとソフトウェアがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e752f-112">Before you being preparing your environment, be sure you have the necessary hardware and software.</span></span> <span data-ttu-id="e752f-113">詳細については、 [Skype ルーム システム v2 の要件](requirements.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e752f-113">For more information, see [Skype Room Systems v2 requirements](requirements.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e752f-114">Skype ルーム システム v2 は、使用で Skype ビジネス サーバー 2015 または Skype のオンライン ビジネスの。</span><span class="sxs-lookup"><span data-stu-id="e752f-114">Skype Room Systems v2 is intended for use with Skype for Business Server 2015 or Skype for Business Online.</span></span> <span data-ttu-id="e752f-115">Lync Server 2013 のような以前のプラットフォームは、Skype ルーム システム v2 を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e752f-115">Earlier platforms like Lync Server 2013 are not expected to work with Skype Room Systems v2.</span></span> 
  
<span data-ttu-id="e752f-116">Skype ルーム システム v2 は、ビジネス経験の豊富な共同の Skype 会議室に変換するように設計された、マイクロソフトの最新の会議ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="e752f-116">Skype Room Systems v2 is Microsoft's latest conferencing solution designed to transform your meeting room into a rich, collaborative Skype for Business experience.</span></span> <span data-ttu-id="e752f-117">ユーザーは慣れ親しんだ Skype for Business インターフェイスを活用し、IT 管理者は Windows 10 Skype Meeting アプリを簡単に展開および管理することができます。</span><span class="sxs-lookup"><span data-stu-id="e752f-117">Users will enjoy its familiar Skype for Business interface and IT administrators will appreciate an easily deployed and managed Windows 10 Skype Meeting app.</span></span> <span data-ttu-id="e752f-118">Skype ルーム システム v2 は、Skype をビジネスの会議室に移動するのにはインストールの容易さの LCD パネルと同様に既存の機器を活用するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="e752f-118">Skype Room Systems v2 is designed to leverage existing equipment like LCD panels for ease of installation to bring Skype for Business into your meeting room.</span></span>
  
 <span data-ttu-id="e752f-119">**Skype for Business 用**</span><span class="sxs-lookup"><span data-stu-id="e752f-119">**Built for Skype for Business**</span></span>
  
- <span data-ttu-id="e752f-120">Skype 会議のワンタッチ参加</span><span class="sxs-lookup"><span data-stu-id="e752f-120">One-touch join of Skype Meetings</span></span>
    
- <span data-ttu-id="e752f-121">画面を埋め尽くす HD ビデオと HD ワイドバンド オーディオを使用するルーム向けに最適化されたSkype 会議のエクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="e752f-121">Skype Meeting experience optimized for rooms with screen-filling HD video and HD wideband audio</span></span>
    
- <span data-ttu-id="e752f-122">すべての参加者は、各自希望のデバイスを使用して、どこからでも Skype Meeting に接続することができる</span><span class="sxs-lookup"><span data-stu-id="e752f-122">All participants can connect to the Skype Meeting using their device of choice from wherever they may be located</span></span>
    
- <span data-ttu-id="e752f-123">状態を簡単に表示できるディレクトリから、または通話経由でユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="e752f-123">Invite people from your directory where you can instantly see their availability or via a phone call</span></span>
    
- <span data-ttu-id="e752f-124">ルーム内のスタンドアロン会議電話を置き換える Skype for Business PSTN 会議と PSTN 通話をサポート</span><span class="sxs-lookup"><span data-stu-id="e752f-124">Supports Skype for Business PSTN Conferencing and PSTN Calling to replace the stand-alone conference phone in your room</span></span>
    
 <span data-ttu-id="e752f-125">**どの会議室でも変換**</span><span class="sxs-lookup"><span data-stu-id="e752f-125">**Transform Any Meeting Room**</span></span>
  
- <span data-ttu-id="e752f-126">中央のテーブル タッチ コントローラーと正面にある大型室内ディスプレイ向けに最適化された専用の Skype 会議アプリ</span><span class="sxs-lookup"><span data-stu-id="e752f-126">Dedicated Skype Meeting app optimized for center of table touch controller and large front of room display</span></span>
    
- <span data-ttu-id="e752f-127">正面の室内ディスプレイやプロジェクターで既存の投資を再利用</span><span class="sxs-lookup"><span data-stu-id="e752f-127">Re-use existing investments in your front of room display or projectors</span></span>
    
- <span data-ttu-id="e752f-128">ちょっとした打ち合わせから、大規模な会議室まで、すべてのタイプのミーティング スペースに対応</span><span class="sxs-lookup"><span data-stu-id="e752f-128">Works in all types of meeting spaces from huddle spaces to large conference rooms</span></span>
    
- <span data-ttu-id="e752f-129">Skype for Business の認定オーディオ デバイスとビデオ デバイスはさまざまなサイズのルームで利用可能</span><span class="sxs-lookup"><span data-stu-id="e752f-129">Certified Skype for Business audio and video devices are available for various room sizes</span></span>
    
- <span data-ttu-id="e752f-130">ルームおよび Skype 会議でデスクトップ共有を投影する組み込みの有線取り込み</span><span class="sxs-lookup"><span data-stu-id="e752f-130">Built-in wired ingest for to project desktop sharing to the room and to the Skype Meeting</span></span>
    
- <span data-ttu-id="e752f-131">ルームの USB デバイス & #x 2776; のオーディオおよびビデオ会議のアプリケーションでのユーザーの選択</span><span class="sxs-lookup"><span data-stu-id="e752f-131">In-app user selection of meeting room audio and video USB devices &#x2776;</span></span>
    
- <span data-ttu-id="e752f-132">デュアル画面対応 (従来のシステムのパリティ) & #x 2777 です。</span><span class="sxs-lookup"><span data-stu-id="e752f-132">Dual-Screen support (for legacy system parity) &#x2777;</span></span>
    
- <span data-ttu-id="e752f-133">(組み込みのテーマとユーザー設定のテーマを設定する機能) の themability & #x 2777 です。</span><span class="sxs-lookup"><span data-stu-id="e752f-133">Themability (built-in themes and the ability to set custom theme) &#x2777;</span></span>
    
 <span data-ttu-id="e752f-134">**展開が容易、管理が簡単**</span><span class="sxs-lookup"><span data-stu-id="e752f-134">**Easy to Deploy, Simple to Manage**</span></span>
  
- <span data-ttu-id="e752f-135">室内でユーザーを検出すると自動的ディスプレイをオンにする Always-on アプライアンス</span><span class="sxs-lookup"><span data-stu-id="e752f-135">Always-on appliance that will automatically wake up the displays when it detects people in the room</span></span>
    
- <span data-ttu-id="e752f-136">UWP (ユニバーサル Windows プラットフォーム) Skype 会議アプリの展開と更新が簡単</span><span class="sxs-lookup"><span data-stu-id="e752f-136">Simple deployment and updating of the UWP (Universal Windows Platform) Skype Meeting App</span></span>
    
- <span data-ttu-id="e752f-137">Windows AppLocker で Skype 会議アプリへのデバイスをロック ダウン</span><span class="sxs-lookup"><span data-stu-id="e752f-137">Windows AppLocker locks down the device to the Skype Meeting app</span></span>
    
- <span data-ttu-id="e752f-138">Intune および SCCM (MDM) 経由で Windows 10 Enterprise デバイスとして監視および管理</span><span class="sxs-lookup"><span data-stu-id="e752f-138">Monitored and managed as a Windows 10 Enterprise device via Intune and SCCM (MDM)</span></span>
    
- <span data-ttu-id="e752f-139">エンタープライズ レベルの信頼性</span><span class="sxs-lookup"><span data-stu-id="e752f-139">Enterprise-grade reliability</span></span>
    
- <span data-ttu-id="e752f-140">慣れ親しんだ Skype ユーザー インターフェイスのためにトレーニングの労力が少ない</span><span class="sxs-lookup"><span data-stu-id="e752f-140">Low training effort of end-users due to familiar Skype user interface</span></span>
    
- <span data-ttu-id="e752f-141">Surface Pro 4 タブレット上で動作</span><span class="sxs-lookup"><span data-stu-id="e752f-141">Runs on Surface Pro 4 tablet</span></span>
    
- <span data-ttu-id="e752f-142">ルーム コンソールのステータスがマイクロソフトの運用管理スイートを使用しているお客様のレポートを統合 ( [OMS を使用して Skype ルーム システムの計画 v2 の管理](oms-management.md)を参照してください) & #x 2776。</span><span class="sxs-lookup"><span data-stu-id="e752f-142">Integrated room console status reporting for customers using Microsoft Operations Management Suite (see [Plan Skype Room Systems v2 management with OMS](oms-management.md)) &#x2776;</span></span>
    
- <span data-ttu-id="e752f-143">パブリック ビルド & #x 2777 にフィードバックする機能</span><span class="sxs-lookup"><span data-stu-id="e752f-143">Ability to Give Feedback for public builds &#x2777;</span></span>
    
- <span data-ttu-id="e752f-144">信頼性 & #x 2777; に参加する会議の周りの改善された遠隔測定</span><span class="sxs-lookup"><span data-stu-id="e752f-144">Improved Telemetry around meeting join reliability &#x2777;</span></span>
    
- <span data-ttu-id="e752f-145">追加 OMS 報告 & #x 2777 です。</span><span class="sxs-lookup"><span data-stu-id="e752f-145">Additional OMS reporting &#x2777;</span></span>
    
- <span data-ttu-id="e752f-146">機能デバイスをリモートで構成する IT 管理 & #x 2777 です。</span><span class="sxs-lookup"><span data-stu-id="e752f-146">Ability for IT Admin to configure devices remotely &#x2777;</span></span>
    <!--  - Front-of-Room UX shows room details pre-meeting U2  -->
- <span data-ttu-id="e752f-147">Surface Pro タブレット & #x 2778; で実行されています。</span><span class="sxs-lookup"><span data-stu-id="e752f-147">Runs on Surface Pro tablet &#x2778;</span></span>
    
- <span data-ttu-id="e752f-148">Windows 10 企業の作成元の更新プログラム (英語の言語をビルド 1703) & #x をサポートしている 2778 です。</span><span class="sxs-lookup"><span data-stu-id="e752f-148">Supports Windows 10 Enterprise Creator's Update (English language, build 1703) &#x2778;</span></span>
    
- <span data-ttu-id="e752f-149">[Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system)のサポートはドッキング ハードウェア & #x 2778 です。</span><span class="sxs-lookup"><span data-stu-id="e752f-149">Support for [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) dock hardware &#x2778;</span></span>
    
- <span data-ttu-id="e752f-150">OEM のサポート環境のコントロール (Crestron) & #x 2778 です。</span><span class="sxs-lookup"><span data-stu-id="e752f-150">OEM Support for Environment Controls (Crestron) &#x2778;</span></span>
    
- <span data-ttu-id="e752f-151">[ポリコム MSR シリーズ](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl)のサポートはドッキング ハードウェア & #x 2779 です。</span><span class="sxs-lookup"><span data-stu-id="e752f-151">Support for [Polycom MSR Series](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) dock hardware &#x2779;</span></span>
    
- <span data-ttu-id="e752f-152">[Logitech (ロジクール) Brio](https://www.logitech.com/en-us/product/brio) & #x 2779; のサポート</span><span class="sxs-lookup"><span data-stu-id="e752f-152">Support for the [Logitech Brio](https://www.logitech.com/en-us/product/brio) &#x2779;</span></span>

- <span data-ttu-id="e752f-153">[ハブ 500 の Lenovo](https://www3.lenovo.com/us/en/hub500)のサポートはドッキング ハードウェア & #x277A;</span><span class="sxs-lookup"><span data-stu-id="e752f-153">Support for [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500) dock hardware &#x277A;</span></span>  
    
<span data-ttu-id="e752f-154">& #x 2776。機能の更新プログラム 1 (ソフトウェアのバージョンで導入されました。</span><span class="sxs-lookup"><span data-stu-id="e752f-154">&#x2776; - Feature introduced in Update 1 (SW Ver.</span></span> <span data-ttu-id="e752f-155">2.0.2.0)。</span><span class="sxs-lookup"><span data-stu-id="e752f-155">2.0.2.0).</span></span>
  
<span data-ttu-id="e752f-156">& #x 2777 です。機能の更新プログラム 2 (ソフトウェアのバージョンで導入されました。</span><span class="sxs-lookup"><span data-stu-id="e752f-156">&#x2777; - Feature introduced in Update 2 (SW Ver.</span></span> <span data-ttu-id="e752f-157">3.0.6.0)。</span><span class="sxs-lookup"><span data-stu-id="e752f-157">3.0.6.0).</span></span> 
  
<span data-ttu-id="e752f-158">& #x 2778 です。機能の更新プログラム 3 (ソフトウェアのバージョンで導入されました。</span><span class="sxs-lookup"><span data-stu-id="e752f-158">&#x2778; - Feature introduced in Update 3 (SW Ver.</span></span> <span data-ttu-id="e752f-159">3.0.12.0)。</span><span class="sxs-lookup"><span data-stu-id="e752f-159">3.0.12.0).</span></span> 
  
<span data-ttu-id="e752f-160">& #x 2779 です。更新 4 (ソフトウェアのバージョンで導入された機能の</span><span class="sxs-lookup"><span data-stu-id="e752f-160">&#x2779; - Feature introduced in Update 4 (SW Ver.</span></span> <span data-ttu-id="e752f-161">3.0.15.0)。</span><span class="sxs-lookup"><span data-stu-id="e752f-161">3.0.15.0).</span></span> 

<span data-ttu-id="e752f-162">& #x277A;機能の更新 5 (ソフトウェアのバージョンで導入されました。</span><span class="sxs-lookup"><span data-stu-id="e752f-162">&#x277A; - Feature introduced in Update 5 (SW Ver.</span></span> <span data-ttu-id="e752f-163">3.1.98.0)。</span><span class="sxs-lookup"><span data-stu-id="e752f-163">3.1.98.0).</span></span> 
  
## <a name="preparing-your-skype-for-business-environment"></a><span data-ttu-id="e752f-164">Skype for Business 環境の準備</span><span class="sxs-lookup"><span data-stu-id="e752f-164">Preparing your Skype for Business Environment</span></span>

<span data-ttu-id="e752f-165">このセクションには、すべての Skype ルーム システム v2 の機能を使用できるように、環境を準備するのに必要な手順の概要が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e752f-165">This section contains an overview of the steps required to prepare your environment so that you can use all of the features of Skype Room Systems v2.</span></span>
  
1. <span data-ttu-id="e752f-166">各 Skype ルーム システム v2 のコンソールのデバイスのアカウントを準備します。</span><span class="sxs-lookup"><span data-stu-id="e752f-166">Prepare a device account for each Skype Room Systems v2 console.</span></span> <span data-ttu-id="e752f-167">詳細については、 [Skype ルーム システムの配置のバージョン 2](../../deploy/deploy-clients/room-systems-v2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e752f-167">See [Deploy Skype Room Systems v2](../../deploy/deploy-clients/room-systems-v2.md) for details.</span></span>
    
2. <span data-ttu-id="e752f-168">デバイスが使用する、正常に動作しているネットワーク/インターネット接続があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e752f-168">Ensure that there is a working network/Internet connection for the device to use.</span></span> 
    
  - <span data-ttu-id="e752f-169">DHCP を使用して IP アドレスを受信できる必要があります (注: 最初のユニットの起動時に静的 IP アドレスを持つ Skype ルーム システム v2 を構成することはできません)</span><span class="sxs-lookup"><span data-stu-id="e752f-169">It must be able to receive an IP address using DHCP (note: Skype Room Systems v2 cannot be configured with a static IP address at the first unit startup)</span></span>
    
  - <span data-ttu-id="e752f-170">次のポートが開かれている必要があります (Skype for Business メディアの通常のポートも開かれている必要があります)。</span><span class="sxs-lookup"><span data-stu-id="e752f-170">It must have these ports open (in addition to opening the normal ports for Skype for Business media):</span></span>
    
  - <span data-ttu-id="e752f-171">HTTPS: 443</span><span class="sxs-lookup"><span data-stu-id="e752f-171">HTTPS: 443</span></span>
    
  - <span data-ttu-id="e752f-172">HTTP: 80</span><span class="sxs-lookup"><span data-stu-id="e752f-172">HTTP: 80</span></span>
    
  - <span data-ttu-id="e752f-173">プロキシを介してネットワークが動作している場合は、プロキシのアドレスまたはスクリプトの情報も必要です。</span><span class="sxs-lookup"><span data-stu-id="e752f-173">If your network runs through a proxy, you'll need the proxy address or script information as well.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e752f-174">V2 は HDMI での問題を引き起こすことが確認されています、HDCP の入力をサポートしていません、Skype ルーム システムは、機能 (ビデオ、オーディオ) を取り込みします。</span><span class="sxs-lookup"><span data-stu-id="e752f-174">Skype Room Systems v2 does not support HDCP input, which has been observed to cause issues with HDMI ingest functionality (video, audio).</span></span> <span data-ttu-id="e752f-175">Skype ルーム システム v2 に接続されたスイッチが HDCP 機能をオフにできるように注意します。</span><span class="sxs-lookup"><span data-stu-id="e752f-175">Take care to ensure that switches connected to Skype Room Systems v2 have HDCP options turned off.</span></span> 
  
3. <span data-ttu-id="e752f-p113">エクスペリエンスを改善するために、マイクロソフトではデータを収集しています。データを収集するために、以下のサイトをホワイトリストに記載しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e752f-p113">In order to improve your experience, Microsoft collects data. To collect data, we need these sites whitelisted:</span></span>
    
  - <span data-ttu-id="e752f-178">「遠隔測定」クライアントのエンドポイント。https://vortex.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="e752f-178">Telemetry client endpoint: https://vortex.data.microsoft.com/</span></span>
    
  - <span data-ttu-id="e752f-179">「遠隔測定」の設定の終了点:https://settings.data.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="e752f-179">Telemetry settings endpoint: https://settings.data.microsoft.com/</span></span>
    
### <a name="create-and-test-a-device-account"></a><span data-ttu-id="e752f-180">デバイス アカウントを作成してテストする</span><span class="sxs-lookup"><span data-stu-id="e752f-180">Create and test a device account</span></span>

<span data-ttu-id="e752f-181">*デバイスのアカウント*は、ビジネス用の Skype を有効にして、予定表のように、Exchange の機能にアクセスする Skype ルーム システムのバージョン 2 のクライアントが使用しているアカウントです。</span><span class="sxs-lookup"><span data-stu-id="e752f-181">A  *device account*  is an account that the Skype Room Systems v2 client uses to access features from Exchange, like calendar, and to enable Skype for Business.</span></span> <span data-ttu-id="e752f-182">詳細については、 [Skype ルーム システムの配置のバージョン 2](../../deploy/deploy-clients/room-systems-v2.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e752f-182">See [Deploy Skype Room Systems v2](../../deploy/deploy-clients/room-systems-v2.md) for details.</span></span>
  
### <a name="check-network-availability"></a><span data-ttu-id="e752f-183">ネットワークの状態をチェックする</span><span class="sxs-lookup"><span data-stu-id="e752f-183">Check network availability</span></span>

<span data-ttu-id="e752f-184">正常に機能するために Skype ルーム システムのバージョン 2 のデバイスにこれらの要件を満たしているワイヤード (有線) ネットワークへのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e752f-184">In order to function properly, the Skype Room Systems v2 device must have access to a wired network that meets these requirements:</span></span>
  
- <span data-ttu-id="e752f-185">Active Directory または Azure Active Directory (Azure AD) インスタンスと、Microsoft Exchange および Skype for Business Server へのアクセス。</span><span class="sxs-lookup"><span data-stu-id="e752f-185">Access to your Active Directory or Azure Active Directory (Azure AD) instance, as well as your Microsoft Exchange and Skype for Business servers.</span></span>
    
- <span data-ttu-id="e752f-186">DHCP を使用して IP アドレスを提供することができるサーバーへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="e752f-186">Access to a server that can provide an IP address using DHCP.</span></span> <span data-ttu-id="e752f-187">Skype ルーム システム v2 は、静的 IP アドレスを構成できません。</span><span class="sxs-lookup"><span data-stu-id="e752f-187">Skype Room Systems v2 cannot be configured with a static IP address.</span></span>
    
- <span data-ttu-id="e752f-188">HTTP ポート 80 と 443 へのアクセス。</span><span class="sxs-lookup"><span data-stu-id="e752f-188">Access to HTTP ports 80 and 443.</span></span>
    
- <span data-ttu-id="e752f-189">TCP および UDP ポートの[Lync Server 2013 のポート要件](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx)をオンプレミス Skype ビジネスの実装、または[Office 365 の Url と IP アドレスの範囲](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)の Skype のオンラインでのビジネスの説明に従って構成します。</span><span class="sxs-lookup"><span data-stu-id="e752f-189">TCP and UDP ports configured as described in [Port requirements for Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx) for on premise Skype for Business implementations, or [Office 365 URLs and IP address ranges](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) for Skype for Business online implementations.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="e752f-190">有線の 1 Gbps ネットワーク接続を使用して、必要な帯域幅を確保してください。</span><span class="sxs-lookup"><span data-stu-id="e752f-190">Be sure to use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span> 
  
### <a name="certificates"></a><span data-ttu-id="e752f-191">証明書</span><span class="sxs-lookup"><span data-stu-id="e752f-191">Certificates</span></span>

<span data-ttu-id="e752f-192">Skype ルーム システム v2 デバイスは、Exchange Web サービス、Skype のビジネス、ネットワーク使用率、および認証に証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="e752f-192">Your Skype Room Systems v2 device uses certificates for Exchange Web Services, Skype for Business, network usage, and authentication.</span></span> <span data-ttu-id="e752f-193">関連のサーバーがオンラインと一部の設置型展開の場合は、パブリック証明書を使用する場合は、証明書をインストールするのには、管理者側で必要なアクションをさらにいけません。</span><span class="sxs-lookup"><span data-stu-id="e752f-193">If the related servers use public certificates, which is the case for Online and some On-Premises deployments, there should be no further action required on the part of the admin to install certificates.</span></span> <span data-ttu-id="e752f-194">場合、その一方で、証明機関が (設置型展開では一般的な) プライベート CA を信頼する必要があるデバイスとは、CA と CA が CA チェーンの証明書がデバイスにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="e752f-194">If, on the other hand, the certificate authority is a private CA (typical for On-Premises deployments) then the device needs to trust that CA which means having the CA + CA chain certificates installed on the device.</span></span> <span data-ttu-id="e752f-195">デバイスをドメインに追加すると、このタスクが自動的に実行可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e752f-195">Adding the device to the domain may perform this task automatically.</span></span>
  
<span data-ttu-id="e752f-196">その他の Windows クライアントの場合と同じ方法で証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e752f-196">You will install certificates the same way you would for any other Windows client.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e752f-197">Skype ルーム システム v2 のビジネスのサーバーに Skype を使用するために証明書を必要があります。</span><span class="sxs-lookup"><span data-stu-id="e752f-197">Certificates may be required in order to have Skype Room Systems v2 use Skype for Business Server.</span></span> 
  
### <a name="proxy"></a><span data-ttu-id="e752f-198">プロキシ</span><span class="sxs-lookup"><span data-stu-id="e752f-198">Proxy</span></span>

<span data-ttu-id="e752f-199">Skype ルーム システム v2 は、Windows OS のプロキシ設定を継承するよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="e752f-199">Skype Room Systems v2 is designed to inherit Proxy settings from the Windows OS.</span></span> <span data-ttu-id="e752f-200">以下の方法で Windows OS にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e752f-200">Access the Windows OS in the following manner:</span></span>
  
1. <span data-ttu-id="e752f-201">Skype ルーム システム v2 UI で、場所が表示されます (デフォルトのパスワードは、「デバイス」) デバイスのローカル管理者のパスワードの設定の歯車アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e752f-201">In the Skype Room Systems v2 UI, click on the Settings gear icon where you'll be prompted for the local Administrator password on the device (the default password is "sfb").</span></span>
    
2. <span data-ttu-id="e752f-202">後に"Windows へ移動] ボタンをタップしての順にタップして、[設定] をタップして、"管理者の記号をで」ボタンと、[管理者] ボタンをクリックして (「その他のユーザー」を選択しを使用してコンピューターがドメインに参加している場合。 \admin ユーザー名と)。</span><span class="sxs-lookup"><span data-stu-id="e752f-202">Tap on "Settings" followed by tapping on the "Go to Windows" button and then tapping on the "got to Admin Sign In" button and then clicking the "Administrator" button (if the computer is domain joined choose "Other User," then use .\admin as the user name).</span></span>
    
3. <span data-ttu-id="e752f-203">検索ウィンドウでは、regedit (長いキーを押して画面か、右クリックし、[管理者として実行] を選択) の下の左型をボックスします。</span><span class="sxs-lookup"><span data-stu-id="e752f-203">In the "Search Windows" box bottom left type in regedit (either long press the screen or right click and choose "Run as administrator").</span></span>
    
4. <span data-ttu-id="e752f-204">HKEY_USERS フォルダーをクリックします (マシン ユーザー SID の一覧が表示されます)。ルート フォルダー HKEY_USERS が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e752f-204">Click on the HKEY_USERS folder (you'll see a list of machine user SIDs) ensure the root folder HKEY_USERS is selected.</span></span>
    
    <span data-ttu-id="e752f-205">新しくロードされたハイブは、キー名の入力を要求しますSkype の (すると、Skype のユーザーのレジストリ設定) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e752f-205">You'll be prompted for a Key Name for your newly loaded Hive; type in Skype (you should now see the registry settings for the Skype User).</span></span>
    
5. <span data-ttu-id="e752f-206">[ファイル] をクリックし、[ハイブの読み込み] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e752f-206">Click on File and then choose "Load Hive."</span></span>
    
6. <span data-ttu-id="e752f-207">フォルダー「C:\Users\Skype」を参照して、[ファイル名] ボックスに NTUSER.dat を入力し、[開く] ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="e752f-207">Browse the to the following folder "C:\Users\Skype" and type in the File name box NTUSER.dat and press the open button</span></span>
    
7. <span data-ttu-id="e752f-208">Skype キーを開き、[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet の設定を参照し、これらの設定が入力されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e752f-208">Open the Skype key and browse to HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings then ensure these settings are entered:</span></span> 
    
    <span data-ttu-id="e752f-209">[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]</span><span class="sxs-lookup"><span data-stu-id="e752f-209">[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]</span></span>
    
    <span data-ttu-id="e752f-210">"MigrateProxy"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="e752f-210">"MigrateProxy"=dword:00000001</span></span>
    
    <span data-ttu-id="e752f-211">"ProxyEnable"= dword:00000001</span><span class="sxs-lookup"><span data-stu-id="e752f-211">"ProxyEnable"=dword:00000001</span></span>
    
    <span data-ttu-id="e752f-212">"ProxyServer"="xx.xx.xx.xx:8080"</span><span class="sxs-lookup"><span data-stu-id="e752f-212">"ProxyServer"="xx.xx.xx.xx:8080"</span></span>
    
    <span data-ttu-id="e752f-213">ProxyServer が存在しない場合は、このキーを文字列として追加し、xx.xx.xx.xx:8080 をプロキシ サーバーの IP/ホストとポートに変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e752f-213">If ProxyServer doesn't exist you may have to add this key as a string, change the xx.xx.xx.xx:8080 to the ip/host and port of your Proxy server.</span></span>
    
8. <span data-ttu-id="e752f-214">Skype ユーザー (Skype のルート フォルダー) のキーし、選択の強調表示 (説明の入力を求め確認 - [**はい]** )、レジストリ ファイル] メニューからハイブをアンロードすると、変更が完了した後です。</span><span class="sxs-lookup"><span data-stu-id="e752f-214">Once you are finished making your changes highlight the Skype User key (root folder for Skype) and choose unload Hive from the Registry file menu (you'll be prompted for confirmation - select **Yes** ).</span></span>
    
9. <span data-ttu-id="e752f-215">これで、レジストリ エディターを閉じて、Windows の検索ボックスに logoff と入力できます。</span><span class="sxs-lookup"><span data-stu-id="e752f-215">You can now close the registry editor and type logoff into the Windows search box.</span></span>
    
10. <span data-ttu-id="e752f-216">サインイン画面に戻り、**Skype** ユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e752f-216">Back at the sign-in screen, choose the **Skype** user.</span></span> <span data-ttu-id="e752f-217">以前のすべてのステップが成功した場合 Skype ルーム システムのバージョン 2 のデバイスはサインインが正常にします。</span><span class="sxs-lookup"><span data-stu-id="e752f-217">If all the previous steps were successful, the Skype Room Systems v2 device will sign-in successfully.</span></span>
    
<span data-ttu-id="e752f-p119">このアプリケーションを使用するには、以下に説明されているエンドポイントに接続できる必要があります。IP アドレスを表示するには、トラフィックのフローを説明する表の下にある [IP アドレス] セクションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e752f-p119">To use this application, you must be able to connect to the endpoints described below. To see the IP addresses, expand the IP address section below the table describing the traffic flow.</span></span>
  
<span data-ttu-id="e752f-220">**ファイアウォール プロキシのホスト名とポートの例**</span><span class="sxs-lookup"><span data-stu-id="e752f-220">**Firewall Proxy Host Name/Port Examples**</span></span>

|<span data-ttu-id="e752f-221">**目的**</span><span class="sxs-lookup"><span data-stu-id="e752f-221">**Purpose**</span></span>|<span data-ttu-id="e752f-222">**ソースまたは資格情報**</span><span class="sxs-lookup"><span data-stu-id="e752f-222">**Source or Credentials**</span></span>|<span data-ttu-id="e752f-223">**発信元ポート**</span><span class="sxs-lookup"><span data-stu-id="e752f-223">**Source Port**</span></span>|<span data-ttu-id="e752f-224">**宛先**</span><span class="sxs-lookup"><span data-stu-id="e752f-224">**Destination**</span></span>|<span data-ttu-id="e752f-225">**CDN**</span><span class="sxs-lookup"><span data-stu-id="e752f-225">**CDN**</span></span>|<span data-ttu-id="e752f-226">**Office 365 の ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="e752f-226">**ExpressRoute for Office 365**</span></span>|<span data-ttu-id="e752f-227">**宛先 IP**</span><span class="sxs-lookup"><span data-stu-id="e752f-227">**Destination IP**</span></span>|<span data-ttu-id="e752f-228">**宛先ポート**</span><span class="sxs-lookup"><span data-stu-id="e752f-228">**Destination Port**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e752f-229">認証と ID</span><span class="sxs-lookup"><span data-stu-id="e752f-229">Authentication and identity</span></span>  <br/> |<span data-ttu-id="e752f-230">[Office 365 の認証と id](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e752f-230">See [Office 365 authentication and identity](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity)</span></span> <br/> |||
|<span data-ttu-id="e752f-231">ポータルと共有</span><span class="sxs-lookup"><span data-stu-id="e752f-231">Portal and shared</span></span>  <br/> |<span data-ttu-id="e752f-232">[Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e752f-232">See [Office 365 portal and shared](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity)</span></span> <br/> |||
|<span data-ttu-id="e752f-233">SIP 信号</span><span class="sxs-lookup"><span data-stu-id="e752f-233">SIP Signaling</span></span>  <br/> |<span data-ttu-id="e752f-234">クライアント コンピューターまたはログオン ユーザー</span><span class="sxs-lookup"><span data-stu-id="e752f-234">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="e752f-235">短いポート</span><span class="sxs-lookup"><span data-stu-id="e752f-235">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="e752f-236">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="e752f-236">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="e752f-237">なし</span><span class="sxs-lookup"><span data-stu-id="e752f-237">No</span></span>  <br/> |<span data-ttu-id="e752f-238">あり</span><span class="sxs-lookup"><span data-stu-id="e752f-238">Yes</span></span>  <br/> |[<span data-ttu-id="e752f-239">Skype ビジネス IP の範囲の</span><span class="sxs-lookup"><span data-stu-id="e752f-239">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="e752f-240">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e752f-240">TCP 443</span></span>  <br/> |
|<span data-ttu-id="e752f-241">永続共有オブジェクト モデル (PSOM) 接続 Web 会議</span><span class="sxs-lookup"><span data-stu-id="e752f-241">Persistent Shared Object Model (PSOM) connections web conferencing</span></span>  <br/> |<span data-ttu-id="e752f-242">クライアント コンピューターまたはログオン ユーザー</span><span class="sxs-lookup"><span data-stu-id="e752f-242">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="e752f-243">短いポート</span><span class="sxs-lookup"><span data-stu-id="e752f-243">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="e752f-244">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="e752f-244">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="e752f-245">なし</span><span class="sxs-lookup"><span data-stu-id="e752f-245">No</span></span>  <br/> |<span data-ttu-id="e752f-246">あり</span><span class="sxs-lookup"><span data-stu-id="e752f-246">Yes</span></span>  <br/> |[<span data-ttu-id="e752f-247">Skype ビジネス IP の範囲の</span><span class="sxs-lookup"><span data-stu-id="e752f-247">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="e752f-248">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e752f-248">TCP 443</span></span>  <br/> |
|<span data-ttu-id="e752f-249">HTTPS ダウンロード</span><span class="sxs-lookup"><span data-stu-id="e752f-249">HTTPS downloads</span></span>  <br/> |<span data-ttu-id="e752f-250">クライアント コンピューターまたはログオン ユーザー</span><span class="sxs-lookup"><span data-stu-id="e752f-250">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="e752f-251">短いポート</span><span class="sxs-lookup"><span data-stu-id="e752f-251">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="e752f-252">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="e752f-252">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="e752f-253">なし</span><span class="sxs-lookup"><span data-stu-id="e752f-253">No</span></span>  <br/> |<span data-ttu-id="e752f-254">あり</span><span class="sxs-lookup"><span data-stu-id="e752f-254">Yes</span></span>  <br/> |[<span data-ttu-id="e752f-255">Skype ビジネス IP の範囲の</span><span class="sxs-lookup"><span data-stu-id="e752f-255">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="e752f-256">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e752f-256">TCP 443</span></span>  <br/> |
|<span data-ttu-id="e752f-257">オーディオ</span><span class="sxs-lookup"><span data-stu-id="e752f-257">Audio</span></span>  <br/> |<span data-ttu-id="e752f-258">クライアント コンピューターまたはログオン ユーザー</span><span class="sxs-lookup"><span data-stu-id="e752f-258">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="e752f-259">TCP/UDP 50,000-50019</span><span class="sxs-lookup"><span data-stu-id="e752f-259">TCP/UDP 50,000-50019</span></span>  <br/> |<span data-ttu-id="e752f-260">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="e752f-260">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="e752f-261">なし</span><span class="sxs-lookup"><span data-stu-id="e752f-261">No</span></span>  <br/> |<span data-ttu-id="e752f-262">あり</span><span class="sxs-lookup"><span data-stu-id="e752f-262">Yes</span></span>  <br/> |[<span data-ttu-id="e752f-263">Skype ビジネス IP の範囲の</span><span class="sxs-lookup"><span data-stu-id="e752f-263">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="e752f-264">TCP 443、UDP 3478、TCP/UDP 50,000-59,999</span><span class="sxs-lookup"><span data-stu-id="e752f-264">TCP 443, UDP 3478, TCP/UDP 50,000-59,999</span></span>  <br/> |
|<span data-ttu-id="e752f-265">ビデオ</span><span class="sxs-lookup"><span data-stu-id="e752f-265">Video</span></span>  <br/> |<span data-ttu-id="e752f-266">クライアント コンピューターまたはログオン ユーザー</span><span class="sxs-lookup"><span data-stu-id="e752f-266">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="e752f-267">TCP/UDP 50,020-50039</span><span class="sxs-lookup"><span data-stu-id="e752f-267">TCP/UDP 50,020-50039</span></span>  <br/> |<span data-ttu-id="e752f-268">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="e752f-268">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="e752f-269">なし</span><span class="sxs-lookup"><span data-stu-id="e752f-269">No</span></span>  <br/> |<span data-ttu-id="e752f-270">あり</span><span class="sxs-lookup"><span data-stu-id="e752f-270">Yes</span></span>  <br/> |[<span data-ttu-id="e752f-271">Skype ビジネス IP の範囲の</span><span class="sxs-lookup"><span data-stu-id="e752f-271">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="e752f-272">TCP 443、UDP 3478、TCP/UDP 50,000-59,999</span><span class="sxs-lookup"><span data-stu-id="e752f-272">TCP 443, UDP 3478, TCP/UDP 50,000-59,999</span></span>  <br/> |
|<span data-ttu-id="e752f-273">デスクトップ共有</span><span class="sxs-lookup"><span data-stu-id="e752f-273">Desktop Sharing</span></span>  <br/> |<span data-ttu-id="e752f-274">クライアント コンピューターまたはログオン ユーザー</span><span class="sxs-lookup"><span data-stu-id="e752f-274">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="e752f-275">TCP/UDP 50,040-50059</span><span class="sxs-lookup"><span data-stu-id="e752f-275">TCP/UDP 50,040-50059</span></span>  <br/> |<span data-ttu-id="e752f-276">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="e752f-276">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="e752f-277">なし</span><span class="sxs-lookup"><span data-stu-id="e752f-277">No</span></span>  <br/> |<span data-ttu-id="e752f-278">あり</span><span class="sxs-lookup"><span data-stu-id="e752f-278">Yes</span></span>  <br/> |[<span data-ttu-id="e752f-279">Skype ビジネス IP の範囲の</span><span class="sxs-lookup"><span data-stu-id="e752f-279">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="e752f-280">TCP 443、50,000-59,999</span><span class="sxs-lookup"><span data-stu-id="e752f-280">TCP 443, 50,000-59,999</span></span>  <br/> |
|<span data-ttu-id="e752f-p120">iOS デバイス上の Lync Mobile 2010 向け Lync Mobile プッシュ通知。Android、Nokia Symbian、Windows Phone モバイル デバイスの場合、これは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e752f-p120">Lync Mobile push notifications for Lync Mobile 2010 on iOS devices. You don't need this for Android, Nokia Symbian or Windows Phone mobile devices.</span></span>  <br/> |<span data-ttu-id="e752f-283">クライアント コンピューターまたはログオン ユーザー</span><span class="sxs-lookup"><span data-stu-id="e752f-283">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="e752f-284">短いポート</span><span class="sxs-lookup"><span data-stu-id="e752f-284">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="e752f-285">\*。 contoso.com</span><span class="sxs-lookup"><span data-stu-id="e752f-285">\*.contoso.com</span></span>  <br/> |<span data-ttu-id="e752f-286">なし</span><span class="sxs-lookup"><span data-stu-id="e752f-286">No</span></span>  <br/> |<span data-ttu-id="e752f-287">あり</span><span class="sxs-lookup"><span data-stu-id="e752f-287">Yes</span></span>  <br/> |[<span data-ttu-id="e752f-288">Skype ビジネス IP の範囲の</span><span class="sxs-lookup"><span data-stu-id="e752f-288">Skype for Business IP ranges</span></span>](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |<span data-ttu-id="e752f-289">TCP 5223</span><span class="sxs-lookup"><span data-stu-id="e752f-289">TCP 5223</span></span>  <br/> |
|<span data-ttu-id="e752f-290">Skype テレメトリ</span><span class="sxs-lookup"><span data-stu-id="e752f-290">Skype Telemetry</span></span>  <br/> |<span data-ttu-id="e752f-291">クライアント コンピューターまたはログオン ユーザー</span><span class="sxs-lookup"><span data-stu-id="e752f-291">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="e752f-292">短いポート</span><span class="sxs-lookup"><span data-stu-id="e752f-292">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="e752f-293">skypemaprdsitus.trafficmanager.net</span><span class="sxs-lookup"><span data-stu-id="e752f-293">skypemaprdsitus.trafficmanager.net</span></span>  <br/> <span data-ttu-id="e752f-294">pipe.skype.com</span><span class="sxs-lookup"><span data-stu-id="e752f-294">pipe.skype.com</span></span>  <br/> |<span data-ttu-id="e752f-295">いいえ</span><span class="sxs-lookup"><span data-stu-id="e752f-295">No</span></span>  <br/> |<span data-ttu-id="e752f-296">いいえ</span><span class="sxs-lookup"><span data-stu-id="e752f-296">No</span></span>  <br/> |<span data-ttu-id="e752f-297">該当なし</span><span class="sxs-lookup"><span data-stu-id="e752f-297">N/A</span></span>  <br/> |<span data-ttu-id="e752f-298">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e752f-298">TCP 443</span></span>  <br/> |
|<span data-ttu-id="e752f-299">Skype クライアントのヒント</span><span class="sxs-lookup"><span data-stu-id="e752f-299">Skype client quicktips</span></span>  <br/> |<span data-ttu-id="e752f-300">クライアント コンピューターまたはログオン ユーザー</span><span class="sxs-lookup"><span data-stu-id="e752f-300">Client Computer or Logged on user</span></span>  <br/> |<span data-ttu-id="e752f-301">短いポート</span><span class="sxs-lookup"><span data-stu-id="e752f-301">Ephemeral ports</span></span>  <br/> |<span data-ttu-id="e752f-302">quicktips.skypeforbusiness.com</span><span class="sxs-lookup"><span data-stu-id="e752f-302">quicktips.skypeforbusiness.com</span></span>  <br/> |<span data-ttu-id="e752f-303">いいえ</span><span class="sxs-lookup"><span data-stu-id="e752f-303">No</span></span>  <br/> |<span data-ttu-id="e752f-304">いいえ</span><span class="sxs-lookup"><span data-stu-id="e752f-304">No</span></span>  <br/> |<span data-ttu-id="e752f-305">該当なし</span><span class="sxs-lookup"><span data-stu-id="e752f-305">N/A</span></span>  <br/> |<span data-ttu-id="e752f-306">TCP 443</span><span class="sxs-lookup"><span data-stu-id="e752f-306">TCP 443</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="e752f-307">contoso.com および broadcast.skype.com のワイルドカードは、Office 365 専用で使用されるノードの長いリストを表しています。</span><span class="sxs-lookup"><span data-stu-id="e752f-307">The wildcard for contoso.com and broadcast.skype.com represents a long list of nodes that are exclusively used for Office 365.</span></span> 
  
### <a name="create-provisioning-packages"></a><span data-ttu-id="e752f-308">プロビジョニング パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="e752f-308">Create provisioning packages</span></span>

<span data-ttu-id="e752f-309">プロビジョニング パッケージは、Exchange Server や Skype for Business Server の認証に使用します。</span><span class="sxs-lookup"><span data-stu-id="e752f-309">You will use provisioning packages to authenticate to Exchange Server or Skype for Business Server.</span></span>
  
### <a name="admin-group-management"></a><span data-ttu-id="e752f-310">管理グループの管理</span><span class="sxs-lookup"><span data-stu-id="e752f-310">Admin group management</span></span>

<span data-ttu-id="e752f-311">ドメインの参加後、ドメイン内の Widonws PC の場合と同じ方法で、グループ ポリシーまたはローカルのコンピュータの管理を使用して、ローカル管理者としてセキュリティ グループを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e752f-311">After domain joining, you can use Group Policy or the Local Computer Management to set a Security Group as local administrator just like you would for a Windows PC in your domain.</span></span> <span data-ttu-id="e752f-312">そのセキュリティ グループのどのメンバーでも、各自の資格情報を入力して設定をロック解除することができます。</span><span class="sxs-lookup"><span data-stu-id="e752f-312">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e752f-313">Skype ルーム システム v2 デバイスで (たとえば、ドメインからドメインに参加しては、その後 Skype ルーム システム v2 を削除する場合) ドメインとの信頼関係が失われた場合にデバイスを認証し、設定を開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="e752f-313">If your Skype Room Systems v2 device loses trust with the domain (for example, if you remove the Skype Room Systems v2 from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="e752f-314">回避策として、ローカル管理アカウントでログインできます。</span><span class="sxs-lookup"><span data-stu-id="e752f-314">The workaround is to log in with the local Admin account.</span></span> 
  
## <a name="local-accounts"></a><span data-ttu-id="e752f-315">ローカル アカウント</span><span class="sxs-lookup"><span data-stu-id="e752f-315">Local accounts</span></span>

### <a name="skype-room-systems-local-user-account"></a><span data-ttu-id="e752f-316">Skype Room Systems ローカル ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="e752f-316">Skype Room Systems Local User Account</span></span>

<span data-ttu-id="e752f-317">通常、デバイス アカウントではパスワードを使用しません。</span><span class="sxs-lookup"><span data-stu-id="e752f-317">The Device Account does not typically use a password.</span></span> <span data-ttu-id="e752f-318">パスワードを指定することは可能ですが、パスワードが期限切れとなった場合にユーザーがコンソール アプリケーションケーションからロックアウトされる可能性などの因果関係があります。</span><span class="sxs-lookup"><span data-stu-id="e752f-318">It is possible to give it a password, but there are consequences, including a possibility that users might get locked out of the console application when that password expires.</span></span> <span data-ttu-id="e752f-319">その結果として、管理者は、パスワードが期限切れにならないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e752f-319">Consequently, the administrator should take are to ensure that the password is not allowed to expire.</span></span>
  
### <a name="admin---local-administrator-account"></a><span data-ttu-id="e752f-320">"Admin" - ローカル管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="e752f-320">"Admin" - Local Administrator Account</span></span>

<span data-ttu-id="e752f-321">Skype ルーム システム v2 のデフォルトのパスワードは、「デバイス」に設定されていますいます。</span><span class="sxs-lookup"><span data-stu-id="e752f-321">Skype Room Systems v2 default password is set to "sfb".</span></span> <span data-ttu-id="e752f-322">Windows の設定に移動してローカルでは、パスワードを変更することができます\>Windows または AutoUnattend.xml ファイル (xml ファイルに変更を加えるに ADK から Windows システム イメージ マネージャーを使用します) での移動。</span><span class="sxs-lookup"><span data-stu-id="e752f-322">The Password can be changed locally by going to Windows Settings \> Go to Windows or in the AutoUnattend.xml file (use the Windows System Image manager from ADK to make the change to the xml file).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e752f-323">必ず Skype ルーム システム v2 パスワードをできるだけ早く変更してください。</span><span class="sxs-lookup"><span data-stu-id="e752f-323">Be sure to change the Skype Room Systems v2 password as soon as possible.</span></span> 
  
<span data-ttu-id="e752f-324">ドメイン管理者をローカル管理者として設定したグループ ポリシーを設定することで、ローカル管理者のパスワードを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="e752f-324">You can also manage the Local Administrator password by setting up a group policy where domain admins are made local admins.</span></span>
  
<span data-ttu-id="e752f-325">ローカルの管理者パスワードは、セットアップ中には選択肢に含まれているではありません。</span><span class="sxs-lookup"><span data-stu-id="e752f-325">The Local admin password is not included as a choice during Setup.</span></span>
  
### <a name="machine-account"></a><span data-ttu-id="e752f-326">コンピューター アカウント</span><span class="sxs-lookup"><span data-stu-id="e752f-326">Machine Account</span></span>

<span data-ttu-id="e752f-327">任意の Windows デバイスと同じようにコンピューター名名前を変更できる設定で右クリックして\>の\>PC の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="e752f-327">Much like any Windows device, the Machine Name can be renamed by right clicking in Settings \> About \> Rename PC.</span></span>
  
 <span data-ttu-id="e752f-328">ドメインへの参加後、コンピューターの名前を変更したい場合は、コンピューターの新しい名前の後に名前の変更-コンピューターの PowerShell コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e752f-328">If you would like to rename the computer after joining it to a domain, use the Rename-Computer PowerShell command followed by the computer's new name.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e752f-329">関連項目</span><span class="sxs-lookup"><span data-stu-id="e752f-329">See also</span></span>

#### 

[<span data-ttu-id="e752f-330">Skype ルーム システム v2 の要件</span><span class="sxs-lookup"><span data-stu-id="e752f-330">Skype Room Systems v2 requirements</span></span>](requirements.md)
  
[<span data-ttu-id="e752f-331">Skype の部屋を配置するシステム v2</span><span class="sxs-lookup"><span data-stu-id="e752f-331">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)
  
[<span data-ttu-id="e752f-332">Skype ルーム システム v2 のコンソールを構成します。</span><span class="sxs-lookup"><span data-stu-id="e752f-332">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)
  
[<span data-ttu-id="e752f-333">Skype ルームの管理システム v2</span><span class="sxs-lookup"><span data-stu-id="e752f-333">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

