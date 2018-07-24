---
title: Skype Room System の管理容易性とツール
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: このトピックでは、Skype Room System の管理ツールについて説明します。
ms.openlocfilehash: 8e509059cc2fdffc35bba0d43a84c0699aa536d5
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977459"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="d05ae-103">Skype Room System の管理容易性とツール</span><span class="sxs-lookup"><span data-stu-id="d05ae-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="d05ae-104">このトピックでは、Skype Room System の管理ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="d05ae-105">管理ポータル</span><span class="sxs-lookup"><span data-stu-id="d05ae-105">Administrative Portal</span></span>

<span data-ttu-id="d05ae-106">ビジネス サーバー設置型展開では Skype は、積極的に管理し、組織内で Skype ルーム システムの展開を監視する Skype ルーム システムの管理ポータルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="d05ae-107">詳細については次の資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d05ae-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="d05ae-108">ビジネス サーバーの Skype で SRS v1 の管理用の Web ポータルを展開します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a><span data-ttu-id="d05ae-109">System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="d05ae-109">System Center Operations Manager</span></span>

<span data-ttu-id="d05ae-110">[Skype ルーム システムの管理パック](https://www.microsoft.com/download/details.aspx?id=42320)をダウンロードし、SCOM サーバー上にインストールすることによって Skype ルームのシステムをシステム センター操作マネージャー (SCOM) を監視できます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-110">Skype Room System can be monitored through the System Center Operations Manager (SCOM) by downloading the [Skype Room System Management Pack](https://www.microsoft.com/download/details.aspx?id=42320) and installing it on your SCOM server.</span></span> <span data-ttu-id="d05ae-111">SCOM を使用するアラートを設定する、Skype ルーム システムの稼働状態の監視、稼動状況のレポートなどの作業を生成します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-111">You can use SCOM to set alerts, monitor the health of Skype Room System, generate uptime reports, and much more.</span></span> <span data-ttu-id="d05ae-112">Skype ルーム システム SCOM サーバーを指すように構成することを事前にインストールされているモニタリング ・ エージェントが付属します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-112">Skype Room System comes with a pre-installed monitoring agent that can be configured to point to SCOM server.</span></span> <span data-ttu-id="d05ae-113">Skype ルーム システムのモニタリング ・ エージェントを構成する方法を知っている Skype ルーム システムの製造元から提供されたインストール ・ ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d05ae-113">Refer to the installation guide provided by your Skype Room System manufacturer to know how to configure the monitoring agent on Skype Room System.</span></span>
  
## <a name="exchange-checklist"></a><span data-ttu-id="d05ae-114">Exchange チェックリスト</span><span class="sxs-lookup"><span data-stu-id="d05ae-114">Exchange Checklist</span></span>

- <span data-ttu-id="d05ae-115">自動検出がセットアップされており、autodiscover.domain.com に対して内部 DNS A/CNAME RECORD が利用可能であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-115">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="d05ae-116">自動検出の ping を実行します (例: Ping Autodiscover.contoso.com)。</span><span class="sxs-lookup"><span data-stu-id="d05ae-116">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="d05ae-117">Microsoft 接続アナライザー ツールで自動検出サービスをテストします。</span><span class="sxs-lookup"><span data-stu-id="d05ae-117">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="d05ae-118">「ログオンできません Office Outlook とします。」最初のテストを選択します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-118">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="d05ae-119">会議室には、リソース メールボックスが割り当てられている場合は、Skype ルーム システム (ページの下部にあるスクリプトの例) のアカウントを拡張します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-119">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="d05ae-120">Skype がビジネス チェックリストについて</span><span class="sxs-lookup"><span data-stu-id="d05ae-120">Skype for Business Checklist</span></span>

- <span data-ttu-id="d05ae-121">次のツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-121">Run the following tools:</span></span>
    
  - <span data-ttu-id="d05ae-122">ビジネスのベスト プラクティス アナライザーの Skype</span><span class="sxs-lookup"><span data-stu-id="d05ae-122">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="d05ae-123">Skype のビジネスの稼働状態分析ツール (Excel)</span><span class="sxs-lookup"><span data-stu-id="d05ae-123">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="d05ae-124">32 ビットまたは 64 ビットの Business Connectivity アナライザーの Skype</span><span class="sxs-lookup"><span data-stu-id="d05ae-124">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="d05ae-125">[便利な新しいトラブルシューティングと分析ツールを Office 365 で](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)確認します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-125">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="d05ae-126">ビジネスのプールと、Office Web Apps サーバーの Skype してビジネスのクライアントは、Skype を使用して PowerPoint デッキを共有することができますを確認します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-126">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="d05ae-127">会議室には、リソース メールボックスが割り当てられている場合は、Skype のビジネスに有効にします。</span><span class="sxs-lookup"><span data-stu-id="d05ae-127">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="d05ae-128">必要に応じて、会議室システムの DID (電話番号) を要求し、Active Directory ツールで [一般電話] フィールドを更新します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-128">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="d05ae-129">ネットワーク</span><span class="sxs-lookup"><span data-stu-id="d05ae-129">Network</span></span>

- <span data-ttu-id="d05ae-130">Skype ルーム システムのワイヤード (有線) ネットワーク接続があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-130">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="d05ae-131">ネットワーク ビジネス用の Skype については、ガイドの計画を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d05ae-131">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="d05ae-132">ビジネス パートナーに、Skype、Skype のビジネス ネットワークの評価を要求します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-132">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="d05ae-133">ビジネスの稼働状態分析ツール (Excel) の Skype でキャプチャされたパフォーマンス データを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d05ae-133">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="d05ae-134">ネットワーク分析ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-134">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="d05ae-135">通話前診断ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-135">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="d05ae-136">Skype ルーム システムのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="d05ae-136">Skype Room System Security</span></span>

<span data-ttu-id="d05ae-137">Skype ルーム システムは、ビジネス ・ セキュリティ ・ モデル、著作権管理、および SCOM などの管理ツールは、Skype を使用して、Windows の展開に完全に統合されている組み込みシステムです。</span><span class="sxs-lookup"><span data-stu-id="d05ae-137">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="d05ae-138">次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-138">Features include:</span></span>
  
- <span data-ttu-id="d05ae-139">ユーザー モードでのディスクの書き込みを防止する書き込みフィルター</span><span class="sxs-lookup"><span data-stu-id="d05ae-139">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="d05ae-p105">許可されていないアプリの実行を防止するアプリ ロッカー。すべての USB ポートがユーザー モードで無効になります。</span><span class="sxs-lookup"><span data-stu-id="d05ae-p105">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="d05ae-142">標準的なアプリケーションまたはビューアー上に存在しない Skype ルーム システムのハードウェアです。</span><span class="sxs-lookup"><span data-stu-id="d05ae-142">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="d05ae-143">すべてのコンテンツは、HTTP プロトコルまたは RDP プロトコル経由で表示されます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-143">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="d05ae-p107">アプライアンス PC では、Windows Embedded Standard 7 オペレーティング システムを実行します。デバイスを含むすべてのハードウェアは、OEM パートナーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-p107">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="d05ae-146">Active Directory ドメイン サービス (AD DS) へのオプションのドメイン参加で、ローカル セキュリティ アカウントの管理および制御が可能になります。</span><span class="sxs-lookup"><span data-stu-id="d05ae-146">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="d05ae-147">ビジネス管理センターは、Skype を使用して、ローカルの管理者アカウントを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-147">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="d05ae-148">Skype ルーム システムは、標準の Microsoft 更新プログラムのプロセスを通じて更新されます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-148">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="d05ae-149">Skype ルーム システムは、ビジネスの Skype に接続します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-149">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="d05ae-150">ビジネス用の Skype を使用して、エンド ・ ツー ・ エンドの暗号化および認証のすべての通信モード</span><span class="sxs-lookup"><span data-stu-id="d05ae-150">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="d05ae-151">Skype ルームのシステムでは、ビジネスのセキュリティとコンプライアンスの標準の Skype をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d05ae-151">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="d05ae-152">詳細については、 [Skype のビジネス サーバーでのセキュリティの計画](../../plan-your-deployment/security/security.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d05ae-152">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="d05ae-153">ライセンス</span><span class="sxs-lookup"><span data-stu-id="d05ae-153">License</span></span>

<span data-ttu-id="d05ae-154">ソフトウェアのライセンス認証に KMS を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-154">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="d05ae-155">場合は、確認するか、Skype のビジネス クライアント KMS キーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d05ae-155">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="d05ae-156">KMS を使用していない場合は、ボリューム、Skype のビジネス クライアント MAK のライセンス キーを要求します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-156">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="d05ae-157">ライセンス キー</span><span class="sxs-lookup"><span data-stu-id="d05ae-157">License keys</span></span>

<span data-ttu-id="d05ae-158">Skype ルームのシステムでは、バック グラウンドで、Skype のビジネス デスクトップ クライアントを実行します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-158">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="d05ae-159">Skype ルーム システムがドメインのメンバーである場合は、KMS を検出します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-159">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="d05ae-160">(と自動的にアクティブには、ボリューム ライセンスの KMS キーがある場合)。</span><span class="sxs-lookup"><span data-stu-id="d05ae-160">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="d05ae-161">ボリューム ライセンスは、MAK では、xxxxx xxxxx xxxxx xxxxx が表示されるを入力しても提供します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-161">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="d05ae-162">(インターネットにアクセスする必要が、MAK、KMS ではないを使用してアクティブにする)。</span><span class="sxs-lookup"><span data-stu-id="d05ae-162">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="d05ae-163">詳細については、Office 2013 のボリューム ライセンス認証を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d05ae-163">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="d05ae-164">MAK キーを入力するには、OEM の設定に移動\>SRS ライセンス ツールです。</span><span class="sxs-lookup"><span data-stu-id="d05ae-164">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="d05ae-165">[状態の確認] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d05ae-165">Click Check Status.</span></span> <span data-ttu-id="d05ae-166">「製品のライセンス認証されていない」と表示されている、キーを入力します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-166">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="d05ae-167">ライセンス認証中に、エラーが発生した場合は、"' ソフトウェア ライセンス サービス プロダクト キーが有効ではないことを報告される」ことを確認し。</span><span class="sxs-lookup"><span data-stu-id="d05ae-167">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="d05ae-168">キーが正しく入力された。</span><span class="sxs-lookup"><span data-stu-id="d05ae-168">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="d05ae-169">ビジネス MAK キーと他のキーに、Skype を入力したとします。</span><span class="sxs-lookup"><span data-stu-id="d05ae-169">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="d05ae-170">システムにインターネット アクセスがある。</span><span class="sxs-lookup"><span data-stu-id="d05ae-170">The system has Internet access.</span></span>
    
- <span data-ttu-id="d05ae-171">電話でアクティブにすることができますが、最初に、SRS のライセンス ツールを使用してアクティブにしよう必要があります。</span><span class="sxs-lookup"><span data-stu-id="d05ae-171">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="d05ae-172">電話でライセンス認証をするには、テスト用会議 (いないテストの呼び出しとしては短すぎる) を起動します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-172">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="d05ae-173">Office ライセンス認証ウィザードで、電話によるライセンス認証を選択して、マイクロソフト long 型の値を入力し、応答を入力してください。</span><span class="sxs-lookup"><span data-stu-id="d05ae-173">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="d05ae-174">認証局</span><span class="sxs-lookup"><span data-stu-id="d05ae-174">Certificate Authority</span></span>

<span data-ttu-id="d05ae-175">Office Web Apps Server 2013 の証明書を発行するために使用された認証局で、証明書失効リストのプロパティに HTTP パスが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-175">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="d05ae-176">Skype を使用してビジネスのサーバーの場合は、Skype ルーム システムに証明書ファイル (.crt) をインポートします。</span><span class="sxs-lookup"><span data-stu-id="d05ae-176">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="d05ae-177">このファイルは、CA サーバーの CertEnroll 共有、またはドメインに参加する任意の PC の Trusted Root フォルダーで、簡単に入手できます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-177">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="d05ae-178">証明書</span><span class="sxs-lookup"><span data-stu-id="d05ae-178">Certificates</span></span>

<span data-ttu-id="d05ae-p114">認証局に証明書失効リストの http パスが含まれることを確認します。このパスが含まれない場合は、CA を更新してパスを含めます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-p114">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="d05ae-181">管理システムのセットアップ、Skype ルーム システムの設定] の下で証明書をインストール\>証明書マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="d05ae-181">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="d05ae-182">内部証明書のエンタープライズ ルート CA が必要です。</span><span class="sxs-lookup"><span data-stu-id="d05ae-182">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="d05ae-183">必要な証明書を取得する方法の 1 つは、証明書を発行した CA を見つけることです。</span><span class="sxs-lookup"><span data-stu-id="d05ae-183">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="d05ae-184">Skype ビジネス上のサーバー、ビジネス用の Skype で PC 用の [設定] をクリックします\>ツール\>では、ダイヤルイン会議の設定です。</span><span class="sxs-lookup"><span data-stu-id="d05ae-184">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="d05ae-185">内部証明書を発行した CA がセキュリティで保護された web ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-185">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="d05ae-186">ブラウザーのアドレス バーのロック アイコンをクリックして、セキュリティ レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-186">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="d05ae-187">[証明書の表示] をクリックし、CRL 配布ポイントのプロパティを調べます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-187">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="d05ae-188">第 2 の CN パラメーターは、CA のサーバー名であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="d05ae-188">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="d05ae-189">ここでそのアドレスを Windows エクスプ ローラーを開き\\ \< CA サーバー名\>\CertEnroll。</span><span class="sxs-lookup"><span data-stu-id="d05ae-189">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="d05ae-190">フラッシュ ドライブに 2 つの .crl ファイルと .crt ファイルをコピーし、SMART ボードの左側に格納します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-190">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="d05ae-191">Skype ルーム システム領域の信頼された証明機関] フォルダーの下に、.crt ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d05ae-191">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="d05ae-192">中間証明機関] フォルダーの下の Skype ルーム システムの .crl ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d05ae-192">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="d05ae-193">(必要な .crl ファイルを表示する証明書マネージャーで [ファイル拡張子のフィルターを変更するのには)。</span><span class="sxs-lookup"><span data-stu-id="d05ae-193">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="d05ae-194">注: Office の Web アプリ 2013 のサーバーは、ビジネスの Skype と同じ CA を共有できます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-194">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="d05ae-195">CA を共有していない場合、会議で PowerPoint を共有できません。</span><span class="sxs-lookup"><span data-stu-id="d05ae-195">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="d05ae-196">IT に連絡し、前述したように CA ネットワーク共有 CertEnroll から CRT ファイルおよび CRL ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="d05ae-196">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="d05ae-197">ドメインのメンバーシップは、Windows システムと Skype ・ ルーム ・ システムを扱うことができますし、それに使用できる Active Directory 証明書のさまざまな側面のいくつかあるために、いくつかの点を簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="d05ae-197">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="d05ae-198">ただし、これは手動で管理することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d05ae-198">However, it's best to manually manage this.</span></span>
  

