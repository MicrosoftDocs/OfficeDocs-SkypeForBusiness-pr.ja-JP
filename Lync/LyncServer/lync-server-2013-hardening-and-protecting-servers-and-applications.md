---
title: 'Lync Server 2013: サーバーおよびアプリケーションの強化と保護'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00fea9bd192dedaf16567209798f12c7bff23e6a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="73aff-102">Lync Server 2013 のサーバーおよびアプリケーションの強化と保護</span><span class="sxs-lookup"><span data-stu-id="73aff-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73aff-103">_**最終更新日:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="73aff-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="73aff-104">特定のコンポーネントのベストプラクティスに従って、オペレーティングシステムとアプリケーションを強化して保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73aff-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="73aff-105">このセクションでは、アプリケーションサーバーを強化する方法と、グループポリシーを使ってセキュリティ lockdowns を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="73aff-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73aff-106">Microsoft Lync Server 2013 の展開に使用されるデータベースを強化および保護することもできます。</span><span class="sxs-lookup"><span data-stu-id="73aff-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="73aff-107">詳細については、「 <A href="lync-server-2013-hardening-and-protecting-databases.md">Lync Server 2013 のデータベースの強化と保護</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73aff-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="73aff-108">アプリケーションサーバーをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="73aff-108">Securing Application Servers</span></span>

<span data-ttu-id="73aff-109">アプリケーションサーバーの場合、オペレーティングシステムとアプリケーションが強化されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="73aff-109">For applications servers, the operating system and the application should be hardened.</span></span> <span data-ttu-id="73aff-110">たとえば、Microsoft インターネットセキュリティとアクセラレータ (ISA) サーバー2006の実行専用の Windows Server 2008 コンピューターは、オペレーティングシステムとアプリケーションの観点から強化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73aff-110">For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective.</span></span> <span data-ttu-id="73aff-111">サーバーによって実行されるサービスの数を最小限に抑えることは、主な目標です。</span><span class="sxs-lookup"><span data-stu-id="73aff-111">Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="73aff-112">仮想サーバーをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="73aff-112">Securing Virtual Servers</span></span>

<span data-ttu-id="73aff-113">仮想サーバースナップショットには、サーバーのデータディスクのコピーと、メモリ内データのダンプも含まれています。どちらの場合も、攻撃を招く可能性のある機密性の高い暗号化データが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73aff-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="73aff-114">仮想化を使用して実装された運用サーバーの場合は、サーバースナップショットをすべて無効にするか、非常に制御された方法で管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73aff-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="73aff-115">Hyper-v 仮想サーバーのセキュリティ保護の詳細については、「」の Hyper-v セキュリティガイド[http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73aff-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="73aff-116">グループポリシー</span><span class="sxs-lookup"><span data-stu-id="73aff-116">Group Policy</span></span>

<span data-ttu-id="73aff-117">Windows Server 2008 および Windows Server 2008 R2 では、グループポリシーによってディレクトリベースのデスクトップ構成管理が提供されます。</span><span class="sxs-lookup"><span data-stu-id="73aff-117">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management.</span></span> <span data-ttu-id="73aff-118">グループポリシーを使用して、次のようにコンピューターとユーザーの設定をグループポリシーオブジェクト (GPO) 内で定義することにより、セキュリティ lockdowns を実装できます。</span><span class="sxs-lookup"><span data-stu-id="73aff-118">You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="73aff-119">レジストリベースのポリシー</span><span class="sxs-lookup"><span data-stu-id="73aff-119">Registry-based policies</span></span>

  - <span data-ttu-id="73aff-120">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="73aff-120">Security</span></span>

  - <span data-ttu-id="73aff-121">ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="73aff-121">Software installation</span></span>

  - <span data-ttu-id="73aff-122">スクリプト</span><span class="sxs-lookup"><span data-stu-id="73aff-122">Scripts</span></span>

  - <span data-ttu-id="73aff-123">フォルダリダイレクション</span><span class="sxs-lookup"><span data-stu-id="73aff-123">Folder redirection</span></span>

  - <span data-ttu-id="73aff-124">リモートインストールサービス</span><span class="sxs-lookup"><span data-stu-id="73aff-124">Remote installation services</span></span>

<span data-ttu-id="73aff-125">これらの設定を構成する管理者向けのユーザーインターフェイスを提供するために、管理用テンプレートは、オペレーティングシステムリリース、service pack リリース、および Lync Server 2013 などの一部のアプリケーションに付属しています。</span><span class="sxs-lookup"><span data-stu-id="73aff-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="73aff-126">Communicator ファイルは、Lync Server 2013 に付属している管理用テンプレートであり、% windir%\\inf\\ディレクトリにインストールされ、グループポリシー設定のインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="73aff-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="73aff-127">Communicator の各設定は、アプリケーションの動作に影響するレジストリ内の設定に対応しています。</span><span class="sxs-lookup"><span data-stu-id="73aff-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="73aff-128">設定は、Active Directory ユーザーとコンピューター本体およびグループポリシー管理コンソール (GPMC) から利用できる GPedit からアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="73aff-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="73aff-129">グループポリシーのセキュリティ設定</span><span class="sxs-lookup"><span data-stu-id="73aff-129">Group Policy Security Settings</span></span>

<span data-ttu-id="73aff-130">グループポリシーには、GPedit からアクセスした場合の、[コンピューターの構成]、[Windows の設定]、[セキュリティ設定] の下にある GPO のセキュリティ設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="73aff-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="73aff-131">セキュリティテンプレートをインポートして、GPO のセキュリティ設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="73aff-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="73aff-132">Windows server 2008 セキュリティガイド[http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186)と windows Server 2008 R2 セキュリティコンプライアンス管理ツールキットに[http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882)は、必要に応じて変更できる多数のサンプルテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="73aff-132">The Windows Server 2008 Security Guide at [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="73aff-133">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="73aff-133">Best Practices</span></span>

  - <span data-ttu-id="73aff-134">すべてのサーバーオペレーティングシステムとアプリケーションを強化します。</span><span class="sxs-lookup"><span data-stu-id="73aff-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="73aff-135">サーバーのスナップショットを保護し、すべての仮想サーバーのセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="73aff-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="73aff-136">グループポリシーを使用して、セキュリティ lockdowns を実装します。</span><span class="sxs-lookup"><span data-stu-id="73aff-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

