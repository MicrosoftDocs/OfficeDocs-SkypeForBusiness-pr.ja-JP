---
title: 'Lync Server 2013: Active Directory スキーマの準備'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27c785596d1fe994e3156eb0e52ed840609a5c26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506854"
---
# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a><span data-ttu-id="d2896-102">Lync Server 2013 での Active Directory スキーマの準備</span><span class="sxs-lookup"><span data-stu-id="d2896-102">Preparing the Active Directory schema in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2896-103">_**トピックの最終更新日:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="d2896-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="d2896-104">Active Directory ドメインサービスの準備を開始する前に、Windows メモ帳などのテキストエディターを使用してスキーマファイルを開くか、または lync [server 2013 によって使用される Active directory スキーマ拡張、クラス、属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) を参照して、lync server 2013 に対して変更されるすべての Active Directory ドメインサービスのスキーマ拡張を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d2896-104">Before you begin preparing Active Directory Domain Services, you can open the schema files by using a text editor, such as Windows Notepad, or see [Active Directory schema extensions, classes, and attributes used by Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) to review all the Active Directory Domain Services schema extensions that will be modified for Lync Server 2013.</span></span> <span data-ttu-id="d2896-105">Lync Server は、次の4つのスキーマファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="d2896-105">Lync Server uses four schema files:</span></span>

  - <span data-ttu-id="d2896-106">ExternalSchema は、Microsoft Exchange Server との相互運用性に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2896-106">ExternalSchema.ldf, which is used for interoperability with Microsoft Exchange Server</span></span>

  - <span data-ttu-id="d2896-107">ServerSchema。これは、プライマリ Lync Server 2013 スキーマファイルです。</span><span class="sxs-lookup"><span data-stu-id="d2896-107">ServerSchema.ldf, which is the primary Lync Server 2013 schema file</span></span>

  - <span data-ttu-id="d2896-108">BackCompatSchema.ldf (以前のリリースのコンポーネントとの相互運用性を確保するために使用されます)</span><span class="sxs-lookup"><span data-stu-id="d2896-108">BackCompatSchema.ldf, which is used for interoperability with any components from prior releases</span></span>

  - <span data-ttu-id="d2896-109">VersionSchema.ldf (準備したスキーマのバージョン情報を保持するために使用されます)</span><span class="sxs-lookup"><span data-stu-id="d2896-109">VersionSchema.ldf, which is used for version information of the prepared schema</span></span>

<span data-ttu-id="d2896-110">以前のリリースから移行しているかどうかや、クリーン インストールを実行しているかどうかに関係なく、すべての .ldf ファイルがスキーマの準備時にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d2896-110">All .ldf files are installed during schema preparation, regardless of whether you are migrating from a previous release or performing a clean installation.</span></span> <span data-ttu-id="d2896-111">これらのスキーマファイルは、上記の一覧に示されている順序でインストールされ、 \\ \\ インストールメディアの Support スキーマフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="d2896-111">These schema files are installed in the sequence shown in the preceding list and are located in the \\Support\\schema folder on the installation media.</span></span>

<span data-ttu-id="d2896-112">Lync Server スキーマ拡張機能は、すべてのドメイン間でレプリケートされ、ネットワークトラフィックに影響します。</span><span class="sxs-lookup"><span data-stu-id="d2896-112">The Lync Server schema extensions are replicated across all domains, which impacts network traffic.</span></span> <span data-ttu-id="d2896-113">スキーマの準備は、ネットワークの使用率が低いときに実行してください。</span><span class="sxs-lookup"><span data-stu-id="d2896-113">Run schema preparation at a time when network usage is low.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d2896-114">Lync 1.0 モバイルクライアント用の Microsoft® Office Communicator Mobile 2007 R2 および Microsoft® Office Communicator Mobile のサポートを Lync Server 2013 展開に追加する必要がある場合は、Lync Server 2013 のインストール時に Microsoft Office Communications Server 2007 R2 用の Active Directory スキーマを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2896-114">If you need to add support for Microsoft® Office Communicator Mobile 2007 R2 for Java and Microsoft® Office Communicator Mobile for Nokia 1.0 mobile clients to your Lync Server 2013 deployment, you need to prepare the Active Directory schema for Microsoft Office Communications Server 2007 R2 during installation of Lync Server 2013.</span></span> <span data-ttu-id="d2896-115">必要なソフトウェアおよびドキュメントについては、「」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> 。</span><span class="sxs-lookup"><span data-stu-id="d2896-115">For the necessary software and documentation, see <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>.</span></span>



</div>

<div>

## <a name="adsi-edit"></a><span data-ttu-id="d2896-116">ADSI エディター</span><span class="sxs-lookup"><span data-stu-id="d2896-116">ADSI Edit</span></span>

<span data-ttu-id="d2896-117">Active Directory サービス インターフェイス エディター (ADSI エディター) は AD DS の管理ツールです。これを使用すると、スキーマの準備およびレプリケーションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d2896-117">Active Directory Service Interfaces Editor (ADSI Edit) is an AD DS administration tool that you can use to verify schema preparation and replication.</span></span>

<span data-ttu-id="d2896-118">既定では、AD DS の役割をインストールしてサーバーをドメイン コントローラーにするときに ADSI エディターがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d2896-118">ADSI Edit is installed by default when you install the AD DS role to make a server a domain controller.</span></span> <span data-ttu-id="d2896-119">Windows Server 2008 および Windows Server 2008 R2 の場合、ADSI Edit (adsiedit) はリモートサーバー管理ツール (RSAT) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="d2896-119">For Windows Server 2008 and Windows Server 2008 R2, ADSI Edit (adsiedit.msc) is included with the Remote Server Administration Tools (RSAT).</span></span> <span data-ttu-id="d2896-120">また、RSAT をドメイン メンバー サーバーまたはスタンドアロン サーバーにインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d2896-120">You can also install RSAT on domain member servers or stand-alone servers.</span></span> <span data-ttu-id="d2896-121">RSAT パッケージは、既定で、Windows のインストール時にこれらのサーバーにコピーされますが、インストールされません。</span><span class="sxs-lookup"><span data-stu-id="d2896-121">The RSAT package is copied to these servers by default when you install Windows, but it is not installed by default.</span></span> <span data-ttu-id="d2896-122">各ツールをインストールするには、サーバー マネージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="d2896-122">You install individual tools by using Server Manager.</span></span> <span data-ttu-id="d2896-123">ADSI エディターは、**[役割管理ツール]**、**[Active Directory ドメイン サービス ツール]**、**[Active Directory ドメイン コントローラー ツール]** を順に展開すると見つかります。</span><span class="sxs-lookup"><span data-stu-id="d2896-123">ADSI Edit is included under **Role Administration Tools**, **Active Directory Domain Services Tools**, **Active Directory Domain Controller Tools**.</span></span>

<span data-ttu-id="d2896-124">Windows Server 2003 の場合、ADSI エディターはサポート ツールに付属しています。</span><span class="sxs-lookup"><span data-stu-id="d2896-124">For Windows Server 2003, ADSI Edit is included with the Support Tools.</span></span> <span data-ttu-id="d2896-125">サポートツールは、サポートツールフォルダーの Windows Server 2003 CD から \\ 入手 \\ するか、「windows Server 2003 Service Pack 2 32-Bit Support tools」からダウンロードでき [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) ます。</span><span class="sxs-lookup"><span data-stu-id="d2896-125">The Support Tools are available from the Windows Server 2003 CD in the \\SUPPORT\\TOOLS folder, or you can download them from “Windows Server 2003 Service Pack 2 32-bit Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770).</span></span> <span data-ttu-id="d2896-126">製品 CD からサポートツールをインストールする手順については、「Windows サポートツールをインストールする」を参照して [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) ください。</span><span class="sxs-lookup"><span data-stu-id="d2896-126">Instructions for installing the Support Tools from the product CD are available from “Install Windows Support Tools” at [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771).</span></span> <span data-ttu-id="d2896-127">サポート ツールをインストールすると、adsiedit.dll が自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="d2896-127">Adsiedit.dll is automatically registered when you install the support tools.</span></span> <span data-ttu-id="d2896-128">ただし、ファイルをコンピューターにコピーした場合は、ツールを実行する前に、**regsvr32** コマンドを実行して adsiedit.dll ファイルを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d2896-128">If, however, you copied the files to your computer, you must run the **regsvr32** command to register the adsiedit.dll file before you can run the tool.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d2896-129">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d2896-129">In This Section</span></span>

  - [<span data-ttu-id="d2896-130">Lync Server 2013 での Active Directory スキーマの準備の実行</span><span class="sxs-lookup"><span data-stu-id="d2896-130">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)

  - [<span data-ttu-id="d2896-131">Lync Server 2013 での Active Directory スキーマのレプリケーションの確認</span><span class="sxs-lookup"><span data-stu-id="d2896-131">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2896-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="d2896-132">See Also</span></span>


[<span data-ttu-id="d2896-133">Lync Server 2013 のフォレストの準備</span><span class="sxs-lookup"><span data-stu-id="d2896-133">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
[<span data-ttu-id="d2896-134">Lync Server 2013 のドメインの準備</span><span class="sxs-lookup"><span data-stu-id="d2896-134">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

