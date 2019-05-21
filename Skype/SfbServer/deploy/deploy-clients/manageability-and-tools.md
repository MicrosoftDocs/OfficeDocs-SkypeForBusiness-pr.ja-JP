---
title: Skype Room System の管理容易性とツール
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: このトピックでは、Skype Room System の管理ツールについて説明します。
ms.openlocfilehash: 4ae57457eb244e7cf72183bfadba0bd0b89d44a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293544"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="61c63-103">Skype Room System の管理容易性とツール</span><span class="sxs-lookup"><span data-stu-id="61c63-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="61c63-104">このトピックでは、Skype Room System の管理ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="61c63-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="61c63-105">管理ポータル</span><span class="sxs-lookup"><span data-stu-id="61c63-105">Administrative Portal</span></span>

<span data-ttu-id="61c63-106">Skype for Business Server のオンプレミス展開の場合、Skype Room System 管理ポータルを使用して、組織内の Skype Room システムの展開を積極的に管理および監視できます。</span><span class="sxs-lookup"><span data-stu-id="61c63-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="61c63-107">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61c63-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="61c63-108">Skype for Business Server で SRS v1 管理 Web ポータルを展開する</span><span class="sxs-lookup"><span data-stu-id="61c63-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a><span data-ttu-id="61c63-109">System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="61c63-109">System Center Operations Manager</span></span>

<span data-ttu-id="61c63-110">Skype Room System [Management Pack](https://www.microsoft.com/download/details.aspx?id=42320)をダウンロードして、scom サーバーにインストールすると、System Center Operations MANAGER (SCOM) を通じて Skype ルームシステムを監視できます。</span><span class="sxs-lookup"><span data-stu-id="61c63-110">Skype Room System can be monitored through the System Center Operations Manager (SCOM) by downloading the [Skype Room System Management Pack](https://www.microsoft.com/download/details.aspx?id=42320) and installing it on your SCOM server.</span></span> <span data-ttu-id="61c63-111">SCOM を使用して、通知の設定、Skype Room System の正常性の監視、稼働時間レポートの生成などを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="61c63-111">You can use SCOM to set alerts, monitor the health of Skype Room System, generate uptime reports, and much more.</span></span> <span data-ttu-id="61c63-112">Skype Room System には、SCOM サーバを参照するように構成できる事前にインストールされた監視エージェントが付属しています。</span><span class="sxs-lookup"><span data-stu-id="61c63-112">Skype Room System comes with a pre-installed monitoring agent that can be configured to point to SCOM server.</span></span> <span data-ttu-id="61c63-113">Skype room system メーカーから提供されているインストールガイドを参照して、Skype Room システムで監視エージェントを設定する方法を確認してください。</span><span class="sxs-lookup"><span data-stu-id="61c63-113">Refer to the installation guide provided by your Skype Room System manufacturer to know how to configure the monitoring agent on Skype Room System.</span></span>
  
## <a name="exchange-checklist"></a><span data-ttu-id="61c63-114">Exchange チェックリスト</span><span class="sxs-lookup"><span data-stu-id="61c63-114">Exchange Checklist</span></span>

- <span data-ttu-id="61c63-115">自動検出がセットアップされており、autodiscover.domain.com に対して内部 DNS A/CNAME RECORD が利用可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61c63-115">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="61c63-116">自動検出の ping を実行します (例: Ping Autodiscover.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="61c63-116">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="61c63-117">Microsoft 接続アナライザー ツールで自動検出サービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="61c63-117">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="61c63-118">最初のテストの [Office Outlook でログオンできない] を選択します。</span><span class="sxs-lookup"><span data-stu-id="61c63-118">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="61c63-119">会議室に既にリソースメールボックスがある場合は、このアカウントを Skype Room System (ページ下部のサンプルスクリプト) に拡張します。</span><span class="sxs-lookup"><span data-stu-id="61c63-119">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="61c63-120">Skype for Business のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="61c63-120">Skype for Business Checklist</span></span>

- <span data-ttu-id="61c63-121">次のツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="61c63-121">Run the following tools:</span></span>
    
  - <span data-ttu-id="61c63-122">Skype for Business ベストプラクティスアナライザー</span><span class="sxs-lookup"><span data-stu-id="61c63-122">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="61c63-123">Skype for Business の正常性分析ツール (Excel)</span><span class="sxs-lookup"><span data-stu-id="61c63-123">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="61c63-124">Skype for Business Connectivity Analyzer 32 ビットまたは64ビット</span><span class="sxs-lookup"><span data-stu-id="61c63-124">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="61c63-125">[Office 365 用の新しいトラブルシューティングツールと分析ツールを](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)確認します。</span><span class="sxs-lookup"><span data-stu-id="61c63-125">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="61c63-126">Skype for Business のプールと Office Web Apps サーバーを使用していて、Skype for Business クライアントを使って PowerPoint デッキを共有できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61c63-126">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="61c63-127">会議室に既にリソースメールボックスがある場合は、Skype for Business で有効にします。</span><span class="sxs-lookup"><span data-stu-id="61c63-127">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="61c63-128">必要に応じて、会議室システムの DID (電話番号) を要求し、Active Directory ツールで [一般電話] フィールドを更新します。</span><span class="sxs-lookup"><span data-stu-id="61c63-128">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="61c63-129">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="61c63-129">Network</span></span>

- <span data-ttu-id="61c63-130">Skype Room システムの有線ネットワーク接続があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="61c63-130">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="61c63-131">Skype for Business のネットワーク計画ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61c63-131">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="61c63-132">Skype for Business パートナーから Skype for Business ネットワークの評価を要求する。</span><span class="sxs-lookup"><span data-stu-id="61c63-132">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="61c63-133">詳細については、「Skype for Business 正常性分析ツール (Excel) で収集したパフォーマンスデータ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61c63-133">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="61c63-134">ネットワーク分析ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="61c63-134">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="61c63-135">通話前診断ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="61c63-135">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="61c63-136">Skype Room System のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="61c63-136">Skype Room System Security</span></span>

<span data-ttu-id="61c63-137">Skype Room System は、Skype for Business のセキュリティモデル、rights management、および SCOM などの管理ツールを使用して、Windows 展開に完全に統合できる埋め込みシステムです。</span><span class="sxs-lookup"><span data-stu-id="61c63-137">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="61c63-138">次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="61c63-138">Features include:</span></span>
  
- <span data-ttu-id="61c63-139">ユーザー モードでのディスクの書き込みを防止する書き込みフィルター</span><span class="sxs-lookup"><span data-stu-id="61c63-139">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="61c63-p105">許可されていないアプリの実行を防止するアプリ ロッカー。すべての USB ポートがユーザー モードで無効になります。</span><span class="sxs-lookup"><span data-stu-id="61c63-p105">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="61c63-142">Skype Room システムのハードウェアには、標準のアプリやビューアーは存在しません。</span><span class="sxs-lookup"><span data-stu-id="61c63-142">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="61c63-143">すべてのコンテンツは、HTTP プロトコルまたは RDP プロトコル経由で表示されます。</span><span class="sxs-lookup"><span data-stu-id="61c63-143">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="61c63-p107">アプライアンス PC では、Windows Embedded Standard 7 オペレーティング システムを実行します。デバイスを含むすべてのハードウェアは、OEM パートナーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="61c63-p107">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="61c63-146">Active Directory ドメイン サービス (AD DS) へのオプションのドメイン参加で、ローカル セキュリティ アカウントの管理および制御が可能になります。</span><span class="sxs-lookup"><span data-stu-id="61c63-146">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="61c63-147">また、Skype for Business 管理センターを使って、ローカル管理者アカウントを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="61c63-147">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="61c63-148">Skype Room System は、Microsoft の標準的な更新プロセスによって更新されます。</span><span class="sxs-lookup"><span data-stu-id="61c63-148">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="61c63-149">Skype Room System は Skype for Business と接続します。</span><span class="sxs-lookup"><span data-stu-id="61c63-149">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="61c63-150">Skype for Business では、すべての通信モードでエンドツーエンドの暗号化と承認が使用されます。</span><span class="sxs-lookup"><span data-stu-id="61c63-150">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="61c63-151">Skype Room System は、Skype for Business のセキュリティとコンプライアンス標準をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="61c63-151">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="61c63-152">詳細については、「 [Skype For Business Server のセキュリティの計画](../../plan-your-deployment/security/security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61c63-152">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="61c63-153">ライセンス</span><span class="sxs-lookup"><span data-stu-id="61c63-153">License</span></span>

<span data-ttu-id="61c63-154">ソフトウェアのライセンス認証に KMS を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61c63-154">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="61c63-155">その場合は、Skype for Business クライアントの KMS キーを確認または追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61c63-155">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="61c63-156">KMS を使用していない場合は、Skype for Business クライアント MAK のボリュームライセンスキーを要求します。</span><span class="sxs-lookup"><span data-stu-id="61c63-156">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="61c63-157">ライセンス キー</span><span class="sxs-lookup"><span data-stu-id="61c63-157">License keys</span></span>

<span data-ttu-id="61c63-158">Skype Room System は、バックグラウンドで Skype for Business デスクトップクライアントを実行します。</span><span class="sxs-lookup"><span data-stu-id="61c63-158">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="61c63-159">Skype Room System がドメインメンバーである場合は、KMS が検出されます。</span><span class="sxs-lookup"><span data-stu-id="61c63-159">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="61c63-160">(また、ボリュームライセンスの KMS キーが含まれている場合は、ライセンス認証が自動的に有効になります)。</span><span class="sxs-lookup"><span data-stu-id="61c63-160">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="61c63-161">ボリュームライセンスにも MAK が用意されています。この場合、「xxxxx」と入力します。</span><span class="sxs-lookup"><span data-stu-id="61c63-161">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="61c63-162">(ライセンス認証を行うには、インターネットに接続している必要があります)。</span><span class="sxs-lookup"><span data-stu-id="61c63-162">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="61c63-163">詳細については、「Office 2013 のボリュームライセンス認証」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61c63-163">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="61c63-164">MAK キーを入力するには、OEM 設定\>の SRS ライセンスツールに移動します。</span><span class="sxs-lookup"><span data-stu-id="61c63-164">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="61c63-165">[状態の確認] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61c63-165">Click Check Status.</span></span> <span data-ttu-id="61c63-166">状態に "製品はライセンス認証されていません" と表示される場合は、キーを入力します。</span><span class="sxs-lookup"><span data-stu-id="61c63-166">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="61c63-167">ライセンス認証中に "" というエラーメッセージが表示される場合は、「ソフトウェアライセンスサービスでプロダクトキーが無効であることが報告されました」というエラーが表示されます。次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="61c63-167">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="61c63-168">キーが正しく入力された。</span><span class="sxs-lookup"><span data-stu-id="61c63-168">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="61c63-169">Skype for Business MAK キーを入力したが、別のキーではありませんでした。</span><span class="sxs-lookup"><span data-stu-id="61c63-169">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="61c63-170">システムにインターネット アクセスがある。</span><span class="sxs-lookup"><span data-stu-id="61c63-170">The system has Internet access.</span></span>
    
- <span data-ttu-id="61c63-171">電話でライセンス認証することはできますが、最初に SRS ライセンスツールを使用してライセンス認証を行おうとする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61c63-171">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="61c63-172">電話でライセンス認証するには、テスト会議を開始します (これは短いため、テスト通話ではありません)。</span><span class="sxs-lookup"><span data-stu-id="61c63-172">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="61c63-173">Office ライセンス認証ウィザードで、[電話でのライセンス認証] を選択し、[Microsoft に電話をかける] を選びます。長い番号を入力して、返信を入力します。</span><span class="sxs-lookup"><span data-stu-id="61c63-173">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="61c63-174">認証局</span><span class="sxs-lookup"><span data-stu-id="61c63-174">Certificate Authority</span></span>

<span data-ttu-id="61c63-175">Office Web Apps Server 2013 の証明書を発行するために使用された認証局で、証明書失効リストのプロパティに HTTP パスが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="61c63-175">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="61c63-176">Skype for Business Server を使用している場合は、証明書ファイル (.crt) を Skype Room System にインポートします。</span><span class="sxs-lookup"><span data-stu-id="61c63-176">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="61c63-177">このファイルは、CA サーバーの CertEnroll 共有、またはドメインに参加する任意の PC の Trusted Root フォルダーで、簡単に入手できます。</span><span class="sxs-lookup"><span data-stu-id="61c63-177">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="61c63-178">証明書</span><span class="sxs-lookup"><span data-stu-id="61c63-178">Certificates</span></span>

<span data-ttu-id="61c63-p114">認証局に証明書失効リストの http パスが含まれることを確認します。このパスが含まれない場合は、CA を更新してパスを含めます。</span><span class="sxs-lookup"><span data-stu-id="61c63-p114">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="61c63-181">システム設定\>証明書マネージャーの下にある Skype Room システムの管理セットアップで、証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="61c63-181">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="61c63-182">内部証明書のエンタープライズ ルート CA が必要です。</span><span class="sxs-lookup"><span data-stu-id="61c63-182">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="61c63-183">必要な証明書を取得する方法の 1 つは、証明書を発行した CA を見つけることです。</span><span class="sxs-lookup"><span data-stu-id="61c63-183">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="61c63-184">Skype for business Server の場合は、Skype for Business の PC で、[ \>設定\>ツール] の [ダイヤルイン会議の設定] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61c63-184">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="61c63-185">これにより、内部証明書を発行した CA によって保護された web ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="61c63-185">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="61c63-186">ブラウザーのアドレス バーのロック アイコンをクリックして、セキュリティ レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="61c63-186">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="61c63-187">[証明書の表示] をクリックし、CRL 配布ポイントのプロパティを調べます。</span><span class="sxs-lookup"><span data-stu-id="61c63-187">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="61c63-188">第 2 の CN パラメーターは、CA のサーバー名であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="61c63-188">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="61c63-189">次に、そのアドレス\\ \< CA サーバー名\>\CertEnroll. の Windows エクスプローラーを開きます。</span><span class="sxs-lookup"><span data-stu-id="61c63-189">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="61c63-190">フラッシュ ドライブに 2 つの .crl ファイルと .crt ファイルをコピーし、SMART ボードの左側に格納します。</span><span class="sxs-lookup"><span data-stu-id="61c63-190">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="61c63-191">.Crt ファイルを、[Trusted Room サーティフィケーション Authority] フォルダーの下にある Skype Room System にインポートします。</span><span class="sxs-lookup"><span data-stu-id="61c63-191">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="61c63-192">[中間証明機関] フォルダーの下にある Skype Room システムに .crl ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="61c63-192">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="61c63-193">(ファイルを表示するには、証明書マネージャーの [ファイル拡張子] フィルターを [crl] に変更する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="61c63-193">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="61c63-194">注: Office Web Apps 2013 サーバーは、Skype for Business と同じ CA を共有している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="61c63-194">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="61c63-195">CA を共有していない場合、会議で PowerPoint を共有できません。</span><span class="sxs-lookup"><span data-stu-id="61c63-195">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="61c63-196">IT に連絡し、前述したように CA ネットワーク共有 CertEnroll から CRT ファイルおよび CRL ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="61c63-196">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="61c63-197">Skype Room System を Windows システムとして扱うことができるため、証明書の一部については Active Directory に依存していることがあります。</span><span class="sxs-lookup"><span data-stu-id="61c63-197">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="61c63-198">ただし、これは手動で管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="61c63-198">However, it's best to manually manage this.</span></span>
  

