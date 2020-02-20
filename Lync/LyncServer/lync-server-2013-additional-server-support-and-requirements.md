---
title: 'Lync Server 2013: その他のサーバーのサポートと要件'
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
ms.openlocfilehash: fa21b481d58d149bcc4c8189e210dfc23647a673
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="71f02-102">Lync Server 2013 におけるその他のサーバーのサポートおよび要件</span><span class="sxs-lookup"><span data-stu-id="71f02-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71f02-103">_**トピックの最終更新日:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="71f02-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="71f02-104">このサポートドキュメントの他のセクションで説明されているソフトウェアサポートに加えて、Lync Server 2013 には次のサポート制限があります。</span><span class="sxs-lookup"><span data-stu-id="71f02-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="71f02-105">Lync Server 2013 では、特定のサーバーの役割に対してドメインネームシステム (DNS) とハードウェア負荷分散がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="71f02-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="71f02-106">また、仲介サーバーのアプリケーション負荷分散も、必要に応じてサポートします。</span><span class="sxs-lookup"><span data-stu-id="71f02-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="71f02-107">それぞれをいつ使用するかの詳細については、「計画」のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f02-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="71f02-108">Lync Server 2013 は、配布リスト展開プロトコル (DLX) を使用して、配布リストを展開します。</span><span class="sxs-lookup"><span data-stu-id="71f02-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="71f02-109">このプロトコルは、配布リストのメンバーシップの取得に使用する Web サービス メソッドも指定します。</span><span class="sxs-lookup"><span data-stu-id="71f02-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="71f02-110">Microsoft Exchange Server は、静的に割り当てられたメンバーを持たない動的グループをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="71f02-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="71f02-111">代わりにこれらのグループは、グループの展開時に評価されるクエリを格納します。</span><span class="sxs-lookup"><span data-stu-id="71f02-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="71f02-112">DLX は動的な配布リストをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="71f02-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="71f02-113">この DLX の制限は、Lync Server のすべてのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="71f02-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="71f02-114">ユーザーの有効化ウィザードでは、英語以外の文字の SIP 準拠 URI への自動変換はサポートされていません。したがって、SIP アドレスを手動で変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f02-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="71f02-115">ウイルス対策ソフトウェアを実行しているサーバーについては、「 [Lync Server 2013 のウイルス対策スキャン除外](lync-server-2013-antivirus-scanning-exclusions.md)」を参照してください。ウイルスの推奨候補およびその他のセキュリティ関連の推奨事項</span><span class="sxs-lookup"><span data-stu-id="71f02-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="71f02-116">IPsec を使用する場合は、音声およびビデオ トラフィックに使用されるポート範囲に対する IPsec を無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="71f02-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="71f02-117">詳細については、「計画」のドキュメントの「 [IPsec 例外 (Lync Server 2013](lync-server-2013-ipsec-exceptions.md) )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f02-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="71f02-118">組織でサービスの品質 (QoS) インフラストラクチャが使用されている場合、メディア サブシステムは、この既存のインフラストラクチャで機能するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="71f02-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="71f02-119">QoS の実装の詳細については、「操作」のドキュメントの「 [Lync Server 2013 でのサービスの品質 (qos) の管理](lync-server-2013-managing-quality-of-service-qos.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f02-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="71f02-120">オペレーティング システムのファイアウォールの使用がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="71f02-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="71f02-121">Lync Server 2013 は、Microsoft SQL Server データベースソフトウェアを除き、オペレーティングシステムファイアウォールのファイアウォール例外を管理します。</span><span class="sxs-lookup"><span data-stu-id="71f02-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="71f02-122">SQL Server のファイアウォールの要件の詳細については、SQL Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f02-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="71f02-123">外部ユーザー アクセスのサポートの実装で使用する外部インターフェイスは、内部インターフェイスと同じネットワーク上*ではなく*、別のサブネット上にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f02-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="71f02-p106">Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。</span><span class="sxs-lookup"><span data-stu-id="71f02-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="71f02-126">Lync Server 2013 の累積的な更新プログラム (2013 年7月) のリリースでは、Lync Server 2013 は2要素認証をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="71f02-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="71f02-127">詳細については、「 [Lync Server 2013 の2要素認証](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f02-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="71f02-128">ほとんどの内部サーバーでは、証明書の種類として **[オープン認証**(OAuth)] と定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f02-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="71f02-129">[Lync Server 展開ウィザード] の [**証明書の要求、インストール、および割り当て**] フェーズで OAuth 証明書を要求して割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f02-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="71f02-130">OAuth 証明書キーの最小サイズは1024ビットです。</span><span class="sxs-lookup"><span data-stu-id="71f02-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="71f02-131">キーの長さが2048ビット未満の証明書を要求した場合は、警告が表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="71f02-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="71f02-132">警告の代わりに2048のキー長が適用された場合に発生する可能性のある問題を回避するために、OAuth 証明書には常に2048のキー長を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="71f02-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="71f02-133">Lync Server 2013 と Microsoft Exchange Server 2010 Service Pack 1 (SP1) は、Windows Server 2008 R2 オペレーティングシステムが、に対して FIPS の140-2 アルゴリズムを使用するように構成されている場合に、連邦情報処理規格 (FIPS) の140-2 アルゴリズムをサポートして動作します。システム暗号化。</span><span class="sxs-lookup"><span data-stu-id="71f02-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="71f02-134">FIPS サポートを実装するには、Lync Server 2013 を実行している各サーバーをサポートするように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f02-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="71f02-135">FIPS 準拠アルゴリズムと FIPS サポートを実装する方法の詳細については、Microsoft サポート技術情報の記事811833「システム暗号化: Windows XP およびそれ以降のバージョンの Windows で暗号化、ハッシュ、署名のセキュリティ設定を使用[https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f02-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="71f02-136">Exchange 2010 の FIPS 140-2 のサポートおよび制限事項の詳細については、「Exchange 2010 SP1 およびサポートさ[https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)れている Fips 準拠アルゴリズムのサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f02-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="71f02-137">Lync Server 2013 では、展開前または展開中に特定のコンポーネントに他のソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71f02-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="71f02-138">これには、オペレーティングシステム、ダウンロード可能なソフトウェア、および Lync Server 2013 のインストール時に自動的にインストールされるソフトウェアで利用できるソフトウェアが含まれています。</span><span class="sxs-lookup"><span data-stu-id="71f02-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="71f02-139">必要になる可能性のある追加ソフトウェアは、次の一覧のとおりです。</span><span class="sxs-lookup"><span data-stu-id="71f02-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="71f02-140">Windows Update</span><span class="sxs-lookup"><span data-stu-id="71f02-140">Windows Update</span></span>

  - <span data-ttu-id="71f02-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="71f02-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="71f02-142">Microsoft .NET 4.5 Framework</span><span class="sxs-lookup"><span data-stu-id="71f02-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="71f02-143">Microsoft Visual C++ 2012 再頒布可能パッケージ</span><span class="sxs-lookup"><span data-stu-id="71f02-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="71f02-144">Microsoft Visual C++ 2012 再頒布可能パッケージは、Lync Server 2013 をインストールすると、自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="71f02-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="71f02-145">他のバージョンをインストールして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="71f02-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="71f02-146">URL Rewrite Module Version 2.0 (再頒布可能)</span><span class="sxs-lookup"><span data-stu-id="71f02-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="71f02-147">Windows Media フォーマット ランタイム</span><span class="sxs-lookup"><span data-stu-id="71f02-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="71f02-148">Windows PowerShell バージョン3.0</span><span class="sxs-lookup"><span data-stu-id="71f02-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="71f02-149">Microsoft Silverlight 4 ブラウザー プラグイン (Lync Server コントロール パネルの場合は Silverlight 4.0.50524.0 または最新バージョン)</span><span class="sxs-lookup"><span data-stu-id="71f02-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="71f02-150">Active Directory ドメインサービスのツール</span><span class="sxs-lookup"><span data-stu-id="71f02-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="71f02-151">上記のソフトウェア要件の中には、特定のサーバーの役割またはコンポーネントに対してのみ適用されるものもあります。</span><span class="sxs-lookup"><span data-stu-id="71f02-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="71f02-152">これらのソフトウェア要件の詳細については、「計画」のドキュメントの「 [Lync Server 2013 の追加ソフトウェア要件](lync-server-2013-additional-software-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71f02-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

