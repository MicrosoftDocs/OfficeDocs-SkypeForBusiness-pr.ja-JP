---
title: 'Lync Server 2013: サーバーおよびアプリケーションの強化と保護'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting servers and applications for Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518331(v=OCS.15)
ms:contentKeyID: 62625491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2a8de372a8ca0ae6ec8c80a147eb74ffb01d0a7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-servers-and-applications-for-lync-server-2013"></a><span data-ttu-id="449b6-102">Lync Server 2013 のサーバーおよびアプリケーションの強化と保護</span><span class="sxs-lookup"><span data-stu-id="449b6-102">Hardening and protecting servers and applications for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="449b6-103">_**トピックの最終更新日:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="449b6-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="449b6-104">個々のコンポーネントのベスト プラクティスに従って、オペレーティング システムおよびアプリケーションを強化して保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="449b6-104">You should harden and protect your operating system and applications according to best practices for that specific component.</span></span> <span data-ttu-id="449b6-105">ここでは、アプリケーション サーバーを強化し、グループ ポリシーを使用してセキュリティ ロックダウンを実装する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="449b6-105">This section describes how to harden application servers and use Group Policy to implement security lockdowns.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="449b6-106">Microsoft Lync Server 2013 の展開に使用するデータベースを強化および保護することもできます。</span><span class="sxs-lookup"><span data-stu-id="449b6-106">You can also harden and protect the databases used for you Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="449b6-107">詳細については、「 <A href="lync-server-2013-hardening-and-protecting-databases.md">Lync Server 2013 のデータベースのセキュリティ強化と保護</A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="449b6-107">For details, see <A href="lync-server-2013-hardening-and-protecting-databases.md">Hardening and protecting the databases of Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="securing-application-servers"></a><span data-ttu-id="449b6-108">アプリケーション サーバーのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="449b6-108">Securing Application Servers</span></span>

<span data-ttu-id="449b6-p103">アプリケーション サーバーの場合は、オペレーティング システムとアプリケーションを強化する必要があります。たとえば、Microsoft Internet Security and Acceleration (ISA) Server 2006 の実行専用に使用する Windows Server 2008 コンピューターは、オペレーティング システムとアプリケーションの両方の面から強化する必要があります。主な目標は、サーバーで実行および提供されるサービスの数をできるだけ少なくすることです。</span><span class="sxs-lookup"><span data-stu-id="449b6-p103">For applications servers, the operating system and the application should be hardened. For example, a Windows Server 2008 computer dedicated to running Microsoft Internet Security and Acceleration (ISA) Server 2006 should be hardened from the operating system and from the application perspective. Minimizing the number of services running and provided by the server should be a primary goal.</span></span>

</div>

<div>

## <a name="securing-virtual-servers"></a><span data-ttu-id="449b6-112">仮想サーバーのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="449b6-112">Securing Virtual Servers</span></span>

<span data-ttu-id="449b6-113">仮想サーバーのスナップショットには、サーバーのデータディスクのコピーが含まれており、メモリ内データのダンプも含まれています。どちらにも、攻撃につながる可能性がある機密性の高い暗号化データを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="449b6-113">Virtual server snapshots contain copies of the server’s data disks and also contain dumps of in-memory data, both of which can contain sensitive cryptographic data that might lead to attacks.</span></span> <span data-ttu-id="449b6-114">仮想化を使用して実装された運用サーバーでは、すべてのサーバーのスナップショットを無効にするか、非常に制御された方法で管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="449b6-114">For production servers implemented using virtualization, you should disable all server snapshots or manage them in a very controlled manner.</span></span> <span data-ttu-id="449b6-115">Hyper-v 仮想サーバーのセキュリティ保護の詳細については、「」の「Hyper-v Security [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176)Guide」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="449b6-115">For details about securing Hyper-V virtual servers, see the Hyper-V Security Guide at: [https://go.microsoft.com/fwlink/p/?LinkId=214176](https://go.microsoft.com/fwlink/p/?linkid=214176).</span></span>

</div>

<div>

## <a name="group-policy"></a><span data-ttu-id="449b6-116">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="449b6-116">Group Policy</span></span>

<span data-ttu-id="449b6-p105">Windows Server 2008 および Windows Server 2008 R2 では、グループ ポリシーにより、ディレクトリ ベースのデスクトップ構成の管理が行われます。次のグループ ポリシー オブジェクト (GPO) 内でコンピューターとユーザーの設定を定義することにより、グループ ポリシーを使用してセキュリティ ロックダウンを実装できます。</span><span class="sxs-lookup"><span data-stu-id="449b6-p105">In Windows Server 2008 and Windows Server 2008 R2, Group Policy provides directory-based desktop configuration management. You can use Group Policy to implement security lockdowns by defining Computer and User settings within a Group Policy object (GPO) for the following:</span></span>

  - <span data-ttu-id="449b6-119">レジストリ ベースのポリシー</span><span class="sxs-lookup"><span data-stu-id="449b6-119">Registry-based policies</span></span>

  - <span data-ttu-id="449b6-120">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="449b6-120">Security</span></span>

  - <span data-ttu-id="449b6-121">ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="449b6-121">Software installation</span></span>

  - <span data-ttu-id="449b6-122">スクリプト</span><span class="sxs-lookup"><span data-stu-id="449b6-122">Scripts</span></span>

  - <span data-ttu-id="449b6-123">フォルダー リダイレクト</span><span class="sxs-lookup"><span data-stu-id="449b6-123">Folder redirection</span></span>

  - <span data-ttu-id="449b6-124">リモート インストール サービス</span><span class="sxs-lookup"><span data-stu-id="449b6-124">Remote installation services</span></span>

<span data-ttu-id="449b6-125">管理者がこれらの設定を構成するためのユーザーインターフェイスを提供するために、管理用テンプレートにはオペレーティングシステムのリリース、service pack のリリース、および Lync Server 2013 を含む一部のアプリケーションが付属しています。</span><span class="sxs-lookup"><span data-stu-id="449b6-125">To provide a user interface for the administrator to configure these settings, administrative templates are shipped with operating system releases, service pack releases, and some applications, including Lync Server 2013.</span></span>

<span data-ttu-id="449b6-126">Communicator ファイルは、Lync Server 2013 に付属している管理用テンプレートで、% windir%\\inf\\ディレクトリにインストールされ、グループポリシー設定へのインターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="449b6-126">The Communicator.adm file is an administrative template that ships with Lync Server 2013, is installed to the %windir%\\inf\\ directory, and provides an interface to the Group Policy settings.</span></span> <span data-ttu-id="449b6-127">Communicator.adm の各設定は、アプリケーションの動作に影響するレジストリの設定に対応しています。</span><span class="sxs-lookup"><span data-stu-id="449b6-127">Each setting in Communicator.adm corresponds to a setting in the registry that affects application behavior.</span></span>

<span data-ttu-id="449b6-128">この設定には、GPedit.dll からアクセスできます。GPedit.dll は、Active Directory ユーザーとコンピューターのコンソールおよびグループ ポリシー管理コンソール (GPMC) から利用できます。</span><span class="sxs-lookup"><span data-stu-id="449b6-128">The settings can be accessed from GPedit.dll, which is available from the Active Directory Users and Computers console and the Group Policy Management Console (GPMC).</span></span>

</div>

<div>

## <a name="group-policy-security-settings"></a><span data-ttu-id="449b6-129">グループ ポリシーのセキュリティの設定</span><span class="sxs-lookup"><span data-stu-id="449b6-129">Group Policy Security Settings</span></span>

<span data-ttu-id="449b6-130">グループポリシーには、GPedit からアクセスする場合の [コンピューターの構成]、[Windows の設定]、[セキュリティの設定] にある GPO のセキュリティ設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="449b6-130">Group Policy contains security settings for a GPO under Computer Configuration/Windows Settings/Security Settings when accessed from GPedit.dll.</span></span> <span data-ttu-id="449b6-131">セキュリティテンプレートをインポートして、GPO のセキュリティ設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="449b6-131">You can import security templates to configure security settings for the GPO.</span></span> <span data-ttu-id="449b6-132">「Windows Server 2008 セキュリティガイド」 [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186)および「windows Server 2008 R2 セキュリティコンプライアンス管理ツールキット[https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) 」には、必要に応じて変更できるサンプルテンプレートがいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="449b6-132">The Windows Server 2008 Security Guide at [https://go.microsoft.com/fwlink/p/?LinkId=145186](https://go.microsoft.com/fwlink/p/?linkid=145186) and the Windows Server 2008 R2 Security Compliance Management Toolkit at [https://go.microsoft.com/fwlink/p/?LinkId=211882](https://go.microsoft.com/fwlink/p/?linkid=211882) contain a number of sample templates that you can modify to meet your needs.</span></span>

</div>

<div>

## <a name="best-practices"></a><span data-ttu-id="449b6-133">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="449b6-133">Best Practices</span></span>

  - <span data-ttu-id="449b6-134">すべてのサーバー オペレーティング システムおよびアプリケーションを強化します。</span><span class="sxs-lookup"><span data-stu-id="449b6-134">Harden all server operating systems and applications.</span></span>

  - <span data-ttu-id="449b6-135">サーバーのスナップショットを保護し、すべての仮想サーバーのセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="449b6-135">Protect server snapshots and enhance the security of all virtual servers.</span></span>

  - <span data-ttu-id="449b6-136">グループ ポリシーを使用して、セキュリティ ロックダウンを実装します。</span><span class="sxs-lookup"><span data-stu-id="449b6-136">Use Group Policy to implement security lockdowns.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

