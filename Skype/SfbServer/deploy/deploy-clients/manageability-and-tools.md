---
title: Skype Room System の管理性とツール
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
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Skype Room System の管理ツールの詳細については、このトピックを参照してください。
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093551"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="f7ea9-103">Skype Room System の管理性とツール</span><span class="sxs-lookup"><span data-stu-id="f7ea9-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="f7ea9-104">Skype Room System の管理ツールの詳細については、このトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="f7ea9-105">管理ポータル</span><span class="sxs-lookup"><span data-stu-id="f7ea9-105">Administrative Portal</span></span>

<span data-ttu-id="f7ea9-106">Skype for Business Server オンプレミス展開の場合、Skype Room System 管理ポータルを使用して、組織内の Skype Room System の展開を積極的に管理および監視できます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="f7ea9-107">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="f7ea9-108">Skype for Business Server で SRS v1 管理 Web ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="f7ea9-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="f7ea9-109">Exchange チェックリスト</span><span class="sxs-lookup"><span data-stu-id="f7ea9-109">Exchange Checklist</span></span>

- <span data-ttu-id="f7ea9-110">自動検出がセットアップされ、内部 DNS A/CNAME RECORD が使用できるのを確認 autodiscover.domain.com。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="f7ea9-111">Ping の自動検出 (Ping の自動検出など Autodiscover.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="f7ea9-112">Microsoft Connectivity Analyzer ツールを使用して自動検出サービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="f7ea9-113">最初のテストを選択します。"Outlook でログオンOfficeします。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="f7ea9-114">会議室に既にリソース メールボックスがある場合は、このアカウントを Skype Room System 用に拡張します (ページの下部にあるスクリプトの例)。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="f7ea9-115">Skype for Business チェックリスト</span><span class="sxs-lookup"><span data-stu-id="f7ea9-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="f7ea9-116">次のツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="f7ea9-117">Skype for Business のベスト プラクティス アナライザー</span><span class="sxs-lookup"><span data-stu-id="f7ea9-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="f7ea9-118">Skype for Business Health Analysis Tool (Excel)</span><span class="sxs-lookup"><span data-stu-id="f7ea9-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="f7ea9-119">Skype for Business Connectivity アナライザー 32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="f7ea9-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="f7ea9-120">[「365 用の便利な新しいトラブルシューティングと分析ツールOffice確認します](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-120">Review [Useful new troubleshooting and analysis tools for Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365).</span></span> <span data-ttu-id="f7ea9-121">Skype for Business プールと Web Apps サーバー Officeし、Skype for Business クライアントを使用して PowerPoint デッキを共有できます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="f7ea9-122">会議室にリソース メールボックスが既に存在する場合は、Skype for Business で有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="f7ea9-123">必要に応じて、会議室システムの DID (電話番号) を要求し、Active Directory ツールの [一般電話] フィールドを更新します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="f7ea9-124">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="f7ea9-124">Network</span></span>

- <span data-ttu-id="f7ea9-125">Skype Room System のワイヤード (有線) ネットワーク接続が確立されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="f7ea9-126">Skype for Business のネットワーク計画ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="f7ea9-127">Skype for Business パートナーから Skype for Business ネットワーク評価を要求します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="f7ea9-128">Skype for Business Health Analysis Tool (Excel) でキャプチャされたパフォーマンス データを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="f7ea9-129">ネットワーク分析ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="f7ea9-130">プレコール診断ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="f7ea9-131">Skype Room System Security</span><span class="sxs-lookup"><span data-stu-id="f7ea9-131">Skype Room System Security</span></span>

<span data-ttu-id="f7ea9-132">Skype Room System は、Skype for Business セキュリティ モデル、権限管理、SCOM などの管理ツールを使用して、Windows 展開に完全に統合できる組み込みシステムです。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="f7ea9-133">以下の機能があります。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-133">Features include:</span></span>
  
- <span data-ttu-id="f7ea9-134">ユーザー モードでのディスク書き込みを防止する書き込みフィルター</span><span class="sxs-lookup"><span data-stu-id="f7ea9-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="f7ea9-135">承認されていないアプリが実行されるのを防ぐためのアプリ ロッカー。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="f7ea9-136">ユーザー モードでは、すべての USB ポートが無効になります。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="f7ea9-137">標準のアプリや閲覧者は Skype Room System ハードウェアに存在します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="f7ea9-138">すべてのコンテンツは、HTTP または RDP プロトコルを介してレンダリングされます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="f7ea9-139">アプライアンス PC は、Windows Embedded Standard 7 オペレーティング システムを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="f7ea9-140">デバイスを含むすべてのハードウェアは、OEM パートナーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="f7ea9-141">オプションの Active Directory ドメイン サービスへのドメイン参加 (AD DS) で、ローカル セキュリティ アカウントの管理と制御を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="f7ea9-142">また、Skype for Business 管理センターを使用してローカル管理者アカウントを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="f7ea9-143">Skype Room System は、標準の Microsoft Update プロセスを通じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="f7ea9-144">Skype Room System は Skype for Business に接続します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="f7ea9-145">Skype for Business は、すべての通信モードでエンドツーエンドの暗号化と承認を使用します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="f7ea9-146">Skype Room System は、Skype for Business のセキュリティとコンプライアンスの標準をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="f7ea9-147">詳細 [については、「Plan for security in Skype For Business Server」](../../plan-your-deployment/security/security.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="f7ea9-148">ライセンス</span><span class="sxs-lookup"><span data-stu-id="f7ea9-148">License</span></span>

<span data-ttu-id="f7ea9-149">ソフトウェアのアクティブ化に KMS を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="f7ea9-150">その場合は、Skype for Business クライアント KMS キーを確認または追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="f7ea9-151">KMS を使用していない場合は、Skype for Business クライアント MAK のボリューム ライセンス キーを要求します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="f7ea9-152">ライセンス キー</span><span class="sxs-lookup"><span data-stu-id="f7ea9-152">License keys</span></span>

<span data-ttu-id="f7ea9-153">Skype Room System は、バックグラウンドで Skype for Business デスクトップ クライアントを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="f7ea9-154">Skype Room System がドメイン メンバーである場合、KMS が検出されます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="f7ea9-155">(ボリューム ライセンス KMS キーがある場合は、自動的にアクティブ化されます)。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="f7ea9-156">ボリューム ライセンスには MAK も用意され、xxxxx-xxxxx-xxxxx-xxxxx-xxxxx を表示する場合に入力します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="f7ea9-157">(MAK を使用してアクティブ化するにはインターネット アクセスが必要ですが、KMS は必要ではありません)。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="f7ea9-158">詳細については、「ボリューム ライセンス認証」を参照Office 2013。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="f7ea9-159">MAK キーを入力するには、[OEM 設定 \> ] SRS ライセンス ツールに移動します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="f7ea9-160">[状態の確認] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-160">Click Check Status.</span></span> <span data-ttu-id="f7ea9-161">状態が "製品がアクティブ化されていません" と表示された場合は、キーを入力します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="f7ea9-162">ライセンス認証中に「ソフトウェア ライセンス サービスからプロダクト キーが無効だと報告されました」というエラーが表示される場合は、次の確認を行います。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="f7ea9-163">キーが正しく入力されました。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="f7ea9-164">別のキーではなく、Skype for Business MAK キーを入力しました。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="f7ea9-165">システムはインターネットにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="f7ea9-166">電話でライセンス認証できますが、最初に SRS ライセンス ツールを使用してライセンス認証を試みた必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="f7ea9-167">電話でアクティブにするには、テスト会議を開始します (短すぎるテスト通話ではありません)。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="f7ea9-168">[ライセンス認証Office] で、[電話のライセンス認証] を選択し、Microsoft に電話し、長い番号を入力して、応答を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="f7ea9-169">証明機関</span><span class="sxs-lookup"><span data-stu-id="f7ea9-169">Certificate Authority</span></span>

<span data-ttu-id="f7ea9-170">Web Apps Server 2013 証明書の発行に使用Office証明書失効リスト プロパティに HTTP パスが含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="f7ea9-171">Skype for Business Server を使用している場合は、証明書ファイル (.crt) を Skype Room System にインポートします。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="f7ea9-172">CA サーバーの CertEnroll 共有、またはドメインに参加している PC の信頼されたルート フォルダーから簡単に取得できます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="f7ea9-173">証明書</span><span class="sxs-lookup"><span data-stu-id="f7ea9-173">Certificates</span></span>

<span data-ttu-id="f7ea9-174">証明機関に証明書失効リストの http パスが含されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="f7ea9-175">含めない場合は、CA を更新して 1 つを含める。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="f7ea9-176">[システム設定証明書マネージャー] の下の Skype Room System の管理者セットアップに証明書を \> インストールします。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="f7ea9-177">内部証明書にはエンタープライズ ルート CA が必要です。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="f7ea9-178">必要な証明書を取得する方法の 1 つは、証明書を発行した CA を検出する方法です。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="f7ea9-179">Skype for Business Server の場合は、Skype for Business の PC で、[設定 \> ツール] [ダイヤルイン会議の設定] \> をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="f7ea9-180">これにより、内部証明書を発行した CA によってセキュリティで保護された Web ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="f7ea9-181">ブラウザーのアドレス バーの [ロック] アイコンをクリックして、セキュリティ レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="f7ea9-182">[証明書の表示] をクリックし、CRL 配布ポイント プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="f7ea9-183">2 番目の CN パラメーターは、CA のサーバー名である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="f7ea9-184">次に、そのアドレス \\ \< CA Server Name \> \CertEnroll の Windows エクスプローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="f7ea9-185">2 つの .crl ファイルと .crt ファイルをフラッシュ ドライブにコピーし、SMART ボードの左側に置きます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="f7ea9-186">.crt ファイルを信頼できる部屋証明機関フォルダーの下の Skype Room System にインポートします。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="f7ea9-187">中間証明書機関フォルダーの下にある Skype Room System の .crl ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="f7ea9-188">(ファイルを表示するには、証明書マネージャーのファイル拡張子フィルターを .crl に変更する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="f7ea9-189">注: Office Web Apps 2013 サーバーは、Skype for Business と同じ CA を共有できます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="f7ea9-190">会議で PowerPoint を共有できない場合。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="f7ea9-191">IT に確認し、上記のように CA ネットワーク共有 CertEnroll から CRT ファイルと CRL ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="f7ea9-192">ドメイン メンバーシップは、Skype Room System を Windows システムとして扱い、証明書の側面の一部を Active Directory に依存できるので、いくつかのことを簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="f7ea9-193">ただし、手動で管理する方が最適です。</span><span class="sxs-lookup"><span data-stu-id="f7ea9-193">However, it's best to manually manage this.</span></span>
