---
title: 'Lync Server 2013: クライアントのインストールのカスタマイズ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce9491e48d107d01f86d18e8154331ef3ae7e478
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="29815-102">Lync Server 2013 でのクライアントインストールのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="29815-102">Customizing client installation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29815-103">_**最終更新日:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="29815-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="29815-104">エンタープライズ管理者は、このセクションで説明する方法を使用して、Office 2013 Windows Installer ベースの (.msi) インストールをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="29815-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="29815-105">1つのツールによってすべてのカスタマイズオプションが提供されるわけではないため、Lync 2013 の展開では、これらの方法を組み合わせて使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29815-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="29815-106">少なくとも、次のセクションで説明するツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="29815-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="29815-107">[Lync Server 2013 で Office カスタマイズツール (OCT) を使用して](lync-server-2013-using-the-office-customization-tool-oct.md)、lync や他の office プログラムのセットアップオプションと機能をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="29815-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="29815-108">[Lync Server 2013 で config.xml を使ってインストールタスクを実行](lync-server-2013-using-config-xml-to-perform-installation-tasks.md)し、ネットワークインストールポイントのパスを指定し、サイレントインストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="29815-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="29815-109">[Lync Server 2013 のセットアップコマンドラインオプションを使用して](lync-server-2013-using-setup-command-line-options.md)、インストール時に使用する config.xml ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="29815-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="29815-110">グループポリシーオブジェクトエディター MMC スナップインを使用して、 [Lync Server 2013 でクライアントブートストラップポリシーを構成](lync-server-2013-configuring-client-bootstrapping-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="29815-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="29815-111">製品の Office スイートを展開するときに構成するオプションが他にある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="29815-111">There will probably be other options you’ll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="29815-112">このセクションのトピックでは、これらのカスタマイズツールの概要と、Lync 固有の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="29815-112">The topics in this section give an overview of these customization tools and discuss Lync-specific considerations.</span></span> <span data-ttu-id="29815-113">各ツールの詳細な Office ヘルプへのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="29815-113">Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

