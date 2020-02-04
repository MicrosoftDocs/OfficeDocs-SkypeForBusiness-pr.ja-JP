---
title: 'Lync Server 2013: 追加サーバー サポートおよび要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f111b80bc88b632ff1020f45e899f220edeb7d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="652ae-102">Lync Server 2013 の追加サーバー サポートおよび要件</span><span class="sxs-lookup"><span data-stu-id="652ae-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="652ae-103">_**最終更新日:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="652ae-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="652ae-104">このサポート文書の他のセクションで説明されているソフトウェアのサポートに加えて、Lync Server 2013 には次のサポート制限があります。</span><span class="sxs-lookup"><span data-stu-id="652ae-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="652ae-105">Lync Server 2013 は、特定のサーバーの役割に対して、ドメインネームシステム (DNS) とハードウェアの負荷分散をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="652ae-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="652ae-106">また、必要に応じて、仲介サーバーのアプリケーションロードバランシングもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="652ae-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="652ae-107">それぞれの用途の詳細については、計画に関するドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="652ae-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="652ae-108">Lync Server 2013 は、配布リスト展開プロトコル (DLX) を使用して配布リストを展開します。</span><span class="sxs-lookup"><span data-stu-id="652ae-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="652ae-109">このプロトコルは、配布リストのメンバーシップを取得するために使用される web サービスメソッドも指定します。</span><span class="sxs-lookup"><span data-stu-id="652ae-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="652ae-110">Microsoft Exchange Server では、メンバーに静的に割り当てられていない動的なグループがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="652ae-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="652ae-111">代わりに、グループを展開したときに評価されるクエリを保存します。</span><span class="sxs-lookup"><span data-stu-id="652ae-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="652ae-112">DLX は動的配布リストをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="652ae-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="652ae-113">この DLX の制限は、すべてのバージョンの Lync Server に適用されます。</span><span class="sxs-lookup"><span data-stu-id="652ae-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="652ae-114">[ユーザーの有効化] ウィザードでは、英語以外の文字の SIP 準拠の URI への自動変換はサポートされていないため、SIP アドレスを手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="652ae-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="652ae-115">ウイルス対策ソフトウェアを実行しているサーバーの場合は、「 [Lync Server 2013 のウイルススキャン除外](lync-server-2013-antivirus-scanning-exclusions.md)」を参照して、ウイルスの除外やその他のセキュリティ関連の推奨事項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="652ae-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="652ae-116">IPsec を使用している場合は、音声とビデオのトラフィックに使われるポート範囲で IPsec を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="652ae-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="652ae-117">詳細については、計画ドキュメントの「 [Lync Server 2013 での IPsec の例外](lync-server-2013-ipsec-exceptions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="652ae-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="652ae-118">組織でサービスの品質 (QoS) インフラストラクチャが使用されている場合、メディア サブシステムは、この既存のインフラストラクチャで機能するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="652ae-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="652ae-119">QoS の実装について詳しくは、「運用ドキュメントの[Lync Server 2013 でのサービスの品質 (QoS) の管理](lync-server-2013-managing-quality-of-service-qos.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="652ae-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="652ae-120">オペレーティングシステムファイアウォールの使用はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="652ae-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="652ae-121">Lync Server 2013 は、Microsoft SQL Server データベースソフトウェアを除き、オペレーティングシステムファイアウォールのファイアウォール例外を管理します。</span><span class="sxs-lookup"><span data-stu-id="652ae-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="652ae-122">SQL Server のファイアウォール要件の詳細については、SQL Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="652ae-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="652ae-123">外部ユーザーアクセスのサポートを実装するために使用される外部インターフェイスは、内部インターフェイスと同じネットワーク上では*なく*、別のサブネット上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="652ae-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="652ae-p106">Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。</span><span class="sxs-lookup"><span data-stu-id="652ae-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="652ae-126">Lync server 2013 累積更新プログラムのリリースでは、2013年7月、Lync Server 2013 で2段階認証がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="652ae-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="652ae-127">詳細については、「 [Lync Server 2013 での2要素認証](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="652ae-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="652ae-128">ほとんどの内部サーバーでは、**オープン認証**(OAuth) として定義された証明書の種類が必要です。</span><span class="sxs-lookup"><span data-stu-id="652ae-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="652ae-129">要求時に OAuth 証明書を要求して割り当てる必要があります。 Lync Server 展開ウィザードの [**証明書のインストールと割り当て]** フェーズを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="652ae-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="652ae-130">OAuth 証明書キーの最小サイズは、1024ビットです。</span><span class="sxs-lookup"><span data-stu-id="652ae-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="652ae-131">長さが2048ビット未満のキーの長さを持つ証明書を要求した場合は、警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="652ae-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="652ae-132">警告の代わりに2048のキーの長さが強制された場合に発生する可能性のある問題を回避するために、OAuth 証明書のキーの長さとして常に2048を使うことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="652ae-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="652ae-133">Lync Server 2013 および Microsoft Exchange Server 2010 Service Pack 1 (SP1) では、Windows Server 2008 R2 オペレーティングシステムが、FIPS 140-2 アルゴリズムを使用するように構成されている場合に、米国連邦情報処理標準 (FIPS) 140-2 アルゴリズムのサポートを利用して動作します。システム暗号化。</span><span class="sxs-lookup"><span data-stu-id="652ae-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="652ae-134">FIPS サポートを実装するには、Lync Server 2013 を実行している各サーバーでサポートされるように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="652ae-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="652ae-135">FIPS 準拠のアルゴリズム、および FIPS サポートを実装する方法の詳細については、Microsoft サポート技術情報の記事811833「システム暗号化: Windows XP およびそれ以降のバージョンの Windows で暗号化、ハッシュ、および署名のセキュリティ[http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)設定を行うための fips 準拠アルゴリズムを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="652ae-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="652ae-136">Exchange 2010 の FIPS 140-2 のサポートと制限事項の詳細については、「Exchange 2010 SP1 と FIPS 準拠アルゴリズム[http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)のサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="652ae-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="652ae-137">Lync Server 2013 では、展開前または展開中に、特定のコンポーネントにその他のソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="652ae-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="652ae-138">これには、オペレーティングシステム、ダウンロード可能なソフトウェア、および Lync Server 2013 のインストール時に自動的にインストールされるソフトウェアで利用できるソフトウェアが含まれます。</span><span class="sxs-lookup"><span data-stu-id="652ae-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="652ae-139">必要に応じて、その他のソフトウェアの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="652ae-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="652ae-140">Windows Update</span><span class="sxs-lookup"><span data-stu-id="652ae-140">Windows Update</span></span>

  - <span data-ttu-id="652ae-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="652ae-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="652ae-142">Microsoft .NET 4.5 フレームワーク</span><span class="sxs-lookup"><span data-stu-id="652ae-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="652ae-143">Microsoft Visual C++ 2012 再頒布可能</span><span class="sxs-lookup"><span data-stu-id="652ae-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="652ae-144">Lync Server 2013 をインストールすると、Microsoft Visual C++ 2012 再頒布可能パッケージが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="652ae-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="652ae-145">他のバージョンをインストールして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="652ae-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="652ae-146">URL リライトモジュールバージョン2.0 の再頒布可能</span><span class="sxs-lookup"><span data-stu-id="652ae-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="652ae-147">Windows Media フォーマット ランタイム</span><span class="sxs-lookup"><span data-stu-id="652ae-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="652ae-148">Windows PowerShell バージョン3.0</span><span class="sxs-lookup"><span data-stu-id="652ae-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="652ae-149">Microsoft Silverlight 4 browser プラグイン (Silverlight 4.0.50524.0 または Lync Server コントロールパネルの最新バージョン)</span><span class="sxs-lookup"><span data-stu-id="652ae-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="652ae-150">Active Directory ドメインサービスツール</span><span class="sxs-lookup"><span data-stu-id="652ae-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="652ae-151">これらのソフトウェア要件の一部は、特定のサーバーの役割またはコンポーネントにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="652ae-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="652ae-152">これらのソフトウェア要件の詳細については、計画ドキュメントの「 [Lync Server 2013 のその他のソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="652ae-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

